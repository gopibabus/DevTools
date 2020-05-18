# 🔥Upgrade React App

## ⚡How to update React Project?

Create React App is divided into two packages:

1. **create-react-app** (global command-line utility that you use to create new projects).
2. **react-scripts** (development dependency in the generated projects)

So we should update above mentioned 2 parts inorder to make successful Upgrade.

[Resource 1](https://create-react-app.dev/docs/updating-to-new-releases/)

[Resource 2](https://www.kirupa.com/react/updating_react_version.htm)

[Resource 3](https://stackoverflow.com/questions/48727922/how-to-upgrade-a-react-project-built-with-create-react-app-to-the-next-create-re)

## ⚡What is npm audit?

> **npm audit** is a new command that performs a moment-in-time security review of your project’s dependency tree. Audit reports contain information about security vulnerabilities in your dependencies and can help you fix a vulnerability by providing simple-to-run npm commands and recommendations for further troubleshooting.

Scan your project for vulnerabilities and automatically install any compatible updates to vulnerable dependencies:

```bash
npm audit fix

npm audit fix --force
```

[🌐 nodejs Blog](https://blog.npmjs.org/post/173719309445/npm-audit-identify-and-fix-insecure)

[🌐 nodejs Documentation](https://docs.npmjs.com/cli/audit)