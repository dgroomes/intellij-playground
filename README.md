# intellij-playground

📚 Learning and exploring Intellij IDEA.

> IntelliJ IDEA: The Capable & Ergonomic Java IDE by JetBrains
> 
> -- <cite>https://www.jetbrains.com/idea/</cite>

## Notes

I want to try out [*Projector*](https://blog.jetbrains.com/blog/2021/03/11/projector-is-out/). So, I thought I would make
a Git repo to keep track of notes, provide commentary, and instructions.

### Notes for `projector-docker`

Commands I executed when trying to run `project-docker`:

* Pull the image:
  * `docker pull registry.jetbrains.team/p/prj/containers/projector-idea-c`
* Run a container:
  * `docker run --rm -p 8887:8887 -it registry.jetbrains.team/p/prj/containers/projector-idea-c`
* Open in the browser:
  * `open http://127.0.0.1:8887`
* Unfortunately, it crashes with:
  > ...
  > 
  > A fatal error has been detected by the Java Runtime Environment:
  > 
  > ...
  > 
  > Could not load hsdis-amd64.so; library not loadable; PrintAssembly is disabled
  > ...

## Wish List

General clean-ups, changes and things I wish to implement for this project:

* Run Project without Docker. Maybe this will avoid the JVM crash.
* Merge my project <https://github.com/dgroomes/intellij-plugin-playground> as a sub-project to this Git repo.

## Reference Materials

* [Jetbrains blog post: *Access Your IDE Remotely With Projector*](https://blog.jetbrains.com/blog/2021/03/11/projector-is-out/)
* [GitHub repo: `projector-docker`](https://github.com/JetBrains/projector-docker) 
