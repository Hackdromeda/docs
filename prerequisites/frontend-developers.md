# Web Developers

## Where do I start? 

* Install the prerequisites
* [Accept the invite](https://github.com/navalpatel384/cloudcite/invitations) to join the repository for frontend team
* Clone the code on GitHub.com using GitKraken
* Get familiar with the skills required and with the code
* Start coding during team live coding sessions until you get the hang of it
* Then, work independantly to make improvements whenever the team is unavailable

## How do I run the project locally?

{% hint style="info" %}
Let us know about any errors you see
{% endhint %}

You must have the [prerequisites installed](https://internal.cloudcite.net/software-required/frontend-developers) before starting. For this project, **only run the Yarn commands** unless they do not work for you. 

The Vue Cli Service is required to run this code. You may either install the packages or devDependencies required to develop globally or locally. Only install globally if you predict needing the packages for other projects. **You don't need to do both unless you are having issues with the local installation of the Vue packages.**

**Start by opening your Bash, Terminal, Command Prompt, or PowerShell Window. Then run either one of these commands.**

#### Locally

Enter the directory where your code is. Use _dir_ \(Windows\) or _ls_ \(Linux or Mac\) to list directories. For example:

{% hint style="info" %}
If your folder has spaces you need to surround the entire cd command or the folder in quotes. such as cd "GitHub Repository" or cd "Documents/GitHub Repository/"
{% endhint %}

```bash
cd Documents/GitHub/cloudcite
yarn install
```

#### Globally

You can run these commands from any directory.

{% hint style="info" %}
Only do this if you are having issues with vue-cli-service and we have asked you to run these commands.
{% endhint %}

```bash
yarn global add @vue/cli
yarn global add @vue/cli-service
yarn global add @vue/cli-service-global
yarn global add @vue/preload-webpack-plugin
yarn global add @vue/cli-plugin-babel
yarn global add @vue/cli-plugin-pwa
yarn global add @vue/cli-plugin-typescript
# ONLY USE THESE NPM COMMANDS IF WE TELL YOU TO:
npm install -g @vue/cli
npm install -g @vue/cli-service
npm install -g @vue/cli-service-global
npm install -g @vue/preload-webpack-plugin
npm install -g @vue/cli-plugin-babel
npm install -g @vue/cli-plugin-pwa
npm install -g @vue/cli-plugin-typescript
```

### Environment Variables in Windows 

{% hint style="info" %}
'{package name}' is not recognized as an internal or external command, operable program or batch file.
{% endhint %}

If you see the error above, you need to add environment variables for certain packages such as Yarn.

{% code-tabs %}
{% code-tabs-item title="Yarn - PATH Variable" %}
```bash
C:\Program Files (x86)\Yarn\bin
```
{% endcode-tabs-item %}
{% endcode-tabs %}

**Windows 10 and Windows 8**

1. In Search, search for and then select: System \(Control Panel\)
2. Click the Advanced system settings link.
3. Click Environment Variables. 
4. In the section System Variables, find the PATH environment variable and select it.
5. Click Edit. If the PATH environment variable does not exist, click New.
6. In the Edit System Variable \(or New System Variable\) window, specify the value of the PATH environment variable.
7. Click OK.
8. Close all remaining windows by clicking OK.
9. Restart Command Prompt, PowerShell, or Git Bash

### Node-Sass bindings

{% hint style="info" %}
Node Sass could not find a binding for your current environment: Windows 64-bit with Node.js 8.x

Found bindings for the following environments:

* OS X 64-bit with Node.js 8.x
{% endhint %}

Node-Sass needs to rebuild bindings using a binary depending on your environment including the OS and the NodeJS version.

If you see a Node-Sass error, run the code below and retry your command for running or building the code. You may ignore any Node-Sass dependancy errors such as errors thrown by the **gyp** package.

```bash
npm rebuild node-sass --force
```

### Run the code

#### To run the code locally, use the command below. The page will reload when you make changes.

First, enter the directory where your code is. Use _dir_ \(Windows\) or _ls_ \(Linux or Mac\) to list directories. For example:

{% hint style="info" %}
If your folder has spaces you need to surround the entire cd command or the folder in quotes. such as cd "GitHub Repository" or cd "Documents/GitHub Repository/"
{% endhint %}

```bash
cd Documents/GitHub/cloudcite
```

**Then run this command while in that directory.**

```bash
yarn serve
```

#### To build the code for production, replace the command above with:

```bash
yarn build
```

### Terminating batch job

{% hint style="info" %}
If Command Prompt, PowerShell, Bash or equivalent don't let you type something, this means a batch job is running.
{% endhint %}

After you're done with running the development server \(the code locally\) or another batch job, you can use CTRL + C or CMD + C to exit the job.

