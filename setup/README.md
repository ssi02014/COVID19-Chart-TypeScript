## ๐จ๐ปโ๐ป ํ์์คํฌ๋ฆฝํธ ํ๋ก์ ํธ ํ๊ฒฝ ๊ตฌ์ฑ

1. ํ๋ก์ ํธ ํด๋ ์์ฑ
2. `npm init -y`๋ก `package.json` ํ์ผ ์์ฑ
3. ํ์์คํฌ๋ฆฝํธ ๋ฐ ๋ฌธ๋ฒ ๊ฒ์ฌ, ์ฝ๋ ์ ๋ฆฌ ๋๊ตฌ ๋ผ์ด๋ธ๋ฌ๋ฆฌ ์ถ๊ฐ

```
  npm i -D typescript @babel/core @babel/preset-env @babel/preset-typescript @typescript-eslint/eslint-plugin @typescript-eslint/parser eslint prettier eslint-plugin-prettier
```

4. ํ๋ก์ ํธ ํด๋ ๋ฐ๋ก ์๋์ `ESLint` ์ค์  ํ์ผ ์ถ๊ฐ

```js
// .eslintrc.js
module.exports = {
  root: true,
  env: {
    browser: true,
    node: true,
  },
  extends: [
    "eslint:recommended",
    "plugin:@typescript-eslint/eslint-recommended",
    "plugin:@typescript-eslint/recommended",
  ],
  plugins: ["prettier", "@typescript-eslint"],
  rules: {
    "prettier/prettier": [
      "error",
      {
        singleQuote: true,
        semi: true,
        useTabs: false,
        tabWidth: 2,
        printWidth: 80,
        bracketSpacing: true,
        arrowParens: "avoid",
      },
    ],
  },
  parserOptions: {
    parser: "@typescript-eslint/parser",
  },
};
```

<br />

5. ESLint ์ด๊ทธ๋ธ์ด ํ์ผ ์ถ๊ฐ
```
  // .eslintignore
  node_modules
```

<br />

## ๐จ๐ปโ๐ป VSCode ESLint ํ๋ฌ๊ทธ์ธ ๊ด๋ จ ์ค์ 
1. VSCode์ ESLint ํ๋ฌ๊ทธ์ธ ์ค์น
2. VSCode์์ ctrl + shift + p / cmd + shift + p ํค๋ฅผ ์ด์ฉํ์ฌ ๋ช๋ น์ด ์คํ ์ฐฝ ํ์
3. ๋ช๋ น์ด ์คํ ์ฐฝ์ open settings (json) ์๋ ฅ ํ ์ ํ
4. VSCode ์ฌ์ฉ์ ์ ์ ํ์ผ์ธ settings.json ํ์ผ์ ๋ด์ฉ์ ์๋์ ๊ฐ์ด ESLint ํ๋ฌ๊ทธ์ธ ๊ด๋ จ ์ค์  ์ถ๊ฐ.
```json
  {
  // ... <-- ๊ธฐ์กด ๋ด์ฉ์ ๊ผญ ์ ์งํ ์ํ์์ ์๋ ๋ด์ฉ์ ์ถ๊ฐํ๊ณ  ์ด ์ฃผ์์ ์ ๊ฑฐํ  ๊ฒ
  "editor.codeActionsOnSave": {
      "source.fixAll.eslint": true
  },
  "eslint.alwaysShowStatus": true,
  "eslint.workingDirectories": [
      {"mode": "auto"}
  ],
  "eslint.validate": [
      "javascript",
      "typescript"
  ]
}
```
5. ctrl + , ๋๋ cmd + , ๋๋ฌ์ VSCode ์ค์  ํ์ผ(Settings)์ ๋ค์ด๊ฐ ํ format on save ๊ฒ์. ์๋์ ๊ฐ์ด ์ฒดํฌ๊ฐ ์๋์ด ์๋์ง ํ์ธ.

<br />