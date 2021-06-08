# Grails Wrapper

[![Build Status](https://travis-ci.org/grails/grails-wrapper.svg?branch=master)](https://travis-ci.org/grails/grails-wrapper)

## HACKETY HACK (don't talk back)

Grails is experiencing an outage with their artifactory service that requires using a non-standard URL.
Unfortunately, the standard URL is hardcoded into the grails wrapper.
See https://github.com/grails/grails-core/issues/11825#issuecomment-856250177

To get the target project to build:
```
cd $grails_wrapper_directory>;
./gradlew clean assemble;
cp wrapper/build/libs/grails4_1-wrapper-3.0.0.BUILD-SNAPSHOT.jar $target_directory/grails-wrapper.jar;
```

The grails wrapper contains a layer of indirection in `starter/build/libs/grails-wrapper.jar`.
We _don't_ use this, because this itself just pulls down the latest `wrapper/build` artifact from a remote.
