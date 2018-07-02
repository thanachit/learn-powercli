# learn-powercli

# Install powercli on Mac

Set-PowerCLIConfiguration -InvalidCertificateAction Ignore

# Delete VMs in resource pool.

$VMs=(Get-Content serverlist)
$vmObj = Get-vm $VMs
foreach($active in $vmObj){   
Remove-VM -VM $active -DeleteFromDisk -Confirm:$true -RunAsync | Out-Null
}
