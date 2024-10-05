# vscode-pddl-devcontainer
Quick repo to test AI Planning on Apple Silicon MacOS with

- Docker Desktop that will emulate AMD64 (as [aiplanning/planutils](https://hub.docker.com/r/aiplanning/planutils) currently only ships an AMD64 version)

- [VS Code](https://code.visualstudio.com/download), with the extensions
  - [Dev Containers](vscode:extension/ms-vscode-remote.remote-containers) 
  - [PDDL](vscode:extension/jan-dolejsi.pddl)



## Quick start

- Clone this repo
- Open VS Code in the cloned folder, with Dev Containers
- Open the files [domain.pddl](./domain.pddl) and [problem.pddl](./problem.pddl) side by side
- Hit `Option` + `P`
  - `LAMA-first` will do just fine
  - Mind that `http://planutils/package` is local to your machine (cf. [docker-compose.yml](.devcontainer/docker-compose.yml))

## Local test, without the PDDL extension

- Clone this repo
- Open VS Code in the folder, with Dev Containers
- In the VS Code dev-containerized terminal, execute
```bash
http post http://planutils:5555/package/lama-first/solve domain=@domain.pddl problem=@problem.pddl
```

This should get you the plan output - and can be useful to understand certain errors.