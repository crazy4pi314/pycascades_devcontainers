# ![PyCascades 2023: Eternal sunshine of the spotless development environment](pycascades.png)
[Schedule](https://2023.pycascades.com/program/talks/eternal-sunshine-of-the-spotless-development-environment/) | [Slides](slides.pdf) | [Demo](demo.ipynb) | [Title inspo: Eloisa To Abelard by Alexander Pope](https://gutenberg.org/cache/epub/9413/pg9413-images.html#link2H_4_0051:~:text=Eternal%20sunshine%20of%20the%20spotless%20mind!)

"But it worked on machine" is one the most frustrating lines to hear when collaborating on a project. Creating and configuring reproducible environments is a major part of modern software development and had led to the popularity of tools like Docker to specify where and how code runs. Setting up Docker and Development Containers in VS Code make it easy to configure not only the where the code runs, but also the developer workspace. Setting up these tools can reduce effort for maintainers of OSS projects, bootstrap contributors, and make running events like workshops or sprints go more smoothly.
In this talk, we will cover why setting up container infrastructure like Docker can be useful for your project, and how you can extend that with Dev Containers to configure a full development experience in VS Code. We will also take a look at two common OSS project scenarios and how workflows for using Docker, Dev Containers and Codespaces make things easier. No container experience required, and some knowledge of VS Code helpful, but not necessary.

## Topics

- Dev Containers: "Desires composed, affections ever even"
Docker setup is portable, but not necessarily editor specific
Specifying an entire VS Code dev experience: JSON with optional Docker file
Quick look at the .decontainer file spec
Sample repo and demo starting experience when cloning a new repo
7 min | Contribution + Collaboration: "Each PR accepted, and each issue closed"
Can help simplify/exemplify CONTRIBUTING.md
Easily share how you develop with contributors or create a container that demos a problem to share
Future: Dev Containers can be shared with CI like GitHub actions so it is using the exact same env as well
7 min | Workshops: "Unequal task! a passion to resign"
Dev containers create accessible and free, out-of-the-box experiences for teaching spaces
Users can launch and use entirely from the browser
Different levels of hardware backend compute available
1 min | Review "Labour and rest, that equal periods keep"

### Speaker Profile:

Sarah has spent most of her career developing technology in the lab, from virtual reality hardware to satellites. She got her PhD in Physics by starting plasma fires with lasers, Python, and Jupyter Notebooks. She has also written tech books for folks of all ages, including ABCs of Engineering and Learn Quantum Computing with Python and Q#.  As a Cloud Developer Advocate for Python at Microsoft and a Python Software Foundation Fellow, she finds all kinds of new ways to build and break OSS tools for data science and machine learning. When not at her split ergo keyboard, she loves boating in the Seattle area, laser cutting everything, and playing with her German Shepard, Chewie.

[sckaiser.com](https://sckaiser.com) | [Mastodon](https://mathstodon.xyz/@crazy4pi314) | [GitHub](https://github.com/crazy4pi314)

Tags:
devcontainers, docker, documentation, community, vscode, infrastructure

This is a template reposotory that can be used to start with a minimal [Dev Container](https://containers.dev/) setup that provides [conda](https://github.com/conda/conda) and [mamba](https://github.com/mamba-org/mamba) for setting up Python environments.
This repo contains a sample Conda environment file ([environment.yml](environment.yml)), demo Jupyter notebook, and Dev Container configuration files that describe how a containerized development can be built for the repo.
These configuration files work for both local Dev Containers as well as [Codespaces](https://github.com/features/codespaces), a GitHub-hosted cloud environment.

The Docker setup for the Dev Container starts with a miniconda image that then will install whatever conda environment file you have at the root of the repo.
There are some additional configuration options in the comments of the [Docker](.devcontainer/Dockerfile) and [devcontainer.json](.devcontainer/devcontainer.json) that have some examples of other steps you may want to add to your Dev Container, like what VS Code extensions to install when the container is launched.

## How to use this template

0. Create a repo of your own by [creating a repo from this template](https://docs.github.com/en/repositories/creating-and-managing-repositories/creating-a-repository-from-a-template) to your GitHub account.

### Work on your computer (requires Docker and VS Code installed)

1. Clone your newly created repo to your local machine and open it in VS Code.
2. Install the Remote Development extension (if you don't already have it).
3. Open the command pallet and run _Dev Containers: Reopen in Container_. Alternately, you can click on the left-most button on the bottom status bar (little arrows facing each other) and choose _Reopen in Container_.
4. This will take a few minutes to download the Docker image and build the rest of the container.
5. You should now have a VS Code window with your clone of the template repo open, running in a local Dev Container.

### Start working instantly on Codespaces

1. From you clone of the template use the green _Code_ button to create a codespace. If you click the triple dots you can customize the type of machine you want to be running your Codespace. You don't need to use any more than the 2-core for the template, but depending on what you use for your environments, you may need more ram/disc space.
2. The Codespace will take a few moments to start, which can be shortened by turning on Codespaces Pre-Builds on your repo*.
3. You should now have a VS Code window in your browser with your clone of the template repo open, running in a Codespace.

\* This can get expensive so make sure to check the settings when enabling this feature.

## Ways to customize the template

- Change the container `name` in [devcontainer.json](.devcontainer/devcontainer.json).
- Change the default conda env name by changing the first line of [environment.yml](environment.yml) and change _python.defaultInterpreterPath_ in [devcontainer.json](.devcontainer/devcontainer.json).
