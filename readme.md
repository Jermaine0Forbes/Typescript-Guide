# Typescript Guide

All the information you need to know about this shitty language


- [how to use typescript in laravel mix][type-mix]

## Errors
-  [TS2451: Cannot redeclare block-scoped variable ][redeclare-variable]

[redeclare-variable]:#cannot-redeclare-block-scoped-variable
[home]:#typescript-guide
[type-mix]:#how-to-use-typescript-in-laravel-mix

### Cannot redeclare block scoped variable

**reference**
- (stackoverflow)[https://stackoverflow.com/questions/40900791/cannot-redeclare-block-scoped-variable-in-unrelated-files]

If you have this problem, put `export = {};` at the top of the file and the error will go away

[go back home][home]


### How to use typescript in laravel mix

Recently laravel has a way compile typescript code with `mix.ts(fileToCompile, LocationToSend)`

1. You need to  create a tsconfig file

```
touch tsconfig.json
```

2. Put this code inside the config file

```
{
    "lib": [
        "dom",
        "es5",
    ],
    "compilerOptions": {
        "target": "es5",
        "module": "commonjs",
        "sourceMap": true,
    },
    "exclude":[
	"node_modules",
	"vendor"
	],

}
```
3. In the `webpack.mix.js` add the ts function

```
mix.ts('/resources/assets/typescript/example.ts', '/public/js/');

```

[go back home][home]
