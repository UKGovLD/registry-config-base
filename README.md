# registry-config-base

Provides configuration, UI templates and bootstraping for a starting registry installation.

Custom installations can fork this repository then customize the configuration and UI files. This makes it possible to pull in an merge upstream UI fixes made in this base repository.

N.B. Requires registry-core 0.1.1 or higher

## Layout

Directory | Role
---|---
`ldregistry` | A starting set of configuration files and templates which should be install in `/opt/ldregistry` on the target system. For details of the role of these files see [Configuration](https://github.com/UKGovLD/registry-core/wiki/Configuration)
`install` | Files used to configure the front end nginx proxy
`scripts` | Example installation scripts

## Customizing the configuration

The base configuration is based on the UK Government Environment registry. 

Files in `ldregistry` which make require customization are:

File | Role
---|---
`templates` | Velocity templates which implement the registry UI, particular targets for customization are ...
`templates/about.vm` | Provides descriptive information on the registry instance
`templates/header.vm` | Customize included style sheets and default page title
`templates/main.vm` | Customize landing page including main title
`ui` | Style sheets and associated javascript and images, the ones here are based on bootstrap3
`boot` | Initial register contents
`config` | Configuration files for the registry instance see [Configuration](https://github.com/UKGovLD/registry-core/wiki/Configuration)

## Change notes

A substantial restructuring of the UI templates and assets is underway. The key changes are noted here:

   * Moved UI assets to subdirectory `ui/assets`. This makes it easier to configure the front end web serve to serve the static assets directly, with only the ui templates being served from tomcat.

   * Updated default look and feel to be more consistent with, but not infringe, gov.uk styling.

   * Restructure the UI templates to split into smaller, more maintanable parts with more consistent naming convention. 
   