# Change Log - @azure/msal-browser

This log was last generated on Mon, 07 Dec 2020 22:19:03 GMT and should not be manually modified.

<!-- Start content -->

## 2.8.0

Mon, 07 Dec 2020 22:19:03 GMT

### Minor changes

- Enable the instance_aware flow (#1804) (prkanher@microsoft.com)

### Patches

- Fix clearing of temporary cache items (#2696) (thomas.norling@microsoft.com)
- Add exports to index.ts (#2680) (joarroyo@microsoft.com)
- Expose idTokenClaims on AccountInfo (#2554) (janutter@microsoft.com)
- Add onRedirectNavigate to redirect operations in browser (#2669) (janutter@microsoft.com)
- Update Internal PCA Configuration (#2602) (thomas.norling@microsoft.com)
- Add allowRedirectInIframe flag to browser (#2593) (janutter@microsoft.com)
- Log messages contain package name and version (#2589) (thomas.norling@microsoft.com)
- Update request types (#2512) (thomas.norling@microsoft.com)

## 2.7.0

Wed, 11 Nov 2020 23:33:20 GMT

### Minor changes

- Support relative paths on redirectUri parameter (#2560) (thomas.norling@microsoft.com)

### Patches

- Adds getAccountByLocalId to PCA Interface (#2588) (thomas.norling@microsoft.com)
- Add navigateFrameWait and change loadFrameTimeout to browser to match core behavior (#2545) (janutter@microsoft.com)

## 2.6.1

Tue, 10 Nov 2020 01:48:44 GMT

### Patches

- Export stubbed PCA instance (#2540) (thomas.norling@microsoft.com)

## 2.6.0

Sat, 07 Nov 2020 01:50:14 GMT

### Minor changes

- Fixing a bug and adding `localAccountId` in AccountInfo interface (#2516) (sameera.gajjarapu@microsoft.com)

## 2.5.2

Mon, 02 Nov 2020 23:33:39 GMT

### Patches

- Fix JSON.parse issue and cache value validation (#2527) (prkanher@microsoft.com)

## 2.5.1

Fri, 30 Oct 2020 00:52:19 GMT

### Patches

- Restore string to cacheLocation type (#2523) (janutter@microsoft.com)

## 2.5.0

Thu, 29 Oct 2020 20:36:48 GMT

### Minor changes

- Add getLogger and setLogger to msal-browser (#2513) (joarroyo@microsoft.com)
- Adding memory storage option for cache location (#2481) (prkanher@microsoft.com)

### Patches

- Add handleRedirect End Event (#2518) (thomas.norling@microsoft.com)
- Ensure history.replaceState is a function (janutter@microsoft.com)
- Allow hash to be passed into handleRedirectPromise, reset non-msal after processing (janutter@microsoft.com)

## 2.4.1

Mon, 26 Oct 2020 21:00:29 GMT

### Patches

- msal-browser and msal-node cache Interfaces to msal-common updated (#2415) (sameera.gajjarapu@microsoft.com)

## 2.4.0

Tue, 20 Oct 2020 23:47:28 GMT

### Minor changes

- Add removeEventCallback API (#2462) (thomas.norling@microsoft.com)
- Add event api to msal-browser (#2394) (joarroyo@microsoft.com)

### Patches

- Use history API to clear hash for msal-browser (janutter@microsoft.com)
- Export InteractionType (#2438) (thomas.norling@microsoft.com)
- Add extraQueryParameters to acquireTokenSilent in msal-browser (janutter@microsoft.com)
- Fix unexpected interaction_required error in redirect flow (#2404) (thomas.norling@microsoft.com)
- Adds support for any OIDC-compliant authority (#2389). (jamckenn@microsoft.com)

## 2.3.1

Wed, 14 Oct 2020 23:45:07 GMT

### Patches

- Remove rogue console.log() in the BrowserCrypto.ts file and add a lint rule to prevent future issues (#2410) (prkanher@microsoft.com)
- Check for Headers class when configuring network client (janutter@microsoft.com)
- Update getItem to return ServerTelemetryEntity (#2223) (thomas.norling@microsoft.com)

## 2.3.0

Fri, 02 Oct 2020 17:42:35 GMT

### Minor changes

- Implementation of Access Token Proof-of-Possession Flow (#2151, #2153, #2154, #2209, #2289) (prkanher@microsoft.com)

## 2.2.1

Wed, 30 Sep 2020 17:58:33 GMT

### Patches

- Support SSR in msal-browser (#2073) (thomas.norling@microsoft.com)

## 2.2.0

Thu, 17 Sep 2020 23:16:22 GMT

### Minor changes

- Added client-side throttling to enhance server stability (#1907) (jamckenn@microsoft.com)

### Patches

- Fix issue with base64 encoding of spaces (#2248) (prkanher@microsoft.com)
- Properly support multiple concurrent RT requests (#2290) (janutter@microsoft.com)
- Default scope addition done in msal-common (#2267) (thomas.norling@microsoft.com)
- acquireTokenSilent calls ssoSilent (#2264) (thomas.norling@microsoft.com)
- Check for interaction in progress when processing redirect hash (#2183) (thomas.norling@microsoft.com)
- Creating ClientApplication.ts subclass (#2199) (prkanher@microsoft.com)
- Add SsoSilentRequest for ssoSilent, update tests and samples (joarroyo@microsoft.com)
- Add Angular 10 browser sample, update documentation (joarroyo@microsoft.com)

## 2.1.0

Tue, 25 Aug 2020 00:40:45 GMT

### Minor changes

- Client Capabilities Support (#2169) (thomas.norling@microsoft.com)

### Patches

- update APP_META_DATA to APP_METADATA (sameera.gajjarapu@microsoft.com)
- Add getAccountByHomeId API (#2114) (thomas.norling@microsoft.com)
- Change msal-browser loginPopup and openPopup, add ability to configure popup delay (#2132) (joarroyo@microsoft.com)
- Update POST header to type Record (#2128) (thomas.norling@microsoft.com)

## 2.0.2

Thu, 13 Aug 2020 02:20:48 GMT

### Patches

- Fix hash parsing issue from #2118 and back button cache clearing (#2129) (prkanher@microsoft.com)

# 2.0.1
## Breaking Changes
* None

## Features and Fixes
* Make request object optional for login APIs in PublicClientApplication (#2061)
* Fix `getAccountByUsername()` API signatures to return null (#2059)
* (#2078) Fix issues with `handleRedirectPromise()` where:
    * state mismatches occur if `handleRedirectPromise()` is called multiple times.
    * `currentUrl` and `loginRequestUrl` being evaluated as not equal if one has a trailing slash and the other does not
    * When `loginRequestUrl` is not in the cache, msal redirects to the homepage but would not process the hash
* Add `sid` from `AuthorizationUrlRequest` to SSO check in `ssoSilent()` (#2030)
* Add interaction type to platform state and check before processing hash (#2045)
* Implements telemetry error calculation and caching for server telemetry information in browser scenarios (#1918)
* Fix promise handling in PublicClientApplication (#2091)

# 2.0.0
## Breaking Changes
* None

## Features and Fixes
* Fix an issue where logout was not clearing all accounts (#1919)
* Typescript sample for browser (#1920)
* Add SilentRequest.ts object (#1964)
* Fix an issue where popup window position value did not have a floor (#1981)
* Fix an issue where getAccountByUsername was case-sensitive for the given username (#1982)
* Fix an issue where `openid` and `profile` were being added to silent requests (#1962)
* Fix an issue where the hash was not handled if `navigateToLoginRequestUrl`=`false` (#1973)
* Fix an error that occurs when the request object is not provided to login and the redirectStartPage is expected (#1998)

# 2.0.0-beta.4
## Breaking Changes
* Updated all APIs to send `openid` and `profile` by default in all requests (#1868)

## Features and Fixes
* add interface for PublicClientApplication (#1870)
* Update `monitorIframeForHash` to be purely time-based (#1873)
* Instantiate Logger instance for PublicClientApplication (#1882)
* Fix an issue with encoding in cookies and state values (#1852)
* Fix issue where cache isn't being cleaned correctly (#1856)
* Fix issue where expiration isn't calculated correctly (#1860)
* Fix an issue where the crypto APIs were not truly random (#1872)
* Remove all non-application specific initialization from PublicClientApplication constructor (#1885, #1886)
* Added support for IE11 (#1883, #1884)
* Added support for redirection to pages with custom hashes or query params (#1862)
* Remove deprecated `handleRedirectCallback()` API (#1863)
* Remove function typings for `redirectUri` and `postLogoutRedirectUri` (#1861).
* Add support for Instance Discovery, combine all authority classes into a single generic class (#1811)

# 2.0.0-beta.3
## Breaking Changes
* `@azure/msal-browser` now follows a unified cache schema similar to other MSAL libraries (#1624, #1655, #1680, #1711, #1762, #1771)
* Updated browser library to follow common format for request, response, and client configurations (#1682, #1711, #1762, #1770, #1771, #1793)
* Account interface updated to AccountInfo.ts (#1789)

## Features and Fixes
* add `setKnownAuthorities` to constructor call for B2C Authority scenarios (#1646)
* Library state is now sent as a encoded JSON object (#1790)
* Added a request object for logout APIs, made logout async (#1802)

# 2.0.0-beta.2
* Fixed an issue where the system config values were being overwritten with `undefined` (#1631)

# 2.0.0-beta.1
## Features
* Added a silent iframe flow in the @azure/msal-browser package (#1451)
    * Includes an ssoSilent() API to acquire tokens silently with a user context (loginHint)

## Bugs
* Fixed an issue where TokenResponse is not exported

## Enhancements
* handleRedirectCallback flow was modified, will be deprecated in favor of handleRedirectPromise(), added log message (#1490, #1543)

# 2.0.0-beta.0
## Features
* Removed client_secret from config and added docs for new registration experience (#1421)

## Enhancements
* Test pipelines in place. (#1393)
* Added docs and samples. (#1421, #1321)

## Bugs
* Minor bug fixes from unit testing. (#1236)
* navigateToLoginRequestUrl works correctly (#1320)

# 2.0.0-alpha.0
## Features
* Added Rollup as build tool (#1108)
* Added APIs and major type files (#1109)
* Added tests and code coverage (#1127)
* Added Authority and protocol classes (#1133)
* Added browser storage implementation (#1140)
* Added implementation of crypto for browser (#1141)
* Added fetch client (#1144)
* Creating of login url (#1149)
* Added logger class (#1155)
* Added redirect handling code (#1164)
* Successful token exchange (#1181)
* Response handling code (#1183)
* Token caching (#1185)
* Popup handling (#1190)
* Silent renewal using refresh tokens and logout (#1208)
* SSO fixes for login_hint (#1211)

# 0.0.1
- Created library with initial files for repo structure, build and package dependencies
