# Show GitHub Workflow Status Using A Badge

__Category: DevOps__

You can show the status of GitHub workflows by linking to a badge for the workflow action. The build status is rendered using an SVG and the text will be the same as the `name` value in the workflow action.

Link directly to the badge as follows:

```text
https://github.com/owner-name/repository-name/actions/workflows/workflow-filename.yml/badge.svg
```

To render the badge in Markdown, wrap the URL link. The following will use an alt text value of "Build".

```text
[![Build](https://github.com/owner-name/repository-name/actions/workflows/workflow-filename.yml/badge.svg)](https://github.com/owner-name/repository-name/actions/workflows/workflow-filename.yml/badge.svg)
```

__Note:__ Workflow badges in a private repository are not accessible externally and cannot be embedded or linked to from an external site.
