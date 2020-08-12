# Essentials of NPM

<img alt="Technology" width="700" src="/assets/images/npm-logo.png" />

- What is NPM?

  - Node Package Manager
  - Pre-installed with Node.js
  - Used to installed Javascript modules/packages on our system/project.

- How to check verison on npm installed on our machine?

  ```text
  npm -v

  npm --version
  ```

- How to get in to npm help page?

  ```text
  npm

  npm help
  ```

- How to create Package.json(Manifest file)?

  ```text
  npm init

  npm init -y

  npm init --yes
  ```

- What is Package.json file?

  - This is the Manifest file with app info
  - This will list all dependencies (name and version of packages)
  - Specify if verions should be updated
  - Used to create npm scripts

- How to change npm default config values?

  ```text
  npm config set init-author-name "gopibabu srungavarapu"

  npm config set init-license "MIT"

  npm set init-name "npm-app"

  npm set init-version "1.0"
  ```

- How to see npm config values from command line?

  ```text
  npm get init-author-name

  npm config get init-license
  ```

- How to delete our custom config values from npm?

  ```text
  npm config delete init-author-name

  npm config delete init-license
  ```

- How to download dependency(npm package) using npm for our project?

  ```text
  npm install lodash

  👉 This will install lodash module in to node_modules directory in the project
  ```

- How to download and save that dependency in to package.json file for our project?

  ```text
  npm install lodash --save

  👉 This will update package.json file with the dependency that we requested
  ```

- How to uninstall dependency and save those changes to package.json file for our project?

  ```text
  npm uninstall lodash --save

  npm rm lodash --save

  npm remove lodash --save
  ```

- How to install all dependencies mentioned in the package.json file for our project?

  ```text
  npm install
  ```

- What are devDependencies?

  - These are dependencies installed on our project only for development activities.

- How to install devDependencies?

  ```text
  npm install gulp gulp-sass --save-dev
  ```

- How to remove devDependency and save those changes to package.json file for our project?

  ```text
  npm uninstall gulp-sass --save-dev

  npm remove gulp --save-dev

  npm rm gulp --save-dev
  ```

- How to install only dependencies and omit devDependencies for our project?

  ```text
  npm install --production
  ```

- How to install specific version of dependency for our project?

  ```text
  npm install lodash@4.17.3 --save

  global:
  npm install -g lodash@4.17.3 --save
  ```

- How to update given dependency to the latest version for our project?

  ```text
  npm update lodash

  All packages:
  npm update

  ```

- How we can explain version number?

  ![version number](https://github.com/gopibabus/project-DeveloperTools/blob/master/assets/versionNUmbers.png)

- what does version mean while running _npm install_?

  - **^4.0.1**<br>
    👉 This will update latest minor and path versions for a given package(dependency)
  - **~4.0.1**<br>
    👉 This will update only latest patch version for a given package(dependency)
  - **4.0.1**<br>
    👉 This will install exact mentioned version for a given package(dependency)
  - **\***<br>
    👉 This will update latest major version for a given package(dependency)

- How to install packages globally on our system?

  ```text
  npm install -g nodemon

  npm install --global nodeman
  ```

- How we can find path for global node_modules?

  ```text
  npm root -g
  ```

- How to remove packages globally from our system?

  ```text
  npm remove -g nodemon
  ```

- How to list all packages that are included in our project with npm?

  ```text
  npm list

  👉 This will list all internal dependencies for the packages that are installed for our project
  ```

- How to list only packages that installed for our project with out their dependencies

  ```text
  npm list --depth=0
  ```

- How to create custom scripts(alias) to run different tasks in our project?

  ```json
  {
    "scripts": {
      "start": "node index.js",
      "server": "live-server"
    }
  }
  ```

- How to run custom scripts using npm?

  ```text
  npm run start

  npm run server
  ```

- How node searches for modules?

  ```text
  Core Modules -> file/folder(in application) -> node_modules
  ```

- How to get all meta data about a package?

  ```text
  npm view <package name>
  ```

- How to get all dependencies of a package?

  ```text
  npm view <package name> dependencies
  ```

- How to get all versions of a package released till date?

  ```text
  npm view <package name> versions
  ```

- How to view all outdated packages?

  ```text
  npm outdated

  (OR)

  npm -g outdated
  ```

- How to publish a package?

  1. Create a folder
  2. Create file with custom logic and export that function
  3. Create package.json file with related information
  4. npm login
  5. npm publish
