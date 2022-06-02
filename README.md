# Deploying your React App to GitHub Pages

GitHub pages is awesome! But it's also a little confusing for React apps and many guides online are a bit convoluted, so here's my guide. I'm assuming you have already created your repo on GitHub and made your React app, and are now looking to deploy it to a live website

1. ```npm install gh-pages — save-dev```
2. Open package.json and below "name" and "version" at the top, press enter and a new key:value named homepage with a link to your repo using github.io like so:

```JavaScript
{
  "name": "tailwind-product-page",
  "version": "0.1.0",
  "homepage": "https://ASproson.github.io/tailwind-product-page",
  "private": true,
  "dependencies": {...
}
```

Note specifically ```"homepage": "https://ASproson.github.io/tailwind-product-page",```. Here you want to replace ASproson with your specific GitHub name, then, you want to replace tailwind-product-page with the name of your repo on GitHub

3. Still within package.json find the "scripts" key:value and add a new entry called predeploy and deploy, it should look exactly like this:

```JavaScript
"scripts": {
    "predeploy": "npm run build",
    "deploy": "gh-pages -d build",
    "start": "react-scripts start",
    "build": "react-scripts build",
    "test": "react-scripts test",
    "eject": "react-scripts eject"
  },
```

4. Lastly, push all of these changes upto GitHub and then we need to go to the terminal and run the command:

```npm run deploy```

This will take a few minutes to resolve and deploy on GitHub. Go into your repo and above the Languages section you will see something called Environments - you will now see that github-pages is listed. Click on this link, then click 'View deployment' to get the link to your hosted website. 

With that, go back to your repo main page and click the cog in the top right corner of the About section and paste the web link in and we're done!
