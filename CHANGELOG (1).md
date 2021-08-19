---
title: "Changelog"
excerpt: "changes"
---
# Changes

## 1.31.4

* Fixed swagger comments for feature-toggle

## 1.31.3

* Update swagger annotation for pub deals get

## 1.31.1

* Fix performance issues

## 1.31.0

* Updated to use new accounts-data-api publisher route instead of deprecated accounts route

## 1.30.2

* Added user-feature-toggle endpoint

## 1.30.1

* Return audience IDs and publisher IDs for platform-deals even if associations cannot be found

## 1.30.0

* Added DELETE `/platform-deals/:dealid`
* Added DELETE `/publisher-deals/:dealid`

## 1.29.3

* Updated audience routes to leverage scope and platform filters

## 1.29.2

* Fixed data client bug

## 1.29.1

* Removed old deals-data-api client

## 1.29.0

* Added GET `/audiences/platform` to retrieve all platform scope audiences from audience-manager-data-api
* Added GET `/publishers/platform` to retrieve all platform deal enabled publishers from accounts-data-api

## 1.28.3

* Utilize GET `/publisher-deals/deal-mode` for PUT `/publisher-deals`

## 1.28.0

* Added GET `/platform-deals/`
* Added GET `/platform-deals/:dealid`
* Added jaeger route tracing

## 1.27.3

* Update helm instructions

## 1.27.2

* Updated references and renamed "services" to "repositories" and vice versa, merged in dealsservices and dealsrepositories

## 1.27.1

* Added test cases for dealmode with 0 deal mode and 0 HV
* Updated deal-data-api version
* Fixed deals mode response coming back as a pointer

## 1.27.0

* Added PUT `/platform-deals/`

## 1.26.3

* Update README instructions to helm3

## 1.26.2

* Remove spacing from `GET /sections` swagger annotations

## 1.26.1

* Fixed swagger comments for `GET /publisher-deals/deal-mode` route

## 1.26.0

* Add `GET /publisher-deals/deal-mode` route to check for deal mode verification

## 1.25.0

* Added PATCH `/platform-deals/:dealid/`

## 1.24.11

* Update tagging of API version

## 1.24.10

* Remove validation to allow force deal pubs to use publisher deals create

## 1.24.9

* Update tagging of API version

## 1.24.8

* Updated KC roles to be `publisher-deals` besides the deals route
* Update precision of performance logging

## 1.24.7

* Update precision of performance logging

## 1.24.6

* Add performance logging

## 1.24.5

* Connect GET /sections to newest deals-data-api route

## 1.24.4

* Updated common ci version from 3.3.0 to 5.3.5 and the related fixes

## 1.24.3

* Updated deals-data-api client version and all associated code

## 1.24.2

* Updated idm-middleware and associated dependencies

## 1.24.1

* Tagged `/dsps` as dsps

## 1.24.0

* Added GET `/dsps/:dspid/seats`

## 1.23.3

* Use inventory-groups Keycloak roles for routes specific to inventory-groups

## 1.23.1

* Fix reference to secret

## 1.23.0

* Prerequisite changes for ArgoCD
* API now accepts config files as command line argument
* Requires updated helm chart for deployment
* Updated helm chart expects kubesealed secrets

## 1.22.9

* Updated deals-data-api client to 1.10.0
* Added in new pubdeals stats route

## 1.22.8

* Moved pubisher deals route and inventory groups route into their own router groups
* Updated permissioning to put all publisher deals requests under the publisher-deals permision, not the deals permission

## 1.22.7

* Added legacy deals support for via PATCH `/publsher-deals/:dealid/`

## 1.22.6

* Fixed swagger annotation for publisher deals GET

## 1.22.5

* Handle account data service errors better

## 1.22.4

* Switch to go-client client and add client error handling

## 1.22.3

* Update publisher-deals GET to include legacyAccountId in annotations

## 1.22.2

* Update map for publisher-deals routes to include the full path

## 1.22.1

* Update GET `/publisher-deals/` to use publisher-deals-read KC role

## 1.22.0

* Added GET `/publisher-deals/`

## 1.21.0

* Merged GET `/legacy-deals/:dealID` functionality into GET `/publisher-deals/:dealID`. GET `/publisher-deals/:dealID` now returns section data for legacy deals.

## 1.20.0

* Added hot reload

## 1.19.1

* Fixed an issue where special priority and discount values are being sent as-is to Searhaack, which is out of bounds

## 1.19.0

* Add support for editing IG deals via PATCH /publsher-deals/:dealid/

## 1.18.0

* Seperate out authn-proxy

## 1.16.4

* Fix for services to through 400s instead of 500s when appropriate

## 1.16.0

* Add Inventory Groups endpoints

## 1.15.0

* Add `inventoryGroupIDs` support to `/publisher-deals` PUT

## 1.14.5

* Add GET `/sites` route

## 1.14.4

* CSV special case - if Publisher Revenue share is undisclosed, make Estimated Total Savings equal to PAD (Discount)

## 1.14.3

* Add GET `/adunits` route
* Add GET `/audiences` route
* Add GET `/countries` route

## 1.14.2

* Fixed bug - null pointer reference when Revenue Share is nil

## 1.14.1

* Fixed bug - CSV export should return XFR Fee instead of Savings
* Fixed bug - CSV export should not return XFR Fee if revenue share is undisclosed

## 1.14.0

## 1.13.1

* Reverting 1.12.1

## 1.13.0

* Add GET `/sections` route

## 1.12.0

* Added PATCH `/publisher-deals/<dealID>`
* Contacts Searhaack PATCH `/publishers/deals`

## 1.11.0

* Added GET `/dsps` route
* Increased max wait timeout for searhaack [DNA-4469]

## 1.10.0

* Add PUT /publisher-deals route

## 1.9.2

* Added Event Log Reports Controller Client
* Added Accounts Data API Client
* Added Publisher Revenue Share and XFR Data to Deal model
* Wrapped deals api calls in go routines to run concurrently

## 1.9.1

* Update swagger annotation for deals stats route

## 1.9.0

* Added publisher revenue share to the deals route
* Added xfr fee to the deals route

## 1.8.0

* Added `/sections/{sectionID}` route

## 1.7.2

* Changed `GET /deals/stats/{deal-id}` to  `GET /deals/{deal-id}/stats`

## 1.7.1

* Set seats to [] if no seats are available.

## 1.7.0

* Added `publisher-deals/{dealid}` route to get a single deal by ID

## 1.6.4

* merge master abck to devlopment to capture RC changes

## 1.6.3

* Performance Improvements
* Minor code restructuring
* Re-wrote the CSV serialization code

## 1.6.2

* Use multistage build with Go version 1.14.3
* Changed from `dep` to go modules
* Updated major version of CI pipeline

## 1.6.1

* Internal structure change, renamed entities->models, models->services, services->clients.
* Publisher deals now return a deal model object in its response (the same one as buyer).

## 1.6.0

* Updated `publishers-deals` to accept legacyUserID explicitely instead of from Keycloak
* Finalized repository pattern on `publishers-deals`

## 1.5.0

* Added `deals/stats/:internalDealID` to retrieve deals stats data

## 1.4.3

* Internal code structure changes

## 1.4.2

* Refactored `publisher-deals` and associated resources to the repository pattern

## 1.4.1

* `publisher-deals` retrieves legacy userID from keycloak
* `publisher-deals` calls Searhaack publishers/deals GET with the legacy CMSSID set by legacy bridge

## 1.4.0

* Added `publisher-deals` route with empty 200 response for users who have the Publisher role

## 1.2.1

* Added `deals-data-api` as healthcheck dependency

## 1.2.0

* Updated GET /deals to call the Deals Data API
* Updated GET /deals to expect Deals Data API to send extra seat name mapping data
* Updated GET /deals to transform the status and seats of each deal

## 1.1.0

* Added GET /deals route
* Updated idm-middleware to 1.4.0

## 1.0.0

* Created Deals Web API
* Added alerting, monitoring, and CD

