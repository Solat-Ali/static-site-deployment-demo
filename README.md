# Static HTML Site - Deployment Demo
This is a simple repository created to document open source deployments on multiple popular platforms. The site contains a simple "Coming Soon" page template. To be able to follow along the guide, make sure you have installed latest Node (LTS) version on your machine. 

**Disclaimer:**
- Picking the right open source platform for deployment is completely your choice. This repository just demonstrates & explains some examples!
- Make sure that whichever platform you choose, you are aware of it's pricing plan. All of the options listed below have a free-tier, however please refer to the pricing page link given against each option. 

## 1. Surge
Here's how you can deploy a website on Surge: 

1. In your project directory, run the command `npx surge`. For the first time, Surge may ask you to enter your email and password to create / login to an account
2. Once done, you would be asked for files to deploy. For this example, I just wrote `.` to select all files
3. Then, Surge will automatically display a random site name, just accept and continue. 
4. And there you have it, your site is deployed on Surge! (ref. screenshot - https://app.screencast.com/Bsetw9zMmnNaf)
   
### Notes: 
1. If you want to setup a custom domain, then follow [this link](https://surge.sh/help/adding-a-custom-domain) for the official guide on the topic. 
2. **Make sure to review the pricing information for this platform. Link [here](https://surge.sh/pricing).**

## 2. Netlify
Here's how you can deploy a website on Netlify: 

1. Go to official site (https://www.netlify.com/) and sign-up.
2. Once you login, you will see your dashboard (ref. screenshot - https://app.screencast.com/iRcAik8GOlPdb)
3. There are multiple ways to deploy a site through Netlify: Through Git integration, manually or from a template. In this example, we will deploy directly through Netlify CLI terminal with minimal number of steps, just like Surge.
4. Open terminal in project directory and run the command `npx netlify-cli deploy` in your project directory terminal. Netlify requires Authentication, so first time it may ask you to login through browser. 
5. After login, terminal would auto-continue with next steps. In this example, we selected a new site with a random name, and default team to deploy our static site. 
6. Once done, you should see a notification of success, and the website URLs within the terminal. Here is a ref. screenshot - https://app.screencast.com/vIoyhgaC5wzwI
7. Now, you can navigate to the site and check it out!

### Note: 
1. Netlify is relatively advanced platform, with a lot of options including CI/CD integration directly from repository. Feel free to check out the documentation in depth.
2. **Make sure to review the pricing information for this platform. Link [here](https://www.netlify.com/pricing/).**

## 3. Vercel
Here's how you can deploy a website on Vercel: 

1. Head over to [Vercel official site](https://vercel.com/) and sign-up.
2. There are multiple ways to deploy a site through Vercel as well: Through Git integration, manually or from a template. In this example, we will deploy directly through Vercel CLI. 
3. Open temrinal in project directory and run the command `npx vercel` in project terminal and follow the automated steps. For the first time, you would have to login to Vercel CLI. In this example, I used "Login with Email" (as sign-up was done with simple email address). Once you select it, an email would be sent to your inbox with a verification link. Once that link is opened, the Vercel CLI automatically authenticates the user and moves to next step
5. Since this was a new site, I used "Link to existing project" as NO. Enter a sample project name, and use `./` as your project files to include all files for upload
6. This will now deploy the site to Vercel and a success notification should be shown! (ref. screenshot - https://app.screencast.com/7LfdyGYE8PLSN)

### Notes: 
1. Just like Netlify, Vercel is an advanced platform with a lot options available for deployments. Feel free to check out the documentation in depth.
2.**Make sure to review the pricing information for this platform. Link [here](https://www.vercel.com/pricing/).**

## 4. Firebase Hosting
Here's how you can deploy a website on Firebase: 

1. Go to [Firebase official site](https://firebase.google.com/). If you already have a Gmail account signed in the browser, you will automatically sign-in to Firebase as well. Else, you can go ahead and sign-up. 
2. Go to firebase console, and create a new project. You can use any random name. 
3. Install Firebase CLI globally through `npm i -g firebase-tools` command in your terminal.
4. Run the command `firebase login` in your project directory terminal. Firebase requires Authentication, so first time it may ask you to login through browser. In this example, we used Login via Gmail account. After it's done, the terminal would show a success notification that you are logged in. 
5. After that, we need to run `firebase init` command in project terminal to configure Firebase and automatically generate `firebase.json` file for deployments. This is an automated process, so follow along the steps. (ref. screenshot - https://app.screencast.com/59N2JI5p0qJCZ)
6. After that, we need to run `firebase deploy` command to deploy the site on Firebase hosting. (ref screenshot - https://app.screencast.com/iJU1yNksb24ZO)
7. Now, you can navigate to the site and check it out! 

### Notes: 
1. Firebase is an advanced platform, and apart from hosting it offers a variety of other services including AI/ML. Feel free to check out the documentation in depth.
2. Here is the official guide on deployment through [Firebase CLI](https://firebase.google.com/docs/cli)
3.**Make sure to review the pricing information for this platform. Link [here](https://firebase.google.com/pricing).**

## 5. GitHub Pages
Here's how you can deploy a website on GitHub Pages: 

1. We need to have an active GitHub account for deployment. So, if not already, then sign-up at [GitHub](https://www.github.com). 
2. Secondly, we need to have our code hosted on a GitHub repository. So, create a new repository first, and make sure that code is uploaded on the repository. 
3. We can host our site on GitHub pages either directly through GitHub UI, or through `gh-pages` plugin from terminal. In this example, we will explore the Github UI approach. 
4. Navigate to "Settings" panel of your repository, left sidebar > Pages. I selected deployment directly from "master" branch. (ref. screenshot - https://app.screencast.com/sHOLetE7c0T3f)
5. After this, GitHub will automatically deploy your site everytime any commit is made to the repository. 

### Notes: 
1. Make sure you include relative paths in file names e.g. "/assets/styles/main.less" should be "./assets/styles/main.less". 
2.**Make sure to review the pricing information for this platform. Link [here](https://github.com/pricing).**

## 6. CloudFare Pages
Deploying on CF requires a few additional steps, follow along this guide: 

1. Install the official CloudFlare Wrangler CLI using the command `npm i -g wrangler` in your global terminal. Note that in order to use Wrangler CLI, we need to get "Account ID" and "API Token Key", both of which we will discuss in next steps. 
2. Go to [Cloudflare official site](https://www.cloudflare.com), sign-up, verify your email and login to the dashboard. 
3. Now, we have to create a "CloudFlare Pages Site". Go back to dashboard home, find "Workers & Pages" option and click to open it, then click on "Create" button to add a new pages site. 
4. Now, go back to project directory terminal and run `wrangler login` command. This will open browser for CF authentication. After that, terminal will display a success notification. 
5. Next, we will deploy the static site to CF pages. Run the command `wrangler pages deploy .` and give a name of project (any random name). This will deploy the static site to CF pages. (ref. screenshot - https://app.screencast.com/ouWi3xj2DOBG7)
6. Now, you can navigate to the site and check it out! 

### Notes: 
1. CF is an advanced platform, and apart from hosting it offers a variety of other services including domain registration, and much more. Feel free to check out the documentation in depth.
2. [Here](https://www.codingwithjesse.com/blog/deploying-a-static-site-to-cloudflare-pages/) is another helpful guide regarding CF Pages Deployment
3.**Make sure to review the pricing information for this platform. Link [here](https://www.cloudflare.com/en-gb/plans/developer-platform/).**

**If you found this repository useful, consider giving it a star! Thank you!**
Created by [Solat-Ali](https://linkedin.com/in/solat-ali)
