<!-- TOC -->

- [Walkoff-js Description](#walkoff-js-description)
- [Assumptions](#assumptions)
- [Tech Stack](#tech-stack)
- [Getting Setup -](#getting-setup--)
    - [Setup your local development environment.](#setup-your-local-development-environment)
    - [Setup your new project](#setup-your-new-project)
- [Notes](#notes)

<!-- /TOC -->


# Walkoff-js Description

This is an ***opinionated*** set of choices for starting a new software product. 
I believe starting a new project should feel like this:

![Walloff Home run](./walkoff.gif)

and not like this:

![Hit by pitch](./hitbypitch.gif)




# Assumptions

You're trying to build a "modern" app.  While there are literally thousands of ways to do this, 
this setup assumes the following:
1. Cost
    * Prefer free/opensource over spending money.  
    * Spend money on tools if it saves significant time.
    * Prefer operational expense vs capital expense.


2. Primary language
    * JavaScript all the things (where possible).  JavaScript has more reach (available platforms) than any other programming language.
2. Testing
    * All tests will be in JavaScript where possible.
    * Unit tests test developer code changes at the atomic level.
    * Integration tests test code changes at either the API or UI level.
    * Performance tests test code changes that impact performance, with some level of tolerance.
    * More code coverage is better, but 100% doesn't mean correct.  
3. Web 
    * Web - React & either Redux or Relay
    * Target Chrome, Safari, and IE
4. Mobile
    * You may have up to three deliveries on mobile: iOS, Android, & mobile web.
    * iOS - React Native + Swift
    * Android - React Native + Android
    * Mobile Web - Same as Web + responsive CSS 
5. Server 
    * JavaScript 
    * In a container environment = Docker + Node.js
    * In a serverless environment = Node.js
6. APIs
    * For client-facing APIs, prefer GraphQL over REST, but REST is still ok.
    * For server-facing APIs, prefer gRPC or Protocol Buffers over REST.
7. Developer Environment
    * Prefer Mac for local development. Avoid Windows for local development [(1)](#subnote_1)
8. DevOps
    * DevOps is a philosophy that can be supported by tooling.
    * DevOps doesn't mean developers don't have to understand their infrastructure.
9. Cloud
    * Prefer Amazon Web Services by default unless one of the following apply:
    * Prefer Google if you need something specific that Google offers (e.g. Firebase, Spanner, etc.)
10. Ownership vs "Throw it over the wall"
    * Prefer people and teams to own their products vs a "throw it over the wall" model.
    * This Implies that people will have production support of their code (at some level)
    * Which implies that APM, failover, degradation, and indicident management need to be 
    backed into the product versus tacked onto the product.



If you don't agree with the setup, then the selections below won't make sense.  That's entirely ok, as there are thousands of other choices 
***that are likely better*** for your assumptions on software development.

# Tech Stack

| Component                  | Choice                 | Reason                                                                                                                       |
|----------------------------|------------------------|------------------------------------------------------------------------------------------------------------------------------|
| IDE                        | VS Code                | Free + Debugger + support for React Native                                                                                   |
| iOS App                    | React Native + Swift   | JavaScript + Ability to drop into Swift as needed.  Ability to share code across iOS, Android, and ***possibly*** web.       |
| Android App                | React Native + Android | Same reasoning as iOS                                                                                                        |
| Web                        | React + Relay          | React is becoming defacto these days and Facebook seems focused on having good tooling around it.  Relay for GraphQL support |
| API                        | GraphQL                | GraphQL = Schema + Fast Development + ***possibly*** fast Performance (client network traffic)                               |
| Node Package Manager       | yarn                   | Yarn is replacing npm as of late 2017.                                                                                       |
| Unit Test Framework        | TBD                    |                                                                                                                              |
| Integration Test Framework | TBD                    |                                                                                                                              |
| Performance Test Framework | TBD                    |                                                                                                                              |
| Code Coverage Tool         | TBD                    |                                                                                                                              |
| Continous Integration      | TBD                    |                                                                                                                              |
| Continous Deployment       | TBD                    |                                                                                                                              |
| Source Code                | TBD                    |                                                                                                                              |
| API Documentation          | TBD                    |                                                                                                                              |
| Source Code Documentation  | TBD                    |                                                                                                                              |
| JavaScript linter          | TBD                    |                                                                                                                              |
| Version Controll           | git                    |                                                                                                                              |


# Getting Setup -

## Setup your local development environment.
1. [Install homebrew](https://brew.sh/)
2. Setup IDE by [downloading and installing VS Code](https://code.visualstudio.com/)
* Add the following VS Code packages after install:
    * Instant Markdown
    * React Native Tools
    * Document This
3. Setup local Node environment
* Install node
```shell
$> brew install node
$> brew install watchman
```
* Install yarn
```shell
$> npm install -g yarn
```
* Add yarn/bin to your $PATH.

In your .profile, add a line like this:
```shell
export PATH=/usr/local/Cellar/node/7.5.0/bin:$PATH
```
4. Setup for react by installing [create-react-app](https://github.com/facebookincubator/create-react-app)
```shell
$> yarn global add create-react-app --prefix /usr/local
```
5. Setup for [React Native](https://facebook.github.io/react-native/docs/getting-started.html)
```shell
$> yarn global add react-native-cli --prefix /usr/local
```

## Setup your new project
1. TBD







# Notes

<a name="subnote_1">(1)</a> Avoid Windows for local development.

The amount of "googleable" information for Windows is significantly lower for this tech stack compared to MacOS or Linux.  Windows is a fine choice for a lot of other problems and tech stacks (e.g. .Net development or gaming consoles).