# Angular Husky

Source code used in the article [Configure Husky with Angular](https://blouppy.com/blog/2023-05-14-configure-husky-with-angular/) on the [Blouppy](https://blouppy.com) website.

It is a new Angular 22 application (`ng new`) with ESLint (`ng add angular-eslint`) and Prettier, plus two Git hooks managed by [Husky](https://typicode.github.io/husky/):

- `.husky/commit-msg` runs [commitlint](https://commitlint.js.org/) with the [Conventional Commits](https://www.conventionalcommits.org/) rules (`commitlint.config.mjs`).
- `.husky/pre-commit` runs [lint-staged](https://github.com/lint-staged/lint-staged), which runs `eslint --fix` and `prettier --write` on the staged files only (`.lintstagedrc.json`).
- `eslint-config-prettier` is the last entry of `eslint.config.js`, so ESLint never fights Prettier over formatting.

The hooks are installed by the `prepare` script (`husky`) every time you run `npm install` or `npm ci`.

## Project version

- Angular 22. This project was generated with [Angular CLI](https://github.com/angular/angular-cli) version 22.2.6.
- Node.js 22.12 or later (required by commitlint 21).

## NPM packages included

- **husky**: 9.1.7 (Git hooks made easy)
- **@commitlint/cli**: 21.2.4 (lint your commit messages)
- **@commitlint/config-conventional**: 21.2.4 (shareable commitlint config enforcing Conventional Commits)
- **lint-staged**: 17.6.0 (run linters on files staged by Git)
- **angular-eslint**: 22.6.0, **eslint**: 10.14.0, **typescript-eslint**: 8.71.0
- **eslint-config-prettier**: 10.1.8 (turns off the ESLint rules that are unnecessary or might conflict with Prettier)
- **prettier**: 3.9.10

## Run it

```bash
npm ci                 # also installs the Git hooks
npm run lint           # ng lint
npm run format-check   # prettier --check .
npm start              # ng serve on http://localhost:4200
npm run build          # production build in dist/
```

## Give a Star! :star:

If you like or are using this project please give it a star. Thanks!

## Support this project! :pray:

If you want to help me to maintain this project or add improvements, it would be a pleasure!
