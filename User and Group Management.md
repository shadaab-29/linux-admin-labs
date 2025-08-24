Linux User Management Commands
useradd [options] username

Purpose: This command creates a new user account. It's the primary way to add users to the system.

Details: By default, it creates a new user but doesn't create a home directory or set a password. The -m option is commonly used to create the user's home directory (/home/username).

Example: sudo useradd -m jdoe (creates a user named jdoe with a home directory).

passwd [username]

Purpose: Used to set or change a user's password.

Details: When run by a regular user, it changes their own password. An administrator (using sudo or as root) can set or change any user's password.

Example: sudo passwd jdoe (prompts to set a new password for the jdoe user).

usermod [options] username

Purpose: Modifies an existing user account.

Details: This is a versatile command for changing user attributes.

-l new_username: Changes the login name.

-g new_groupname: Changes the primary group.

-aG supplementary_group: Appends the user to a new supplementary group.

Example: sudo usermod -aG sudo jdoe (adds jdoe to the sudo group, granting administrative privileges).

userdel [options] username

Purpose: Deletes a user account from the system.

Details: By default, it only removes the user's entry from the system files. The -r option is crucial for removing the user's home directory and mail spool, which is often a desired action to clean up the system fully.

Example: sudo userdel -r jdoe (deletes the user jdoe and their home directory).

id [username]

Purpose: Displays the User ID (UID), Group ID (GID), and the groups a user belongs to.

Details: This is an essential command for verifying a user's identity and group memberships, which are critical for file permissions and access control.

Example: id jdoe (outputs something like uid=1001(jdoe) gid=1001(jdoe) groups=1001(jdoe),27(sudo)).

su - [username]

Purpose: Switches to another user account.

Details: The su command alone switches to the root user without loading their environment. The hyphen - is a critical flag that loads the target user's complete environment, including their home directory and path variables, which is standard practice.

Example: su - jdoe (switches to the jdoe user, loading their full environment).




Linux Group Management Commands
groupadd [groupname]

Purpose: Creates a new group.

Details: Creates a new group entry in the /etc/group file, allowing you to organize users for permissions.

Example: sudo groupadd developers (creates a new group named developers).

groupmod [options] groupname

Purpose: Modifies an existing group's attributes.

Details: The most common use is to change a group's name using the -n option.

Example: sudo groupmod -n dev_team developers (renames the developers group to dev_team).

gpasswd [options] groupname

Purpose: Administers /etc/group and /etc/gshadow files. It's often used for managing group members.

Details: This command provides more granular control over group membership.

-a username: Adds a user to the specified group.

-d username: Removes a user from the specified group.

-r: Removes the group's password.

Example: sudo gpasswd -a jdoe developers (adds the user jdoe to the developers group).

groupdel [groupname]

Purpose: Deletes a group from the system.

Details: This command removes a group entry from /etc/group. It's important to note that it doesn't remove users who are members of that group.

Example: sudo groupdel developers (deletes the developers group).

groups [username]

Purpose: Displays the groups a user is a member of.

Details: If no username is specified, it shows the groups of the current user. It's a quick way to check a user's memberships.

Example: groups jdoe (outputs all groups that the user jdoe belongs to).