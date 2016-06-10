# Deploying to OpenShift

If you deploy your applications to Heroku you can only upload 5 applications, if you want to deploy a new one, you need to verify you account with your credit card.

![Heroku Error](https://i.imgur.com/fY2be3a.jpg)

These are the steps you need to follow to deploy to [OpenShift](https://www.openshift.com/app/account/new).

## Requirements

- An account in [OpenShift](https://www.openshift.com/app/account/new)
- Our app in a [Git](Git) Repository

## Changes in your code

- `app.listen` with `process.env.OPENSHIFT_NODEJS_PORT` and `process.env.OPENSHIFT_NODEJS_IP`, both requires.
- In your **package.json** set your `"main": 'yourMainFile.js` and `"script": { "start": "node yourMainFile.js" }`

## Deploying our app

- [Add a new application](https://openshift.redhat.com/app/console/application_types)

  ![Choose a web programming cartridge](https://i.imgur.com/9k9rj8l.jpg)

- Choose a name (second input will be same for all you apps)

  ![Fill our name and our domain](https://i.imgur.com/gzMcQ3m.jpg)

- Fill our Git URL and our branch name

  ![Where you can find your Git URL and your branch name at Github](https://i.imgur.com/w4n0lNl.jpg)
  
   ![Fill your Git URL and your branch name](https://i.imgur.com/Ec7lX3f.jpg)

- "Create Application". It will take some time

  ![You will be redirected here when you finish deployment](https://i.imgur.com/ddcWa4r.jpg)

- Enter to "Application", then into your App and check it's started.

  ![Your applications list](https://i.imgur.com/ALzAaXp.jpg) ![Details of your application](https://i.imgur.com/uTedlZP.jpg)

## Enviroment variables

In my case I have my database in mLab, so I need to create some enviroment variables.

- [Install Ruby and rhc.](https://developers.openshift.com/getting-started/windows.html#client-tools)

  **rhc** only works with versions 1.9.3 and 2.0.0 of Ruby.

- [Setting up Your Machine](https://developers.openshift.com/getting-started/windows.html#rhc-setup)

  If you are having trouble with setting up `rhc`, try [this](http://stackoverflow.com/questions/28896733/rhc-setup-gives-error-no-such-file-dl-import) answer on StackOverflow.

- [Custom Environment Variables](https://developers.openshift.com/managing-your-applications/environment-variables.html#custom-variables)

  `rhc env set VARIABLE=value VARIABLE2=value2 -a App_Name`.
  
  You need to restart your app to load the variables.

If you find a better way to solve this limitation. Feel free to contribute to our [Wiki](Wiki-Central) and share it with us.

 You can check the app working at [http://voting-pitazo.rhcloud.com/#/polls](http://voting-pitazo.rhcloud.com/#/polls)
