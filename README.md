# Website Evidence Collector

The tool *Website Evidence Collector* (WEC) automates the website evidence collection of storage and transfer of personal data. It is based on the browser Chromium/Chrome and its JavaScript software library for automation [puppeteer].

[puppeteer]: https://developers.google.com/web/tools/puppeteer/

## Installation

1. The Website Evidence Collector is a set of scripts written in JavaScript for execution by *Node.js*. Install Node.js and the *Node.js package manager* (NPM).
  a. Windows or Mac: Follow the guide on <https://nodejs.org/en/>.
  b. Linux: use the Linux package manager to install Node.js, e.g. `zypper in nodejs10` (check version) or `apt install nodejs`.
2. Download WEC using `git clone [source]` or unzip `website-evidence-collector.zip` and open the terminal and navigate to the folder `website-evidence-collector`.
3. Install the dependencies using `npm install`

## Run Website Evidence Collection

To start the collection for e.g. <https://example.com>, open the terminal, navigate to the folder `website-evidence-collector` and run `npm start -- https://example.com`.

### Examples

#### Ignore Certificate Errors during Collection

```sh
npm start -- -y -q https://untrusted-root.badssl.com -- --ignore-certificate-errors
# or
./collect.js -y -q https://untrusted-root.badssl.com -- --ignore-certificate-errors
```

All commandline arguments after `--` (the second in case of `npm`) are applied to launch Chromium.

Reference: <https://peter.sh/experiments/chromium-command-line-switches/#ignore-certificate-errors>

## TODO List

- fix bugs in HAR creation, see <https://github.com/Everettss/puppeteer-har/issues>

## Resources for Developers

- puppeteer sandbox online: <https://puppeteersandbox.com/>
- opensource puppeteer sandbox: <https://github.com/ebidel/try-puppeteer>, online at <https://try-puppeteer.appspot.com/>
- puppeteer API documentation: <https://pptr.dev/>
- puppeteer examples: <https://github.com/checkly/puppeteer-examples>
- puppeteer with chrome-as-a-service: <https://github.com/joelgriffith/browserless>
- stacktrace.js documentation: <https://www.stacktracejs.com/#!/docs/stacktrace-js>
- Chrome DevTools Protocol Documentation: <https://chromedevtools.github.io/devtools-protocol/>

Use of Hooks for restructuring source code:

- https://www.npmjs.com/package/before-after-hook
- https://www.npmjs.com/package/promised-hooks
- https://www.npmjs.com/package/grappling-hook

Generation of Markdown Excerpts:

- https://justmarkup.com/articles/2019-01-04-using-puppeteer-to-crawl-pages-and-save-them-as-markdown-files/

Relevant Github Issues:

- [New HAR page doesn't appear to be created upon navigation chrome-har#19](https://github.com/sitespeedio/chrome-har/issues/19)
- [No mechanism to use seeded random generation lodash#3289](https://github.com/lodash/lodash/issues/3289)

## Contributors

- Robert Riemann (European Data Protection Supervisor, initial author)


## License

See [LICENSE.txt](./LICENSE.txt).
