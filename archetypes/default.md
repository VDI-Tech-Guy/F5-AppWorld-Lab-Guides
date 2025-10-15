---
title: "{{ replace .Name "-" " " | title }}"
# The subtitle displays directly underneath the heading of a given page
nd-subtitle: 
# layout: used when specifying `--kind` 
layout: "default"
# Weights are assigned in increments of 100: determines sorting order
weight: i00
# Creates a table of contents and sidebar
toc: true
# Set to true to show content here on the landing page. This is only for files with custom content for their landing page (aka _index.md)
nd-landing-page: false
---

[//]: # "This is a markdown comment: it won't appear in the final website"

<!-- To use this archetype, run the following command, replacing path/filename with the path and name of the file:

hugo new path/filename.md

To use a specific archetype add the `--kind` flag and the layout name. For example:

hugo new --kind otherArchetype path/filename.md

For further clarification the following will create a new directory, Lab1, with the file _index.md with the content from the default archetype.

hugo new Lab1/_index.md`

You can view more on archetypes in the Hugo Documentation at https://gohugo.io/content-management/archetypes/
 -->

{{< important >}}
This content is built by the F5 Business Development organization. New content will be added periodically to provide additional automation scenarios. Please open a GitHub issue for any new feature requests.
{{</ important >}}

## Overview

The use case templates are built for the F5 environment. These use cases can be adapted to any environment. Feel free to take, fork, or expand upon this code!

{{< call-out sideline="true" title="Audience" >}}
This lab is intended for learners who want a hands-on introduction. 
{{</ call-out >}}

{{< call-out title="Users will be able to" >}}

- Understand the differences between X and Y automation.
- Test common deployment scenarios using X coding and compare them with their Y counterparts.
- Test deployments with Z Automation Platform.

{{</ call-out >}}

## Before you begin
Before starting this lab ensure you have the following prerequisites:

- Up-to-date Git installation
- VS Code 
- F5 BIG-IP Client

{{< call-out "caution" >}}
Make sure to check that your Git version is above V2.50 with `git -v`
{{</ call-out >}}

{{< card-section >}}
    {{< card title="Recommended" titleUrl="https://github.com/git-guides/install-git" icon="code" >}}
        How to install Git
    {{</ card >}}
    {{< card title="Optional" titleUrl="https://clouddocs.f5.com/training/community/automation/html/class10/class10.html" >}}
        Similar labs for reference
    {{</ card >}}
{{</ card-section >}}

## Schedule

Estimated time: 60–90 minutes

| Activity | Time |
| -------- | ----:|
| Intro / Setup | 10 min |
| Hands-on exercises | 40–60 min |
| Wrap-up | 10 min |

## Lab steps

Follow the steps below. Use the tabs to show platform-specific commands or notes.

{{< tabs name="Steps" >}}

{{%tab name="Linux / macOS" %}}

**Prepare your environment**:

```shell
# Example: clone the repo and change directory
git clone https://example.com/your-repo.git
cd your-repo
```

**Run the sample**:

```shell
./run-lab.sh --option value
```

{{%/tab%}}

{{%tab name="Windows" %}}

**Prepare your system** (PowerShell):

```powershell
git clone https://example.com/your-repo.git
Set-Location your-repo
```

**Run the sample**:

```powershell
.\\run-lab.ps1 -Option value
```

{{%/tab%}}

{{</ tabs >}}

## Example configuration

Below is a minimal example configuration used in the lab.

```yaml
# example-config.yaml
service:
	name: example
    replicas: 2
```

## Troubleshooting & support

If you run into problems, try the following:

- Verify network connectivity.
- Check logs in /var/log or the service logs.

{{< call-out sideline="true" title="Support" >}}
For instructor or platform support, please contact a F5 Account Manager or Sales Engineer at F5.
{{</ call-out >}}

## Additional resources

- Link to product docs
- Link to related labs

[//]: # "This is an example image"
{{< img src="F5_logo.png" grid="first-third" >}}

## Appendix

Optional tables, advanced tips, or reference commands.
- There is an optional table shortcode if the content does not look correct with the default styling.

{{< table >}}
| Item | Notes |
| ---- | ----- |
| Config location | /etc/example/config.yaml |
{{</ table >}}

