---
title: Image Push Failing
layout: page
tags:
  - faq
  - builds
  - docker
category: Getting Started
redirect_from:
  - /docker/image-push-fails/
---

The **image** in `codeship-services.yml` has to match the **image_name** in `codeship-steps.yml`, like in the following example:

```yaml
- type: serial
  steps:
    - name: dockerhub_push
      service: demo
      type: push
      image_name: something/test-repo
      registry: https://index.docker.io/v1/
      dockercfg_path: dockercfg
```

Note that our **image_name** here is *something/test-repo*. This is the name of the image in `codeship-services.yml`:

```yaml
demo:
  build:
    image: something/test-repo
    dockerfile_path: Dockerfile
```

Find out more about these two files in [steps configuration]({{ site.baseurl }}{% link _pro/getting-started/steps.md %}) and [services configuration]({{ site.baseurl }}{% link _pro/getting-started/services.md %}).
