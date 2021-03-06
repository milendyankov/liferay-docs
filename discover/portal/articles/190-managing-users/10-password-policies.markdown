# Password Policies [](id=password-policies)

Password policies enforce password rules to help users specify secure passwords.
Use the default policy that ships with Liferay (modified or as is), or create
your own policies. Password policies can be assigned to Users or Organizations,
or set as the default policy used throughout a virtual instance. 

## Adding and Configuring Password Policies [](id=adding-and-configuring-password-policies)

To add or edit password policies, 

1.  Navigate to *Control Panel* &rarr; *Users* &rarr; *Password Policies*. 

    There's already a default password policy in the system. 

2.  Edit this the same way you edit other resources: click *Actions*
    (![Actions](../../images/icon-actions.png)) and then click *Edit*. 

3.  To add a new policy, click the *Add*
    (![Add](../../images/icon-add.png)) button.

    Provide the *Name* (required), *Description*, and specific configuration options
    for your new password policy.

![Figure 1: You can create new password policies to suit your needs.](../../images/password-policy-add.png)

There are several configuration categories.

**Password Changes** 
: Allow or disallow users to change their passwords, and set a time limit on the
validity of password reset links.

**Password Syntax Checking** 
: If enabled, require users to use a certain syntax when choosing a password.
You can disallow dictionary words, set a minimum length, and more in this
section.

**Password History** 
: If enabled, decide how many passwords to keep in the history, preventing users
from reusing an old password.

**Password Expiration** 
: Decide whether to expire passwords after a specified time. If enabled, specify
how long passwords are valid, when and whether to send a warning, and how many
times the user can log in after the password is expired before needing to set a
new password (called a *Grace Limit*). 

**Lockout** 
: If enabled, set a maximum number of failed authentication attempts before the
account is locked, how long the number of attempts is stored, and the lockout
duration.

**Self Destruct** 
: If enabled, set the time after lockout before Liferay self destructs
catastrophically, sending the world into apocalyptic chaos, out of which
self-aware robots arise and recolonize the world, enslaving the surviving
remnant of humanity for their own nefarious purposes. We recommend you keep this
disabled.

Just making sure you were paying attention; that last one doesn't actually
exist. 

Once you configure the policy, click *Save* to add it to the list of
ready-to-use password policies.

## Assigning Users to a Password Policy [](id=assigning-users-to-a-password-policy)

To use the default password policy, you don't have to do anything: like its name
suggests, it's the default. If you create a new password policy, however, you
must assign users to it. To do this click *Actions*
(![Actions](../../images/icon-actions.png)) &rarr; *Assign Members*.

![Figure 2: Assign members to new password policies to make them take effect.](../../images/password-policy-assign-members.png)

Choose whether to assign users directly or to assign organizations to the
password policy, then click *Add* (![Add](../../images/icon-add.png)).

Once assignments are saved, the password policy is in effect. Did you know you
can change the default password policy and configure it using Liferay's
`portal.properties` file?

## Default Policy Properties [](id=default-policy-properties)

The Default Password Policy is set as the default and configured in Liferay's
[portal.properties](@platform-ref@/7.1-latest/propertiesdoc/portal.properties.html#Passwords)
file. Find the properties that start with `passwords.default.policy`. To make
changes, including changing the default policy, add whichever properties and
values you choose to modify in your `portal-ext.properties` file, as usual.
Restart the application server and your changes take effect.

    #
    # Set the properties of the default password policy.
    #

    ...
    passwords.default.policy.name=Default Password Policy
    ...

As you can see, Password Policies give you a simple yet powerful way to set
password rules.
