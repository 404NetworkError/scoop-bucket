# 404NetworkError's Scoop Bucket

[![Tests](https://github.com/404NetworkError/scoop-bucket/actions/workflows/ci.yml/badge.svg)](https://github.com/404NetworkError/scoop-bucket/actions/workflows/ci.yml) [![Excavator](https://github.com/404NetworkError/scoop-bucket/actions/workflows/excavator.yml/badge.svg)](https://github.com/404NetworkError/scoop-bucket/actions/workflows/excavator.yml)

Template bucket for [Scoop](https://scoop.sh), the Windows command-line installer.

## How do I install these manifests?

After manifests have been committed and pushed, run the following:

```pwsh
scoop bucket add 404NetworkError https://github.com/404NetworkError/scoop-bucket
scoop install 404NetworkError/<manifestname>
```

## How do I contribute new manifests?

To make a new manifest contribution, please read the [Contributing Guide](https://github.com/ScoopInstaller/.github/blob/main/.github/CONTRIBUTING.md) and [App Manifests](https://github.com/ScoopInstaller/Scoop/wiki/App-Manifests) wiki page.


----

###### Note: This bucket is a mixture of portable and non-portable applications.
