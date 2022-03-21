# intellij-playground

📚 Learning and exploring Intellij IDEA.

> IntelliJ IDEA: The Capable & Ergonomic Java IDE by JetBrains
> 
> -- <cite>https://www.jetbrains.com/idea/</cite>

## Instructions

Follow these instructions to run Projector:

1. Clone the `projector-server` Git submodule:
   * `git submodule update --init`
   * If you had previously initialized the submodule, you can skip this step. Over time, the submodule will fall behind
     its remote origin. You'll want to periodically update the submodule. Use the command in the next step.  
2. Update the submodule:
   * `git submodule update --remote --merge`
3. Add `local.properties` file
   * Add a file named `local.properties` in the `project-server/` directory. Give it the property `projectorLauncher.ideaPath`
     and set it to the path of Intellij on your computer (I think this only works for Linux; but I'm going to try it on
     my mac). This instruction came from the README in `project-server/`. Read that for more information.
4. Use Java 11
   * It's important to use the version of Java specified by the `project-server/` project. For example, see the version
     used in GitHub Actions by peeking at the [build.yml file](https://github.com/JetBrains/projector-server/blob/64870289fbd5e684288ebfe91e4ac5a4f4e58881/.github/workflows/build.yml#L21).
6. Build and run `projector-server/`:
   * `pushd projector-server; ./gradlew runIdeaServer; popd`
   * Projector should be running its own instances of Intellij! (THIS DOES NOT WORK unfortunately. I'm getting `java.lang.ClassNotFoundException: com.intellij.idea.Main`
     I don't want to investigate more right now. I'm also not sure this can even work on macOS at all)

## Notes

I want to try out [*Projector*](https://blog.jetbrains.com/blog/2021/03/11/projector-is-out/). So, I thought I would make
a Git repo to keep track of notes, provide commentary, and instructions.

### Notes for `projector-docker`

Commands I executed when trying to run `projector-docker`:

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

* (I don't think this will work on macOS but I tried) IN PROGRESS Run Projector without Docker. Maybe this will avoid the JVM crash.
* Merge my project <https://github.com/dgroomes/intellij-plugin-playground> as a sub-project to this Git repo.

## Reference Materials

* [Jetbrains blog post: *Access Your IDE Remotely With Projector*](https://blog.jetbrains.com/blog/2021/03/11/projector-is-out/)
* [GitHub repo: `projector-server`](https://github.com/JetBrains/projector-server)
* [GitHub repo: `projector-docker`](https://github.com/JetBrains/projector-docker) 
