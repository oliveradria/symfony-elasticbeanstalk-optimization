# Symfony + AWS ElasticBeanstalk Optimization

Some files that help me optimize a Symfony (currently version 3.3) + with ElasticBeanstalk setup.

## Deployment

* Copy the `.ebextensions` folder.
  * The container commands in `.ebextensions/app.config` (which is read automatically when deploying
    with ElasticBeanstalk) copies the files. Modify the files as necessary.
  * `enable_mod_deflate.conf` enables compression in the server (compresses many files on the way
     to the browser).
  * `enable_browser_caching.conf` enables basic caching for the browser (e.g. so your users can
     see pages faster, since it saves the already used files in the browser).
  * `redirect_https.config` Use this file if you want to always redirect to https.
  * `symfony.config` sets up the Symfony stuff (e.g. migrations, clearing cache; read file for
     details on permissions)
