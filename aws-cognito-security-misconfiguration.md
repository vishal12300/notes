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
./enumerate-iam.py --access-kry <AccessKeyID> --secret-key <SecreetKey> --session-token <SessionToken>
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
