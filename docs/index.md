# Release tagger for GitHub workflows

In GitHub actions, the major version tags should be automatically updated when
there is a new release so that major version referenced in workflows can use
the latest version.

The recommendation is to
[update only the major tag](https://github.com/actions/toolkit/blob/main/docs/action-versioning.md).

This workflow updates the major tag when there is a minor or a patch release.

## Usage

The workflow can be used by adding the following file to `.github/workflows`:

```yaml title=".github/workflows/update-major-tag.yaml"
name: Update major release tag

on:
  release:
    types: [published]

jobs:
  update-major-tag:
    uses: coopnorge/github-workflow-release-tagger-for-github-workflows/.github/workflows/release-tagger-for-github-workflows.yaml@v0
    with:
      tag-name: ${{ github.event.release.tag_name }}
    secrets:
      GH_TOKEN: ${{ secrets.GITHUB_TOKEN }}
    permissions:
      contents: write
```

If you are using the inventory to create a GitHub workflow template, the file
above is included.
