<p align="center">
<img width="1083" alt="image" src="https://github.com/MeharamSal/azure-network-protocols/assets/173064050/443ee6e7-0560-4171-bab7-72f2cd6d03e5">
</p>

<h1>Building Intuition for DNS </h1>
In this tutorial, we strengthen our understanding of how DNS works by using Azure Virtual Machines. <br />



<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Various Command-Line Tools

<h2>Operating Systems Used </h2>

- Windows 10 (21H2)

<h2>Steps</h2>

- Connect/log into DC-1 as your domain admin account
- Connect/log into Client-1 as an admin
- From Client-1 try to ping “mainframe” notice that it fails
- Nslookup “mainframe” notice that it fails (no DNS record)
- Create a DNS A-record on DC-1 for “mainframe” and have it point to DC-1’s Private IP address
- Go back to Client-1 and try to ping it. Observe that it works
- Local DNS Cache Exercise
- CNAME Record Exercise






<h2>Actions and Observations</h2>

<p>
<img width="336" alt="image" src="https://github.com/MeharamSal/azure-network-protocols/assets/173064050/27b945b5-8aef-4b65-87eb-51f3e8cdf7cb">
</p>
<p>
Connect/log into DC-1 as your domain admin account created in previous section 'Configuring On-premises Active Directory within Azure VMs' 
<br />




<p>
<img width="616" alt="image" src="https://github.com/MeharamSal/azure-network-protocols/assets/173064050/3c26fc26-c5a3-4399-9250-2a23e031a8d2">
<img width="518" alt="image" src="https://github.com/MeharamSal/azure-network-protocols/assets/173064050/3b515909-55f1-44cf-ba8d-593ae297b22b">


</p>
<p>
Connect/log into Client-1 as an admin 
</p>
<p>
  From Client-1 try to ping “mainframe” notice that it fails

</p>
<br />












<p>
<img width="1264" alt="image" src="https://github.com/MeharamSal/azure-network-protocols/assets/173064050/7137971e-43cb-49b4-86fb-7d1adb591222">

  <img width="1271" alt="image" src="https://github.com/MeharamSal/azure-network-protocols/assets/173064050/5ea6dc7e-64a0-407b-978a-944b1273ca8e">

  
<img width="811" alt="image" src="https://github.com/MeharamSal/azure-network-protocols/assets/173064050/fbe527ce-7a71-4214-b1e0-1f34dd2b8867">





</p>
<p>
Create a DNS A-record on DC-1 for “mainframe” and have it point to DC-1’s Private IP address

</p>
<br />






















<p>
<img width="502" alt="image" src="https://github.com/MeharamSal/azure-network-protocols/assets/173064050/bc00ad27-a761-4ed2-95c7-dcd9c5e6ae25">

</p>
<p>
Go back to Client-1 and try to ping it. Observe that it works

</p>
<br />




















<p>
<img width="346" alt="image" src="https://github.com/MeharamSal/azure-network-protocols/assets/173064050/d12f311e-d488-49c1-ac3e-08234578c480">
</p>
<p>
Try 'nslookup mainframe'
</p>
<br />




















<p>
<img width="306" alt="image" src="https://github.com/MeharamSal/azure-network-protocols/assets/173064050/e8180c89-316c-4232-ac3e-04b5c885b19c">
<img width="723" alt="image" src="https://github.com/MeharamSal/azure-network-protocols/assets/173064050/8e7e8438-dec5-4e99-9e74-f7dbd8506983">

  
</p>
<p>
Go back to DC-1 and change mainframe’s record address to 8.8.8.8

</p>
<br />




















<p>
<img width="408" alt="image" src="https://github.com/MeharamSal/azure-network-protocols/assets/173064050/fa9356be-9986-4b89-83df-42fb5232c297">
</p>
<p>
Go back to Client-1 and ping “mainframe” again. Observe that it still pings the old address
</p>
<br />

























<p>
<img width="458" alt="image" src="https://github.com/MeharamSal/azure-network-protocols/assets/173064050/868f2d61-8ccb-4181-88f4-345b5a43c4e4">
</p>
<p>
Observe the local dns cache (ipconfig /displaydns)
</p>
<br />


















<p>
<img width="418" alt="image" src="https://github.com/MeharamSal/azure-network-protocols/assets/173064050/5f6182aa-930f-4e96-a331-0e984c685977">
</p>
<p>
  (Make Sure to Run CMD as an Adminstrator)
</p>
<p>
Flush the DNS cache (ipconfig /flushdns). Observe that the cache is empty. 

</p>
<br />




















<p>
<img width="434" alt="image" src="https://github.com/MeharamSal/azure-network-protocols/assets/173064050/71ddd9b5-342d-4ba1-8aee-4ef381b97185">
</p>
<p>
Attempt to ping “mainframe” again. Observe the address of the new record is showing up
</p>
<br />
















<p align="center">

<p>
CNAME Record Exercise
</p>
<br />






<p>
<img width="315" alt="image" src="https://github.com/MeharamSal/azure-network-protocols/assets/173064050/8db42f55-1e20-42fb-99e2-1b81d36bf25c">
</p>
<p>
Go back to DC-1 and create a CNAME record that points the host “search” to “www.google.com”

</p>
<br />















<p>
<img width="389" alt="image" src="https://github.com/MeharamSal/azure-network-protocols/assets/173064050/e4383ccd-61d1-4ab9-9fd1-e1e6352dee0a">
</p>
<p>
Ping search on Client-1
</p>
<br />


























<p>
<img width="295" alt="image" src="https://github.com/MeharamSal/azure-network-protocols/assets/173064050/9be6b0c8-5a93-4f1c-b949-0c406ad05a5d">
</p>
<p>
Use 'nslookup search' to see results
</p>
<br />





<p align="center">
<img width="629" alt="image" src="https://github.com/MeharamSal/azure-network-protocols/assets/173064050/914b1a5a-1b8d-40d5-83f4-e85df3ba7b36">

</p>
<br />






