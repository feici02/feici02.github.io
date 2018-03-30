---
layout: post
title:  "How to loop through an array of JSON object?"
tags: bash
---

Recently, I wrote a shell script, which needs to loop through an array of JSON object, and process them one by one.
Here is the code snippet for how I do it.

* names.json
```
{
    "names": [
        {
            "first": "James",
            "last": "Bond"
        },
        {
            "first": "Harry",
            "last": "Potter"
        }
    ]
} 
```

* test.sh 
```
i=0
jq -c '.names[]' names.json | while read -r name; do
    echo object "${i}":
    echo "${name}"
    ((i+=1))
done
```

* run
```
$ ./test.sh
object 0:
{"first":"James","last":"Bond"}
object 1:
{"first":"Harry","last":"Potter"}
```
The `-c` option of `jq` means:
> compact instead of pretty-printed output
