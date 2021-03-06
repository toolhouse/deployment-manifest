# Deployment Manifest

![GitHub release](https://img.shields.io/github/release/toolhouse/deployment-manifest.svg) [![Go Report Card](https://goreportcard.com/badge/github.com/toolhouse/deployment-manifest)](https://goreportcard.com/report/github.com/toolhouse/deployment-manifest) [![codebeat badge](https://codebeat.co/badges/0c41e0d2-9cdd-4388-9bbb-0d431c6cb3e8)](https://codebeat.co/projects/github-com-toolhouse-deployment-manifest-master) [![license](https://img.shields.io/github/license/toolhouse/deployment-manifest.svg)](https://github.com/toolhouse/deployment-manifest/blob/master/LICENSE)

A simple method to query information about the deployed version of a site or
application. This is accomplished by providing a JSON deployment manifest that
includes the version control system (typically git) commit id and reference
(branch or tag) from which an application/site was built. (We also recommend
including additional fields which may be useful for inspection by additional
tools and by humans.) 

## Why?

This was developed with two primary use-cases in mind:

- As part of post-deployment tests within a CI/CD pipeline to verify the
  desired version of an application has been successfully deployed.
- Provide the ability to easily and quickly inspect (manually or through tools)
  the currently deployed version of an application in any environment.

## Deployment Manifest Specification

```json
{
    "commit": "052b2762382f956c378c99aa626ca8faf3d76562",
    "ref": "1.1.3",
    "date": "Tue May 9 22:01:14 GMT 2017",
    "pipelineId": "764"
}
```

## Tools

This repository includes the following tools for working with deployment
manifests:

- [`verify-deployment-manifest`][verify] - Validate that the expected commit/
  ref is deployed to an environment by checking a deployment manifest for
  expected versions.

- [`deployment-badge-server`][badge] - Show SVG badge with deployment
   information, suitable for including in a README or wiki page. 

[verify]: ./cmd/verify-deployment-manifest/
[badge]: ./cmd/deployment-badge-server/
