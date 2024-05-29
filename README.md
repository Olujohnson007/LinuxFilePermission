# LinuxFilePermission
File permissions in Linux
Project description
The research team at my organization requires an update to the file permissions for specific files and directories within the projects directory. The current permissions do not align with the necessary authorization levels, which is essential for maintaining system security. To address this, I undertook the following actions:

Check file and directory details
The following code illustrates how I utilized Linux commands to inspect the existing permissions configured for a specific directory in the file system.
![image](https://github.com/Olujohnson007/LinuxFilePermission/assets/169572108/fcacd822-1692-4058-81ee-e86a1e29c321)


The first line of the screenshot shows the command I entered, while the subsequent lines show its output. The ls -la command lists all contents of the projects directory, including hidden files, with detailed information. The output reveals one directory named drafts, one hidden file named .project_x.txt, and five other project files. The 10-character string in the first column indicates the permissions for each file or directory.
Describe the permissions string
1. `drwxr-xr-x`:
   - `d`: Directory
   - `rwx`: Owner has read, write, and execute permissions
   - `r-x`: Group has read and execute permissions
   - `r-x`: Others have read and execute permissions
 2. `drwxr-xr-x`:
   - `d`: Directory
   - `rwx`: Owner has read, write, and execute permissions
   - `r-x`: Group has read and execute permissions
   - `r-x`: Others have read and execute permissions
 3. `-rw-------`:
   - `-`: Regular file
   - `rw-`: Owner has read and write permissions
   - `---`: Group has no permissions
   - `---`: Others have no permissions
 4. `drwx------`:
   - `d`: Directory
   - `rwx`: Owner has read, write, and execute permissions
   - `---`: Group has no permissions
   - `---`: Others have no permissions
 
5. `-rw-rw-rw-`:
   - `-`: Regular file
   - `rw-`: Owner has read and write permissions
   - `rw-`: Group has read and write permissions
   - `rw-`: Others have read and write permissions
 6. `-rw-r-----`:
   - `-`: Regular file
   - `rw-`: Owner has read and write permissions
   - `r--`: Group has read permission
   - `---`: Others have no permissions
 7. `-rw-rw-r--`:
   - `-`: Regular file
   - `rw-`: Owner has read and write permissions
   - `rw-`: Group has read and write permissions
   - `r--`: Others have read permission
 8. `-rw-rw-r--`:
   - `-`: Regular file
   - `rw-`: Owner has read and write permissions
   - `rw-`: Group has read and write permissions
   - `r--`: Others have read permission
Change file permissions
The organization determined that others should not have write access to any of their files. To comply with this directive, I reviewed the file permissions that were previously listed. I identified that write access needed to be removed for others on `project_k.txt`.
The following code demonstrates how I used Linux commands to do this:
![image](https://github.com/Olujohnson007/LinuxFilePermission/assets/169572108/13503808-dde1-4b6a-9ef4-f99cb378595e)

 
 The initial two lines of the screenshot show the commands I entered, while the subsequent lines present the output of the second command. The chmod command is used to modify the permissions on files and directories. The first argument specifies the changes to the permissions, and the second argument designates the target file or directory. In this instance, I removed write permissions for others on the project_k.txt file. Following this, I used ls -la to verify the updates I made
 Change file permissions on a hidden file
The research team at my organization recently archived project_x.txt and determined that write access should be restricted for all users. However, both the user and group should retain read access.
 The following code illustrates how I utilized Linux commands to modify the file permissions accordingly:
 ![image](https://github.com/Olujohnson007/LinuxFilePermission/assets/169572108/e44dad40-fb0b-469c-951c-c8f30f59a226)


The initial two lines of the screenshot show the commands I entered, while the subsequent lines display the output of the second command. The file .project_x.txt is recognized as a hidden file because its name begins with a period (.). In this example, I modified the permissions to remove write access for both the user and group, while ensuring the group has read access. Specifically, I removed write permissions from the user with u-w, removed write permissions from the group with g-w, and added read permissions to the group with g+r.

Change directory permissions
My organization requires that only the researcher2 user has access to the drafts directory and its contents. Consequently, no one other than researcher2 should have execute permissions.
The following code illustrates how I used Linux commands to change the permissions:
![image](https://github.com/Olujohnson007/LinuxFilePermission/assets/169572108/0520b581-18ff-4dc8-9303-3045b153b4a8)


 The first two lines of the screenshot show the commands I entered, while the subsequent lines display the output of the second command. Upon determining that the group had execute permissions, I used the chmod command to remove them. Since the researcher2 user already had execute permissions, no further modifications were necessary.
Summary
I configured various permissions to align with my organization’s desired authorization levels for files and directories within the projects directory. Initially, I used ls -la to review the current permissions, which guided my subsequent actions. I then utilized the chmod command multiple times to modify the permissions on the relevant files and directories accordingly.
