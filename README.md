# Derby Tutorial

_For Derby v0.10. Made for those onboarding to Derby, with some prior model-view-* and/or web-dev experience._

## Getting started

Hello, and welcome to this Derby tutorial!

We'll be going through several core features that Derby provides. Along the way, we may build a few features. You can think of this tutorial as a sandbox of various Derby features, rather than a tutorial that produces a full MVP application. We won't be explaining every aspect in detail, so you can reference the [DerbyJS docs](https://derbyjs.com/docs/derby-0.10) as you work through the tutorial.

To get started:

```shell
# Get the repo
> git clone https://github.com/lever/derby-tutorial.git
> cd derby-tutorial

# Install dependencies
> npm install

# Start Mongo with Docker Compose...
> docker-compose -f ./docker-compose.yaml up
# OR, if you don't want to use Docker Compose...
> docker run -d --rm mongo:3.4

# Start the server
> node src/server.js
```

You may be familiar with *routes* from other frameworks like [express.js](https://expressjs.com). Derby's routing system is built on top of Express.js.

Take a look at `src/index.js` for all the different routes that are available. We have commented this file (and all others) to guide you through it. We suggest having the source code open as you interact with the various tutorial pieces in your browser.

## Contributing

If you find anything confusing, please [submit an issue here](https://github.com/lever/derby-tutorial/issues), or submit a PR with tutorial improvements! Your help and feedback is really appreciated :heart:

Look for open issues or `TODO`s within the code if you want to start contributing!

## Overview

We recommend following the order of this outline. Some info builds on top of each other, and that's especially useful if this is your first time using Derby.

Later on, you can reference this tutorial and [the official docs](https://derbyjs.com/) if you'd like to see anything particular in action.

* [Hello world](#hello-world)
* [Racer basics](#racer-basics)
* [Components in action](#components-in-action)
* [Collaboration and realtime](#collaboration-and-realtime)
* [Collections and data persistence](#collections-and-data-persistence)

## The tutorial

### Hello world

Let's learn the bare minimum of what a component can offer. First, let's visit
[/hello-world](http://localhost:3456/hello-world) in your browser.

Check out the source code in `src/components/hello-world`. `index.js` defines our controller, and `index.html` defines our template.

### Racer basics

Now you are ready to read and manipulate some data!

[Racer](https://derbyjs.com/docs/derby-0.10/models) is used within Derby to provide an interface to our underlying data. Underneath, Racer provides realtime syncing and events - which keeps our data in sync and our app reactive.

Visit [/racer-basics](http://localhost:3456/racer-basics) and the corresponding source code to see all the different ways we can interact with data (via Racer).

### Components in action

This component is more fully-featured. It shows how you can:

* see a component's lifecycle and set relevant functionality at different phases
* reference Racer models and read/write data from it
* add child components inside of the main component, passing in data and receiving outputs
* use view partials without needing a whole component

<!-- TODO 11/18/18: Might be better to break this into smaller subsections -->

### Collaboration and realtime

What makes Derby powerful is its realtime-ness. Let's take a look at [/collaborative-note-editor](http://localhost:3456/collaborative-note-editor) to see this in action.

### Collections and data persistence

At the bottom of Derby sits [ShareDB](https://github.com/share/sharedb), a layer that sits on top of database(s). ShareDB allows you to connect to a persistence layer and actually save your data. (ShareDB's main responsibility is to execute Operational Transform, resolving all the versions of our modified documents.)

To interact with remote persisted data, we look at collections and documents. You can think of this as analogous to [Mongo collections](https://docs.mongodb.com/manual/core/databases-and-collections/#collections) and documents, or SQL tables and records.

<!-- TODO 11/18/18: Reference how this is done on the server -->

## Additional resources

- [derbyjs.com](https://derbyjs.com/) - Official DerbyJS Tutorial
- [github.com/derbyjs](https://github.com/derbyjs/) - DerbyJS on Github
- [github.com/derbyjs/derby-examples](https://github.com/derbyjs/derby-examples) - Other Derby Example Apps
- [github.com/derbyjs/racer](https://github.com/derbyjs/racer/) - Racer
- [github.com/share](https://github.com/share/) - ShareDB on Github
