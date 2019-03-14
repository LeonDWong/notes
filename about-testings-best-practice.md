### Organizing Tests, Logging In, Controlling State

> **Anti-Pattern**: Sharing page objects, using your UI to log in, and not taking shortcuts.

> **Best Practice**: Test specs in isolation, programmatically log into your application, and take control of your application’s state.

### Selecting Elements

>  ~~**Anti-Pattern**: Using highly brittle selectors that are subject to change.~~

>  ~~**Best Practice**: Use **data-*** attributes to provide context to your selectors and insulate them from CSS or JS changes.~~

Not real for all case, using id is better than define specific data-XXX only for testing.

### 




