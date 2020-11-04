# jotformcfc

A CFML wrapper for the [JotForm API](https://api.jotform.com/docs/). Build, manage, and report on your (Jot)forms.

*This is an early stage wrapper. I've implemented the methods that I need to use, but it's by no means complete. It should provide a good starting point, if more functionality is needed. Feel free to use the issue tracker to report bugs or suggest improvements!*

## Acknowledgements

This project borrows heavily from the API frameworks built by [jcberquist](https://github.com/jcberquist). Thanks to John for all the inspiration!

## Table of Contents

- [Quick Start](#quick-start)
- [Setup and Authentication](#setup-and-authentication)
- [`jotformcfc` Reference Manual](#reference-manual)

## Quick Start

The following is a quick example of listing all your account's forms, using this wrapper.

```cfc
jotform = new path.to.jotformcfc.jotform( apiKey = 'xxx' );

writeDump( var='#jotform.listUserForms()#', abort='true' );
```

### Setup and Authentication

To get started with the JotForm API, you'll need an [API Key](https://api.jotform.com/docs/#gettingstarted).

Once you have this, you can provide it to this wrapper manually when creating the component, as in the Quick Start example above, or via an environment variable named `JOTFORM_API_KEY` which will get picked up automatically. This latter approach is generally preferable, as it keeps hardcoded credentials out of your codebase.

If your account is in HIPAA Safe mode, use the baseUrl property to override the default API endpoint when creating the component: `baseURl = 'https://hipaa-api.jotform.com'`.

### Reference Manual

#### `getForm( required string id )`

Get basic information about a form. *[Endpoint docs](https://api.jotform.com/docs/#form-id)*

#### `getFormQuestions( required string id )`

Get a list of all questions on a form. *[Endpoint docs](https://api.jotform.com/docs/#form-id-questions)*

#### `getFormReports( required string id )`

Get all the reports of a specific form. *[Endpoint docs](https://api.jotform.com/docs/#form-id-reports)*

#### `getFormSubmissions( required string id )`

List of form reponses. *[Endpoint docs](https://api.jotform.com/docs/#form-id-submissions)*

#### `getSubmission( required string id )`

Similar to /form/{form-id}/submissions. But only get a single submission. *[Endpoint docs](https://api.jotform.com/docs/#submission-id)*

#### `getUser()`

Get user account details for this JotForm user. *[Endpoint docs](https://api.jotform.com/docs/#user)*

#### `listUserForms()`

Get a list of forms for this account. *[Endpoint docs](https://api.jotform.com/docs/#user-forms)*

---
