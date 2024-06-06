---
title: The Complete Configuration
date: 2024-06-07 12:00:00 +0600
categories: [LewsionPBX]
tags: [pbx,voip,communication,configuration]     # TAG names should always be lowercase
author: afrin
---
# Peresenting The Complete Configuration Guide in Details

## 1. User Configuration: 

It's important to add user before you create extention, ring group, call center, IVR menu etc. To add your users --
    
    - Go to: Dashboard >> Accounts >> Users

Then click on the **Add** button on the top right corner.Fill in the blank boxes with proper informations. To delete any user select the check box by the side of that user and click on **Delete** on the top of the page.
     
- #### Username: 
Provide the name of the user.
- #### Password: 
Enter the Password for the user.
- #### Confirm Password:
Confirm the password by entering it again.
- #### Email:
Provide the email address of that user.
- #### Language:
Select Language from the dropdown box.
- #### Time Zone:
Select the Time zone from the dropdown box. (For BD:Asia/Dhaka)
- #### Status:
Select status from the dropdown box.
- #### Contact:
Select a contact from dropdown.
- #### Groups:
Select **User** from dropdown box.


## 2. Extensions Configuration: (Basic)
        - Go to: Dashboard >> Accounts >> Extentions

Then click on the **Add** button on the top right corner.

- #### Extension
Enter the alphanumeric extension. The default configuration allows 2 - 15 digit extensions.Example: 100,102,80.

- #### User
Add a user to assign the extension to the user.

- #### Voicemail Password
Enter the numeric voicemail password here.

- #### Device Provisioning
Select a device and line number to assign to this extension.

- #### Voicemail Enabled
Enable/disable voicemail for this extension.

- #### Voicemail Mail To
Enter the email address to send voicemail to (optional).

- #### Transcription Enabled
Choose if voicemail transcription is enabled for this extension

- #### Voicemail File
Select a listening option to include with the email notification.

- #### Voicemail Keep Local
Choose whether to keep the voicemail in the system after sending the email notification.

- #### Missed Call
Select the notification type, and enter the appropriate destination.

- #### Toll Allow
Enter the toll allow value here. (Examples: domestic,international,local)

- #### Call Timeout
Enter the ring time (delay in seconds) before sending a call to voicemail.

- #### Call Group
Enter the user call group here. Groups available by default: sales, support, billing.

- #### Hold Music
Select the MOH (Musin On Hold) Category here.

- #### Language
Select the language, voice and dialect.

- #### Type
Select Default to enable registration or to disable registration select Virtual.

- #### Description
Enter the description.

## 3. IVR Menu Configurations

- #### Upload recording
     
      -Go to Applications ->> Recordings

    - Click on **Add** button and upload recording in **.wav** format.

 - #### IVR setup
    
       -Go to Applications ->> IVR Menus
        

     - Click on **Add** button
     -  #### Name:
        Enter a name for the IVR menu.
     - #### Extension
        Enter the extension number.
     - #### Greet Long
       The long greeting is played when entering the menu.
     - #### Greet Short
       The short greeting is played when returning to the menu.
     - #### Options
       Define caller options for the IVR menu. In the "Option" box, write the user number. In the "Destination" box select the destination, where call will be routed after dialing the number by user. In the destination you can choose ring group, call center, voice mail etc.
     - #### Timeout
       The number of milliseconds to wait after playing the greeting or the confirm macro.
     - #### Exit Action
       Select the exit action to be performed if the IVR exits.
     - #### Direct Dial
       Define whether callers can dial directly to registered extensions.
     - #### Ring Back
       Defines what the caller will hear while the destination is being called.
     - #### Caller ID Name Prefix
       Set a prefix on the caller ID name. It will show on the device of the employee before recieving calls to notify them about from where the call is ringing.
     - #### Enabled
       Set the IVR Status.
     - #### Description
       Enter the description.

## 4. Ring Group Configurations
A ring group is a set of destinations that can be called with a ring strategy.
  
      -Go to Applications ->> Ring groups

- Click on **Add** button.
- #### Name
  Enter a Name for the Ring Group.
- #### Extension
  Enter a Extension for the Ring Group.
- #### Greeting
  Select a greeting recording from the dropdown box. To upload new recording see the recording upload part above of this documentation.
- #### Strategy

   - **Simultaneous:** Rings all destinations. All destination share the same thread.

    - **Sequence:** Calls destinations in sequence where order that is lower goes first.

    - **Enterprise:** Ring all destinations. Each destination uses its own thread.

    - **Rollover:** Calls destinations in sequence and skips busy destinations.

    - **Random:** A random destination will ring.

- ####  Destinations
    The destination numbers are the numbers for the ring group to call. Destinations can only be local registered endpoints or external numbers.
     
    - **Extensions:** Local registered extensions.

    - **External numbers:** Destinations out to an external number.

- #### Prompt 
   Where you determine if the call must have a dial to confirm before a pickup event. Change it to **Confirm** and don't forget to save.
- #### Timeout Destination
  Select a Timeout destination. It can be IVR, Voicemail, Hangup etc. 
- #### Call Timeout
  Input the value in Seconds. The amount of time will the call ring before going to Timeout Destination.
- #### User List
  Define users assigned to this ring group. Every time you add a user, click on **Save** button on the top right corner and then add another user.
- #### Call Forward
  Choose to follow a ring group destination's call forward.
- #### Missed Call
  Select the notification type, and enter the appropriate destination. You can choose **Email** option and add your Email to get notification of missed calls.
- #### Ring Group Forward
  Forward a called Ring Group to an alternate destination.you have to first **Enable** the option and then give the credential of forwarding the calls.
- #### Enabled
  Toogle the bar to enable and disable the ring group. Don't forget to click the **Save** Button after changing any settings.
- #### Description
  Write a Description.