# Sample Application & Template Coding Guidelines

## Background

These guidelines have been authored with the following things in mind:

**consistency**: 
All code should be formatted and written the same way.

**maintainability**:
Having automated tests to check the main functionality of the application allows us to keep apps up-to-date.

**pluggability**:
By keeping a consistent application format and a minimum consistent set of dependencies means developer can more easily combine different applications.

**contribution-friendliness**:
Every sample/template should be friendly to new contributors to allow to fix bugs or add missing features.

## Guidelines

With these criteria in mind we came up with the following guidelines. These guidelines have also been used to create the following repository templates that you can use to bootstrap your project:

- [sample-application](https://github.com/algolia-samples/sample-application)

### 1. Be familiar

Any of our applications should feel familiar to the developer. 

Prefer using built-in languages modules and tools or well-known, widely used libraries and frameworks.

### 2. Use a linter

Linting allows us to keep the code consistent. The rules themselves are less important than the actual presence of a linter as long as there's the capability to "auto fix" or proper guides that make it easy for new developers to adhere to the linter rules.

### 3. Testing

Our code should be reliable and maintainable and testing plays a big part in this. The more tests you can author for your application, the better. However, at the very least you should have some general tests covering the core functionality of your application. This will allow us to keep applications easier up-to-date with automated dependency updates.

When in doubt you should cover tests for template applications in the following order:

1. Test the endpoints/webhooks your app is exposing
2. Create E2E tests for your user interface to check for the basic functionality
3. Write additional unit tests starting with the mosts complex/critical functions

### 4. Frameworks & libraries

In general you should use as many or little libraries as it makes sense for the respective target audience. Less libraries and dependencies makes it easier for people to adopt it. But if that means the codebase increases significantly because of code that is seemingly unrelated to the use-case, use a library/dependency instead.

### 5. Using Environment Variables

Credentials for Algolia and other external services as well as things like service SIDs should be stored as environment variables. In order to make it easy for people to get started, every project should use `.env` files for this.

The actual `.env` file should never be included in a template and should be part of the `.gitignore` file. However, a project should have an `.env.example` file that specifies every environment variable necessary, including default values where applicable and a comment line (prefixed with `#`) above it specifying what this value is and how to retrieve the value (for example sign up at algolia.com).

Most programming languages offer libraries that help working with `.env` files.

### 6. Databases & Algolia indices

We want to make the project setup for people as easy as possible. In order to avoid them having to wrestle with databases, whenever possible, you should use a filesystem based one. One database that works with a variety of programming languages is SQLite3.

If possible you should also provide a way to populate the database with some basic data (fixtures...).

The same way for eventual Algolia indices, or other external services, providing the data to populate those will make it easy for people to quickly set up your sample.

### 7. Continous Integration

GitHub introduced GitHub Actions as a way to run continous integration tests directly on their platform allowing to test apps on Windows, Linux and macOS. This is our preferred way of running tests and other automation.

### 8. General Files & Structure

Every sample should have the following files to improve the experience for developers:

- `README.md` with a [structure following the template project](https://github.com/algolia-samples/sample-application/blob/master/README.md)
- `CONTRIBUTING.md` explaining how to contribute to this project for example to fix bugs. This can be included in the `README.md`

As for the overall structure of your project, follow what's the best practice for the target audience.