# Configuring-AD Part 1

<h1>Prepairing AD Infrastructure in Azure</h1>

![image](https://github.com/user-attachments/assets/3b32e7e9-8b18-4233-8a94-dde8afc44543)

<h2>Setup Domain Controller in Azure</h2>

-Create a Resource Group
-Create a Virtual Network and Subnet


![Screenshot 2024-09-29 120921](https://github.com/user-attachments/assets/f6647428-f996-44e9-aa11-18c0770bcb24)

- Create the Domain Controller VM (Windows Server 2022) named “DC-1”
- After VM is created, set Domain Controller’s NIC Private IP address to be static

![image](https://github.com/user-attachments/assets/840a49a1-51f3-444c-ae79-c72e0ad467d3)

- Log into the VM and disable the Windows Firewall (for testing connectivity)

<h2>Setup Client-1 in Azure</h2>

![image](https://github.com/user-attachments/assets/86fbb15c-4ead-49c0-a2b8-7424028c3394)

- Create the Client VM (Windows 10) named “Client-1”
- Attach it to the same region and Virtual Network as DC-1
- After VM is created, set Client-1’s DNS settings to DC-1’s Private IP address
- From the Azure Portal, restart Client-1

![image](https://github.com/user-attachments/assets/7b4c4603-834e-4896-ab19-16864f50a272)

- Login to Client-1
- Attempt to ping DC-1’s private IP address
- Ensure the ping succeeded

![Screenshot 2024-09-29 152723](https://github.com/user-attachments/assets/3d7a3fb0-ae64-4290-ab17-8ecd02772df7)

- From Client-1, open PowerShell and run ipconfig /all
- The output for the DNS settings shows DC-1’s private IP Address



