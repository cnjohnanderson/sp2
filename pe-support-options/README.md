# Support Options

## Description

This can be used to quickly craft a configurable widget with a list items fed from a catalog.

## Screenshots
![](../images/pe-support-options-1.png)

## Additional Information/Notes

Uses ServiceNow® [Service Catalog](https://docs.servicenow.com/bundle/istanbul-it-service-management/page/product/service-catalog-management/concept/c_ServiceCatalogManagement.html)

---
## Installation
---
Download and install update set **[pe-support-options.u-update-set.xml](https://github.com/platform-experience/serviceportal-widget-library/blob/master/pe-support-options/pe-support-options.u-update-set.xml)** <br/><br/>
After installation, the widget can be accessed via the `Service Portal > Widgets` section for use and customization.<br/>
* SN Product Documentation - ['Load a customization from a single XML file'](https://docs.servicenow.com/bundle/istanbul-application-development/page/build/system-update-sets/task/t_LoadCustomizationsFromAnXMLFile.html)

---
## Configuration
---
Widget Option Schema parameters:

**"Title"** This is for changing the title.  `Default: Support Options`<br/>
**"Category"** This is for defining a category  `Default: PE Support Options`<br/>
**"Items"** This is for defining the item or items to display from the category using a comma separated list. For example: sc_cat_item.icon, sc_cat_item.name, etc.  `Default: sc_cat_item.name, sc_cat_item.icon, sc_cat_item.short_description`<br/>

---
## Platform Dependencies
---
### SN System Tables
* sc_cat_item
* sc_category
---
## Sample Data and Data Structures
---
> See 'Configuration' above
---
## API Dependencies
---
<i>Dependencies are included and configured as part of the provided Update Set.</i>
> None
---
## CSS/SASS Variables
---
_CSS/SASS variables are given default values that can be overridden with theming or portal-level CSS._
> None