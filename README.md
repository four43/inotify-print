# inotify-print
A container that will watch a mounted in folder and print the results to stdout/log

## Usage

A very simple container for outputting events for when files change. Simply mount in the directory you would like to monitor, and it will output create, modify, move, and delete events of those files. Additional filtering can be achieved by piping the containers output through grep, awk, etc.

## Example

Run the following container, then run `touch /tmp/baz` in another shell:
```bash
$ docker run -v /tmp/inotify:/watch -it four43/inotify-print
Setting up watches.
Watches established.
[2016-06-13T18:51:08Z] CREATE /watch/baz
```