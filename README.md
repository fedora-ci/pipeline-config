# Configuration for CentOS Stream 9

This repository contains global configuration for c9s pipelines.

## environment

This file contains environment variables that will be available when the pipelines are running.

Example:
```
DEFAULT_TEST_PROFILE=c9s
DEFAULT_PIPELINE_TIMEOUT_MINUTES=1440
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
