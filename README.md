# What is Sauron?

Sauron is a simple self-contained script that follows simultaneously all the specified log files
and notifies the occurrence of errors. It requires *Python* >= 2.3.

The default keywords to determine the presence of an error are: *error*, *exception*, *fail*,
*fails*, *failed*, *failure*, *cannot*, *unable*, *unexpected*, *incorrect*, *invalid*, 
*bad* and *wrong*.

## Command line usage

    $ sauron [options] [paths (default /var/log)]

    Options:
        -h, --help            show this help message and exit
        -f FILENAME_REGEX, --files=FILENAME_REGEX
                              filename regex (default 'log$')
        -a, --all             the log file are followed from the begin
        -w WORDS, --words=WORDS
                              comma-separed words which filters the lines (default:
                              error, exception, fail, fails, failed, failure,
                              cannot, unable, unexpected, incorrect, invalid, bad,
                              wrong)
        -r LINE_REGEX, --regex=LINE_REGEX
                              regex to filter the log lines (it overwrites the
                              --words option)
        -i CHECK_INTERVAL, --interval=CHECK_INTERVAL
                              interval in seconds before to scan again the paths
                              (default 1)
        --version

The specified paths are scanned every `interval` seconds and all found files whose name matches with the regex are monitored.

## Installation

Simply download the latest script and apply the execution permissions.

    curl -O https://raw.githubusercontent.com/maurocchi/sauron/master/sauron && chmod +x sauron