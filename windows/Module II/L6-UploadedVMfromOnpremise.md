# Upload a Windows VM VHD (Lift and Shift) to Azure for Resource Manager deployments

[Microsoft Official Article] - [Click Here]()

Prerequisites:-

*  A virtual machine running Windows - There are many tools for creating virtual machines on-premises.
For example, see [Install the Hyper-V Role and configure a virtual machine](https://technet.microsoft.com/library/hh846766.aspx).
To know which Windows operating systems are supported by Azure, see [Microsoft server software support for Microsoft Azure virtual machines.](https://support.microsoft.com/en-us/kb/2721672)

## Make sure that the VM has the right file format


* Windows Server 2012 R2 (All Windows Update) - No Roles installed
* VHD size - 127 GB
* Enabled Remote Desktop
* WorkGroup VM - Check Windows Firewall for for Guest or Public Networks

1. Make sure you have the RDP enabled inside the VM.
2. Login to Windows server VM and then enable Remote Desktop Feature.
3. Verify the Remote Desktop feature is enabled in Windows Firewall for both Private and Public Profile.

Note – If machine is part of domain, then make sure RDP is enabled for Domain Profile.

Click on "Allow Apps to communicate through Windows Firewall".



How to convert dynamic disk to fixed disk and .vhd format. [Click Here](https://technet.microsoft.com/en-us/library/ee941151(v=ws.10).aspx)


Steps :

To create or find an Azure storage account by using PowerShell
Open Azure PowerShell and sign in to your Azure account.


Login-AzureRmAccount
This command will open a pop-up window for you to enter your Azure credentials.

If the subscription ID that is selected by default is different from the one that you want to work in, use either of the following commands to set the right subscription.


Set-AzureRmContext -SubscriptionId "xxxx-xxxx-xxxx-xxxx"
or
Select-AzureRmSubscription -SubscriptionId "xxxx-xxxx-xxxx-xxxx"

You can find the subscriptions that your Azure account has by using the command Get-AzureRmSubscription.