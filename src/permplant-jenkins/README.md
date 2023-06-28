# VS Code Devcontainer

## Overview

[Developing inside a Container](https://code.visualstudio.com/docs/remote/containers). Check the official documentation if you encounter problems and submit a PR with any corrections you find for the instructions below.

## Usage

1. Ensure you have all [Devcontainer Prerequisites](#devcontainer-prerequisites)
2. Open the directory you just cloned (/permaplant).
3. Install the [Remote Development](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.vscode-remote-extensionpack) extension pack for VS Code. This will be included if you install recommended workspace extensions upon opening this repository.
4. Ensure Docker is running
5. [Open your workspace in the provided devcontainer](https://code.visualstudio.com/docs/remote/containers#_open-an-existing-workspace-in-a-container): Open this repository in VS Code and run **Remote-Containers: Reopen in Container...** from the Command Palette (<kbd>F1</kbd>).

### Devcontainer Prerequisites

[Developing inside a Container: Getting Started](https://code.visualstudio.com/docs/remote/containers#_getting-started).

1. Docker (Docker Desktop recommended)
2. VS Code
3. X window host - required if you want to be able to interact with a GUI from your Docker host

### Filesystem performance

This is optional, but highly advised as many filesystem/IO heavy operations (`cargo build`, `yarn install`, etc) will be very slow if they operate on directories shared with a Docker container from the Docker host.

Open your project with VS Code and run **Remote-Containers: Clone Repository in Container Volume...** from the Command Palette (<kbd>F1</kbd>)
[Source](https://code.visualstudio.com/remote/advancedcontainers/improve-performance#_use-clone-repository-in-container-volume)

### GUI / X window.

There is a way to expose the GUI inside a container to an X window server. I have not spend time researching this. It should work somehow with
setting the DISPLAY env variable.

```bash
export DISPLAY="host.docker.internal:0"
```

[Source](https://docs.docker.com/desktop/windows/networking/#i-want-to-connect-from-a-container-to-a-service-on-the-host)
