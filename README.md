# intellij-playground

📚 Learning and exploring Intellij IDEA.

> IntelliJ IDEA – the Leading Java and Kotlin IDE
> 
> The IDE that makes development a more productive and enjoyable experience
> 
> -- <cite>https://www.jetbrains.com/idea </cite>


## Overview

I originally created this repository to explore  [*Projector*](https://blog.jetbrains.com/blog/2021/03/11/projector-is-out/)
but that project is now discontinued. But, I can still this repository to explore other things about Intellij like its
support for remote development via SSH, Intellij plugin development, and more.


## Container-Based Development via SSH

NOT YET IMPLEMENTED

Intellij and other JetBrains IDEs support [remote development](https://www.jetbrains.com/remote-development/) via cloud
development environments like [JetBrains Space](https://www.jetbrains.com/space/features/dev-environments.html), [GitHub Codespaces](https://github.com/features/codespaces),
or you can [orchestrate your own development environment with SSH](https://www.jetbrains.com/help/idea/remote-development-starting-page.html#start_from_IDE).

I'm a fan of cloud development environments for demos, learning expeditions, and open source collaboration but I generally
want more control and power than what the cloud constrains me to and costs. With that in mind, we can create a container-based
development environment that runs an Intellij *IDE backend* and connect to it from an *IDE client* like Intellij or [Gateway](https://www.jetbrains.com/help/idea/remote-development-a.html#gateway)
via SSH. This is what I'll be exploring in this repository.

To make sense of the components and how they work together, refer to [this architecture diagram in the Intellij docs](https://www.jetbrains.com/help/idea/remote-development-overview.html#defs).

We need to create a Docker image and container that hosts the IDE backend and is complete with the development tooling
we need to work on our projects. For me, I often work on Java projects and so I depend on an installation of OpenJDK.
Personally, I find the [Dev Containers](https://containers.dev/) project effective and it shows promise for future investment
and improvement. We can define a dev container configuration file (`.devcontainer/devcontainer.json`) and use the [Dev Container CLI](https://github.com/devcontainers/cli)
to define and build our ideal development environment! I have explored the Dev Containers project in the context of VS Code
and GitHub Codespaces. You can see my notes and working examples in my repository <https://github.com/dgroomes/vscode-playground>.


## Wish List

General clean-ups, changes and things I wish to implement for this project:

* [x] ABANDONED (I don't think this will work on macOS but I tried) Run Projector without Docker. Maybe this will avoid the JVM crash.
* [ ] Merge my project <https://github.com/dgroomes/intellij-plugin-playground> as a sub-project to this Git repo.
* [x] DONE Remove Projector stuff. That project was discontinued and is now part of the closed-source product Gateway (which is
  totally fine; JetBrains can do what they need to do to stay competitive) 
* [ ] IN PROGRESS Create a container-based development environment. Use JetBrains Gateway. Use Dev Containers. Describe
  all instructions.


## Reference Materials

* [Jetbrains blog post: *Access Your IDE Remotely With Projector*](https://blog.jetbrains.com/blog/2021/03/11/projector-is-out/)
* [GitHub repo: `projector-server`](https://github.com/JetBrains/projector-server)
* [GitHub repo: `projector-docker`](https://github.com/JetBrains/projector-docker) 
