# DATA 515A HW1
Homework 1: Bash and Data Essentials
Due: Tuesday Apr 3, midnight PDT

This homework combines developing facility with command line tools and some of the data essentials. The homework uses youtube data from Kaggle.

* (3 points) Create a text file called `homework1.sql` that has SQL that operates on the `class.db` database in the Lectures repository. Your code should be in a text file that is executed by `executeSQL.sh`. The SQL should construct a query that returns data that contains the `video_id, category_id, language` (one of  ‘us’, ‘gb’, ‘fr’, ‘de’, ‘ca’).
* * Hint: Since `language` is not a column in the existing tables, you must construct it. For example, for the `language` = ‘us’ you might use `select video_id, category_id, ‘us’ as language from USvideos`
* Create a second file called `homework1.txt` and enter text to answer the following questions:
* * (2 points) What column or columns in #1 are a minimal key? (By minimal is meant that no column can be removed and the result will still be a key.)
* * (2 points) What test can you perform to see if columns in #2 are a key? Are a minimal key?

File `executeSQL.sh`

```bash
#!/bin/bash
# Runs the SQL provided
sqlite3 << EOF
.read $1
.exit
EOF
```

