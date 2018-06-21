# Skelect TODO list

## Add template support

Like files, skelect source want to be able to have files that can be generated based upon the environment. An easy solution would just be envsubst, but it might be cooler to have a more comprehensive and capable templating system, or maybe something pluggable

## Add script support

Skelect sources want to be able to include scripts that run to do sanity checks or other preparations & cleanups. Think of this like a system package's post-install and pre-install hooks.

## Update synchronization with conflict management

The skelect implementation makes use of a staging environment to create a pristine result from the skelect source. The staging environment could be used to check for conflicts as things diverge between source revisions and destination deployments which may have been edited. It might be possible to calculate a diff between the stale stage to the deployed file, the stale stage to the new stage, and the new stage to the deployed file to help the user set things straight.

NOTE: Easy to overlook, we'll also need a way to track the deletion of files between source revisions and to make sure they're reflected on the deployed target.

## Manuals

For real. But maybe wait until after reimplementation.

## Distribution Packages

You know the drill
 
 * dpkg
 * rpm
 * apk
 * tar

## A more portable implementation

The current implementation is a simple prototype involving bashisms. Re-implenting the software in go or c would be friendly to users of non-bash-having poSIX systems.

## System state database?

Backburner until needed. In the future we may require a means of tracking the status of a target and its position in each selected source. This would be helpful for system update shortcuts and possibly conflict resolution.

## Optional source manifest

Rather than forcing the user to override the default SKELECTFILES variable, it would be cool if there was a standard manifest file that skelect looked at to automatically configure itself with the settings that apply to the source that implements it

Potential features of the optional manifest could include

 * Directives on where to look for files, templates, hook scripts
 * Contextual transformations:
   * A software package might plant itself differently if it's being installed in the system root or in a single-user's subdirectory.
 * References to other dependency or supplemental sources

## Distributable skelect source packages

Instead of relying on git repos, we could extract a skelect archive package from any supportable URI location.

## Stock sources & compelling use cases

Capabilities & applications we want to see

 * Initial home directory provisioning
 * Dotfile management & synchronization
 * Static content deployment?
 * Embedded systems provisioning - like an out-of-band package manager 
 * SDK & Framework skeleton project bootstrapping
   * It would be cool to demonstrate mulitple selections to solve blended frameworks

