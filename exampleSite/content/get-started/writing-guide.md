---
title: Guidelines for writing guides
linkTitle: Write a  guide
description: Learn how to write guides for pure-hugo.
---

This guide provides instructions and best practices for writing tutorial-style
usage guides that help users achieve specific goals. These guides
will be featured in the [guides section](/guides/_index.md) of your website,
alongside any other content.

The documentation is written in Markdown, with YAML front matter for metadata.
We use [Hugo](https://gohugo.io) to build the website.

## Purpose of the guides

The usage guides aim to:

- Educate users on a specific topic.
- Provide explanations through step-by-step tutorials.

## Metadata for guides

Each guide must include a metadata section at the beginning of the document.
This metadata helps users discover and filter guides based on their interests
and needs.

### Example metadata format

```yaml
---
title: How to secure your Linux operating system.
linkTitle: Secure linux
description: Learn how to secure your Linux operating system step-by-step.
summary: |
  This guide walks you through the steps to secure your operating system.
  It assumes you are using Arch Linux (but any Linux system can be used)
tags: [linux, security]
languages: [bash]
params:
  time: 30 minutes
---
```

### Metadata fields

- `title` (required): The main title of the guide in sentence case.
- `linkTitle` (optional): A shorter title used in navigation menus.
- `description` (required): A concise description for SEO purposes.
- `summary` (required): A brief overview of the guide's content.
- `languages` \* (optional): List of programming languages used.
- `tags` \* (optional): Domains or subject areas covered.
- `params`
  - `time` (optional): Estimated reading or completion time.

\* Do apply at least one of the `languages` or `tags` taxonomies. The values
are used to associate the page with the filter options on the guides landing
page.

## Guide document structure

All guides live directly under the `content/guides/` directory in the
repository. Guides can either be a single page or multiple pages. In the
case of multi-page guides, every page is a step in a sequential workflow.

If you're creating a single-page guide, create a single markdown file in the
guides directory:

```bash
# Create the file
touch content/guides/my-pure-guide.md
# or if you have Hugo installed:
hugo new content/guides/my-pure-guide.md
```

To create a multi-page guide, create a directory where each page is a markdown
file, with an `_index.md` file representing the introduction to the guide.

```bash
# Create the index page for the guide
mkdir content/guides/my-pure-guide.md
touch content/guides/my-pure-guide/_index.md
# or if you have Hugo installed:
hugo new content/guides/my-pure-guide/_index.md
```

Then create the pages for the guide under `content/guides/<dir>/<page>.md` as
needed. The [metadata](#metadata-for-guides) lives on the `_index.md` page (you
don't need to assign metadata to individual pages).

### Guides for specific frameworks or languages

For guides that demonstrate how to use a particular framework or
programming language, consider the following outline:

1. **Introduction**
   - Briefly introduce the framework or language.
   - Explain what the user will achieve by the end of the guide.
   - List required software, tools, and knowledge.
2. **Development setup**
   - Guide the user through setting up a development environment.
   - Include instructions on writing or obtaining sample code.
   - Show how to run virtual environments for local development.
3. **Building the application**
   - Explain how to create the application.
   - Provide step-by-step instructions for building the application.
   - If applicable, show how to test the application.
4. **Deploying**
   - Show how to run the application.
   - Discuss configuration options and best practices.
5. **Best practices and conclusions**
   - Offer tips for optimizing using the framework or language.
   - Summarize key takeaways, suggest next steps, and further reading.

### Use-case guides

For guides focused on accomplishing a specific goal or use case
(e.g., deploying a machine learning model), use a flexible outline that ensures
a logical flow.

The following outline is an example. The structure should be adjusted to best
fit the content and ensure a clear, logical progression. Depending on the
subject matter of your use-case guide, the exact structure will vary.

1. **Introduction**
   - Describe the problem or goal.
   - Explain the benefits of using the application in this context.
2. **Prerequisites**
   - List required tools, technologies, and prior knowledge.
3. **Setup**
   - Provide instructions for setting up the environment.
   - Include any necessary configuration steps.
4. **Implementation**
   - Walk through the process step by step.
   - Use code snippets and explanations to illustrate key points.
5. **Running or deploying the application**
   - Guide the user on how to execute or deploy the solution.
   - Discuss any verification steps to ensure success.
6. **Conclusion**
   - Recap what was achieved.
   - Suggest further reading or advanced topics.
