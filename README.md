# skelect

Skeleton templating &amp; selection utility.

## About

Skelect is a system for managing and deploying skeletons of any kind. The foremost use cases are:

 * User dotfiles
 * SDK & Framework application bootstrapping 
 * Minimalist package management
 * Content deployment

## Usage

### The help screen

```
# skelect help

./skelect - Utilities for selecting, maintainaing and creating workspace skeletons
Usage:
    ./skelect <subcommand> [[<subcommand>]...] [[<arguments>]...]

Examples:
    ./skelect help
    ./skelect apply <https://git.example.com/owner/projname.git/path/to/desired/skel> [<desired-branch>]
    ./skelect create </filesystem/path/to/new/skel/root> [-from=url://existing/skel/to/clone]

Available subcommands:
     apply help update

```

### Apply a skeleton to your CWD

```
cd ~
skelect apply https://git.example.com/someones/dotfiles
```

### Future Planned Features

Skelect is a little baby project. See TODO.md for more information about what's planned. In this README we're only going to cover things that are critical enough to be considered "missing features".

### Updating

Update would perform a synchronization maneuver with user-intervention for conflict resolution.

```
skelect update https://git.example.com/someones/dotfiles
```

### Skeleton source creation helpers

Some utilities should exist to help people create & audit skeletons for best practices.

### --no-scripts flag

There should be a flag to prevent any hook scripts from firing.

#### --no-template flag

There should be a flag to prevent templates from filling & deploying.

## Security

The current bash implementation of skelect is a prototype. It was not build with security in mind. It is a script that runs scripts. If your acquaintances offer their dotfiles (or any other skeleton) to you, it's your responsibility to vet them before applying them.
