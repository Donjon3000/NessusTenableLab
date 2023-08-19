<h1>Nessus Tenable Lab </h1>
<h2>Description</h2>

In this walkthrough we will be installing and configuring a nessus vulnerability scanner to perform credtental scans against a windows 10 host machine.



<h2>Languages and Utilities Used</h2>
Kali Linux terminal VirtualBox Nessus Tenable


<h2>Environments Used </h2>
Kali Linux


<h2> Walk-through:</h2>


First install either virtualBox or VMware for the host machine that you will be running scans against. Then intall Nesssus tenable right after.
![nessus and VB](https://github.com/Donjon3000/NessusTenableLab/assets/140426313/e9b89860-b752-47bb-a294-f096ad7343ab)

Make sure to download a windows 10 iso file for the virtual machine aswell and save it to your downloads folder.
![windows iso](https://github.com/Donjon3000/NessusTenableLab/assets/140426313/b43d5e41-098f-4bf3-9d70-89d8611ab26d)

When setting up your vitrual machine make sure the network is set to Bridged adapter so that your local computer can connect to the Vitrual machine.
![adapter2](https://github.com/Donjon3000/NessusTenableLab/assets/140426313/bafc64b2-90d9-40e0-b214-3ca473de1f34)

Once you have your vitrual machine and vulnerability scanner up and running the first thing we can do is aquire the ip address of the VM by clicking the search bar in the VM type command prompt and then type ipconfig.
![command 1](https://github.com/Donjon3000/NessusTenableLab/assets/140426313/6485d4b2-c88e-4a27-a36e-68d2e1fadfb5)
![admin1](https://github.com/Donjon3000/NessusTenableLab/assets/140426313/9e23e946-109f-4d46-9a4a-306aa088ed14)

Then take copy the ip address into your terminal and ping it so that you can establish a connection to the VM. If the session times out then disable the firewall on your VM then try again.
![ping ip](https://github.com/Donjon3000/NessusTenableLab/assets/140426313/1194b428-b065-4c88-bb42-685682474a75)
![VM2](https://github.com/Donjon3000/NessusTenableLab/assets/140426313/10d4d9bd-3726-4386-8856-49dea4bb2eff)

Now we can create a new scan. Click on the new scan icon and click basic network scan and you will be brought to a page to setup the up the scan by entering the name of the VM and the IP address.
![VM3](https://github.com/Donjon3000/NessusTenableLab/assets/140426313/48cee500-aeab-4bd8-9dd7-64e7c6748e35)
![basic scan 2](https://github.com/Donjon3000/NessusTenableLab/assets/140426313/9445aa8f-897f-44e1-bdf0-371c3ca68402)

After setting up you can now start a new scan by pressing the play button and once its finished wil show a check mark.
![my scans](https://github.com/Donjon3000/NessusTenableLab/assets/140426313/b3b865c2-bd85-493e-aebb-e11361d38347)

Now we can look at what vulnerabilites that the Nessus scan mangaged to find as yuo can see since it was just a basic network scan there were not to many high risk vulnerabilites. 
![basic scan results](https://github.com/Donjon3000/NessusTenableLab/assets/140426313/f3031348-5535-4d2e-9b4e-00cc630c9501)

You can still go through each vulnerability and check the details and remediations. 
![VM5](https://github.com/Donjon3000/NessusTenableLab/assets/140426313/67bc9512-62a9-43d6-9fc8-4685febb8100)

 Next step is to set up the vitural machine to accept credential scans. First thing we can do is to go back to the VM and open services.msc and enable the remote registry and allow the scanner to connect to the VMS registry and look for vulenrabilites.

![remote reg](https://github.com/Donjon3000/NessusTenableLab/assets/140426313/afeb074c-2aa1-45b7-b764-a77e9f641ede)

Next go to your advanced sharing settings and turn on file and printer sharing.

![file printer](https://github.com/Donjon3000/NessusTenableLab/assets/140426313/36f7c7be-c387-4a6f-be27-b49903bc9413)

Next go to user account control and set the bar to never notifiy and click ok.

![VM7](https://github.com/Donjon3000/NessusTenableLab/assets/140426313/7768fc73-f0d6-4950-b023-d4861960f156)

final step is to open the registry editor and add a key that is supposed futher disable user account control. In this order go to local machine,software,microsoft,windows, current version, polices and finally system.

![local machine](https://github.com/Donjon3000/NessusTenableLab/assets/140426313/e1440194-fa3f-47c2-a400-0479d6b87b16)

![localacc](https://github.com/Donjon3000/NessusTenableLab/assets/140426313/da08c8f6-d324-480a-9364-3dda13401400)

Then create a D-WORD by right clicking and type LocalAccountTokenFilterPolicy press enter and set the value to 1.

![local2](https://github.com/Donjon3000/NessusTenableLab/assets/140426313/acbcca9b-edf5-4ba2-b1ed-0270eeda8578)

Next restart your virtual machine

![restart](https://github.com/Donjon3000/NessusTenableLab/assets/140426313/189e4744-2518-4cf2-a878-efd275503908)

Now go back to nessus and click my scans and then click configure. Now add windows credentials and set the authenitcation method to password. Use whatever name and password you created. click save then go back to my scans and click the play buttom to begin a new scan.

![configure 3](https://github.com/Donjon3000/NessusTenableLab/assets/140426313/5227aded-36b4-4bae-b12e-c9280dcae16f)

You should now get new results for vulnerabilites and can now compare from the previous scan.

![new scan 1](https://github.com/Donjon3000/NessusTenableLab/assets/140426313/8c1bede5-7a45-4829-a685-004b20a4cb0b)

Let start now with some remediations that we can implment by installing an older version of firefox and scanning it for any vulnerbilites.

![firefox](https://github.com/Donjon3000/NessusTenableLab/assets/140426313/cf0d586d-68ed-47d1-97ba-19724ac82043)

Make sure that you dowload firefox on your vitrual machine.

![firefox 2](https://github.com/Donjon3000/NessusTenableLab/assets/140426313/5b4599b2-5992-458c-80f7-a8ec68d39c97)

After installing firefox got back nessus and run a new scan. after scanning you can see that there more high criticals that were found in the last scan 

![firefox scan](https://github.com/Donjon3000/NessusTenableLab/assets/140426313/eddc2e27-d40d-4391-803e-3e1be67cc71b)

Go the the criticals and see what remediations are recomended.

![firefoxscan3](https://github.com/Donjon3000/NessusTenableLab/assets/140426313/595b7941-e871-4bef-bcdb-1559892d9d75)

When can start practicing simple remmeditaitons by unistalling firefox and running windows updates. 

![unistall firefox](https://github.com/Donjon3000/NessusTenableLab/assets/140426313/566808fb-27d7-4d5e-abcb-6655e529b24b)

Keep running windows updates until theres no more updates. You might have to restart your VM a couple of times for the updates to complete.

![windows update](https://github.com/Donjon3000/NessusTenableLab/assets/140426313/489a5f79-121d-47fa-b202-3ae6332dd0f2)

Go back to nessus and conduct one final scan and see the changes in the scan compared to the previous one with firefox.  

![firefox unistall scan](https://github.com/Donjon3000/NessusTenableLab/assets/140426313/c8d5755b-95ff-4ec3-9a36-6634332b18e3)

This is the core concept of vulnerability scanning which scanning and remediating any criticals. There is more to what nessus can do but this is just to show my knowlegde of using Nessus and practice to gain exeprince. 






