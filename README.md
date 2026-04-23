# git-prune-branches
Removes/rebases branches with no diffs from default branch

## Usage
Simply run from 

Run with `-h` to display advanced usage information.
```
% ./git-prune-branches -h
git-prune-branches [-N] [-f] [-h] [-(n|y)] [-q] [-z] [<branch_regex>]

Compare & optionally delete branches that have no changes from default branch.
Default behavior is interactive and safe to use; options for rebase or shell.
Use -n for a non-interactive display of changes, or -qn for a quiet test.
Use -y to delete branches with no diffs, -fy to delete all matching branches.
Returns 0 if no empty branches exist, otherwise 1.

-N  dry run (use with -y to print the branch delete command but not run it)
-f  force (use with -y) !!! CAUTION will delete branches with diffs !!!
-h  help (usage information)
-n  assume no (dry run for branches with no diff)
-q  quiet mode (will skip branches when a prompt is required)
-y  assume yes (delete all branches with no diff)
-z  do not log to /Users/rzwissler/.config/git-prune-branches/activity.log
<branch_regex>  specify a regex to run against only matching branches
```
