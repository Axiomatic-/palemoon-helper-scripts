# Pale Moon Helper Scripts

_... because nothing can escape the vigilant eyes of [Axiomatic-](https://github.com/Axiomatic-) :wink:_

This repository provides a set of scripts that may help Pale Moon developers and enthusiasts.

At present, it provides the following:

* Scripts and configuration files for continuous integration via Travis-CI (it is an online service for running builds from each commit pushed).
* A script for pulling HSTS preload updates from mozilla-central.

This repository may be expanded with other scripts in the future.

## Continuous integration with Travis-CI

Integrating with Travis-CI is very easy! You need log in to Travis-CI using your Github account and have to enable Travis-CI for that repository to use this.

To integrate the scripts with the source, open a terminal window and execute:

	$ git branch continuous-integration
	$ git checkout continuous-integration
	$ cp -r ../palemoon-helper-scripts/travis-ci/. .
	$ git add --all .
	$ uname | grep -Eiq 'msys|mingw' && git update-index --chmod=+x build/travis_ci/travis_ci.sh
	$ git commit -m "Enable continuous integration."
	$ git push origin continuous-integration

These builds (as of the present) will be built on a Ubuntu 12.04 x86-64 VM. On a successful build, these will be uploaded to Zippyshare.

## HSTS preload updates

The script in `hsts-preload-update/hsts-preload-update` pulls the latest HSTS preload lists from mozilla-central into the Pale Moon specific locations, and removes invalid rules from it. To use it, open a terminal window and execute:

	$ ../hsts-preload-update/hsts-preload-update
