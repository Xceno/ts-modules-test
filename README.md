# ts-modules-test

A small project to test `yarn link` with some TypeScript modules.

## Info

This example assumes a global install of **TypeScript 2.6.2** and **VSCode 1.19.0**.

## How to use

* Open a shell in _module-a_ and run `yarn link`

You should see this:

> **success** Registered "module-a".<br/>
 > **info** You can now run `yarn link "module-a"` in the projects where you want to use this module and it will be used instead.

* Open a shell in _module-b_ and run `yarn add file:../module-a`
* After the previous cmd, run `yarn link module-a`

You should see this:

> **success** Using linked module for "module-a".

This example uses [`concurrently`](https://github.com/kimmobrunfeldt/concurrently) to compile both modules simultaniously.
Install it by running `yarn` and start the task by running `yarn tsc` in the root folder.

You should now get full intellisense for **module-a** in **module-b**, that is always up-to-date as long as the tsc task runs.
