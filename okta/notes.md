# CHAPTER 2 - WORKING WITH UNIVERSAL DIRECTORY

## USING GROUPS

- Groups are used to manage user access to mail accounts, fileservers, WiFi, applications, and so on, in bulk, instead of managing them individually on a case-by-case basis

- Types of groups:
	- `Everyone`
		- Default group that cannot be deleted or renamed
		- Assigning applications to this group allows everyone within Okta to gain access to the app, including any outside or third-party users that aren't part of the organization
		- It should be considered lowest in the hierarchy of policy setup as it will catch everyone
	- Okta
		- Standard grouping method within Okta Universal Directory, each having its own unique ID that is immutable and can be used in functions and API calls
		- Created from within Okta via the admin interface, and can be managed to do multiple things
		- Users can be assigned to groups, applications can be assigned, managing any provisioning for the assigned users
		- Directories can be attached to the groups, allowing users to be provisioned into the directory
	- Directory
	- Application


- How to assign applications to groups?
	- Any type of application can be added to any type of group in Okta
	- Depending on the type of application being provisioned, or the sign-on settings being configured, the group can be used in different combined methods
	- Adding Single-Sign On (SSO) applications based on their group

- What are the best practices for group usage in Okta?
	- Naming Okta groups - There is no nesting capability in Okta gorups. To still allow this to happen, it is recommended to name your Okta groups with a number in the front of it. This will allow the groups to float to the top, as Okta will show the gropus based on the naming order, helping you to determine the structure of these groups
	- Using the groups - A single group can do multiple things (such as assigning sales applications, sales policies, adn push into applications as the sales group)
	- Specific application groups - When you can't automate within the organizational structure use a range numbering for groups for applications to allow you to find and structure (for eg. creating a range higher up allows you to create group rules that send users to correct groups). Having that range will keep the Okta groups together, and stop them from floating into the abyss of all the groups imported into Okta
	- Import only on a need basis - 
	- Using directory groups - 

# CHAPTER 6 - CUSTOMIZING YOUR OKTA GUI

- 