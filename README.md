### A simple way to rebuild your web app container on every commit with local `docker-compose` and `post-commit` `git` hook
1. Initialize your `git` repo with `git init`
1. Place the attached `post-commit` file into `.git/hooks/` directory and make it executable with `chmod +x .git/hooks/post-commit`
1. Use the attached `docker-compose.yaml` and `Dockerfile` as examples to create and run container
1. The `.env` file is not commited to VCS as it may contain secure configuration details. Put variables there like the following ones:
    * `APPNAME=myapp`
    * `APPVERSION=latest`
1. `post-commit` working directory is the repo root, it is the same one where `.git` is located
1. The `post-commit` script is Linux and MacOS compartible
1. Logs for building and running container is available in `/tmp/git-post-commit` as `APPNAME-YYYYMMDD-HHMMSS-XXX` files
1. [Link to the Repo](https://github.com/mtilson/git-post-commit-hooks)
