# link-package

This is just a simple little tool for work, it is heavily dependent on our git repository structure, so unless you follow our pattern of structuring projects, it won't work. Sorry.

## Installation

This tool can be installed using homebrew.

* `brew tap lifeglug/formulae`
* `brew install link-package`

## Manual Installation

This has no dependencies as it is a simple bash script. You can either download `./bin/link-package` and make sure it's set to be executable and put it in your `/usr/local/bin` folder, or similar.

###

## Usage

Simply call `link-package <package-name>` such as `link-package shared-services`.

What this does is look into your workspace folder (~/workspace as default) for a folder named `shared-services`, and from there it will see if the package.json exists within the root folder, or the `frontend` subfolder, call `npm run build` in the frontend subdirectory, then `npm pack` in the built `dist` folder.

Each of these paths and commands above can be customised via the env vars below.

After all this, it will `npm i` the built tarball in your current directory.

## Configuration

Configuration can be overridden with env vars. Just export them in your bash profile, or just inline when calling the script, however you want.

| Env Var | Default | Description |
|-|-|-|
| LINK_PACKAGE_WORKSPACE | ~/ | The root directory for your workspace, where all your project files are kept |
| LINK_PACKAGE_SUBFOLDER | "frontend" | The subfolder where package.json is contained |
| LINK_PACKAGE_DIST | "dist" | The folder where the distributable is built to. |
| LINK_PACKAGE_COMMAND | "npm run build" | The command which is run in the project to produce the distributable |



