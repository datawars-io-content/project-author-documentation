---
icon: package
order: 900
---
[!embed](https://www.loom.com/embed/810f369756bc4c38ac59da83e73d5083?sid=f4d3dee4-88cb-4194-a6b4-fdbeb1eda0da)

# Github project structure

![](/static/github/high-level-project-structure.png)

This page contains a summary of each of the most important components in a project. The reference contains detailed information of each one of them.

### 1. `english.md`

The **MOST** important file. It contains all the content that is rendered on the left side of the screen. It contains all the text of the pages and the activities.

Refer to the [main documentation about `english.md`](github-repo-artifacts/english-md.md) for a full description including the snippets to download for VS Code.

High level overview of the structure:

* `english.md`
* `notebooks/`
* `public.md`
* `chat.txt`
* `docker-compose.yml`

### 2. `public.md`

This markdown file contains the public description of the project. [Read more](github-repo-artifacts/public-md.md).

### 3. `chat.txt`

The context for the AI Assistant, including objectives of the project and description of the data. [Read more](github-repo-artifacts/chat-txt.md).

### 4. Notebooks and lab files

The lab (right hand size) of your project will contains the notebooks, datasets, images, and other components needed. You can install custom requirements.
