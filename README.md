<h1>Nessus Tenable Lab </h1>
<h2>Description</h2>

In this walkthrough we will be installing and configuring a nessus vulnerability scanner to perform credtental scans against a windows 10 host machine.



<h2>Languages and Utilities Used</h2>
Kali Linux terminal VirtualBox Nessus Tenable


<h2>Environments Used </h2>
Kali Linux


<h2> Walk-through:</h2>


First install either virtualBox or VMware for the host machine that you will be running scans against. then intall Nesssus tenable right after
![nessus and VB](https://github.com/Donjon3000/NessusTenableLab/assets/140426313/e9b89860-b752-47bb-a294-f096ad7343ab)

make sure to download a windows 10 iso file for the virtual machine aswell and save it to your downloads folder
![windows iso](https://github.com/Donjon3000/NessusTenableLab/assets/140426313/b43d5e41-098f-4bf3-9d70-89d8611ab26d)

When setting up your vitrual machine make sure the network is set to Bridged adapter so that your local computer can connect to the Vitrual machine
![adapter2](https://github.com/Donjon3000/NessusTenableLab/assets/140426313/bafc64b2-90d9-40e0-b214-3ca473de1f34)

Once you have your vitrual machine and vulnerability scanner up and running the first thing we can do is aquire the ip address of the VM by clicking the search bar in the VM type command prompt and then type ipconfig
![command 1](https://github.com/Donjon3000/NessusTenableLab/assets/140426313/6485d4b2-c88e-4a27-a36e-68d2e1fadfb5)
![admin1](https://github.com/Donjon3000/NessusTenableLab/assets/140426313/9e23e946-109f-4d46-9a4a-306aa088ed14)

Then take copy the ip address into your terminal and ping it so that you can establish a connection to the VM. If the session times out then disable the firewall on your VM then try again.
![ping ip](https://github.com/Donjon3000/NessusTenableLab/assets/140426313/1194b428-b065-4c88-bb42-685682474a75)
![VM2](https://github.com/Donjon3000/NessusTenableLab/assets/140426313/10d4d9bd-3726-4386-8856-49dea4bb2eff)





















