Because user profiles contain user state and users can modify their state, users must have Write permissions to their user profiles. As long as users have Write permissions, they can write as much data as they want if there is available free disk space, unless an administrator limits them. Because user profiles contain user data and user data can increase rapidly.

For example, if users store large graphic or multimedia files in their Documents folder, which is in their profile, an administrator often limits the space for storing user profiles.

Administrators can do this in several ways:

 -  Use quotas to limit the space that is available to a user on a volume or on a shared folder where the roaming user profile is stored.
 -  Redirect folders that typically contain large user files and are stored in the user profile by default, for example, the Documents folder, outside of the user profile.
 -  Use the Group Policy setting to limit user profile sizes. You can limit the size of local or roaming user profiles by configuring settings in the user part of Group Policy.

#### Using quotas

An option to limit user profile sizes is to use quotas. You can use the same approach to limit the disk space that a user consumes in general, and it applies to limiting user profile sizes. You can set a disk quota on a local Windows volume by using volume properties. By using File Server Resource Manager in Windows Server 2016, you can set a quota on a shared folder on the file server where roaming user profiles or redirected folders are stored. If you set a disk quota on a local volume, users will not be able to write additional data when they reach their disk quota. If a quota is set on a shared folder, the local copy of a roaming user profile will not synchronize with the network share, and changes to the user profile will not copy to the file server until the user deletes some data and the local copy of the roaming user profile is smaller than the quota limit. In such cases, users will see a message during sign-out that their roaming user profiles did not completely synchronize, and an entry will be added to Event Viewer.

#### Redirecting folders out of user profiles

You can make user profiles smaller by redirecting folders that typically consume a lot of space out of the user profiles. When you do that, the redirected folders are available from any computer in AD DS even if the user is configured with a local user profile. You can configure Folder Redirection by using Group Policy, and several settings are available for each redirected folder. Even if you use Folder Redirection, you can also use quotas to limit the size of redirected folders.

#### Using Group Policy to limit user profile sizes

You can limit local or roaming user profile sizes by enabling the Limit profile size setting in the user part of Group Policy. When you enable this setting, you can configure the maximum profile size and custom message that users see periodically when their profiles exceed the allowed size. You can limit profile size to up to 30KBs. With local user profiles, users can be periodically reminded that their user profile exceeds the allowed size, but they can still write data to their profiles and sign out. If users are configured with roaming user profiles, they can also sign out, but changes to the local copy of the roaming user profile will not synchronize with the network share. This means that changes to their local copy of the user profile will not copy to the file server until the users delete some data and their local copy of the roaming user profile is smaller than the maximum profile size that is configured in Group Policy.

Users can have smaller user profiles if they store data files outside of their user profiles, for example, in a dedicated shared folder or in the home folder.
