---
title: "{{ replace .Name "-" " " | title }}"
# layout: used when specifying `--kind` 
layout: "default"
# Weights are assigned in increments of 100: determines sorting order
weight: i00
# Creates a table of contents and sidebar
toc: true
# Set to true to exclude from build and server unless `--buildDrafts` or `hugo serve -D` are used
draft: true
---

[//]: # "This is a markdown comment it won't appear in the final website"

<!-- To use this archetype, run the following command, replacing path/filename with the path and name of the file:

hugo new path/filename.md

To use a specific archetype add the `--kind` flag and the layout name. For example:

hugo new --kind otherArchetype path/filename.md

You can view more on archetypes in the Hugo Documentation at https://gohugo.io/content-management/archetypes/
 -->

## Overview

The use case templates are built for the F5 environment. These use cases can be adapted to any environment. Feel free to take, fork, or expand upon this code!

{{<call-out sideline="true" title="Audience">}}
This lab is intended for learners who want a hands-on introduction. 
{{</call-out>}}

{{<call-out title="Users will be able to">}}

- Understand the differences between X and Y automation.
- Test common deployment scenarios using X coding and compare them with their Y counterparts.
- Test deployments with Z Automation Platform.

{{</call-out>}}

## Prerequisites
Before starting this lab ensure you have the following prerequisites:

- Up-to-date Git installation
- VS Code 
- F5 BIG-IP Client

{{<caution>}}
Make sure to check that your Git version is above V2.50 with `git -v`
{{</caution>}}

{{<card-section>}}
    {{<card title="Recommended" titleUrl="https://github.com/git-guides/install-git" icon="code">}}
        How to install Git
    {{</card>}}
    {{<card title="Optional" titleUrl="https://clouddocs.f5.com/training/community/automation/html/class10/class10.html">}}
        Similar labs for reference
    {{</card>}}
{{</card-section>}}

## Schedule

Estimated time: 60–90 minutes

| Activity | Time |
| -------- | ----:|
| Intro / Setup | 10 min |
| Hands-on exercises | 40–60 min |
| Wrap-up | 10 min |

## Lab steps

{{<important>}}
This content is built by the F5 Business Development organization. New content will be added periodically to provide additional automation senarios. Please open a github issue for any new feature request.
{{</important>}}

Follow the steps below. Use the tabs to show platform-specific commands or notes.

{{<tabs name="Steps">}}

{{%tab name="Linux / macOS" %}}

1. Step 1 — prepare your environment.

```bash
# Example: clone the repo and change directory
git clone https://example.com/your-repo.git
cd your-repo
```

2. Step 2 — run the sample command.

```bash
./run-lab.sh --option value
```

{{%/tab%}}

{{%tab name="Windows" %}}

1. Step 1 — prepare your system (PowerShell):

```powershell
git clone https://example.com/your-repo.git
Set-Location your-repo
```

2. Step 2 — run the sample:

```powershell
.\\run-lab.ps1 -Option value
```

{{%/tab%}}

{{</tabs>}}

## Example configuration

Below is a minimal example configuration used in the lab.

```yaml
# example-config.yaml
service:
	name: example
	replicas: 2
```

## Troubleshooting & Support

If you run into problems, try the following:

- Verify network connectivity.
- Check logs in /var/log or the service logs.

{{<call-out sideline="true" title="Support">}}
For instructor or platform support, please contact a F5 Account Manager or Sales Engineer at F5.
{{</call-out>}}

## Additional resources

- Link to product docs
- Link to related labs

[//]: # "This is an example image"
{{<img src="F5_logo.png" grid="first-third">}}

## Appendix

- Optional tables, advanced tips, or reference commands.

{{<table variant="narrow">}}
| Item | Notes |
| ---- | ----- |
| Config location | /etc/example/config.yaml |
{{</table>}}

