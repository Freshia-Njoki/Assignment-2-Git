# Gitignore Cheatsheet

The `.gitignore` file is used to specify intentionally untracked files to ignore. It uses glob patterns to match files and directories.

### Rules for Matching Patterns in .gitignore Files

| Pattern            |                                             Explanations/Matches                                             |                                                                Examples |
| ------------------ | :----------------------------------------------------------------------------------------------------------: | ----------------------------------------------------------------------: | --- |
| \*\*/lib/name.file |    Starting with \*\* before / specifies that it matches any folder in the repository. Not just on root.     |                                      /lib/name.file /test/lib/name.file |
| lib/name.file      | Patterns specifying files in specific folders are always relative to root (even if you do not start with / ) |                                                          /lib/name.file |
| \*\*/name          |                          All name folders, and files and folders in any name folder                          |                    /name/log.file /lib/name/log.file /name/lib/log.file |
| /lib/\*\*/name     |              All name folders, and files and folders in any name folder within the lib folder.               | /lib/name/log.file /lib/test/name/log.file /lib/test/ver1/name/log.file |
| \*.file            |                                       All files withe .file extension                                        |                                               /name.file /lib/name.file |
| \*.log             |                                            ignore ALL .log files                                             |                                                                    .log |
| \*.temp            |                                            ignore all .temp files                                            |                                                                   .temp |
|                    |                                           Blank lines are ignored                                            |                                                                         |
| name               |                    All name files, name folders, and files and folders in any name folder                    |                                  /name.log /name/file.txt /lib/name.log |
| name/              |    Ending with / specifies the pattern is for a folder. Matches all files and folders in any name folder     |                                       /name/file.txt /name/log/name.log |     |
| /name.file         |                 Starting with / specifies the pattern matches only files in the root folder                  |                                                              /name.file |
| name.file          |                                         All files with the name.file                                         |                                               /name.file /lib/name.file |
| lib.name.file      | Patterns specifying files in specific folders are always relative to root (even if you do not start with / ) |                                                          /lib/name.file |
| `logs/`            |                                        Matches the "logs" directory.                                         |                                                                 `logs/` |
| `!important.log`   |                            Excludes the "important.log" file from being ignored.                             |                                                        `!important.log` |
| `# Comment`        |                         Lines starting with a hash (#) are comments and are ignored.                         |                                              `# Ignore temporary files` |
