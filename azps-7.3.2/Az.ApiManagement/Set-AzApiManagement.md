---
external help file: Microsoft.Azure.PowerShell.Cmdlets.ApiManagement.dll-Help.xml
Module Name: Az.ApiManagement
online version: https://docs.microsoft.com/powershell/module/az.apimanagement/set-azapimanagement
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ApiManagement/ApiManagement/help/Set-AzApiManagement.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ApiManagement/ApiManagement/help/Set-AzApiManagement.md
ms.openlocfilehash: 8fd50e2f57a8935dce3dde99d6fcb24aef8e436f
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140560679"
---
# Set-AzApiManagement

## SYNOPSIS
Memperbarui layanan Manajemen Api Azure

## SYNTAX

```
Set-AzApiManagement -InputObject <PsApiManagement> [-SystemAssignedIdentity] [-UserAssignedIdentity <String[]>]
 [-AsJob] [-PassThru] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

Cmdlet **Set-AzApiManagement** memperbarui layanan Manajemen API Azure.

## EXAMPLES

### Contoh 1: Dapatkan layanan Manajemen API dan  scale untuk Premium dan Tambahkan kawasan
```powershell
$apim = Get-AzApiManagement -ResourceGroupName "ContosoGroup" -Name "ContosoApi"
$apim.Sku = "Premium"
$apim.Capacity = 5
$apim.AddRegion("Central US", "Premium", 3)
Set-AzApiManagement -InputObject $apim
```

Contoh ini mendapatkan instans Manajemen Api, menskalakan ke lima unit premium lalu menambahkan tiga unit tambahan ke kawasan premium.

### Contoh 2: Perbarui penyebaran (VNET eksternal)
```powershell
$virtualNetwork = New-AzApiManagementVirtualNetwork -SubnetResourceId "/subscriptions/a8ff56dc-3bc7-4174-a1e8-3726ab15d0e2/resourceGroups/Api-Default-WestUS/providers/Microsoft.Network/virtualNetworks/dfVirtualNetwork/subnets/backendSubnet"
$apim = Get-AzApiManagement -ResourceGroupName "ContosoGroup" -Name "ContosoApi"
$apim.VpnType = "External"
$apim.VirtualNetwork = $virtualNetwork
Set-AzApiManagement -InputObject $apim
```

Perintah ini memperbarui penyebaran Manajemen API yang sudah ada dan bergabung ke *VpnType eksternal*.

### Contoh 3: Membuat dan memulai contoh PsApiManagementCustomHostNameConfiguration menggunakan Rahasia dari Sumber Daya KeyVault
```powershell
$portal = New-AzApiManagementCustomHostnameConfiguration -Hostname "portal.contoso.com" -HostnameType Portal -KeyVaultId "https://apim-test-keyvault.vault.azure.net/secrets/api-portal-custom-ssl.pfx"
$proxy1 = New-AzApiManagementCustomHostnameConfiguration -Hostname "gatewayl.contoso.com" -HostnameType Proxy -KeyVaultId "https://apim-test-keyvault.vault.azure.net/secrets/contoso-proxy-custom-ssl.pfx"
$proxy2 = New-AzApiManagementCustomHostnameConfiguration -Hostname "gatewayl.foobar.com" -HostnameType Proxy -KeyVaultId "https://apim-test-keyvault.vault.azure.net/secrets/foobar-proxy-custom-ssl.pfx"
$proxyCustomConfig = @($proxy1,$proxy2)
$apim = Get-AzApiManagement -ResourceGroupName "ContosoGroup" -Name "ContosoApi"
$apim.PortalCustomHostnameConfiguration = $portal
$apim.ProxyCustomHostnameConfiguration = $proxyCustomConfig 
Set-AzApiManagement -InputObject $apim -SystemAssignedIdentity
```

### Contoh 4: Perbarui Publisher Email, NotificationSender Email, dan Nama Organisasi
```powershell
$apim = Get-AzApiManagement -ResourceGroupName "api-Default-West-US" -Name "Contoso"
$apim.PublisherEmail = "foobar@contoso.com"
$apim.NotificationSenderEmail = "notification@contoso.com"
$apim.OrganizationName = "Contoso"
Set-AzApiManagement -InputObject $apim -PassThru
```

## PARAMETERS

### -AsJob
Jalankan cmdlet di latar belakang

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Contoh ApiManagement.

```yaml
Type: Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagement
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -PassThru
Mengirimkan PsApiManagement yang diperbarui ke saluran jika operasi berhasil.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SystemAssignedIdentity
Buat dan tetapkan identitas Azure Active Directory untuk server ini untuk digunakan dengan layanan manajemen kunci seperti Azure KeyVault.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UserAssignedIdentity
Tetapkan Identitas Pengguna ke server ini untuk digunakan dengan layanan manajemen kunci seperti Azure KeyVault.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Konfirmasi
Meminta konfirmasi Anda sebelum menjalankan cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan. Cmdlet tidak berjalan.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagement

## OUTPUTS

### Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagement

## CATATAN

## RELATED LINKS

[Get-AzApiManagement](./Get-AzApiManagement.md)

[New-AzApiManagement](./New-AzApiManagement.md)

[Remove-AzApiManagement](./Remove-AzApiManagement.md)
