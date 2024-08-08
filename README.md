## Setup a Full-Stack Development
* Use VS Code IDE
Install the following extensions
* Docker (by Microsoft)
* ESLint (by Microsoft)
* Prettier – Code formatter (by Prettier)
* MongoDB for VS Code (by MongoDB)

  Setting up a project with Vite
  ` npm create vite@5.0.0 .`
  ` npm install`
  ` npm run dev`

  Alternatives to Vite are bundlers, such as webpack, Rollup, and Parcel. These are highly configurable but often do not offer a great experience for dev servers.

  ### Setting up ESLint and Prettier to enforce best practices and code style

  ```bash
  $ npm install --save-dev prettier@3.1.0 eslint@8.54.0   eslint-plugin-react@7.33.2  eslint-config-prettier@9.0.0  eslint-plugin-jsx-a11y@6.8.0
  ```

  
* `prettier`: Formats our code automatically according to a defined code style
* `eslint`: Analyzes our code and enforces best practices
* `eslint`-config-react: Enables rules in ESLint relevant to React projects
* `eslint-config-prettier`: Disables rules relating to code style in ESLint so that Prettier can handle them instead
* `eslint-plugin-jsx-a11y`: Allows ESLint to check for accessibility (a11y) issues in our JSX code

  ### Configuring the Prettier extension
  * File | Preferences... | Settings -->  Workspace (This ensures that we save all our settings in a .vscode/settings.json )
  * Search for editor format on save and check the checkbox to enable formatting code on save.
  * Search for editor default formatter and select Prettier - Code formatter from the list.
To improve performance and avoid running Prettier on files that should not be automatically formatted, we can ignore certain files and folders by creating a Prettier ignore file.

While Prettier focuses on the style and formatting of our code, ESLint focuses on the actual code, avoiding common mistakes or unnecessary code. Let’s configure it now

we can set up Husky and lint-staged, which run before we commit our code to Git and ensure that Prettier and ESLint are executed successfully on the source code before it is committed.

* Add the husky install script to a prepare script in package.json, so that Husky gets installed automatically when the project is cloned and npm install is executed:
  ```bash
  $ npm run prepare
  ```
Add a pre-commit hook for lint-staged, so that ESLint and Prettier run every time we do git commit
```bash
  $ npx husky add .husky/pre-commit "npx lint-staged"
```

* Commit messages in the commitlint conventional config (https://www.conventionalcommits.org/) are structured in a way where a type must be listed first, then an optional scope follows, and then the description follows, such as type(scope): description. Possible types are as follows:
* fix: For bug fixes
* feat: For new features
* refactor: For restructuring the code without adding features or fixing bugs
* build: For changes in the build system or dependencies
* ci: For changes in the CI/CD configuration
* docs: For changes in the documentation only
* perf: For performance optimizations
* style: For fixing code formatting
* test: For adding or adjusting tests
* 
