# Chrome Network Error List

Taken straight from [https://cs.chromium.org/chromium/src/net/base/net_error_list.h](https://cs.chromium.org/chromium/src/net/base/net_error_list.h) and put into JSON.

This can be useful in Electron apps that load remote URLs.

For example:

```javascript
chromeErrors = require('chrome-network-errors');
webview.addEventListener('did-fail-load', (event, code, desc, url, isMainFrame) => {
  displayMessageInUI(`Oops, something failed. Error: ${code}, ${chromeErrors[code]}`);
  writeToLog({ level: 'error', message: `Webview failed to load: ${url}, ${code}, ${chromeErrors[code]}. Bummer.` });
});
```
