# Portfolio In Terminal Style

![Terminal in browser](/public/example.gif)

This is a SPA in reactJS with a MacOS terminal style. The terminal is a draggable and resizable React component and has sections about me, so it's will be my personal portfolio for while.

See the [demo](https://raulpy271.github.io) page.

If you are interested in using this app for your portfolio, see the sections: [How to setup](#how-to-setup) and [Deploy](#deploy).

#### To turn the terminal draggable i used this [library](https://github.com/raulpy271/DraggableDialog)

## How to setup

To use this page, first fork this repository and clone it on your machine, so you will can add your information.

To edit the sections and put your information you should edit the `contentEN` object in the `src/text/` path. Besides, you can add more sections creating more properties to the object.

Or if you want to add support to another language you should create an object like these in the mentioned path and import it in the `src/text/textManager.js` file.

Read the files of the `src/text/` path and you'll understand more about how to edit, add more sections, or support for multiples languages.

If something isn't clear feels free to open an issue.

## Deploy

After making your changes, you can deploy the app on github pages. The steps are:

Install github pages as dev dependecies:

```sh
npm install gh-pages --save-dev
```

Put the link of your homepage in the `homepage` properties of `package.json`, the link is like this `http://{username}.github.io/{repo-name}`.

After all, run the command:

```sh
npm run deploy
```

And the application will be deployed in the `homepage` link.

## Deploy in another repository

Following the steps above, I get a repository with the source code in the branch `main` and another branch with the bundled version of the source. Besides, I get the link `https://raulpy271.github.io/portfolioInTerminal` to access the page.

The problem is that this link is too large, I want to use `https://raulpy271.github.io`. To use it, the user should create a repository named `{username}.github.io`.

But to deploy it, I should explicitly tell to github pages the new repository link. To make this I will add a remote branch in git and use this branch in the command `gh-pages`, See the steps:

```sh
git remote add homepage https://github.com/raulpy271/raulpy271.github.io
```

I added a new remote called `homepage`, and then will create a new bundled source in the directory `build`:

```sh
npx react-scripts build
```

And then I will use the files of the above directory and the new remote branch in `gh-pages`:

```sh
npx gh-pages -d build -o homepage
```

Now, the app is deployed 🚀! And I get a short link and a separate version with the production-ready code.

