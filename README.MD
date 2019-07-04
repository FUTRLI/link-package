# link-package

This is just a simple little tool for work, it is heavily dependent on our git repository structure, so unless you follow our pattern of structuring projects, it won't work. Sorry.

## Installation

This has no dependencies as it is a simple bash script. You can either download `./bin/link-package` and make sure it's set to be executable and put it in your `/usr/local/bin` folder, or similar.

## Usage

Simply call `link-package <package-name>` such as `link-package shared-services`.

What this does is look into your workspace folder (~/workspace as default) for a folder named `shared-services`, and from there it will call `npm run build` in the frontend subdirectory, then `npm pack` in the built `dist` folder.

After all this, it will `npm i` the built tarball in your current directory.

## Configuration

Configuration can be overridden with env vars. Just export them in your bash profile, or however you want to deal with them.

| Env Var        | Default     | Description                                                                  |
|----------------|-------------|------------------------------------------------------------------------------|
| WORKSPACE_PATH | ~/workspace | The root directory for your workspace, where all your project files are kept |



