# test-dependency-injection

**Dependency Injection (DI)** is a high level implementation of the *inversion of control* pattern which uses *containers*.

**Dependency injection** (DI) *decouples* the pieces of your application as dependencies are not hardcoded but injected at construction time.

An important benefit of DI is that it helps **testing** as you can inject *mocked dependencies* and verify calls made on those.

There are two patterns related to dependency injection:

- **Container Pattern**: allows objects to be configured by the container instead of the client.  A container is an object created to hold other objects that are accessed, placed and maintained with the class methods of the container. (http://best-practice-software-engineering.ifs.tuwien.ac.at/patterns/container.html).
- **Abstract Factory**: allows an application to acquire objects and components without exposing too much information about how components fit togheter or what dependencies each component might have. (http://best-practice-software-engineering.ifs.tuwien.ac.at/patterns/factory.html)


### How Dependency Injection has been implemented in Ember

In Ember DI works through the container (https://www.emberjs.com/api/ember/2.16/classes/Container and https://github.com/emberjs/ember.js/blob/v2.16.4/packages/container/lib/container.js#L16), a birthplace of Objects.

Ember provides api to deal with the container in order to register and inject a dependency on your code.
First you need to register a dependency on the container, then you can inject the dependency.

In Ember a Container must be associated with a Registry.

When an Ember app is created, the first thing it does is creating a container it uses internally.
You can see the code of the container here: https://github.com/emberjs/ember.js/blob/v2.16.4/packages/container/lib/container.js
where we can see that the only public method is factoryFor, that given a fullName, return the corresponding factory

Let's see the Registry:
https://github.com/emberjs/ember.js/blob/v2.16.4/packages/container/lib/registry.js



Ember application class uses the RegistryProxyMixin:
https://emberjs.com/api/ember/2.16/classes/RegistryProxyMixin

References:

- https://martinfowler.com/articles/injection.html


## Prerequisites

You will need the following things properly installed on your computer.

* [Git](https://git-scm.com/)
* [Node.js](https://nodejs.org/) (with NPM)
* [Ember CLI](https://ember-cli.com/)
* [Google Chrome](https://google.com/chrome/)

## Installation

* `git clone <repository-url>` this repository
* `cd test-dependency-injection`
* `npm install`

## Running / Development

* `ember serve`
* Visit your app at [http://localhost:4200](http://localhost:4200).
* Visit your tests at [http://localhost:4200/tests](http://localhost:4200/tests).

### Code Generators

Make use of the many generators for code, try `ember help generate` for more details

### Running Tests

* `ember test`
* `ember test --server`

### Building

* `ember build` (development)
* `ember build --environment production` (production)

### Deploying

Specify what it takes to deploy your app.

## Further Reading / Useful Links

* [ember.js](https://emberjs.com/)
* [ember-cli](https://ember-cli.com/)
* Development Browser Extensions
  * [ember inspector for chrome](https://chrome.google.com/webstore/detail/ember-inspector/bmdblncegkenkacieihfhpjfppoconhi)
  * [ember inspector for firefox](https://addons.mozilla.org/en-US/firefox/addon/ember-inspector/)
