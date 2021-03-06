# Jordy's React structure

## Base Structure

The root of your application should contain configs for any tools you might use, a `README`, `package.json` and so on.

**Example**

```
root
├── README.md
├── node_modules
├── package.json
├── public
├── src
├── yarn-error.log
└── yarn.lock
```

`node_modules` obviously stores any and all libraries, tools, and frameworks you use.

`public/` should store your `index.html`, `favicon`, and your `manifest`

`src/` should store all your actual code.

Most of this structure should look natural to you as it's the base structure of any app bootstrapped with `create-react-app`, it's a CLI tool that takes the work of configuring Webpack and all that out of your hands and takes care of business.

---------------

Since src/ folder stores all your actual code, most work will be done in here.

An example markup of this folder is as follows;

```
src/
├── components
├── index.js
├── lib
├── modules
└── registerServiceWorker.js
```

`lib/` is where your custom libraries should live, it's usually a good idea to turn these into packages at some point.

`components/` is where your application-wide components should live, such as layouts, your `<App />` component, etc…

`modules` is where your other components will live.

## Modules

Every part of your application is to be divided into separate modules.

Things like `auth`, `home` and `dashboard` make for good modules.

---

Modules are chunks of your application that may never cross boundaries. One module may not use code from any other module. 

### Sharing code between modules

If a module requires code from another module you are to lift the code up to the application's shared code, usually by means of a library.

It is also possible to create a new module with the code required, and to add the other modules that use the code as submodules.

### Folder structure

You'll notice the folder structure is a lot like the structure of the app itself;

1. Each module should have a `src/` folder
2. Each module may have a `lib/` folder, if you have any module specific libraries.
3. Inside the `src/` folder your components, submodules etc should live.
4. A `src/views` folder is to have components that display entire pages of content. Each view can again have a `components/` folder to house any components to be used in the view.

## Libraries

### Flow

Flow is a static type checker for JavaScript.

## Code Style

1. You should end statements with a semicolon `;`
2. You should use double quotes for strings
  1. If you need variables inside strings you are to use back ticks to interpolate strings; "`"
1.   2. You should destructure imports or variables whenever possible.