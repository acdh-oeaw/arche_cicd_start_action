# ARCHE CI/CD Start Action

Packs in one action all the steps done at the beginning of an ARCHE microservices build, test and redeploy GitHub workflow:

* checkout the repo
* set up PHP version with extensiont
* run the static code analysis with the phpstan
* run tests with the phpunit
* create direct database connection config files for ARCHE production and curation instances
* clean up after tests

Use with something like:

```yaml
- uses: acdh-oeaw/arche_cicd_start_action@main
  with:
    phpVersion: 8.3 # the default
    phpExtensions: mbstring,json,yaml,pdo,pdo_sqlite,pdo_pgsql # the default
    phpCoverage: xdebug # the default
    phpstanLevel: 6 # the default, 0 to skip
    phpstanPaths: src index.php # the default
    phpunit: true # the default
    prepareRepoConfig: false # the default
```

most probably:

```yaml
- uses: acdh-oeaw/arche_cicd_start_action@main
  with:
    phpExtensions: whatever you need
    prepareRepoConfig: true
```
