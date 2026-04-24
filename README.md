# git-prune-branches
Removes/rebases branches with no diffs from default branch

## Usage
Run with no options inside a repo, it's safe.
```shell
% ./git-prune-branches
feat/add_script - differences detected
000d4a1 add README
742f15e add git-prune-branches
Delete branch? (y)es (n)o (r)ebase (s)hell (q)uit: n
feat/increase_memory - no differences
Delete branch? (y)es (n)o (q)uit: y
> Deleted branch feat/increase_memory (was 67f7ae1).
hotfix/fix_memory_leak - no differences
Delete branch? (y)es (n)o (q)uit: y
> Deleted branch hotfix/fix_memory_leak (was 67f7ae1).
```
Deleted branches with restore commands are logged to `~/.config/git-prune-branches/activity.log`

Run with `-h` to display advanced usage information.
```shell
% ./git-prune-branches -h
git-prune-branches [-N] [-f] [-h] [-(n|y)] [-q] [-z] [<branch_regex>]

Compare & optionally delete branches with no commits ahead of default branch.
Default behavior is interactive & safe to use with options for rebase or shell.
Use -n for a non-interactive display of changes, or -qn for a quiet test.
Use -y to delete branches with no commits, -fy to delete all matching branches.
Returns 0 if no such branches exist, otherwise 1.

-N  dry run (use with -y to print the branch delete command but not run it)
-f  force (use with -y) !!! CAUTION will delete branches with commits !!!
-h  help (usage information)
-n  assume no (dry run for branches with no commits)
-q  quiet mode (will skip branches when a prompt is required)
-y  assume yes (delete all branches with no commits)
-z  do not log to /Users/rzwissler/.config/git-prune-branches/activity.log
<branch_regex>  specify a regex to run against only matching branches
```
