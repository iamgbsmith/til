# Bind To Active Directory

__Category: Mac__

Integrate your Mac with Microsoft Active Directory (AD) using the process outlined below.

### Bind macOS to Active Directory

1.	Login to your Mac as an Administrator
2.	Open __System Preferences__ and select __Users & Groups__
3.	Select the __Login Options__ menu in the sidebar and use the __Join__ button
4.	Enter the fully-qualified name of the AD domain you are binding to
5.	Enter your domain account credentials when prompted

### Modify Directory Services Settings

1.	From the __Login Options__ menu, edit the __Network Account Server__ settings
2.	Configure the __Force Local home directory on startup__ option
3.	Configure the __Use UNC path from Active Directory to derive network home location__
4.	Select __Mapping__ which specifies unique IDs for certain attributes that server to identify a computer account
5.	There will be three optional settings to choose from. Select whichever option is most applicable.
    - "Prefer this domain server"
    - "Allow administration by" 
    - "Allow authentication from any domain in the forest"