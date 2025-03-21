<h1>Creating A Virtual Machine in Azure </h1>
This tutorial provides a guide on implementing a Virtual Machine (VM) in Microsoft Azure. <br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Azure Network Watcher
- Remote Desktop

<h2>Operating Systems Used </h2>

- Windows Server 2019
- Windows 11

<h2>Implementations and Deployments</h2>

- Create resources
- Create a Virutal Machine
- Join the Virtual Machine using RDP (port 3389)
- See how resources get grouped on creation

<h2>Deployment and Configuration Steps</h2>
<h3 align="center">In the Azure (portal.azure.com)</h3>
<br />
<p>
  Create a Resource > Virtual Machine > Create. 
  Choose a Resource Group or create a new one (RG-1) and name the Virtual Machine (ErickL-VM)
  Leave the other following values as the default value unless specified.
</p>

![Screenshot 2025-03-20 160931](https://github.com/user-attachments/assets/db559150-f663-4caf-bd91-446b341858e1)
<br>
<br/>


  For Image, I chose Windows Server 2019 & to save some credits, I decided to go with the Standard B2s VM configuration, which has 2 virtual CPUs and 4 GB of RAM in size.
  **In administrator account, create a Username (AzureUserEL) and password (Can be anything, just remember what it is**


![Screenshot 2025-03-20 161019](https://github.com/user-attachments/assets/b491a4a3-5daa-495a-a7bb-49cea8f65f61)
<br>
<br/>

<p>
  For the OS disk type, I initially changed it from a Premium SSD, which is best for production & high performance to a Standard SSD, which is more suitable for web servers. However, since this is just a basic testing environment, Standard SSD makes the most sense.
</p>

![Screenshot 2025-03-20 162028](https://github.com/user-attachments/assets/6ecf8823-01a1-48a4-8a8f-458effa39120)
<br>
<br/>

<p>
  In the Networking tab, I left all settings at their default values but added HTTP (port 80) & RDP (port 3389) in the "inbound ports" selection to be able to access the Virtual Machine. 
  
  **(This allows all IP addresses to access the VM. Since this is only for testing, I plan to configure the network settings in a future lab to create rules to allow and deny incomming traffic to the VM)**
</p>

![Screenshot 2025-03-20 162116](https://github.com/user-attachments/assets/13f2f27d-7e4b-4272-9a41-d85e92014409)
<br>
<br/>

<p>
  I left the Management, Monitoring, Advanced & Tags tab settings at their defualt value. As you can see, the validation for my Virtual Machine passed. Notice the estimated hourly cost of running the Virtual Machine. 
</p>

![Screenshot 2025-03-20 163228](https://github.com/user-attachments/assets/62de0161-ec50-4670-9cb3-4843956e2ba7)
<br>
<br/>

 After clicking "Create", the deployment process begins. The status will change to complete once the VM has been successfully provisioned 
 **Once the deployment is completed, Azure does not only create the VM but also provisions all of the associated resources the VM needs** 


![Screenshot 2025-03-20 163359](https://github.com/user-attachments/assets/ac77143f-7f23-4c13-aa24-ea100f49c309)
![Screenshot 2025-03-20 163646](https://github.com/user-attachments/assets/dd641f61-f0ea-4ebc-a46e-fe10e96a7663)
<br>
<br/>

<p>
  Make sure your VM is running & then click Connect. Download the RDP file to connect to your Virtual Machine (ErickL-VM.rdp)
 Afterwards, you want to sign in with the credentials created (AzureUserEL)
</p>

![Screenshot 2025-03-21 132343](https://github.com/user-attachments/assets/8d2cf8ef-3fac-4a24-b78a-d97fad7aedfe)
![Screenshot 2025-03-21 132851](https://github.com/user-attachments/assets/def4044c-1dad-4802-8dcc-ff1ffb128475)
![Screenshot 2025-03-20 164415](https://github.com/user-attachments/assets/fa98081f-38f6-443a-a712-5649e0ac10d9)
<br>
<br/>

<p>
  After successfully entering your credentials, you are now connected and can access your Virtual Machine. 
</p>

![Screenshot 2025-03-21 134258](https://github.com/user-attachments/assets/0aa6d147-0310-41e4-8526-f5624dcae2f7)
![Screenshot 2025-03-21 134413](https://github.com/user-attachments/assets/93e78bab-cff8-4bac-9d47-3ce7727979ca)
![Screenshot 2025-03-21 134606](https://github.com/user-attachments/assets/a3d75a27-1212-4831-9a5a-b328d457e5fe)
<br>
<br/>

I hope this tutorial helped you learn a little bit about how to create a Virutal Machine. This can be easily done on a PC or a Mac. Mac would just have an extra step to download the Remote Desktop App

<h1>
  Summary/Recap 
</h1>

  You have created a VM in Azure & had the chance to see how resources get grouped on creation

- When creating a Virtual Machine, resources were created and by default, Azure gave them all a similar name to help with association and grouped them in the same resource group
- You can view the list of resources in the Resource group when creating a VM (Public/Private IP, NSG, VNet, NIC, Disk)

<h1>
  Don't forget to clean up your environmnent
</h1>

Now that we're done, DON'T FORGET TO CLEAN UP YOUR AZURE ENVIRONMENT so that you don't incur unnecessary charges.
- Close your Remote Desktop connection, delete or deallocate any RGs or VMs , and verify deletion to stop all costs.
- It's a good idea at the end of a project to identify whether you still need the resources you created. Resources that you leave running can cost you money. You can dellocate the VM or delete the resource group to delete the entire set of resources

<br>
</br>

<h3 align="center"> In addition:</h3>
You can always view a visual respresentation of how your resources are interconnected with Azure Network Watcher's Topology feature.

**(This visualization helps in understanding & managing your network infrastructure effectively)**

![Screenshot 2025-03-21 134902](https://github.com/user-attachments/assets/d820c2f3-c026-46b1-81f6-73640e0188f8)
