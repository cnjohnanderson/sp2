## Synopsis

This a guide to be followed for widgetizing. Each section below is something we need to consider while widgetizing.

***

## Widgets

**Widgets available now:**

* [Approval Cards](https://github.com/platform-experience/serviceportal-widget-library/tree/master/approve-card)

* [Feedback Card](https://github.com/platform-experience/serviceportal-widget-library/tree/master/pe-feedback-card)

* [People Info](https://github.com/platform-experience/serviceportal-widget-library/tree/master/people-card/pe-people-info)

* [Scratch Pad](https://github.com/platform-experience/serviceportal-widget-library/tree/master/pe-scratch-pad)

* [Timelines](https://github.com/platform-experience/serviceportal-widget-library/tree/master/timeline/)

* [Tabs Selector](https://github.com/platform-experience/serviceportal-widget-library/tree/master/tabs)

* [Donut Charts](https://github.com/platform-experience/serviceportal-widget-library/tree/master/donut-widgets)

* [Horizontal Stacked Bar](https://github.com/platform-experience/serviceportal-widget-library/tree/master/pe-horizontal-stacked-bar)

**Snippets available now:**

* [Inbox](https://github.com/platform-experience/serviceportal-widget-library/tree/master/pe-emp-exp-inbox-snippet)

* [Status Card Snippet](https://github.com/platform-experience/serviceportal-widget-library/tree/master/pe-status-card-snippet)

* [Employee Experience Overview Card Snippet](https://github.com/platform-experience/serviceportal-widget-library/tree/master/pe-emp-exp-overview-card-snippet)

* [Employee Experience Signature Modal Snippet](https://github.com/platform-experience/serviceportal-widget-library/tree/master/pe-emp-exp-signature-modal-snippet)

* [Employee Experience Services List Snippet](https://github.com/platform-experience/serviceportal-widget-library/tree/master/pe-emp-exp-services-list-snippet)

* [Cloud Sprawl Summary Data Snippet](https://github.com/platform-experience/serviceportal-widget-library/tree/master/pe-cloud-sprawl-vm-summary-snippet)

* [Cloud Sprawl Overview Snippet](https://github.com/platform-experience/serviceportal-widget-library/tree/master/pe-cloud-sprawl-overview-snippet)

* [Tier Overview Snippet](https://github.com/platform-experience/serviceportal-widget-library/tree/master/pe-cloud-sprawl-tier-overview-snippet)

* [Tab Chart Selector Snippet](https://github.com/platform-experience/serviceportal-widget-library/tree/master/tabs/pe-cloud-sprawl-tab-with-donut-chart-snippet)

***

## Update Set

**Please make sure you capture widget related updates correctly.** update set should start with prefix **pe-** and end with **update-set**. For example ***pe-approval-card-update-set.u-update-set.xml**. Make sure you don't capture widget instance related records/ grid related records like row, column etc. Keep the update set clean and capture on widget related stuff.

***

## Widget Name

All widget name should start prefix **PE**, this will help in searching widgets easy.

***

## Widget ID Naming

Widgets and Pages IDs need to be unique in an instance, we need to take care while naming ID's to avoid collisions when Widget or Page is being loaded into instance or while committing an Update Set, or when an Upgrade or Plugin is applied. Thus we need to keep these points in mind.

1. Every Widget must have an ID
2. IDs should be hyphenated alphanumeric strings (i.e. no spaces, no special characters)
3. The ID of all Widgets developed/created for widget library should start with prefix **pe-**

Ex: **pe-approval-card**

***

## SASS Variables

All SASS variables created for this project will start with prefix **$pe-**. You can add the variables at the Theme level as well as at the widget level.
While adding the variable at widget level make sure you use **!default** keyword. This will let us override these variables at the theme level. This will make the widget self-contained. We can easily drag and drop them on to any page.

For Ex at Theme level:

`$pe-brand-success: #5cb85c;`

For Ex at Widget level:

`$pe-brand-success: #5cb85c !default;`

***

## List of SASS variables defined so far

`$pe-brand-primary:         #337ab7;`

`$pe-brand-success:         #5cb85c;`

`$pe-brand-info:            #5bc0de;`

`$pe-brand-warning:         #f0ad4e;`

`$pe-brand-danger:          #d9534f;`

`$pe-brand-text-color-primary: 	#a8abaf;`

`$pe-brand-text-color-secondary: #fff;`

`$pe-brand-text-size-small: 12px;`

`$pe-brand-text-size-medium: 18px;`

`$pe-brand-text-size-big: 24px;`

`$pe-brand-text-size-normal: 16px;`

`$pe-timeline-items-color: #ff6f00;`


**plan to add following variables:**

`$pe-brand-secondary`

`$pe-icons-color`


*etc.*

## Includes (JS, CSS, etc.)

Even the includes with standard FWs should be renamed with prefix **pe-**. This to avoid duplication errors during the import of the update set in existing instances.

For instance:

`highcharts-ng`

should be renamed to:

`pe-highcharts-ng`


## Folder and File Naming Convention

1. Create a folder with widget name for ex: **pe-people-card**
2. Create another folder called **widget** inside the above folder.
3. Widget record fields should go inside **widget** folder. Fields must be named as follows

* HTML->               `<widget-name>.u-body-html-template.html`

* Client Controller->  `<widget-name>.u-client-script.js`

* Server Script->      `<widget-name>.u-server-script.js`

* CSS->                `<widget-name>.u-css.scss`


4. UI Scripts should go inside a folder called **ui-script** , all ui scripts should be named as follows

* `<widget-name>-<purpose>.u-client-script.js` .. some purspose examples can be **service**, **factory**, **module**

If its a js library file, which users dont need to edit for ex: "highcart-ng", emit this **u-client-script** part in name. This will make sure we dont pull the huge library files from SNOW.

5. Style Sheets should go inside a folder called **style-sheet** , all stylesheets should be named as follows.

* `<widget-name>-<purpose>.u-css.scss`

If its a css library file, which users dont need to edit for ex: "animates.css", emit this **u-css** part in name. This will make sure we dont pull the huge library files from SNOW.

6. Angular Providers should go inside a folder called **angular-provider** , all providers should be named as follows

* `<widget-name>-<purpose>.u-client-script.js`

7. Angular Templates should go inside a folder called **angular-template** , all ui scripts should be named as follows

* `<widget-name>-<template-id>.u-body-html-template.html`

8. Script Includes should go inside a folder called **script-include** , all these scripts should be named as follows

* `<widget-name>-<purpose>.u-client-script.js`

9. Update Sets must be named as follows

* `<widget_name>.u-update-set.xml`

## Internationalization

All Widgets should support [Internationlization](https://docs.servicenow.com/bundle/istanbul-servicenow-platform/page/build/service-portal/concept/c_WidgetLocalization.html), so that they can be translated into other languages in non-English speaking markets.