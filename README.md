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

