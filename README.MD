# link-package

This is just a simple little tool for work, it is heavily dependent on our git repository structure, so unless you follow our pattern of structuring projects, it won't work. Sorry.

## Installation

This tool can be installed using homebrew.

- `brew tap lifeglug/formulae`
- `brew install link-package`

## Manual Installation

This has no dependencies as it is a simple bash script. You can either download `./bin/link-package` and make sure it's set to be executable and put it in your `/usr/local/bin` folder, or similar.

###

## Usage

Simply call `link-package <package-names>` such as `link-package shared-services flow pulse`.

What this does is look into your monorepo folder (~/workspace/frontend-platform as default) and checks if the package exists in ${MONOREPO_ROOT}/packages/${PACKAGE_NAME}. It will then call the `yarn build-quick` command on the monorepo, then drill down into the specified package and creates a tarball in the build folder.

Each of these paths and commands above can be customised via the env vars below.

After all this, it will `npm i` the built tarballs in your current directory.

## Configuration

Configuration can be overridden with env vars. Just export them in your bash profile, or just inline when calling the script, however you want.

| Env Var              | Default                       | Description                                                          |
| -------------------- | ----------------------------- | -------------------------------------------------------------------- |
| LINK_PACKAGE_ROOT    | ~/workspace/frontend-platform | The root directory for our monorepo                                  |
| LINK_PACKAGE_COMMAND | "yarn build"                  | The command which is run in the project to produce the distributable |
