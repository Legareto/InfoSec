---
title: Active Directory (AD)
---
# Microsoft Active Directory (AD)

Microsoft's Active Directory is the backbone of the corporate world.

It simplifies the management of devices and users within a corporate environment.

The core of any Windows Domain is the **Active Directory Domain Service (AD DS)**. This service acts as a catalogue that holds the information of all of the "objects" that exist on your network.

AD support :

- user
- groups
- machines
- printers
- shares
- many others.

## Users

Users are one of the most common object types in Active Directory.

Users are one of the objects known as **security principals**, meaning that they can be authenticated by the domain and can be assigned privileges over resources like files or printers.

You could say that a security principal is an object that can act upon resources in the network.

Users can be used to represent two types of entities:

- People: users will generally represent persons in your organisation that need to access the network, like employees.
- Services: you can also define users to be used by services like IIS or MSSQL. Every single service requires a user to run, but service users are different from regular users as they will only have the privileges needed to run their specific service.

## Machines

For every computer that joins the Active Directory domain, a machine object will be created.

Machines are also considered "security principals" and are assigned an account just as any regular user. This account has somewhat limited rights within the domain itself.

The machine accounts themselves are local administrators on the assigned computer, they are generally not supposed to be accessed by anyone except the computer itself, but as with any other account, if you have the password, you can use it to log in.

- Note: Machine Account passwords are automatically rotated out and are generally comprised of 120 random characters.

**Identifying machine accounts** is relatively easy. They follow a **specific naming scheme**. The machine account name is the computer's name followed by a dollar sign. For example, a machine named `DC01` will have a machine account called `DC01$`.

## Security Groups

Security groups are also considered security principals and, therefore, can have privileges over resources on the network.

Groups can have both users and machines as members. If needed, groups can include other groups as well.

| Security Group     | Description                                                                                                                                               |
| ------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Domain Admins      | Users of this group have administrative privileges over the entire domain. By default, they can administer any computer on the domain, including the DCs. |
| Server Operators   | Users in this group can administer Domain Controllers. They cannot change any administrative group memberships.                                           |
| Backup Operators   | Users in this group are allowed to access any file, ignoring their permissions. They are used to perform backups of data on computers.                    |
| Account Operators  | Users in this group can create or modify other accounts in the domain.                                                                                    |
| Domain Users       | Includes all existing user accounts in the domain.                                                                                                        |
| Domain Computers   | Includes all existing computers in the domain.                                                                                                            |
| Domain Controllers | Includes all existing DCs on the domain.                                                                                                                  |


## Configure Users and Computers

To configure users, groups or machines in Active Directory, we need to log in to the Domain Controller and run "Active Directory Users and Computers".

Objects are organised in **Organizational Units (OUs)** which are container objects that allow you to classify users and machines.

OUs are mainly used to define sets of users with similar policing requirements.

The people in the Sales department of your organisation are likely to have a different set of policies applied than the people in IT, for example.

Keep in mind that **a user can only be a part of a single OU at a time**.

Example :

![Organizational Units - OU](/knowledge/assets/ad-ou-thm.png)

> Checking our machine, we can see that there is already an OU called `THM` with four child OUs for the IT, Management, Marketing and Sales departments. It is very typical to see the OUs mimic the business' structure, as it allows for efficiently deploying baseline policies that apply to entire departments. Remember that while this would be the expected model most of the time, you can define OUs arbitrarily.

## Default containers

There are other default containers. These containers are created by Windows automatically and contain the following:

- **Builtin:** Contains default groups available to any Windows host.
- **Computers:** Any machine joining the network will be put here by default. You can move them if needed.
- **Domain Controllers:** Default OU that contains the DCs in your network.
- **Users:** Default users and groups that apply to a domain-wide context.
- **Managed Service Accounts:** Holds accounts used by services in your Windows domain.

## Security Groups vs OUs

- **OUs** are handy for **applying policies to users and computers**, which include specific **configurations** that pertain to sets of users depending on their particular role in the enterprise. Remember, a user can only be a member of a single OU at a time, as it wouldn't make sense to try to apply two different sets of policies to a single user.

- **Security Groups**, on the other hand, are used to **grant permissions over resources**. For example, you will use groups if you want to allow some users to access a shared folder or network printer. A user can be a part of many groups, which is needed to grant access to multiple resources.

## Managing Users in AD

By default, OUs are protected against accidental deletion. To delete the OU, we need to enable the Advanced Features in the View menu:

![AD Advanced Features](/knowledge/assets/ad-advanced-features.png)

![AD Advanced Features Properties](/knowledge/assets/ad-advanced-features-2.png)

## Delegation

One of the nice things you can do in AD is to **give specific users some control over some OUs**. This process is known as **delegation** and allows you to grant users specific privileges to perform advanced tasks on OUs without needing a Domain Administrator to step in.

![AD Delegate Control](/knowledge/assets/ad-delegate-control.png)

Example PowerShell to reset password:

`Set-ADAccountPassword -Identity <User Name> -Reset -NewPassword (Read-Host -AsSecureString -Prompt 'New Password') -Verbose`

## Managing Computers in AD
