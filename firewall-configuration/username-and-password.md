# To change the username and password on a Palo Alto Networks firewall, you need to access the device's management interface, either through the web interface (Panorama or the firewall's GUI) or via the command-line interface (CLI). Below are the steps for both methods:
##Method 1: Changing Username and Password via Web Interface (GUI)
Log in to the Firewall:
--------------------------------------------------------------------------------------------------
**Open a web browser and navigate to the management IP address of your Palo Alto firewall.
Log in with an account that has administrative privileges.
Navigate to the User Account Settings:
Go to Device > Administrators.

This will display a list of all user accounts configured on the firewall.

Edit the User Account:
Select the user account you want to modify.

Click the Edit (pencil icon) button.

Change the Username:
Update the Username field if you want to change the username.

Change the Password:

Enter the new password in the Password and Confirm Password fields.
Ensure the password meets the complexity requirements.

Save Changes:

Click OK to save the changes.**
-------------------------------------------------------------------

##Method 2: Changing Username and Password via CLI

Log in to the Firewall via SSH or Console:
Use an SSH client (e.g., PuTTY) or a console cable to access the firewall's CLI.
Log in with an account that has administrative privileges.
Enter Configuration Mode:
Type configure and press Enter to enter configuration mode.
Change the Username (Optional):
To change the username, you need to delete the existing user and create a new one with the desired username.
Delete the existing user:
Copy
`delete shared admin <old-username>`
Create a new user with the updated username:
Copy
`set shared admin <new-username> superuser`
Change the Password:
Set the password for the user:
Copy
`set shared admin <username> password`
You will be prompted to enter and confirm the new password.
commit the Changes:
Commit the configuration changes:
Copy
commit
Save the Configuration:
Save the configuration to make it persistent:
Copy
save
Notes:
Password Complexity Requirements: Palo Alto firewalls enforce password complexity rules. Ensure your new password meets these requirements (e.g., minimum length, uppercase, lowercase, numbers, and special characters).

Superuser Access: Only users with superuser privileges can modify other user accounts.

Backup Configuration: Before making changes, consider backing up the configuration in case you need to revert.
