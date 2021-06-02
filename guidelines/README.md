# Samples and templates coding guidelines

These guidelines ensure consistency across all Algolia samples. The following guidelines focus on:

- **Consistency:** all code is formatted and written in the same way
- **Maintainability:** automated tests check the core application logic
- **Modularity:** samples use a consistent structure and a consistent, minimal set of dependencies
- **Contribution-friendly:** every sample is open and friendly to new contributors, inviting bug fixes, or new features

## Repository template

With these goals in mind, we created a template you can use to bootstrap your projects: [sample-application](https://github.com/algolia-samples/sample-application).

## Be familiar

Sample applications should _feel_ familiar to the developer. Prefer built-in standard library modules or well-known, widely-used libraries and frameworks.

## Use linters

Linting keeps the code consistent. Using a linter at all is more important than which specific rules you adopt. Linters, which can automatically fix linting errors, make it easy to apply consistent formatting and style to your code.

## Use tests

Our code should be reliable and maintainable. The more (meaningful) tests you include, the better. As a bare minimum, write a few general tests for the core functionality. Testing helps us maintaining the sample with automated dependency updates.

For more guidelines, write tests in this order:

1. Test the endpoints/webhooks your app is exposing.
2. Create end-to-end tests for your user interface to check for the basic functionality.
3. Write additional unit tests starting with the most complex/critical functions.

## Use few frameworks and libraries

In general, use as many or as few libraries as it makes sense for the target audience of your sample apps. Fewer libraries mean fewer dependencies, which makes the code easier to maintain. But don't re-invent the wheel. If your code starts to include many unrelated functions for doing common tasks, consider using a well-known library.

## Use environment variables

Store identities, API keys, security identifiers (SID), and similar information as environment variables in a `.env` file. Don't include the `.env` file itself in the repository, but add it to the `.gitignore` file. Instead, provide an example file `.env.example` that lists all the environment variables the user needs. Provide default values if applicable and include comments explaining the purpose of each environment variable. 
Explain, how users can get credentials and API keys, for example, by including links to the relevant websites. 

Most programming languages have libraries for working with `.env` files.

## Prefer filesystem databases and prepopulated Algolia indices

We want to make it as easy as possible to get started with a sample app. To avoid wrestling with database administration, use a simple local database with broad support, for example, [SQLite](https://www.sqlite.org/index.html).

To make it even easier, provide some sample data for users to get started. 

## Use continous integration

You can use [GitHub Actions](https://docs.github.com/en/actions) to run continuous integration tests on Windows, Linux, and macOS without registering with external providers. Prefer GitHub Actions for running tests on every [push or pull request](https://docs.github.com/en/actions/reference/events-that-trigger-workflows).

## Include basic information

Provide at least the following files: 

- `README.md` with a [structure following the template project](https://github.com/algolia-samples/sample-application/blob/master/README.md)
- `CONTRIBUTING.md` explaining how to contribute to this project, for example, to fix bugs. Alternatively, include this information in `README.md`.

For the overall structure of your project, follow the best practices of your target audience.
