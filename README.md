# Fine-Grained Password Policies (FGPP) in Active Directory

In this tutorial, we configure a Fine-Grained Password Policy (FGPP) in an Active Directory environment to apply more restrictive password and account lockout requirements to privileged accounts. Unlike the Default Domain Policy, Fine-Grained Password Policies allow specific password requirements to be assigned to individual users or groups. This lab uses VMware Workstation with one Domain Controller and two Windows client virtual machines to demonstrate how different security requirements can be applied to specific groups within a domain.

## Environments and Technologies Used

* VMware Workstation
* Windows Server
* Active Directory Domain Services (AD DS)
* Active Directory Administrative Center
* Fine-Grained Password Policies (FGPP)
* Active Directory Users and Computers
* Windows Command Line

## Operating Systems Used

* Windows Server
* Windows 10

## Actions and Observations

### 1. Open Active Directory Administrative Center

* Open **Active Directory Administrative Center** on the Domain Controller.
* Select the domain name from the navigation pane.
* Navigate to:

  **System**
  → **Password Settings Container**

The Password Settings Container contains the Fine-Grained Password Policies configured for the domain.

### 2. Create a Fine-Grained Password Policy

* In the top-right corner, select:
  **New**
* Select:
  **Password Settings**
* Name the policy:
  **Admin Password Policy**

### 3. Configure Password Requirements

Configure the following password settings:

* **Precedence:** `1`
* **Minimum password length:** `15 characters`
* **Password history:** `3 passwords remembered`

Setting the precedence to **1** gives this policy the highest precedence when multiple Fine-Grained Password Policies could apply to the same user.

The 15-character minimum password length requires members of the targeted group to use longer passwords, while password history prevents users from immediately reusing their previous passwords.

### 4. Configure the Account Lockout Settings

* Locate:
  **Enforce Account Lockout Policy**
* Check the option to enable the setting.
* Set the number of failed login attempts to:
  **3**

This provides a more restrictive account lockout threshold for the targeted privileged accounts.

### 5. Apply the Policy to the Administrators Group

* Locate the option to add users or groups to the policy.
* Select:
  **Add**
* Choose the group that should receive the policy.
* For this lab, select the:
  **ADMINS** group
* Confirm the group selection and save the password policy.

The policy will now apply specifically to members of the targeted group rather than applying the settings to every user in the domain.

Example Active Directory s

