---
pubDatetime: 2025-12-30T21:00:00+11:00
title: AI Agent Skills and you
slug: ai-agent-skills-and-you
featured: true
draft: false
tags:
  - ai
  - mcp
  - cli
  - docker
  - api
description: Thoughts about AI Agent Skills, CLI and API's inside Docker Containers.
---

![My Terminal](@/assets/images/terminal-cli.png)
_Image credit: Me_

I was just reading an interest post by Martin Alderson about [Why I'm building my own CLIs for agents](https://martinalderson.com/posts/why-im-building-my-own-clis-for-agents/). It's good - go read it now please come back.

...
..
.

## Why I agree with Martin

As I've been using AI Agents more and more (context: I use Copilot in Visual Studio or VS Code) I find that I wish the agent had more 'understanding' (context?) of my domain. For example:

- Understand my MSSql database
- Understand how we have setup our API's in Azure
- etc.

I've been led to believe that MCP's are able to be the bridge between my AI Agent and specific resources that hold my domain knowledge.

Bummer is that where I currently work, we don't have MCP server access (they are blocked by security policy). So I can't use MCP's to help my AI Agent understand my domain. _SIDE NOTE: I'm really hate how local MCP servers require certain languages, like Go or Python. I refuse to install Python or Node on my machine. Docker MCP's save me here._ Which made me think like Martin - why can't the AI Agent just call CLI commands or API's that I have in Docker containers on my local machine?

## AI Agent Skills in Docker

So I started thinking about how I could package up my domain knowledge into Docker containers that expose CLI commands or API's that my AI Agent could call.

For example - starting out simple.

- A docker container that has a CLI application which can access a database
- A docker container that has GitHub CLI installed and configured
- A docker container that has Azure CLI installed and configured
- A docker container that has AWS CLI installed and configured
  .. etc ..

Then I can have docker-compose files that bring up multiple containers that my AI Agent can use to get domain knowledge.

This way, when a developer starts work on a new project, they can

- `git clone` the repo
- `docker-compose up -d` to bring up the AI Agent Skills containers
- Start using their AI Agent with the CLI accessible straight away.

Using the `Skills.md` file (that is checked into the repo) has all the prompts needed for the agent to start quering the resources required.

## But there's no CLI for the resource I need!

Like Martin suggested -> make a CLI for the API. Tools like [Kiota](https://github.com/microsoft/kiota) make it super easy to generate CLI apps from OpenAPI specs, etc.

## Conclusion

I think Martin is onto something here - this has been a gut feeling I've also had for a while. Packaging up CLI apps in Docker containers that can be used by AI Agents to get domain knowledge is a great idea.

And hopefully it will reduce token usage / costs too!
