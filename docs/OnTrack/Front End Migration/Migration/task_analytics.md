# OnTrack Component Review

## Team Member Name

### Pasindu Fernando

### Student ID : 
s224263102

## Component Name
Analytics Configuration (virtual page views)

### Files in this Component
analytics.coffee (to be removed)

## Description

The analytics.coffee file was previously responsible for configuring Google Analytics tracking in the AngularJS version of the application. Its key functionality included disabling automatic route change tracking by setting ``` $analyticsProvider.virtualPageviews(false) ```, preventing virtual pageviews from being recorded.

## Why Removal is Required

It is no longer functional due to the migration to Angular 17.

All analytics functionality has been migrated to Google Analytics 4 (GA4), which is fully managed through gtag.js in index.html.

Virtual pageviews and event tracking are now handled explicitly using Angular’s Router and manual event tracking with gtag().


# How Has This Been Tested?

Monitoring Network Activity (Before and After Removing analytics.coffee): there is no change in the network activity ( Browser developer tools-> network tab-> filter the keyword "google"), before and after removing analytics.coffee since tracking is now fully handled by gtag.js in index.html.

Modifying virtualPageviews to True/False : No visible change in pageview tracking behavior, indicating that analytics.coffee is no longer controlling analytics.

## Screenshots
before commenting analytics.coffee file and depenency in config.coffee

![before commenting analytics.coffee file and depenency in config.coffee](https://github.com/user-attachments/assets/6e10e0c3-0962-4cad-9988-b8d08d54b4a6)

After commenting analytics.coffee file and depenency in config.coffee
![after commenting analytics.coffee file and ddepenency in config.coffee](https://github.com/user-attachments/assets/176f026b-806e-4b21-bcc5-8ab493f93fc9)


## Testing Checklist:

- [x] Tested in latest Chrome
- [ ] Tested in latest Safari
- [x] Tested in latest Firefox

# Checklist:

- [x] My code follows the style guidelines of this project
- [x] I have performed a self-review of my own code
- [ ] I have commented my code in hard-to-understand areas
- [ ] I have made corresponding changes to the documentation
- [x] My changes generate no new warnings
- [ ] I have requested a review from ... on the Pull Request

## Component Migration Plan:

1. Remove the File:analytics.coffee


2. Clean Up Dependencies:
    Remove doubtfire.config.analytics from config.coffee.
    Delete any references to angulartics or $analyticsProvider in doubtfire-angularjs.module.ts.

