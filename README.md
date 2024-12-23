# azure-basics
Data Storage, Virtual Machines, NSGs (Network Security Groups), and Internet Protocols.

## Resource Group Creation
Everything in Microsoft Azure must be contained within a resource group, and they're a good way to organize projects, networks, and more. So let's begin by creating a resource group that everything in this repository's demonstration will live inside of. As a minimum requirement, you must choose the subscription, the name of the resource group, and the Microsoft servers it will be hosted on. Optional tags can also be added to oragnize large groups of resource groups.

![1  create resource group](https://github.com/user-attachments/assets/1f064b5a-677a-4645-9e51-8ed157c4883c)

Once the resource group is successfully created, navigate to its contents and controls. You should find yourself in a menu that looks like the next image:

![2  the resource group menu](https://github.com/user-attachments/assets/67ea21b7-7c83-421c-8d0a-a19863f7dc60)

## Data Storage, Editing, and Retrieval

Inside of your resource group, create a storage account. An easy way to find it in the marketplace is to check the "Azure services only" box below the search bar, greatly reducing the number of products shown. The icon and description are shown below.

![3  the storage account](https://github.com/user-attachments/assets/1691a7c8-f1fa-46cc-94e2-c7687db283b2)

The "Basics" section of the storage account creation menu contains the minimum requirements, and the default settings in the advanced menus will suit our purposes. Be sure that your storage account is assigned to the subcription and geographic region of your resource group. "Azure Blob Storage" is what I will be demonstrating today, as it is comprable to Google Drive and compatible with a wide range of file types.

![4  storage account creation](https://github.com/user-attachments/assets/37ba66d7-b702-4283-ae91-dba613af71b2)

While your resource is deploying, create a test file to upload to the storage account. I will create a test document with plaintext to be easily editable in Azure's user interface.

![5  the test document](https://github.com/user-attachments/assets/712020e8-462e-4a78-9308-5699c60ffe58)

Once your resource is deployed, navigate to your storage account and click the "upload" button to upload a file.

![6  the upload button](https://github.com/user-attachments/assets/1f721014-7c15-4ef3-a682-cfcd72c408b1)

Navigate to where your test file was stored and **create a new container that will hold it.** In a business scenario, multiple containers could hold different kinds of files and be used to organize large amounts of storage, but we will just be using one. Once your file is uploaded, click on the "Containers" option for your resource group and find the container you just created, then find the file inside of it. 

![7  container navigation](https://github.com/user-attachments/assets/889b70d0-3f33-4fdd-a0db-b754f81b74bd)

Once you've located the file, right click it and select "View/edit". 

![8  editing the file](https://github.com/user-attachments/assets/14383528-dfe9-429a-920b-b34ec9ebe3d7)

Make some easy to remember changes and then save the new file.

![9  edited test file](https://github.com/user-attachments/assets/5617b752-f51b-4c9b-a139-430c83ffa7cc)

Then, download the file and view the original and the updated version side by side. **Congratulations! You now know how to use Microsoft Azure for basic file storage, editing, and transfer.** If you logged into your azure account on another computer, you could access your test file from anywhere in the world!

![10  the final product](https://github.com/user-attachments/assets/28b7df2a-33f4-43cd-b29c-6f52a34abb3f)

<!-- The first tutorial was somewhat long winded, but I wanted to explain everything that an adept beginner might need a visual reference for. For brevity's sake, I won't explain things twice, and will instead point to certain parts in my tutorial and use less/smaller photos as hopefully a familiarity with the Azure UI is beginning to develop. --> 
# Virtual Machines

**Virtual machines are simulated computers that are running inside of another computer**, and Microsoft Azure allows us to create, access, and modify them with a plethora of options and settings. In this part of the tutorial, I will show you how to create two virtual machines running on the same virtual network so that we can inspect network traffic between them. To begin, a virtual machine is a resource like any other in Azure and must be created inside of a resource group. I will be using the same resource group that contains my storage account. Navigate to your preferred resource group of choice and create a virtual machine. The marketplace product at the time of this tutorial looks like this:

![11  the virtual machine icon](https://github.com/user-attachments/assets/8077f7c6-3ed8-417a-8f6b-df2e39178538)

## Virtual Machine Creation Options

The virtual machine options are much more complex than the ones for our storage account. To begin, start in the **Basics** menu and make sure that the virtual machine is attached to the subscription you want, in the resource group you want. Name it something that describes it so you can easily know what it is in the Azure interface, and choose the availability option that best suits your needs and budget. Then, select a disk image to choose the kind of operating system that you want. We will be creating a Windows 10 and an Ubuntu VM, and the order does not matter (⚠️ **When creating the Windows VM**, make sure to check the "Licensing" option at the bottom. It won't create if you dont'!).

![12  basic vm options](https://github.com/user-attachments/assets/3a560925-b550-4e36-b2ba-1af8037cd0ad)

Next, select the resources you'd like to allocate to the virtual machine with the "Size" option, and select a username and password to be able to log into it. If you need, feel free to put it in a notepad or write it down so you don't forget. For the inbound port rules, I will only be demonstrating remote desktop (RDP 3389) on Windows 10, but will SSH into the Ubuntu VM from both my virtual machine with a private IP address, and my home machine with a public one, so I will need to enable **SSH (22)** in my Ubuntu VM.

![13  basic vm options 2](https://github.com/user-attachments/assets/4dc8b0b0-77b4-4ef2-9c8f-82463e5a8c72)

The default disk options are more than adequate for our purposes, but we will go to the "Networking" menu to create a virtual network and ensure that both machines are running on it. We will simply click "create new" under "Virtual Network" and rename it to something descriptive. For the first VM, no other options need to be changed for our purposes and we can click "Review + create" at the bottom of the screen to start the deployment process.

![14  the new virtual network](https://github.com/user-attachments/assets/46d3d47b-0f82-49ff-8541-74f5c46365db)

I recommend waiting until the machine fully deploys and then a couple extra minutes after that to make sure that Azure will register everything properly when you create the second VM. If you go too quickly, Azure won't register that you have an existing virtual network and you won't be able to select it. Once that's done, though, you're ready to create the second virtual machine!

## The Second Virtual Machine

If you've been following along so far and have already created a Windows VM, it's time to make the Ubuntu one now. The basics settings should be the same except for two things: **You will not need to provide licensing** and you will need to have **password authentication instead of an ssh key**. SSH port 22 should already be allowed by default.

![15  ubuntu settings](https://github.com/user-attachments/assets/ff248f73-3b8d-4553-abc6-8ac61b792811)

If you're able to select the existing virtual network you created with the first VM, congratualtions! All of the setup for the next tutorial is finished. Create and deploy your next VM and head to the next github page to inspect network traffic and manage network security groups with me!

![16  virutal network registered](https://github.com/user-attachments/assets/573621f5-a454-4c6b-a59c-6c074a9ee9cb)

link to next part will have image






