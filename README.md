# ARCHE CI/CD Finish Action

Packs in one action all the steps done at the end of an ARCHE microservices build, test and redeploy GitHub workflow:

* login into the docker hub
* push the image into the docker hub
* redeploy the image on the ACDH cluster
* push the code coverage logs to the coveralls

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
