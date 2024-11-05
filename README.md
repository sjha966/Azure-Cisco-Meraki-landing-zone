# Azure-Cisco-Meraki-landing-zone
Azure Peered VNet Connectivity to Cisco Meraki vMX-S using Auto VPN
Steps to deploy the resource:
1) Access to the vMX offer. A screenshot of the Marketplace list of Cisco Meraki vMX in Azure is included below:
Cisco Meraki's virtual MX (vMX) is a virtual instance of a Meraki security & SD-WAN appliance. It is dedicated to providing the simple configuration benefits of site-to-site Auto VPN for organizations running or migrating IT services to public cloud environments. The vMX extends your physical MX deployment to the cloud in minutes through the same Meraki dashboard. A vMX can be used as your Cisco Meraki SD-WAN and Auto VPN node to easily connect your network with your Azure deployed services.
![image](https://github.com/user-attachments/assets/33fafe17-cecc-46e4-ab2b-fa361ba27968)
2) Generate Token from Meraki Dashboard and paste in Meraki Authentication token
![image](https://github.com/user-attachments/assets/a8e739b5-a1c4-4172-9a59-dd593bddd376)
Azure 
![image](https://github.com/user-attachments/assets/5515655f-d789-4af7-a3f4-a2a9f189b8a8)
You must have the following before you begin:

An Azure virtual network (vNET, also known as a VPC) where you will deploy the vMX.  This vNET and its corresponding resource group can be the same one as the resources you plan to access across the Meraki VPN or a different one.  Refer to this Azure document for creating these resources. 

You MUST have an "SD-WAN" subnet inside the vNET where the vMX will be deployed which is separate from the subnet(s) where the resources you plan to access through the VPN are hosted.  Ex. If your apps and resources are located in the "production" subnet, you will deploy a second subnet in the same vNET called "SD-WAN" in which the vMX will be deployed.  DO NOT deploy the vMX inside the production subnet alongside the other resources as this can result in a routing loop and packet loss within the Azure environment.
Configure virtual networks
Virtual network: Choose an existing virtual network from the list.
Subnet: Choose the SD-WAN subnet mentioned above in which the vMX will be deployed; if needed, refer to the article for more information about subnets in Azure. The subnet chosen here must be different from the subnet where resources you plan to access and route through the vMX are deployed.
![image](https://github.com/user-attachments/assets/5a9ea4a0-a28f-493a-afba-69eb49cc3d14)
Next, review the deployment details and licensing information and hit "Create."
After you click on "Create," the deployment will begin.
Deployment in progress 
![image](https://github.com/user-attachments/assets/871b54d7-4531-4105-a9aa-f2929aaf31bb)
It may be several minutes before the deployment completes and the instance launches. 
![image](https://github.com/user-attachments/assets/a17b4585-f231-4cdd-b486-f0a259d6487f)

