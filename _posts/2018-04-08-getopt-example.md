---
layout: post
title:  "Parse command line options of Bash script with getopt"
tags: bash 
---

I write Bash utilities from time to time. `getopt` is a good tool to parse the command line options for Bash scripts. So I write a simple sample for future reference about its usage. 

- greet.sh:

```
usage() {
    declare -r script_name=$(basename "$0")
    echo """
Usage:
"${script_name}" [option] <name>

Option:
    -h, --help
    -w, --when <morning|afternoon>
"""
}

main() {
    if [[ $# -eq 0 ]]; then
        usage
        exit 1
    fi

    PARSED_OPTIONS=$(getopt -n "$0"  -o hw: \
                            --long help,when: \
                            -- "$@")
    if [[ $? -ne 0 ]];
    then
        # getopt error
        exit 1
    fi

    eval set -- "$PARSED_OPTIONS"

    while true; do
        case "$1" in
            -h|--help)
                usage
                exit 0
                ;;
            -w|--when)
                declare -r when="$2"
                shift 2
                ;;
            --)
                shift
                break
                ;;
        esac
    done

    declare -r name="$@"

    if [[ -n "${when}" ]]; then
        case "${when}" in
            morning)
                echo Good morning, "${name}"!
                ;;
            afternoon)
                echo Good afternoon, "${name}"!
                ;;
            *)
                echo Unkown parameter: "${when}".
                ;;
        esac
    else
        echo Have a good day, "${name}"!
    fi
}

main "$@"
```

- output:

```
$ ./greet.sh -h

Usage:
greet.sh [option] <name>

Option:
    -h, --help
    -w, --when <morning|afternoon>

$ ./greet.sh -w morning James
Good morning, James!
$ ./greet.sh --when morning James Bond
Good morning, James Bond!
$ ./greet.sh James
Have a good day, James!
```
