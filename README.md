<h1>Disk Sanitization Project</h1>

<h2>Description</h2>
Erase all data on a disk, reformat the disk. (not a 'secure' wipe for sensitive data)
<br />


<h2>Languages and Utilities Used</h2>

- <b>Powershell</b> 

<h2>Environments Used </h2>

- <b>Windows 11</b>

<h2>Program walk-through:</h2>

<h3>Part 1: Identify and Erase the Disk.
</h3>

<p>Press Windows + R, enter: diskmgmt.msc
</p>
 <br/>
<img src="https://i.imgur.com/MZ0LDxb.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />

<p>
Opens disk management for windows 11.<br/>
Verify the disk you want to wipe, note the space on the Disk. For this example, I will wipe drive E. (476 GB)<br/>
 <br/>
<img src="https://i.imgur.com/EIMTOny.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />

<p>
Open an administrator powershell window.<br/>
Enter Get-Disk Command to see all available disks on the system.<br/>
Notice disk number 1 is 476 GB <br/>
  <br/>
<img src="https://i.imgur.com/75ib9gF.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />

<p>
This is one way to wipe a disk in powershell. Replace (DiskNumber) with the disk number you want to wipe.<br/>
Clear-Disk -Number (DiskNumber) -RemoveData -RemoveOEM -Confirm:$false<br/>
 <br/>
<img src="https://i.imgur.com/LNgaeOR.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />

<p>
We can observe that our disk has been wiped clean.<br/>
 <br/>
<img src="https://i.imgur.com/WwvtczH.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />

<h3>Part 2: Initialize the Disk:</h3>

<p>
Right click, Select Initialize, Select either MBR or GPT<br/>
<br/>
<img src="https://i.imgur.com/DHjOKbR.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />

<p>
Notice we now have a GPT drive ready to use.<br/>
Further customization:<br/>
Right click, New simple volume<br/>
Opens up a New Simple Volume Wizard:<br/>
<br/>
<img src="https://i.imgur.com/WKKPBiS.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />

<p>
Specify Volume Size:<br/>
<br/>
<img src="https://i.imgur.com/XY5jpOp.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />

<p>
Assign Drive Letter or Path:<br/>
<br/>
<img src="https://i.imgur.com/Ct9EOia.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />

<p>
Format Partition, can select file system, allocation size, and volume name:<br/>
<br/>
<img src="https://i.imgur.com/9PxsAiN.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />

<p>
Click finish to see final results:<br/>
<br/>
<img src="https://i.imgur.com/RazH6FS.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />


<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
