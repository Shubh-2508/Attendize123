---
title: Install MegaLinter on Bitbucket Pipelines
description: Manual instructions to setup MegaLinter as a Bitbucket Pipelines job
---
<!-- markdownlint-disable MD013 -->
<!-- @generated by .automation/build.py, please don't update manually -->
<!-- install-bitbucket-section-start -->

# Bitbucket Pipelines

1. Create a `bitbucket-pipelines.yml` file on the root directory of your repository

2. Copy and paste the following template or add the step to your existing pipeline.

```yaml
image: atlassian/default-image:3
pipelines:
  default:
    - parallel:
      - step:
          name: Run MegaLinter
          image: oxsecurity/megalinter:v6
          script:
            - export DEFAULT_WORKSPACE=$BITBUCKET_CLONE_DIR && bash /entrypoint.sh
          artifacts:
            -  megalinter-reports/**
```


<!-- install-bitbucket-section-end -->