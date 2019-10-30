---
layout: post
title:  How not to convert a React component library to TypeScript
date:   2019-10-22
tags:
- react
- TypeScript
- development 
---

* Do it little by little over time
* Don't fork!
  * You'll end up doing bug fixes and new features twice until you switch to the new TS fork
* Basic, but: don't be tempted to just do a bunch of `any` and `(...args: any[]) => any`. You'll pay for it later.
* For any 3rd party library you use (let's call it `foo`), if it doesn't come with its own type definitions, you need to be sure to also add `@types/foo` to your _direct dependencies_, not to your _devDependencies_. You have to re-publish these types with your library so that they work in production.
