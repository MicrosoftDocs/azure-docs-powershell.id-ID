---
external help file: ''
Module Name: Az.ContainerInstance
online version: https://docs.microsoft.com/powershell/module/az.containerinstance/get-azcontainergroup
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ContainerInstance/help/Get-AzContainerGroup.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ContainerInstance/help/Get-AzContainerGroup.md
ms.openlocfilehash: 578ce5d51928921d0eca28823d373af1c1997e4f
ms.sourcegitcommit: 7e47562b11e670049c3a18af7498414da853a921
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/09/2022
ms.locfileid: "138264123"
---
# Get-AzContainerGroup

## SYNOPSIS
Mendapatkan properti grup wadah yang ditentukan dalam langganan dan grup sumber daya yang ditentukan.
Operasi mengembalikan properti setiap grup wadah termasuk wadah, kredensial registri gambar, kebijakan mulai ulang, tipe alamat IP, tipe OS, status, dan volume.

## SYNTAX

### Daftar (Default)
```
Get-AzContainerGroup [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### Dapatkan
```
Get-AzContainerGroup -Name <String> -ResourceGroupName <String> [-SubscriptionId <String[]>]
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### GetViaIdentity
```
Get-AzContainerGroup -InputObject <IContainerInstanceIdentity> [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

### Daftar1
```
Get-AzContainerGroup -ResourceGroupName <String> [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan properti grup wadah yang ditentukan dalam langganan dan grup sumber daya yang ditentukan.
Operasi mengembalikan properti setiap grup wadah termasuk wadah, kredensial registri gambar, kebijakan mulai ulang, tipe alamat IP, tipe OS, status, dan volume.

## EXAMPLES

### Contoh 1:  List all container groups in the current subscription
```powershell
PS C:\> Get-AzContainerGroup

Location Name    Zone ResourceGroupName
-------- ----    ---- -----------------
eastus   test-cg1      test-rg
eastus   test-cg2      test-rg
```

Perintah ini mendapatkan semua grup wadah dalam langganan saat ini.

### Contoh 2: Mendapatkan grup wadah tertentu
```powershell
PS C:\> Get-AzContainerGroup -Name test-cg1 -ResourceGroupName test-rg | fl


Container                      : {test-container1}
DnsConfigNameServer            :
DnsConfigOption                :
DnsConfigSearchDomain          :
EncryptionPropertyKeyName      :
EncryptionPropertyKeyVersion   :
EncryptionPropertyVaultBaseUrl :
IPAddressDnsNameLabel          :
IPAddressFqdn                  :
IPAddressIP                    : 000.000.000.000
IPAddressPort                  : {Microsoft.Azure.PowerShell.Cmdlets.ContainerInsta 
                                 nce.Models.Api20210301.Port, Microsoft.Azure.Power 
                                 Shell.Cmdlets.ContainerInstance.Models.Api20210301 
                                 .Port}
IPAddressType                  : Public
Id                             : /subscriptions/00000000-0000-0000-0000-000000000000 
                                 0/resourceGroups/test-rg/providers/Microsoft.Contai 
                                 nerInstance/containerGroups/test-cg1
IdentityPrincipalId            :
IdentityTenantId               :
IdentityType                   :
IdentityUserAssignedIdentity   : Microsoft.Azure.PowerShell.Cmdlets.ContainerInstan 
                                 ce.Models.Api20210301.ContainerGroupIdentityUserAs 
                                 signedIdentities
ImageRegistryCredentials       :
InitContainer                  : {}
InstanceViewEvent              :
InstanceViewState              :
Location                       : eastus
LogAnalyticLogType             : 
LogAnalyticMetadata            : Microsoft.Azure.PowerShell.Cmdlets.ContainerInstan 
                                 ce.Models.Api20210301.LogAnalyticsMetadata
LogAnalyticWorkspaceId         :
LogAnalyticWorkspaceKey        :
LogAnalyticWorkspaceResourceId : Microsoft.Azure.PowerShell.Cmdlets.ContainerInstan 
                                 ce.Models.Api20210301.LogAnalyticsWorkspaceResourc 
                                 eId
Name                           : test-cg1
NetworkProfileId               :
OSType                         : Linux
ProvisioningState              : Succeeded
ResourceGroupName              : test-rg
RestartPolicy                  : Never
Sku                            : Standard
Tag                            : Microsoft.Azure.PowerShell.Cmdlets.ContainerInstan 
                                 ce.Models.Api20210301.ResourceTags
Type                           : Microsoft.ContainerInstance/containerGroups        
Volume                         :
```

Perintah mendapatkan grup wadah yang ditentukan.

### Contoh 3: Dapatkan grup wadah dalam grup sumber daya
```powershell
PS C:\> Get-AzContainerGroup -ResourceGroupName test-rg

Location Name    Zone ResourceGroupName
-------- ----    ---- -----------------
eastus   test-cg1      test-rg
eastus   test-cg2      test-rg
```

Perintah tersebut mendapatkan grup wadah dalam grup sumber daya `test-rg`.

### Contoh 4: Dapatkan grup wadah dengan pemipaan
```powershell
PS C:\> Update-AzContainerGroup -Name test-cg1 -ResourceGroupName test-rg -Tag @{"test"="value"} | Get-AzContainerGroup

Location Name    Zone ResourceGroupName
-------- ----    ---- -----------------
eastus   test-cg1      test-rg
```

Perintah mendapatkan grup wadah yang diperbarui dengan pemipaan.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases: AzureRMContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Parameter Identitas Untuk membuat, lihat bagian CATATAN untuk properti INPUTOBJECT dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ContainerInstance.Models.IContainerInstanceIdentity
Parameter Sets: GetViaIdentity
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Nama
Nama grup wadah.

```yaml
Type: System.String
Parameter Sets: Get
Aliases: ContainerGroupName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya.

```yaml
Type: System.String
Parameter Sets: Get, List1
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubscriptionId
Kredensial langganan yang secara unik mengidentifikasi Microsoft Azure langganan tersebut.
ID langganan membentuk bagian dari URI untuk setiap panggilan layanan.

```yaml
Type: System.String[]
Parameter Sets: Get, List, List1
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ContainerInstance.Models.IContainerInstanceIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ContainerInstance.Models.Api20210901.IContainerGroup

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT <IContainerInstanceIdentity>: Parameter Identitas
  - `[ContainerGroupName <String>]`: Nama grup wadah.
  - `[ContainerName <String>]`: Contoh nama wadah.
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[Location <String>]`: Pengidentifikasi untuk lokasi azure fisik.
  - `[ResourceGroupName <String>]`: Nama grup sumber daya.
  - `[SubscriptionId <String>]`: Kredensial langganan yang secara unik mengidentifikasi Microsoft Azure langganan. ID langganan membentuk bagian dari URI untuk setiap panggilan layanan.

## RELATED LINKS

