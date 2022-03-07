<div align="center">
  <h1>React Cheatsheets</h1>
</div>

<!--START-SECTION:setup-->

# Section 1: Setup React

## VS Code Extensions

- refactoring help https://marketplace.visualstudio.com/items?itemName=paulshen.paul-typescript-toolkit
- R+TS Code Snippets (there are a few...)
  - https://marketplace.visualstudio.com/items?itemName=infeng.vscode-react-typescript
  - https://www.digitalocean.com/community/tutorials/the-best-react-extension-for-vs-code
- TypeScript official extension https://code.visualstudio.com/docs/languages/typescript

<!--END-SECTION:setup-->

# Section 2: Getting Started

<!--START-SECTION:hooks-->

## Hooks

Hooks are [supported in `@types/react` from v16.8 up](https://github.com/DefinitelyTyped/DefinitelyTyped/blob/a05cc538a42243c632f054e42eab483ebf1560ab/types/react/index.d.ts#L800-L1031).

## useState

Type inference works very well for simple values:

```js
const [count, setCount] = useState(initialCount);
// `count` is inferred to be variable name
// `setCount` a function is used to update the count
// `initialCount` initial value
```

See also the [Using Inferred Types](https://react-typescript-cheatsheet.netlify.app/docs/basic/troubleshooting/types/#using-inferred-types) section if you need to use a complex type that you've relied on inference for.

However, many hooks are initialized with null-ish default values, and you may wonder how to provide types. Explicitly declare the type, and use a union type:

```js
const [user, setUser] = React.useState<IUser | null>(null);

// later...
setUser(newUser);
```

## useEffect / useLayoutEffect

<!--END-SECTION:hooks-->

## Contributors

This project follows the [all-contributors](https://github.com/all-contributors/all-contributors) specification. See [CONTRIBUTORS.md](/CONTRIBUTORS.md) for the full list. Contributions of any kind welcome!
