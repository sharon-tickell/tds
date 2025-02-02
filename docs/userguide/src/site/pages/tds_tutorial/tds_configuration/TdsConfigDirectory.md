---
title: TDS Content Directory
last_updated: 2020-08-24
sidebar: user_sidebar
toc: false
permalink: tds_content_directory.html
---

## Location Of The TDS Configuration Directory

All THREDDS Data Server configuration information is stored under the TDS content directory.
The location of the directory is controlled by the `tds.content.root.path` Java system property.
There is no default location - `tds.content.root.path` **must be set or the TDS will not start**.
Please see the [Running Tomcat](running_tomcat.html) page of this tutorial for information on how to set this location.


## Layout

The content directory is created and populated with default files the first time the TDS is deployed or any time the directory is empty.
Once created, it is persistent even when the TDS installation is upgraded or re-deployed.
All your configuration, modifications, and additions should be made in this directory.
Do not place files containing passwords or anything else with security issues in this directory.
Typically, you will only be adding and modifying catalogs and configuration files.

For now, we will focus on the following subset of the content directory:

 * `${tds.content.root.path}/thredds/`
   * `catalog.xml` - the main TDS configuration catalog (root catalog for TDS configuration)
   * `enhancedCatalog.xml` - an example catalog [Note: It is referenced from catalog.xml.]
   * `threddsConfig.xml` - [configuration file](tds_config_ref.html) for allowing non-default services, configuring caching, etc.
   * `logs/`
     * `catalogInit.log` - log file for messages generated while reading TDS configuration catalogs during TDS initialization and reinitialization.
     * `threddsServlet.log` - log messages about individual TDS requests, including any error messages. 
             Useful for debugging problems.
   * `cache/` - various cache directories
     * `agg/`
     * `aggNew/`
     * `cdm/`
     * `collection/`
     * `edal-java/`
     * `ncss/`
     * `wcs/`
   * `templates/`
     * `tdsTemplateFragments.html` - user-supplied Thymeleaf HTML templates (see [Customizing TDS](customizing_tds_look_and_feel.html#thymeleaf-templates) for details).
