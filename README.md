&nbsp;
<p align="center">
    <picture>
        <source media="(prefers-color-scheme: dark)" srcset="https://cdn.adguard.com/public/Adguard/Common/Logos/ext_dark.svg" width="300px" alt="AdGuard Browser Extension" />
        <img src="https://cdn.adguard.com/public/Adguard/Common/Logos/ext.svg" width="300px" alt="AdGuard Browser Extension"/>
    </picture>
</p>
<h3 align="center">Ad blocker with advanced privacy protection features</h3>
<p align="center">
    AdGuard is a fast and lightweight ad blocking browser extension<br/>that effectively blocks all types of ads and trackers.
</p>


<p align="center">
    <a href="https://adguard.com/">AdGuard.com</a> |
    <a href="https://reddit.com/r/Adguard">Reddit</a> |
    <a href="https://twitter.com/AdGuard">Twitter</a> |
    <a href="https://t.me/adguard_en">Telegram</a>
    <br /><br />
    </a>
    <a href="https://github.com/AdguardTeam/AdguardBrowserExtension/releases">
        <img src="https://img.shields.io/github/release/AdguardTeam/AdguardBrowserExtension/all.svg" alt="Latest release" />
    </a>
</p>

<br />

<p align="center">
    <img src="https://cdn.adguard.com/public/Adguard/Common/adguard_extension_4_settings.png" width="800" />
</p>

<hr />

AdGuard is a fast and lightweight ad blocking browser extension that effectively blocks all types of ads and trackers on all web pages. We focus on advanced privacy protection features to not just block known trackers, but prevent web sites from building your shadow profile. Unlike its standalone counterparts (AG for Windows, Mac), the browser extension is completely free and open source. You can learn more about [the difference](https://adguard.com/compare.html) here.

> AdGuard does not collect any information about you, and does not participate in any acceptable ads program. The only source of income we have is selling premium versions of our software, and we intend to keep it that way.

- [Installation](#installation)
  - [Chrome and Chromium-based browsers](#chrome-and-chromium-based-browsers)
  - [Firefox](#firefox)
  - [Opera](#opera)
  - [Microsoft Edge](#microsoft-edge)
- [Contribution](#contribution)
  - [Translating AdGuard](#translating-adguard)
  - [Testing AdGuard](#testing-adguard)
  - [Reporting issues](#reporting-issues)
  - [Other options](#other-options)
- [Development](#development)
  - [Requirements](#requirements)
  - [How to build](#how-to-build)
  - [Linter](#linter)
  - [Update localizations](#update-localizations)
- [Minimum supported browser versions](#minimum-supported-browser-versions)

<a id="installation"></a>
## Installation

<a id="installation-chrome"></a>
### Chrome and Chromium-based browsers
You can get the latest available AdGuard Extension version from the [Chrome Web Store](https://agrd.io/extension_chrome).

<a id="installation-firefox"></a>
### Firefox
You can get the latest version of AdGuard Extension from the [Mozilla Add-ons website](https://agrd.io/extension_firefox).

<a id="installation-opera"></a>
### Opera
Opera is basically a Chromium browser, but it maintains its own add-ons store. You can get AdGuard Extension [from there](https://agrd.io/extension_opera).

<a id="installation-edge"></a>
### Microsoft Edge
The latest stable version of AdGuard browser extension is available in [Microsoft Store](https://agrd.io/extension_edge).

<a id="contribution"></a>
## Contribution

We are blessed to have a community that does not only love AdGuard, but also gives back. A lot of people volunteer in various ways to make other users' experience with AdGuard better, and you can join them!

We, on our part, can only be happy to reward the most active members of the community. So, what can you do?

<a id="contribution-translating"></a>
### Translating AdGuard

If you want to help with AdGuard translations, please learn more about translating our products here: https://kb.adguard.com/en/general/adguard-translations

<a id="contribution-testing"></a>
### Testing AdGuard

You can get a beta version of AdGuard Browser Extension for any browser. All necessary information on this topic can be found on a [dedicated page on our website](https://adguard.com/beta.html).

<a id="contribution-reporting"></a>
### Reporting issues

GitHub can be used to report a bug or to submit a feature request. To do so, go to [this page](https://github.com/AdguardTeam/AdguardBrowserExtension/issues) and click the *New issue* button.

>**Note:** for the filter-related issues (missed ads, false positives etc.) use the [dedicated repository](https://github.com/AdguardTeam/AdguardFilters).

<a id="contribution-other"></a>
### Other options

Here is a [dedicated page](https://adguard.com/contribute.html) for those who are willing to contribute.

<a id="dev"></a>
## Development

> Since version 4.0, Adguard browser extension uses opensource [tsurlfilter](https://github.com/AdguardTeam/tsurlfilter) library for implementing content blocking rules.

<a id="dev-requirements"></a>
### Requirements

- [node.js LTS](https://nodejs.org/en/download/)
- NPM v8
- [yarn v1.22](https://yarnpkg.com/en/docs/install/)

Install local dependencies by running:
```
  yarn install
```

<a id="dev-build"></a>
### How to build

**How to run tests**
```
  yarn test
```

**Building the dev version**

Run the following command:
```
  yarn dev
```

This will create a build directory with unpacked extensions for all browsers:
```
  build/dev/chrome
  build/dev/edge
  build/dev/firefox-amo
  build/dev/firefox-standalone
  build/dev/opera
```

**Building the beta and release versions**

Before building the release version, you should manually download necessary resources: filters and public suffix list.

```
  yarn resources
```

```
  yarn beta
  yarn release
```
You will need to put certificate.pem file to the `./private` directory. This build will create unpacked extensions and then pack them (crx for Chrome).

**Building the sample extension with API**

Run the following command:
```
yarn adguard-api
```
This will create a build directory with unpacked sample extension for chromium browsers:

```
build/dev/adguard-api
```

<a id="dev-linter"></a>
### Linter
Despite our code may not currently comply with new style configuration,
please, setup `eslint` in your editor to follow up with it `.eslintrc`

<a id="dev-localizations"></a>

### Update localizations

To download and append localizations run:

```bash
    yarn locales download
```

To upload new phrases to crowdin you need the file with phrases `./Extension/_locales/en/messages.json`. Then run:

```bash
    yarn locales upload
```

To remove old messages from locale messages run:

```bash
  yarn locales renew
```

To validate translations run:

```bash
  yarn locales validate
```

To show locales info run:

```bash
  yarn locales info
```

<a id="minimum-supported-browser-versions"></a>

## Minimum supported browser versions

| Browser                 	| Version      |
|-------------------------	|:------------:|
| Chromium Based Browsers 	|  79   	   |
| Firefox                 	|  78   	   |
| Firefox Mobile            |  113    	   |
| Opera                   	|  66   	   |
| Edge                    	|  79   	   |
