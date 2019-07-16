# terraform
Error while creating VM in azure through terraform can anyone please help me.
code

resource azurerm_virtual_machine myvm {
name = "windowsserver"
location = "East US 2"
resource_group_name = "production"
vm_size = "Standard_D2s_v3"
network_interface_ids = ["/subscriptions/0fd36863-9ed4-45ff-8a0c-2f9677d0cd7d/resourceGroups/Default-Networking/providers/Microsoft.ClassicNetwork/virtualNetworks/ExpressRoutenewcnet"]


storage_os_disk {
name = "mydisk-osdisk"
caching = "ReadWrite"
create_option = "FromImage"
managed_disk_type = "Standard_LRS"
}

storage_image_reference {
publisher = "MicrosoftWindowsServer"
offer = "WindowsServe"
sku = "2012-R2-Datacenter"
version = "lattest"
}

os_profile_windows_config {

}

os_profile {
computer_name = "windows2012"
admin_username = "juned"
admin_password = "Pa$$w0rd@123"
}

}


error
compute.VirtualMachinesClient#CreateOrUpdate: Failure sending request: StatusCode=400 -- Original Error: Code="InvalidParameter" Message="The value of parameter imageReference.version is invalid." Target="imageReference.version"
