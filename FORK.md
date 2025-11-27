To fork this Git repo and publish your own Home Assistant Add-on repo:

* Fork this Git repo in GitHub.

# TODO: do all of this in an update script
* Edit `nut-latest/config.yaml` and update the `url` and `image` fields.
  The `image` value must be lowercase.
* Edit `nut-latest/DOCS.md`:
  * Update the URL in step 1 of the "Installation" instructions.
  * Update `repository_url` parameter within the `addon-inst` URL.
  * Update the repository hash value in the `addon` parameter within the `addon-inst` URL.
    To calculate the new hash value, use one of the following:
    * `python` followed by `url = 'https://github.com/PaulSD/addons-nut'` (substitute your Git repo
      URL) followed by `import hashlib ; hashlib.sha1(url.lower().encode()).hexdigest()[:8] ; exit()`
      followed by `exit()`.
    * In a BASH shell, run `URL='https://github.com/PaulSD/addons-nut'` (substitute your Git repo
      URL) followed by ``.
      echo -n 'https://github.com/PaulSD/addon-nut-latest' | tr '[:upper:]' '[:lower:]' | sha1sum | cut -c -8
  * Update the `github-issue` and `contributors` URLs.
* Edit `nut-latest/Dockerfile` and update the `maintainer` and `org.opencontainers.image.authors`
  fields.
