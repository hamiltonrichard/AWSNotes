# Configuring Self Service Management Capabilities in Amazon Workspaces

To enable self-service management capabilities for Amazon WorkSpaces, follow these steps in the AWS Management Console:

1. Open the WorkSpaces console at this link.
2. In the navigation pane, click on Directories.
3. Select your directory, and choose Actions, then click Update Details.
4. Expand the section for User Self-Service Permissions.
5. Enable or disable the following options as needed to determine the WorkSpace management tasks that users can perform directly from their WorkSpaces client:

* **Remember me:** Users can choose whether to cache their credentials on their client by selecting the “Remember Me” or “Keep me logged in” checkbox on the login screen. When credentials are cached, users can reconnect to their WorkSpaces without re-entering their credentials.
  
* **Restart WorkSpace from client:** Users can restart (reboot) their WorkSpace. Restarting disconnects the user from their WorkSpace, shuts it down, and reboots it. User data, operating system, and system settings remain unaffected.
  
* **Increase volume size:** Users can expand the root and user volumes on their WorkSpace to a specified size without contacting IT support. They can increase the size of the root volume (for Windows, the C: drive; for Linux, /) up to 175 GB, and the size of the user volume (for Windows, the D: drive; for Linux, /home) up to 100 GB. Keep in mind that WorkSpace root and user volumes come in predefined groups that cannot be changed.

* **Change compute type (bundle):** Users can switch the compute type (bundle) for their WorkSpace.

* **Switch running mode:** Users can change the running mode of their WorkSpace. This one allows the machine to be left on or powered off after some inactivity.

* **Rebuild WorkSpace:** Users can rebuild their WorkSpace.

**NOTE:** Review the [Workspaces Documentation](https://docs.aws.amazon.com/workspaces/) for additional details as some of these options do effect costs.

## Additional Resources
* [Best Practices for Deploying Amazon WorkSpaces Whitepaper](https://docs.aws.amazon.com/whitepapers/latest/best-practices-deploying-amazon-workspaces/best-practices-deploying-amazon-workspaces.html)

* Implementing Amazon WorkSpaces for High-Security Environments – [AWS Virtual Workshop Youtube Video](https://www.youtube.com/watch?v=HdCcXiZXV1s).
  
* [Slide deck download and video](https://pages.awscloud.com/Implementing-Amazon-WorkSpaces-for-High-Security-Environments_2022_VW_s52e01-SID_OD). Same video as mentioned above, Requires registration.
