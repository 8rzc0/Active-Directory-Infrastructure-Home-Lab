# Active Directory Infrastructure Home Lab

## Objective

The Active Directory Infrastructure Home Lab was created to build hands-on experience with Windows Server, PowerShell, and core network services. The lab focused on deploying an Active Directory domain, configuring DHCP, DNS, and RRAS/NAT, automating bulk user creation with PowerShell, and connecting a client to the domain.

### Skills Learned

- Configured Active Directory Domain Services on Windows Server 2022
- Configured internal DNS for domain resolution
- Configured RRAS/NAT to provide internet connectivity to an internal virtual network
- Created and configured a separate domain administrator account
- Used PowerShell to automate creation of approximately 1,000 Active Directory users
- Joined a client to the Active Directory domain and verified domain authentication
- Configured and authorized DHCP with scope, lease, and gateway settings
- Troubleshot a missing default gateway and renewed the client DHCP configuration

### Tools Used

- Windows Server 2022
- Windows 10
- Active Directory Domain Services
- Active Directory Users and Computers
- PowerShell
- DHCP
- DNS
- RRAS
- NAT
- VirtualBox

## Lab Implementation

### Domain Controller & Internal Network

Configured Windows Server 2022 as the domain controller with separate external and internal network interfaces and assigned static addressing to the internal network.

<img width="795" height="600" alt="VirtualBox_DC_15_09_2026_13_43_22" src="https://github.com/user-attachments/assets/54847e45-b97a-432b-a3e8-1b0fffbef7fc" />

*Ref 1: Configuring separate external and internal network adapters on the domain controller*

<img width="795" height="600" alt="VirtualBox_DC_15_09_2026_13_44_51" src="https://github.com/user-attachments/assets/9b7df3db-983d-4866-9a42-167a0372f835" />

*Ref 2: Assigning static IPv4 addressing to the internal network adapter*

### Active Directory Domain Services & Domain Configuration

Installed Active Directory Domain Services on Windows Server 2022, promoted the server to a domain controller, created a new forest, and configured the Active Directory domain.

<img width="795" height="600" alt="VirtualBox_DC_15_09_2026_13_46_29" src="https://github.com/user-attachments/assets/b748439c-1da6-4ad8-b819-240dab5427ab" />

*Ref 3: Opening the Add Roles and Features in Server Manager*

<img width="795" height="600" alt="VirtualBox_DC_15_09_2026_13_47_53" src="https://github.com/user-attachments/assets/c13b343b-e14d-40b9-a97b-4d8f94bc50b5" />

*Ref 4: Selecting the Active Directory Domain Services server role*

<img width="795" height="600" alt="VirtualBox_DC_15_09_2026_13_49_32" src="https://github.com/user-attachments/assets/8e54d934-b326-491f-a752-2bcac61f3f31" />

*Ref 5: Installing Active Directory Domain Services*

<img width="795" height="600" alt="VirtualBox_DC_15_09_2026_13_49_47" src="https://github.com/user-attachments/assets/1f913183-f8c5-4182-90b3-9fc993100160" />

*Ref 6: Starting the domain controller promotion process*

<img width="795" height="600" alt="VirtualBox_DC_15_09_2026_13_50_47" src="https://github.com/user-attachments/assets/f961160b-6941-411b-90ca-f41166cff4eb" />

*Ref 7: Creating a new Active Directory forest and domain*

<img width="795" height="600" alt="VirtualBox_DC_15_09_2026_13_52_57" src="https://github.com/user-attachments/assets/1e68d7b4-2ee1-47b5-be7a-93bca7f264a6" />

*Ref 8: Completing the domain controller promotion and domain configuration*

### Domain Administrator Account

Created a dedicated admin OU, created a separate user account, and added the account to the Domain Admins group to provide domain-level administrative privileges.

<img width="795" height="600" alt="VirtualBox_DC_15_09_2026_13_59_20" src="https://github.com/user-attachments/assets/8da6379c-7e69-43b6-a306-64c7bd00af28" />

*Ref 9: Opening Active Directory Users and Computers*

<img width="795" height="600" alt="VirtualBox_DC_15_09_2026_14_00_15" src="https://github.com/user-attachments/assets/c2d515f9-49c7-4fb3-9498-7d121cae4bf4" />

*Ref 10: Starting the creation of a new user account* 

<img width="795" height="600" alt="VirtualBox_DC_15_09_2026_14_01_48" src="https://github.com/user-attachments/assets/c6df355a-0829-4ea0-8d88-cb3a9f36f7b4" />

*Ref 11: Reviewing the new admin user account before creation*

<img width="795" height="600" alt="VirtualBox_DC_15_09_2026_14_03_54" src="https://github.com/user-attachments/assets/94064d83-1204-4e48-97d9-24db0e9d2ba0" />

*Ref 12: Starting the creation of a new OU*

<img width="795" height="600" alt="VirtualBox_DC_15_09_2026_14_04_26" src="https://github.com/user-attachments/assets/07506be1-6e1d-4f12-b9f8-14b3e220d7d8" />

*Ref 13: Creating the _ADMINS organizational unit*

<img width="795" height="600" alt="VirtualBox_DC_15_09_2026_14_05_47" src="https://github.com/user-attachments/assets/c550dc33-8d62-497c-b6d6-b58389400f10" />

*Ref 14: Moving the admin account into the _ADMINS organizational unit*

<img width="795" height="600" alt="VirtualBox_DC_15_09_2026_14_08_40" src="https://github.com/user-attachments/assets/013f06cc-b8f5-44e0-96a7-572fb53eb846" />

*Ref 15: Opening the admin account properties*

<img width="795" height="600" alt="VirtualBox_DC_15_09_2026_14_09_12" src="https://github.com/user-attachments/assets/2a7b61b2-3c0d-4429-a94d-4ad7ca772db2" />

*Ref 16: Reviewing the admin account's current group membership*

<img width="795" height="600" alt="VirtualBox_DC_15_09_2026_14_09_29" src="https://github.com/user-attachments/assets/7bb6ecf7-39eb-49a9-9a9e-3a8833ea5d96" />

*Ref 17: Adding the admin account to the Domain Admins group*

<img width="795" height="600" alt="VirtualBox_DC_15_09_2026_14_12_22" src="https://github.com/user-attachments/assets/d9499b1c-4184-44ba-aeca-58729c326830" />

*Ref 18: Signing in with the dedicated domain admin account*

<img width="795" height="600" alt="VirtualBox_DC_15_09_2026_16_57_25" src="https://github.com/user-attachments/assets/4542c832-28c8-48d7-a6b5-dbf17d0db9b2" />

*Ref 19: Verifying the domain admin account from Command Prompt*

### RRAS & NAT

Configured RRAS and NAT to allow Windows clients on the internal virtual network to access external network resources through the domain controller.

<img width="795" height="600" alt="VirtualBox_DC_15_09_2026_14_14_56" src="https://github.com/user-attachments/assets/50a4a1f7-b662-4ddf-bd21-13fb5f5cdab7" />

*Ref 20: Selecting the Remote Access server role* 

<img width="795" height="600" alt="VirtualBox_DC_15_09_2026_14_22_49" src="https://github.com/user-attachments/assets/a756745e-fdcb-4f07-848b-e4252f672b9d" />

*Ref 21: Confirming successful installation of the Remote Access role* 

<img width="795" height="600" alt="VirtualBox_DC_15_09_2026_14_23_46" src="https://github.com/user-attachments/assets/ef469b1a-7d97-47dd-b934-a41f2647314a" />

*Ref 22: Opening the Routing and Remote Access management tool*

<img width="795" height="600" alt="VirtualBox_DC_15_09_2026_14_24_07" src="https://github.com/user-attachments/assets/17ece87f-1ae0-4d92-ba3f-123ce1a1abf7" />

*Ref 23: Starting the Routing and Remote Access configuration* 

<img width="795" height="600" alt="VirtualBox_DC_15_09_2026_14_24_17" src="https://github.com/user-attachments/assets/7b7165c5-46b1-4d17-95fc-b0e9a766398d" />

*Ref 24: Selecting NAT in the RRAS setup wizard*

<img width="795" height="600" alt="VirtualBox_DC_15_09_2026_14_25_55" src="https://github.com/user-attachments/assets/4fcc8abe-fe38-439b-946f-ee17ab792608" />

*Ref 25: Completing RRAS/NAT configuration and starting the service*

### DHCP & DNS

Installed the DHCP Server role, authorized the DHCP server, configured and activated a DHCP scope to assign IP addresses to clients, and set the domain controller as the default gateway and DNS server for the internal network.

<img width="795" height="600" alt="VirtualBox_DC_15_09_2026_14_26_56" src="https://github.com/user-attachments/assets/2d17cbe9-e7ec-4736-9120-6616e8835b2b" />

*Ref 26: Selecting the DHCP Server role*

<img width="795" height="600" alt="VirtualBox_DC_15_09_2026_14_31_45" src="https://github.com/user-attachments/assets/dea1b9c8-1046-40b5-9a99-d9862ebb432d" />

*Ref 27: Confirming successful installation of the DHCP Server role*

<img width="795" height="600" alt="VirtualBox_DC_15_09_2026_14_32_08" src="https://github.com/user-attachments/assets/f39eefcd-314e-41e6-b6f6-63e55f4c4457" />

*Ref 28: Opening the DHCP tool*

<img width="795" height="600" alt="VirtualBox_DC_15_09_2026_14_32_37" src="https://github.com/user-attachments/assets/13e0b715-379c-4485-9fa0-9637ff30ff48" />

*Ref 29: Starting the creation of a new IPv4 DHCP scope*

<img width="795" height="600" alt="VirtualBox_DC_15_09_2026_14_34_06" src="https://github.com/user-attachments/assets/2bb1d6a7-4f21-4164-b41c-5f257a2e4d40" />

*Ref 30: Naming the DHCP scope*

<img width="795" height="600" alt="VirtualBox_DC_15_09_2026_14_35_08" src="https://github.com/user-attachments/assets/d80d4152-3307-4852-bb65-2d00e5e4bc59" />

*Ref 31: Configuring the DHCP address range* 

<img width="795" height="600" alt="VirtualBox_DC_15_09_2026_14_35_51" src="https://github.com/user-attachments/assets/03cbfca0-ab68-4ffb-83e8-d1c5c28cbba4" />

*Ref 32: Configuring the DHCP address lease duration*
 
<img width="795" height="600" alt="VirtualBox_DC_15_09_2026_14_36_59" src="https://github.com/user-attachments/assets/f0dc3adb-818e-482a-9613-918a9269f3c3" />

*Ref 33: Configuring the default gateway*

<img width="795" height="600" alt="VirtualBox_DC_15_09_2026_14_37_31" src="https://github.com/user-attachments/assets/bb8dc39a-9756-4a93-b962-a8b3b923c963" />

*Ref 34: Configuring the domain name and DNS server*

### PowerShell User Automation

Used a PowerShell script to create an OU and automate the creation of approximately 1,000 Active Directory user accounts.

<img width="795" height="600" alt="VirtualBox_DC_15_09_2026_14_42_22" src="https://github.com/user-attachments/assets/821f4996-961d-498c-a50e-30db1175eb0d" />

*Ref 35: Opening Windows PowerShell ISE as an administrator*

<img width="795" height="600" alt="VirtualBox_DC_15_09_2026_14_44_01" src="https://github.com/user-attachments/assets/c5713fb7-d8c5-4ec4-b899-629eca638baf" />

*Ref 36: Opening the PowerShell script in Windows PowerShell ISE*

<img width="795" height="600" alt="VirtualBox_DC_15_09_2026_14_45_09" src="https://github.com/user-attachments/assets/dc50963d-3e75-4ab2-b36b-eac3f9f067b0" />

*Ref 37: Configuring the PowerShell execution policy*

<img width="795" height="600" alt="VirtualBox_DC_15_09_2026_14_53_45" src="https://github.com/user-attachments/assets/ff25cd3e-606c-4139-93f4-0e75a361c02c" />

*Ref 38: Running the PowerShell script to create Active Directory users*

<img width="795" height="600" alt="VirtualBox_DC_15_09_2026_14_54_14" src="https://github.com/user-attachments/assets/f8de5fed-8b8d-4f07-a847-ac40b43ab723" />

*Ref 39: Verifying the bulk-created Active Directory user accounts*

### Windows Client & Connectivity Verification

Configured a client on the internal network, verified it received network settings through DHCP, corrected a missing default gateway, and confirmed DNS and internet connectivity through RRAS/NAT.

<img width="795" height="600" alt="VirtualBox_Client_15_09_2026_15_01_09" src="https://github.com/user-attachments/assets/0c7c7352-d5c2-4a0b-bee2-296cd5aa981e" />

*Ref 40: Installing the client on the internal network*

<img width="795" height="600" alt="VirtualBox_Client_15_09_2026_15_13_40" src="https://github.com/user-attachments/assets/e6e88f7a-67db-4a03-8410-5adf2a4dae8d" />

*Ref 41: Identifying the missing default gateway*

<img width="795" height="600" alt="VirtualBox_DC_15_09_2026_15_25_18" src="https://github.com/user-attachments/assets/273f2597-51a3-4903-8997-7c8e683b38d1" />

*Ref 42: Correcting the DHCP default gateway configuration*

<img width="795" height="600" alt="VirtualBox_Client_15_09_2026_15_26_59" src="https://github.com/user-attachments/assets/de6718c6-f9ee-43cd-8c10-a63e3c7a242d" />

*Ref 43: Renewing the IP address and verifying connectivity*

<img width="795" height="600" alt="VirtualBox_DC_15_09_2026_15_35_39" src="https://github.com/user-attachments/assets/74bab3bb-db2c-4839-aba3-c5070bfb651b" />

*Ref 44: Verifying the client received a DHCP lease*

### Domain Join & Authentication

Joined the client to the Active Directory domain and authenticated using a domain user account.

<img width="795" height="600" alt="VirtualBox_Client_15_09_2026_17_33_05" src="https://github.com/user-attachments/assets/e7a4a636-b85d-4ae8-901f-ec529849cd99" />

*Ref 45: Opening the client domain settings*

<img width="795" height="600" alt="VirtualBox_Client_15_09_2026_15_31_37" src="https://github.com/user-attachments/assets/65241d6f-95c9-4496-9a1a-9fec07abb7d5" />

*Ref 46: Joining the client to the domain*

<img width="795" height="600" alt="VirtualBox_Client_15_09_2026_15_34_14" src="https://github.com/user-attachments/assets/5a097367-7635-44b2-8c26-c9c6ca220f19" />

*Ref 47: Confirming the client successfully joined the domain*

<img width="795" height="600" alt="VirtualBox_Client_15_09_2026_15_42_54" src="https://github.com/user-attachments/assets/09ffe4de-b531-4abc-b40c-19f9206f27b3" />

*Ref 48: Signing in with a domain user account*

<img width="795" height="600" alt="VirtualBox_Client_15_09_2026_15_43_26" src="https://github.com/user-attachments/assets/d640ed2d-6bbc-4039-9851-95caa9e9384b" />

*Ref 49: Verifying the domain user session*

<img width="795" height="600" alt="VirtualBox_DC_15_09_2026_17_43_31" src="https://github.com/user-attachments/assets/95406c90-b9d5-4823-a2d0-02f9e4e685b9" />

*Ref 50: Verifying the domain user account in Active Directory Users and Computers*
