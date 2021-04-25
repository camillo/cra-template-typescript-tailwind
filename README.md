<p align="middle">
	<img src="img/banner.png" />
</p>
<h1 align="center">cra-template-typescript-eslint-stylelint-prettier-tailwindcss</h1>

Custom template for [Create React App](https://create-react-app.dev/) to scaffold a new web app project with React, TypeScript, TailwindCss, ESLint (Airbnb style by default), Prettier and Stylelint.

You can find information below on how these tools are configured within this template and how you can customize it further.

This version is based on the [official TypeScript template](https://www.npmjs.com/package/cra-template-typescript), version `1.1.2`.

TailwindCss configuration without ejecting is achieved using [Create React App Configuration Override](https://github.com/gsoft-inc/craco), a.k.a. CRACO.

## Requirements
 
Make sure you have Node.js `12.0.3` or higher installed. This requirement is specific for running the tools needed by TailwindCss.

## Creating a new app

To use this template, add the parameter `--template typescript-eslint-stylelint-prettier-tailwindcss` to the Create React App command line when creating a new app.

For example:

    npx create-react-app my-app --template typescript-eslint-stylelint-prettier-tailwindcss
    
    # or
    
    yarn create react-app my-app --template typescript-eslint-stylelint-prettier-tailwindcss

Once the project is created you can navigate to its folder and execute `npm start` or `yarn start` to run the development server.

Then you can open `http://localhost:3000/` in your browser to view the default app running (browser won't open automatically when using this template).

## Available Scripts

### `npm start` or `yarn start`

Runs the app in development mode.

### `npm test` or `yarn test`

Runs the test watcher in an interactive mode.

### `npm run build` or `yarn build`

Builds the app for production to the `build` folder.

### `npm run lint-code` or `yarn lint-code`

Runs ESLint and output any style errors found in your code as per the rules defined in its [configuration](#eslint). By default, it will check any JavaScript or TypeScript file in your `src` folder.

### `npm run lint-code:fix` or `yarn lint-code:fix`

Attempts to fix automatically any style errors detected in your code using [ESLint](#eslint) and [Prettier](#prettier).  By default, it will check any JavaScript or TypeScript file in your `src` folder.

### `npm run lint-styles` or `yarn lint-styles`

Runs Stylelint and output any style errors found in the `.css` files within your `src` folder.

Keep in mind that by default any other extensions (like `.scss` or `.less`) will not be checked by Stylelint. If you need that behavior you will need to change the configuration.

### `npm run lint-styles:fix` or `yarn lint-styles:fix`

Attempts to fix automatically any style error detected in the `.css` files within your `src` folder.

Keep in mind that by default any other extensions (like `.scss` or `.less`) will not be checked by Stylelint. If you need that behavior you will need to change the configuration.

## Extra Features

### TailwindCss

[TailwindCss](https://tailwindcss.com/) is a popular utility-first CSS framework that you can use to compose and build any design, directly in your markup.

It is already configured when you create a project using this template. You can start using Tailwind's classes in any component right away. You can find the default configuration for this template [here](#tailwindcss-configuration).

### ESLint

[ESLint](https://eslint.org/) is a tool for identifying and reporting on patterns found in ECMAScript/JavaScript code.

When you use this template ESLint will check your code against Airbnb JavaScript style guide (adapted to TypeScript). 

By default, it will check any JavaScript or TypeScript file (`{js,jsx,ts,tsx}`) in your `src` folder.

### Stylelint

[Stylelint](https://stylelint.io/) is a mighty, modern linter that helps you avoid errors and enforce conventions in your styles.

You can run the `lint-styles` and `lint-styles:fix` scripts to check and fix style errors.

Keep in mind that by default any other extensions (like `.scss` or `.less`) will not be checked by Stylelint. If you need that behavior you will need to change the configuration.

### Prettier

[Prettier](https://prettier.io/) is an opinionated code formatter. It ensures that all outputted code conforms to a consistent style. This is the tool used behind the scenes when trying to fix formatting issues in your code and styles, be it when issuing one of the [available scripts](#available-scripts) or while working on your project in your code editor (more on that below).

## Configuration

You can find below more specific information on what is included in this template.

The base of this template is the [official Typescript template from Create React App](https://www.npmjs.com/package/cra-template-typescript), version `1.1.2`.

### ESLint configuration

This template comes configured with `eslint-config-airbnb-typescript` and `eslint-plugin-prettier`.

Settings can be found at the root of your project in `.eslintrc.json`.

After creating your project you might find a key `eslintConfig` in your `package.json`. You can/should remove this key to avoid confusion and make sure that configuration is being read from the standalone json configuration file.

### Stylelint configuration

This template comes configured with `stylelint-prettier/recommended` and `stylelint-config-prettier`. Prettier will be used for formatting rules.

Stylelint configuration can be found at the root of your project in `stylelint.config.js`.

### TailwindCss configuration

You can find `tailwind.config.js` in the root of your project. This is where you can customize Tailwind's classes for your project. You can find all the information on how to do it in the [official docs](https://tailwindcss.com/docs/configuration).

Here's a list of how it is initially configured:

* It includes all of the [default colors](https://tailwindcss.com/docs/customizing-colors);
* Sets `darkMode` to `'class'` to that you can manually change themes;
* Includes the plugin `@tailwindcss/forms` for resetting form fields;
* The responsive breakpoints are set by default like this:
	* `sm`: `576px`
	* `md`: `768px`
	* `lg`: `992px`
	* `xl`: `1200px`
	* `xxl`: `1400px`

Keep in mind that these are not the usual default for breakpoints in TailwindCss. If you want to use the defaults, edit its configuration file and remove the key `screens` from the `theme` object.

### Formatting settings

This template comes with a standalone Prettier configuration file (`.prettierrc`) specifying formatting rules. You can find this file in the root directory of your project.

The same settings are also supplied in the form of an [EditorConfig](https://editorconfig.org/) file (`.editorconfig`) for compatibility with code editors that support it.

### Visual Studio Code settings

You will also get code editor specific settings. More specifically, it comes with Visual Studio Code settings so that your files are automatically formatted by Prettier when saving them. For that to work you need to install Prettier extension for Visual Studio Code (more on that below).

There are also settings to avoid clashes between Visual Studio Code error checking in css files and Stylelint.

You can view and edit this configuration as usual in the `.vscode/settings.json` file.

### Environment variables

You will find a `.env` file at the root of your project. By default it comes configured:

* For not opening a browser window automatically when running the development server;
* For not generating source maps when generating a production build.

You can change this configuration directly in the file and you can find the full list of supported variables on [Create React App's docs](https://create-react-app.dev/docs/advanced-configuration/).

### Scripts for generating Self Signed Certificates

After creating your project you will find a `ssl` folder containing a shell script. You can use it to generate a self signed certificate to run your development server with `https`.

To do that, run the `ssl/generate_development_certificate.sh` script. You can even run it in Windows if you have [WSL](https://docs.microsoft.com/en-us/windows/wsl/about) enabled.

The script will generate two files in the `ssl` folder: `development_certificate.key` and `development_certificate.crt`.

**You should NOT commit the generated `.key` and `.crt` files in your repository**. In fact, `.gitignore` is already set up to ignore them (assuming they are in the `ssl` folder). In a shared project, every developer should generate their own self signed certificates. And if you have multiple projects using `https` in development you might wanna consider using a single certificate for all of your projects.

Assuming you ran the shell script, you can start the development server with `https` by adding the following lines in the `.env` file at the root directory of your project:

    SSL_CRT_FILE=ssl/development_certificate.crt
    SSL_KEY_FILE=ssl/development_certificate.key

You also need to install the self signed certificates in your operating system in the Trusted Root folder. Otherwise your browser will show an error when you try to run the app.

With that, the next time you [run your development server](#npm-start-or-yarn-start), it will use `https` and you will be able to access the app at `https://localhost:3000/` (you won't be able to use the `http` URL unless you disable `https` in your `.env` file).

If you are not interested in using `https` in your development server, you can safely delete the `ssl` folder after creating the project.

## Visual Studio Code Recommended Extensions

If you use Visual Studio Code for development, when you open the project it will recommend you a few extensions. You are not required to install and use any of them. However, they do help improving the coding experience.

Here's a list of recommendations provided when using this template (all of them are free):

* [ESLint](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint) - Integrates ESLint with Visual Studio Code;
* [stylelint](https://marketplace.visualstudio.com/items?itemName=stylelint.vscode-stylelint) - Integrates Stylelint with Visual Studio Code;
* [Prettier - Code formatter](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode) - Integrates Prettier with Visual Studio Code. It allows Prettier to automatically format your code according to the rules you defined;
* [Tailwind CSS IntelliSense](https://marketplace.visualstudio.com/items?itemName=bradlc.vscode-tailwindcss) - As the name suggests, add intellisense for TailwindCss classes;
* [npm Intellisense](https://marketplace.visualstudio.com/items?itemName=christian-kohler.npm-intellisense) - An extension to autocomplete npm modules in import statements;
* [Auto Import](https://marketplace.visualstudio.com/items?itemName=steoates.autoimport) - Automatically finds, parses and provides code actions and code completion for all available imports.
* [Auto Rename Tag](https://marketplace.visualstudio.com/items?itemName=formulahendry.auto-rename-tag) - Automatically rename paired HTML tag.
