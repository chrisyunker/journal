journal
===

Simple command line tool for managing daily log files. Journal uses vim to
open or edit log files in markdown format.

## Usage

### Writing to a new or existing log

The `journal-write` command opens a daily log file for writing. It takes an optional single argument to specify the log date. The argument can be either a day offset, or an explicit date.

If no argument is provided, it defaults to the current date.


Write to log for current day

```
$ journal-write
```

Write to log for different day using day offset

```
$ journal-write +2

$ journal-write -5
```

Write to log for different day using date

```
$ journal-write 2017-12-29

$ journal-write 4-1
```

### Reading logs

The `journal-read` command prints daily logs files in chronological order within a specified date range. It takes an optional two arguments to specify the start and end dates. Each argument can be either a day offset, or an explicit date.

If only a single argument is provided, it will specify the start date. The end date with be today's date.

If no arguments are provided, both the start and end dates default to the current date, so it just prints the current log (if it exists).


Read log for current date (if exists):

```
$ journal-read
```

Read logs between specified date and current date:

```
$ journal-read 2017-10-01

$ journal-read -3
```

Read logs between specified date range:

```
$ journal-read 2017-10-01 2017-10-20

$ journal-read 2017-10-01 -1

$ journal-read -3 -1
```

###  Searching logs

TBD


## Installation

### Log directory

Journal writes its log files under a configurable root directory. The default directory is `$HOME/journal`.

To configure, set env variable `JOURNAL_DIR` in your .bashrc file.

```
export JOURNAL_DIR=[custom log dir]
```

### Homebrew

```
brew tap chrisyunker/formulae
brew install journal
```

### Manual install

Clone journal repo to a local directory (e.g. ~/tools).

```
cd ~/tools
git clone git@github.com:chrisyunker/journal.git
```

Add journal directory to path in .bashrc file

```
export PATH=$PATH:~/tools/journal
```

