---
title: Using Stencil Groups
lead: "How to define and use StencilGroups and StencilGroup rules"
---

## How to define a StencilGroup

{% callout type="info" title="What are StencilGroups?" %}
 If you aren't already familiar with the concept of StencilGroups, they are [explained here](/docs/skycap/formations-stencils-and-snapshots#what-are-stencil-groups). 
{% /callout %}

To define a StencilGroup click on the New Group button on the Formation detail page. This will open a form with three fields: Name, Tags and Rules. 

Name and Tags should be self explanatory. Rules are JSON objects that determine what's included in or excluded from your StencilGroup. For example the following rule, includes any Stencil named `setup.yml` in this group:

```json
	{
		"include" : ["name:setup.yml"]
	}
```

...while the following rule includes any Stencil with the `production` tag in the group:

```json
	{
		"include" : ["tag:production"]
	}
```

## More about StencilGroup rules

Each StencilGroup JSON object (rule) must start with **one** of two possible keys: `"include"` or `"exclude"`. Each object (rule) is a JSON array of strings, each selecting Stencils by `name` or `tag`.

To select Stencils by name use the `name:foo.yml` format and to select Stencils by tag, use the `tag:foo` format. Selectors can be used together (as ANDs) separated by commas: `["name:foo.yml", "name:bar.yml", "tag:fuzz", "tag:buzz"]`

If both `include` and `exclude` keys exist, the list of Stencils is selected by first applying the `include` selectors and then removing the `exclude` ones.

Here is an example of a complete StencilGroup rule:

```json
	{
		"include" : ["name:setup.yml", "tag:config"],
		"exclude" : ["tag:test", "tag:qa", "name:deployment.yml"]
	}
```

As you can see, this includes the base set up for the application along with all its configurations, but excludes all the components tagged as "test" and "qa" as well as the Kubernetes Deployment definition.

## Rendering StencilGroups

After you have defined a StencilGroup, you can click on the cog icon for that group at the top of the Formation detail page, and then click "Render group".

Once you have rendered the group you can apply it to your Kubernetes cluster(s) as needed by either downloading the stencils or by using Cloud 66 Toolbelt.

{% callout type="info" title="Learn how to use Formations" %}
 If you need help using Formations with your cluster, check out our "[Getting Started with Skycap Formations](/docs/skycap/using-formations)" guide. 
{% /callout %}
