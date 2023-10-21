### To Read

- eslint
- prettier
- typescript config

[TypeScript Monorepo Setup with PNPM Workspaces, Vite, VueJS and TailwindCSS](https://www.youtube.com/watch?v=HM03XGVlRXI)

### Steps

1. pnpm init && git init 3:28

2. create .gitignore, folder @app/client, @app/server and packages

3. create pnpm-workspace.yaml, set standalone package

4. create vite at @app/client

```
cd @app/client
pnpm create vite .
```

5. rename name in @app\client\package.json

```
{
  "name-example": "@name-of-app/name-of-package"
}
```

6. reuse typescript configuration

7. add typescript to root level folder. add w flag to confirm installation at the top level

```
pnpm add -Dw typescript
```

8. enforcing linking and code formatting rules

- functions of packages 6:49

9. create eslint RC file 7:43

10. create prettier config 8:08

11. create tailwind css config that be used by client and component 8:18

12. add tailwind.config and postcss.config to @app/client and add base style to style.css

```
pnpm client add -D @demo/tailwind-config@workspace:*
```

13. create vue.js component library 11:25,

```
mkdir packages/ui-lib
cd packages/ui-lib
pnpm create vite .
```

- copy ts config and tailwind config from @app/client and replace it.
- Remove .gitignore from @app/client and ui-lib

```
pnpm lib add -D @demo/tailwind-config@workspace:*
```

14. install ui-lib to @app/client 16:54

- must build ui-lib before using it.
- if you want to work on both ui-lib and client at same time, run client in dev mode and run ui-lib in watch mode

```
pnpm --recursive --parallel --stream run dev
```
