# 協助工具

應用程式的易用性很重要，所以我們在 [Devtron](https://electron.atom.io/devtron) 及 [Spectron](https://electron.atom.io/spectron) 中加入了新功能，讓開發人員更容易打造出適用每個人的應用程式。

* * *

Accessibility concerns in Electron applications are similar to those of websites because they're both ultimately HTML. With Electron apps, however, you can't use the online resources for accessibility audits because your app doesn't have a URL to point the auditor to.

These new features bring those auditing tools to your Electron app. You can choose to add audits to your tests with Spectron or use them within DevTools with Devtron. Read on for a summary of the tools or checkout our [accessibility documentation](https://electron.atom.io/docs/tutorial/accessibility) for more information.

### Spectron

In the testing framework Spectron, you can now audit each window and `<webview>` tag in your application. For example:

```javascript
app.client.auditAccessibility().then(function (audit) {
  if (audit.failed) {
    console.error(audit.message)
  }
})
```

You can read more about this feature in [Spectron's documentation](https://github.com/electron/spectron#accessibility-testing).

### Devtron

In Devtron, there is a new accessibility tab which will allow you to audit a page in your app, sort and filter the results.

![devtron screenshot](https://cloud.githubusercontent.com/assets/1305617/17156618/9f9bcd72-533f-11e6-880d-389115f40a2a.png)

Both of these tools are using the [Accessibility Developer Tools](https://github.com/GoogleChrome/accessibility-developer-tools) library built by Google for Chrome. You can learn more about the accessibility audit rules this library uses on that [repository's wiki](https://github.com/GoogleChrome/accessibility-developer-tools/wiki/Audit-Rules).

If you know of other great accessibility tools for Electron, add them to the [accessibility documentation](https://electron.atom.io/docs/tutorial/accessibility) with a pull request.