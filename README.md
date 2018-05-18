# git push-branches

You can always `git push --all`, but what if you want to get rid of old
branches? By default, this script pushes only branches with code less than a
month old.


## Installation

One-liner using [Sinister][1]:

	$ sh <(curl -sSL http://git.io/sinister) --local --url https://github.com/augustohp/git-push-branches

Or you can clone the project where you want to, all you need after is to symlink
the `git-push-branches` script to your `$PATH`:

	$ cd <my-src-dir>
	$ git clone http://github.com/augustohp/git-push-branches
	$ chmod a+x git-push-branches/git-push-branches
	$ ln -s <my-src-dir>/git-push-branches /usr/local/bin

Now you should be able to execute `git push-branches` anywhere.

## Help

```
Usage: git-push-branches [options]
       git-push-branches --since="2018-01-01" --to-remote gitlab --from-remote gerrit

Sends branches from a remote to another, avoiding sending ones that are old or
already merged.

Options

  -s, --since <date>        Only migrate branchs that have the last commit since
                            the mentioned date (default: "1 month ago").
  -t, --to-remote <name>    Remote that will receive branches to be migrated,
                            allowing other rules here descibed (default: "mine").
  -f, --from-remote <name>  Remote that will be the source of branches (default: "origin").
  -d, --dry-run             Does nothing, only print branch names to migrate.
  -v, --version             Displays version of the program.
  -h                        Displays this help message.
```
