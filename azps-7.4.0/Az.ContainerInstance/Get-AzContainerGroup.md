---
external help file: ''
Module Name: Az.ContainerInstance
online version: https://docs.microsoft.com/powershell/module/az.containerinstance/get-azcontainergroup
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ContainerInstance/help/Get-AzContainerGroup.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ContainerInstance/help/Get-AzContainerGroup.md
ms.openlocfilehash: fdfe7037db630d230c79bcb98dde9e3643fa5658
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144648138"
---
# Get-AzContainerGroup

## SYNOPSIS
Mendapatkan properti grup kontainer yang ditentukan dalam grup langganan dan sumber daya yang ditentukan.
Operasi mengembalikan properti setiap grup kontainer termasuk kontainer, kredensial registri gambar, kebijakan hidupkan ulang, jenis alamat IP, jenis OS, status, dan volume.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.containerinstance/get-azcontainergroup) untuk informasi terbaru.

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
Mendapatkan properti grup kontainer yang ditentukan dalam grup langganan dan sumber daya yang ditentukan.
Operasi mengembalikan properti setiap grup kontainer termasuk kontainer, kredensial registri gambar, kebijakan hidupkan ulang, jenis alamat IP, jenis OS, status, dan volume.

## EXAMPLES

### Contoh 1: Mencantumkan semua grup kontainer dalam langganan saat ini
```powershell
Get-AzContainerGroup
```

```output
Location Name    Zone ResourceGroupName
-------- ----    ---- -----------------
eastus   test-cg1      test-rg
eastus   test-cg2      test-rg
```

Perintah ini mendapatkan semua grup kontainer dalam langganan saat ini.

### Contoh 2: Mendapatkan grup kontainer tertentu
```powershell
Get-AzContainerGroup -Name test-cg1 -ResourceGroupName test-rg | Format-List
```

```output
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

Perintah mendapatkan grup kontainer yang ditentukan.

### Contoh 3: Mendapatkan grup kontainer dalam grup sumber daya
```powershell
Get-AzContainerGroup -ResourceGroupName test-rg
```

```output
Location Name    Zone ResourceGroupName
-------- ----    ---- -----------------
eastus   test-cg1      test-rg
eastus   test-cg2      test-rg
```

Perintah mendapatkan grup kontainer dalam grup `test-rg`sumber daya .

### Contoh 4: Mendapatkan grup kontainer dengan menyalurkan
```powershell
Update-AzContainerGroup -Name test-cg1 -ResourceGroupName test-rg -Tag @{"test"="value"} | Get-AzContainerGroup
```

```output
Location Name    Zone ResourceGroupName
-------- ----    ---- -----------------
eastus   test-cg1      test-rg
```

Perintah mendapatkan grup kontainer yang diperbarui dengan menyalurkan.

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
Parameter Identitas Untuk membangun, lihat bagian CATATAN untuk properti INPUTOBJECT dan buat tabel hash.

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

### -Name
Nama grup kontainer.

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
Kredensial langganan yang secara unik mengidentifikasi langganan Microsoft Azure.
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ContainerInstance.Models.IContainerInstanceIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ContainerInstance.Models.Api20210901.IContainerGroup

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT <IContainerInstanceIdentity>: Parameter Identitas
  - `[ContainerGroupName <String>]`: Nama grup kontainer.
  - `[ContainerName <String>]`: Nama instans kontainer.
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[Location <String>]`: Pengidentifikasi untuk lokasi azure fisik.
  - `[ResourceGroupName <String>]`: Nama grup sumber daya.
  - `[SubscriptionId <String>]`: Kredensial langganan yang secara unik mengidentifikasi langganan Microsoft Azure. ID langganan membentuk bagian dari URI untuk setiap panggilan layanan.

## RELATED LINKS

