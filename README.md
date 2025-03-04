# osticket-install
<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Setup / Install</h1>
Here I will show you the necessary steps / prerequisites to correctly installing the osTicketing system .<br />




<h2>The Technologies and Environments we will be using include</h2>

- Remote Desktop
- Internet Information Services (IIS)
- Microsoft Azure ( Virtual machines / Compute )
<h2>Necessary Operating Systems </h2>

- Windows 10</b> (21H2)

<h2> Prerequisites</h2>

- Successfully log into Microsoft Azure 
- Launch VM with at least 2vcpus, 8gb of ram, and Windows 10
- Copy the VM's Public IP address
- Launch Remote Desktop and Log in 


<h2>Installation Steps</h2>

<p>
https://i.imgur.com/TJPWRdb.png

</p>
<p>
After you have logged into your VM, go ahead and download the files below. These zip files are essential for osTicket installation. 
https://docs.google.com/document/d/1DyjX8LeVU98LjhXO2t2K2F0aHywI2N9GD57T3taO5qo/edit?tab=t.0
Next, press the folder icon on the download tab > right click the file > extract all 
  
</p>
<br />
<p>
https://i.imgur.com/cO5zVmH.png
https://i.imgur.com/ZqDVztA.png
</p>
<p>
Now you will need to press the windows symbol on your desktop and head to the Control Panel. Press Uninstall a program > press Turn windows features on or off > Check the box next to "Internet Information Services" > hit the "+" next to IIS > hit the "+" next to world wide web services > hit the "+" next to application devlopment features > check the box next to CGI and hit OK.
The web server will now be installed.
</p>
<br />

<p>
https://i.imgur.com/V3H4z7w.png
</p>
<p>
Go ahead and open up the osTicket files we extracted earlier. Press php manager > hit next > hit agree > hit close > now go back to the files and hit the rewrite amd > install and hit finish
</p>
<br />

<p>
https://i.imgur.com/SQIh0zJ.png
</p>
<p>
 It's time to create the PHP directory. File explorer > C drive > create a new folder on this drive called PHP 
</p>
<br />
<p>
https://i.imgur.com/26viXFa.png
</p>
<p>
Go back to the extracted files right click "php 7.3.8" and extract files > hit browse > c drive > select PHP folder > extract. Now you should be able to see all the files within the PHP file.
</p>
<br />
<p>
https://i.imgur.com/6BYQ4db.png
</p>
<p>
Head back to the osTicket files, now hit the "VC_redist file". Then agree and install.
</p>
<br />
<p>
https://i.imgur.com/MlAVjd9.png
</p>
<p>
Installing mySQL. Head to the files > hit "mysql" > install > typical > Launch > next > standard config > now it will ask you for the user and password > after you have entered that info hit next > execute > Finish
</p>
<br />
https://i.imgur.com/X1QQk6x.png
</p>
<p>
Hit the desktop windows icon and head to IIS. Run as admin > PHP manager > Register new PHP version > hit the three dots > go to C drive and find the PHP CGI file > OK and install 
</p>
https://i.imgur.com/4Z3uWSt.png
</p>
<p>
Press the osticket-vm on the far left. You can either right click and start / stop, or press stop and start on the right side, Either will work. 
</p>
https://i.imgur.com/vGoexuV.png
https://imgur.com/8SgQPW5
</p>
<p>
Head back to the osTicket files and select the osTicket v1 file so we can extract all. It may take a few seconds to finish. Head to c drive > inetpub > wwwroot > drag the "Upload" file to the "iistart" files > let them copy > and rename upload to "osTicket" > Go back to IIS and stop / start the server again  
</p>
https://i.imgur.com/IsjaBZN.png
</p>
<p>
While you are still in IIS, look under osTicket vm and hit "sites" > default site > osTicket > hit "browse" on the far right > You should now be redirected to the osTicket site. We're almost there!
</p>
https://i.imgur.com/hFrokGo.png
</p>
<p>
Go back to IIS > default site > osTicket > php manager > hit enable or disable extension > enable "php_imap" , "php_intll" , "php_opcache" > then refresh osTicket site
</p>
https://i.imgur.com/PUwdP2w.png
https://i.imgur.com/1IWuO2i.png
</p>
<p>
Go ahead and go back to the wwwroot folder > osTicket > hit include > find "ost-sampleconfig.php" and rename it to "ost-config.php" > right click it and head to properties > security > advanced > disable inheritance > remove all inherited permissions > add > select principal > add your selected user and check full control > OK > Apply > OK 
</p>
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>
<p>
You can finally go back to the osTicket website and press continue. Setup helpdesk name and email > fill in admin user info
</p>
https://i.imgur.com/t7sxQjh.png
https://i.imgur.com/vviyJP0.png
<p>
<!- Just a few more things to do :). Go back to the osTicket > install folders. Install "HeidiSQL" > accept terms > hit next and install > Finish > open Heidi > new+ > enter the password you selected earlier when creating the user > open > right click the doplhin > create new > database > name it "osTicket" > OK > 
</p>

</p>
<p>
Head back to the osTicket site to finish the setup. Add "osTicket" under MySQL database > enter SQL username and password > hit install now!
</p>
https://i.imgur.com/058KfCy.png
</p>
<p>
Congratulations you have sucessfully installed osTicket!!! :) 

