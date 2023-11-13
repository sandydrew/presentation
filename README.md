# Driving Hybrid Success At Toyota

## The problems

* Sitecore 9.2 - long in the tooth, rich-text everywhere. Increasingly difficult to maintain.
* Typical Sitecore setup with large infrastructure footprint to support a highly trafficked site.
* No search

## The plan

* Move to Sitecore headless with NextJS
* Sitecore composable
   - OrderCloud
   - Discover
   - Sitecore Search
* 

## The results

### The Architecture
* Sitecore - NextJS - BFF
* BFF - OrderCloud - Discover - MongoDB


### Sitecore Headless
* Pure CMS - no cruft, just content (and a little bit of config)
* No custom code
* Sitecore first dev
  - Create the templates and handover to FE devs
  - FE devs using the CI environment for local development
  - Ensuring that the FE components expect the unexpected
    - No datasource
    - Experience editor mode
    - Null fields
    - Removed fields
* NextJS Preview pipelines
   - increases issues found in PRs
   - reduces rework
* Tricky bits
   - SSG caching headers (1 year)

### The BFF
* Orchestrates data across multiple systems
* Validation for FE submissions
* Caching
* Minimal processing

### Discover
* The good bits
   - faceting and filtering
   - boosting and burying
   - tracking for analysis/optimisation (screenshot popular)
* The tricky bits
   - ingestion via SFTP, CSV with JSON fields
   - geo-search

### OrderCloud
* The good bits
   - Opinionated - in a good way
   - Headless APIs, consistent across all objects

* The tricky bits
   - 8K xp object limit
   - Staging environment restores