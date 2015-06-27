# Pale Moon Helper Scripts

_... because nothing can escape the vigilant eyes of [Axiomatic-](https://github.com/Axiomatic-) :wink:_

This repository provides a set of scripts that may help Pale Moon developers and enthusiasts.

At present, it provides a script for continuous integration via Travis-CI (it is an online service for running builds from each commit pushed). This repository may be expanded with other scripts in the future.


## Continuous integration with Travis-CI

Integrating with Travis-CI is very easy! You need to have a Travis-CI account and have to enable Travis-CI for that repository to use this.

To integrate the scripts with the source, open a terminal window and execute:

	$ git branch continuous-integration
	$ git checkout continuous-integration
	$ cp -r ../palemoon-helper-scripts/travis-ci/. .
	$ git add --all .
	$ uname | grep -Eiq 'msys|mingw' && git update-index --chmod=+x build/travis_ci/travis_ci.sh
	$ git commit -m "Enable continuous integration."
	$ git push origin continuous-integration

These builds (as of the present) will be built on a Ubuntu 12.04 x86-64 VM. On a successful build, these will be uploaded to Zippyshare.
