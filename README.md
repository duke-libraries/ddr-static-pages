# ddr-static-pages
ddr-static-pages contains configurations, template overrides, and assets (images and stylesheets) for static page content in the Duke's Digital Repository.


## Syncing with DDR-Public

DDR-Public has rake tasks to sync with the latest version of ddr-static-pages. To update DDR-Public with the master branch of ddr-static-pages run the following rake command in DDR-Public:

```sh
$ rake ddr_public:ddr_static_pages:sync
```

You can specify a branch of ddr-static-pages by adding an environmental variable to the command:

```sh
$ rake ddr_public:ddr_static_pages:sync BRANCH=develop
```

## Configuring a Static Page

A static page configuration comprises a template file named for the page that contains yml files that set configurations for the page as well as a directory structure for view partial overrides.

The directory structure generally looks like following:

```
ddr-static-pages/
        views/
                the-static-page-template.html.erb  

        assets/
                images/
                        ddr-static-pages/
                        # include any used images here
                stylesheets/
                        ddr-static-pages/
                        # include any used scss files here - note that inheritance order of files is not able to be set

        **static_pages_doc_configs.yml


development:
  <<: *defaults

test:
  <<: *defaults

production:
  <<: *defaults
```

### portal_view_configs.yml

Should I use this to configure the routes somehow?
(homepage, etc?)

development:
  <<: *defaults

test:
  <<: *defaults

production:
  <<: *defaults
```
