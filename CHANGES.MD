# Init/Install CRA and TS with yarn

- yarn create react-app --template typescript

# Install eslint prettier husky etc.

- yarn add -D eslint eslint-plugin-react prettier prettier-eslint eslint-plugin-jest eslint-plugin-react-hooks @typescript-eslint/eslint-plugin @typescript-eslint/parser husky @commitlint/{config-conventional,cli}

# Add prettierrc

- add .prettierrc config file

# Add scripts to package json

- add scripts to package json

```json
{
  "scripts": {
    "lint": "eslint \"**/*.{ts,tsx,js,jsx}\"",
    "prepare": "husky install",
    "test": "react-scripts test"
  }
}
```

# Running yarn lint

- running yarn lint - no error in this project since it's new.

# Add commitlint config

```bash
echo "module.exports = {extends: ['@commitlint/config-conventional']};" > commitlint.config.js
```

# Install git hooks

- install git hooks with yarn prepare

# Add hooks

- Add hooks: you can add any number of hooks you need. In this case, we are adding a pre-commit hook that will check the linting and run tests. We are also adding a Commitlint hook.

- npx husky add .husky/pre-commit 'yarn lint && yarn test --watchAll=false'
- npx husky add .husky/commit-msg 'npx --no-install commitlint --edit $1'

# FIRST ERRORS ARISE

- SUBJECT AND TYPE MAY NOT BE EMPTY.
- A commit message must look like the following:

```markdown
<type>[optional scope]: <description>
[optional body]
[optional footer(s)]
```

