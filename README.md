# vue-phaser-vite

#### Vite boilerplate that integrates Phaser 3 into a Vue 3 project.

This project template has been set up using **Vite** and includes:
* *Typescript*
* *Code Splitting*
* *Source Minification*
* *CSS Postprocessing*

## Build Setup

``` bash
# install dependencies
npm install

# serve with live reloading on localhost
npm run dev

# build for production
npm run build

# serve your production build on localhost
npm run preview
```

## Extending the project to your needs

If you want to add more features like *linting*, *unit testing* or *SCSS* to
your own project, you can do so quite easily with Vite. Read the
<a href="https://vitejs.dev/guide/" target="_blank">documentation</a> to get
familiar with the tool. Also take a look at
<a href="https://github.com/vitejs/awesome-vite#plugins" target="_blank">
awesome-vite</a> for plugins and more.

## Converting into your own repository

If you want to maintain your own repo based on this boilerplate, you first need
to detach it from this repo. Here is what you need to do:

1. edit these files and enter your own project info
	* *package.json*
	* *README.md*
	* *index.html*

2. delete *LICENSE* (and perhaps add your own)

3. reinitialize git
<pre><code>rm -rf .git
git init
git add .
git commit -m "Initial commit"
</code></pre>

## Sharing data between Vue and Phaser

You might want to expose some game state that lives inside of your Phaser code
to your Vue components and vice versa, for example a highscore. Here are two
ways you can achieve sharing state between the frameworks.

* Import a Phaser <a href="https://photonstorm.github.io/phaser3-docs/Phaser.Events.EventEmitter.html" target="_blank">EventEmitter</a> instance in
both your Vue components and Phaser modules. Both sides can then listen to and
emit events on that emitter.

* Have both sides share a <a href="https://pinia.vuejs.org/introduction.html" target="_blank">
Pinia</a> store instance. It works like an event emitter, but can also hold
state. The Pinia store is nicely integrated into your Vue components and is easily
accessible on the Phaser side by applying the *useStore* hook.
