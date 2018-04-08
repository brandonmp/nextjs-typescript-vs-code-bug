[![Deploy to now](https://deploy.now.sh/static/button.svg)](https://deploy.now.sh/?repo=https://github.com/zeit/next.js/tree/master/examples/with-typescript)

When using a NextJs project with TypeScript, Visual Studio Code editor integration works fine--problems are underlined, autocompletion works, etc.

However, when adding absolute import paths into the mix (e.g., `import x from 'components/x'` instead of `import x from '../../../components/x'`), the editor fails to parse the typings of any module imported with absolute paths.

Here's a screen cap of editor underlining the absolute path import. Note that this compiles just fine--so it's only the editor integration failing.

![A screenshot of the editor identifying the absolute path import as a 'module not found' error](https://raw.githubusercontent.com/brandonmp/nextjs-typescript-vs-code-bug/master/editor-underlines.png)

Note that `tsconfig.json` has both `compilerOptions.baseUrl` and `compilerOptions.paths` properties set.

The same problem presents when using different solutions for absolute path imports, such as modifying `webpack` config via `next.config.js`, or by using the `module-alias` package from `npm`.
