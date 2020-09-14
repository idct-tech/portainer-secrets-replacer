portainer-secrets-replacer
==========================

Simple Bash script which allows to replace portainer secrets in a config file.

usage
=====

In case you have your secrets in a folder called `/run/secrets` wher each secret
is stored in a different file - for example:

* `/run/secrets/USERNAME`
* `/run/secrets/OTHER_SECRET`

and your config file is stored in `/app/my_config.json` then by calling:
```
./psr-replace /app/my_config.json /run/secrets
```

you will replace all encounters of `{SECRET_USERNAME}` and `{SECRET_OTHER_SECRET}`
with the contents of respective files.

As you may have noticed secrets need to have the `SECRET_` prefix.

installation
============

in your docker file be sure to download the replacer into your image:
```
curl