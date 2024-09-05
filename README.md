# Managing File Permissions Using Linux Commands 
![Badge](https://www.bitslovers.com/wp-content/uploads/sites/5/2021/06/linux-file-permission.png)

## Project Description

The research team at my organization needs to revise the file permissions for specific files and directories within the projects directory. 
The current permissions don't accurately reflect the required authorization levels. Verifying and updating these permissions will enhance the security of their system.
To carry out this task, I completed the following 4 steps:

### 1- Check file and directory details

The following code demonstrates how I used Linux commands to determine the existing permissions set for a specific directory in the file system.

![image](https://github.com/user-attachments/assets/0117a524-58c5-4718-8122-eef2256d4ab2)

The first line of the screenshot shows the command I input, while the remaining lines display the output. The command lists all items in the `projects` directory. 
I used the `ls` command with the `-la` option to generate a detailed list of the contents, including hidden files. 
The output reveals one directory called `drafts`, a hidden file named `.project_x.txt`, and five other project files. 
The 10-character string in the first column represents the permissions assigned to each file or directory.

###  Describing the permissions string

The 10-character string can be broken down to identify who has access to the file and what specific permissions they have. Here's what each character represents:

**1st character:** Either a `d` or a hyphen (`-`), indicating the file type. `d` means it's a directory, while `-` means it's a regular file.

**2nd-4th characters:** Represent the read (`r`), write (`w`), and execute (`x`) permissions for the user. A hyphen (`-`) in place of any of these means the permission is not granted.

**5th-7th characters:** Indicate the read (`r`), write (`w`), and execute (`x`) permissions for the group. A hyphen (`-`) means that permission is denied for the group.

**8th-10th characters:** Show the read (`r`), write (`w`), and execute (`x`) permissions for others, which include all users outside the user and group. A hyphen (`-`) means no permission is given.

For example, the permissions for `project_t.txt` are `-rw-rw-r--`. The first character being a hyphen (`-`) indicates it's a regular file. 
The second, fifth, and eighth characters are `r`, showing that the user, group, and others all have read permissions. 
The third and sixth characters are `w`, meaning the user and group can write to the file. No one has execute permissions, as there are no `x` characters.

### 2- Change file permissions

The organization decided that others should not have write access to any of their files. To align with this policy, I reviewed the file permissions I had previously retrieved. 
I identified that write access needed to be removed for others on `project_k.txt`.

The code below shows how I used Linux commands to accomplish this:

![image](https://github.com/user-attachments/assets/e8d7ec80-a927-4a4f-a17a-3de665af2297)

The first two lines of the screenshot show the commands I entered, while the remaining lines display the output of the second command. 
The `chmod` command is used to modify permissions on files and directories. The first argument specifies the permission changes, and the second argument identifies the file or directory. 
In this case, I removed write permissions for others on the `project_k.txt` file. Afterward, I ran `ls -la` to verify the changes I made.

### 3- Change file permissions on a hidden file

The research team at my organization recently archived `project_x.txt` and wants to ensure that no one has write access to the file, 
while the user and group should still retain read access.

The code below shows how I used Linux commands to adjust the permissions:

![image](https://github.com/user-attachments/assets/73d24f8d-6f43-4f15-b2f8-3c6314c77626)

The first two lines of the screenshot show the commands I entered, while the remaining lines show the output of the second command. 
The file `.project_x.txt` is hidden because it begins with a period (`.`). In this instance, I removed write permissions from both the user and the group, and granted read permissions 
to the group. I removed write permissions from the user using `u-w`, then did the same for the group with `g-w`, and finally added read permissions for the group with `g+r`.

### 4- Change directory permissions

My organization requires that only the user `researcher2` has access to the `drafts` directory and its contents. Therefore, no one else should have execute permissions.

The code below illustrates how I used Linux commands to update the permissions:

![image](https://github.com/user-attachments/assets/c2c2661b-f75b-483e-a68f-d36067e96cf6)

The output here shows the permission listing for the contents within the `drafts` directory. 
Line 1 denotes the current directory (`drafts`), represented by a single dot (`.`), while Line 2 refers to the parent directory (`home`), represented by two dots (`..`).

![image](https://github.com/user-attachments/assets/4aca359e-48ea-4432-bd98-bc4d4ddd3d22)

My organization decided that only the `researcher2` user should have access to the `drafts` directory and its contents. 
Since the group had execute permissions, I used the `chmod` command to remove them. The `researcher2` user already had execute permissions, so no additional changes were needed for them.
I then used the `ls` command with the `-la` option to confirm the changes made.

## Summary

I adjusted various permissions to align with the authorization levels required by my organization for files and directories in the projects directory. 
The initial step involved using `ls -la` to review the existing permissions, which guided my subsequent actions. 
I then utilized the `chmod` command multiple times to modify the permissions for the files and directories.





