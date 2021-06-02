# Sample application and template coding guidelines

## Background

We authored these guidelines with the following things in mind:

- **Consistency**: 
all code should be formatted and written the same way.

- **Maintainability**:
having automated tests to check the application's main functionality allows us to keep apps up-to-date.

- **Pluggability**:
with a consistent application format and a minimal consistent set of dependencies, developers can more easily combine different applications.

- **Contribution-friendliness**:
every sample/template should be friendly to new contributors to allow fixing bugs or adding missing features.

## Guidelines

With these criteria in mind, we came up with the following guidelines. We also used these guidelines to create the following repository templates that you can use to bootstrap your project:

- [sample-application](https://github.com/algolia-samples/sample-application)

### 1. Familiarity

Any of our applications should feel familiar to the developer. 

Prefer using built-in languages modules and tools or well-known, widely used libraries and frameworks.

### 2. Linting

Linting allows us to keep the code consistent. The rules themselves are less important than the actual presence of a linter. The ability to "auto fix" or having proper guides makes it easy for new developers to adhere to the linter rules.

### 3. Testing

Our code should be reliable and maintainable, and testing plays a big part in this. The more tests you can author for your application, the better. However, at the very least, you should have some general tests covering the core functionality of your application. This will allow us to keep applications easier up-to-date with automated dependency updates.

When in doubt, you should cover tests for template applications in the following order:

1. Test the endpoints/webhooks your app is exposing
2. Create end-to-end tests for your user interface to check for the basic functionality
3. Write additional unit tests starting with the most complex/critical functions

### 4. Frameworks and libraries

In general, you should use as many or as few libraries as it makes sense for the respective target audience. Having fewer libraries and dependencies makes it easier for people to adopt it. But if that means the codebase increases significantly because of code seemingly unrelated to the use case, use a library/dependency instead.

### 5. Environment variables

Credentials for Algolia and other external services, and things like service SIDs, should be stored as environment variables. To make it easy for people to get started, every project should use `.env` files for this.

The actual `.env` file should never be included in a template and should be part of the `.gitignore` file. Instead, a project should have a `.env.example` file that specifies every necessary environment variable, including default values where applicable, and a comment line (prefixed with `#`) above it specifying what this value is and how to retrieve the value (for example, sign up at algolia.com).

Most programming languages offer libraries for working with `.env` files.

### 6. Databases and Algolia indices

We want to make the project setup for people as easy as possible. To avoid wrestling with databases, whenever possible, you should use a file system-based one. One database that works with a variety of programming languages is SQLite3.

If possible, you should also provide a way to populate the database with some basic data (fixtures...).

In the same way, providing the data to populate Algolia indices or other external services makes it easy for people to set up your sample quickly.

### 7. Continuous integration

GitHub introduced GitHub Actions as a way to run continuous integration tests directly on their platform, allowing to test apps on Windows, Linux and macOS. This is our preferred way of running tests and other automation.

### 8. General files and structure

Every sample should have the following files to improve the experience for developers:

- `README.md` with a [structure following the template project](https://github.com/algolia-samples/sample-application/blob/master/README.md)
- `CONTRIBUTING.md` explaining how to contribute to this project for example to fix bugs. This can be included in the `README.md`

As for the overall structure of your project, follow what's the best practice for the target audience.
