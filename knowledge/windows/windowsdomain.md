# Windows domain

Windows domain is a group of users and computers under the administration of a given business.

The main idea behind a domain is to centralise the administration of common components of a Windows computer network in a single repository called Active Directory (AD).

The server that runs the Active Directory services is known as a [Domain Controller (DC)](/knowledge/windows/domaincontroller.md).

![Domain controlller](/knowledge/assets/domaincontroller.pngdomaincontroller.png)

The main advantages of having a configured Windows domain are:

- **Centralised identity management:** All users across the network can be configured from Active Directory with minimum effort.
- **Managing security policies:** You can configure security policies directly from Active Directory and apply them to users and computers across the network as needed.

Example :

> In school/university networks, you will often be provided with a username and password that you can use on any of the computers available on campus. Your credentials are valid for all machines because whenever you input them on a machine, it will forward the authentication process back to the Active Directory, where your credentials will be checked. Thanks to Active Directory, your credentials don't need to exist in each machine and are available throughout the network.
