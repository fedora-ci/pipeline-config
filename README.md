# Configuration for Fedora CI Pipelines

This repository contains global configuration for Fedora CI pipelines.

## environment

This file contains environment variables that will be available when the pipelines are running.

Example:
```
FEDORA_CI_RAWHIDE_RELEASE_ID=f35
FEDORA_CI_PAGURE_DIST_GIT_URL=https://src.fedoraproject.org
```

The file can contain comments -- lines starting with `#` will be ignored.

## topics-mapping.json

This file contains mapping between artifact types and messaging topics.

Example:
```
...
    "koji-build": {
        "test": {
            "queued": "org.centos.prod.ci.koji-build.test.queued",
            "running": "org.centos.prod.ci.koji-build.test.running",
            "complete": "org.centos.prod.ci.koji-build.test.complete",
            "error": "org.centos.prod.ci.koji-build.test.error"
        }
    },
...
```

The example above tells pipelines that, for `koji-build` artifacts, "test is running" messages should be sent to the `org.centos.prod.ci.koji-build.test.running` topic.
