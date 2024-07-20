# File Permissions in Linux

## Project Description

This project focuses on managing file permissions within a Linux system. The primary goal was to update the file permissions for specific files and directories within the projects directory to enhance system security. This document details the steps taken to check and update these permissions.

## Tasks Performed

### Check File and Directory Details

The following command was used to list the details of files and directories, including hidden files, within the `projects` directory:

```bash
ls -la
```

![ls -la Command](images/ls-la.png)

The command output displays a detailed listing of the file contents, including hidden files. The first column's 10-character string represents the permissions set on each file or directory.

### Describe the Permissions String

The 10-character string can be deconstructed to determine access permissions:

- **1st character**: Indicates the file type (d for directory, - for regular file).
- **2nd-4th characters**: Read (r), write (w), and execute (x) permissions for the user.
- **5th-7th characters**: Read (r), write (w), and execute (x) permissions for the group.
- **8th-10th characters**: Read (r), write (w), and execute (x) permissions for others.

Example: The permissions for `project_t.txt` are `-rw-rw-r--`.

### Change File Permissions

The organization determined that "others" should not have write access to any files. For `project_k.txt`, write access for others was removed using the following command:

```bash
chmod o-w project_k.txt
```

![chmod Command](images/chmod.png)

### Change Permissions on a Hidden File

For the hidden file `.project_x.txt`, the following commands were used to adjust permissions:

```bash
chmod u-w .project_x.txt
chmod g-w .project_x.txt
chmod g+r .project_x.txt
```

![Hidden File Permissions](images/hidden-file-permissions.png)

### Change Directory Permissions

The `researcher2` user was given exclusive access to the `drafts` directory:

```bash
chmod g-x drafts
```

![Directory Permissions](images/directory-permissions.png)

## Summary

This project involved checking and updating file and directory permissions in the `projects` directory. The steps included:

1. Checking existing permissions with `ls -la`.
2. Changing permissions using the `chmod` command to match the desired level of authorization.
