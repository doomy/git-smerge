
# git-smerge

Smerge (short for supermerge) is a simple shorthand custom git command that automates merging a branch and soft deletion afterwards (only deletes branch if it's been merged succesfully).

## Installation
after downloading the bash script, simply move/copy it somewhere that's included in PATH, for example:

```bash
sudo mv git-smerge /bin
```
and make it executable:
```bash
sudo chmod +x /bin/git-smerge
```

optional: If you want the command to autocomplete branch names, put the following code in your `~/.bashrc` or other boostrap script you're using :
```bash
_git_smerge ()
{
    __gitcomp_nl "$(__git_refs)"
}

```

## Usage

### a) while on a branch to be merged to master:
```bash
git smerge
```
Merges current branch to master and soft deletes it after the merge.


### b) specifying the branch in an argument
```bash
git smerge <branch_name>
```

Merges the specified branch into current working branch and soft deletes it if successful.
