---
external help file: Az.Purview-help.xml
Module Name: Az.Purview
online version: https://docs.microsoft.com/powershell/module/az.purview/update-azpurviewaccount
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Purview/Purview/help/Update-AzPurviewAccount.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Purview/Purview/help/Update-AzPurviewAccount.md
ms.openlocfilehash: 00bf6c3fea8c8158233678335cc16bf77dac7f58
ms.sourcegitcommit: 5df8b100721844736630242c724da453a2168434
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/26/2022
ms.locfileid: "146598522"
---
# Update-AzPurviewAccount

## SYNOPSIS
Updates akun

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.purview/update-azpurviewaccount) untuk informasi terbaru.

## SYNTAX

### UpdateExpanded (Default)
```
Update-AzPurviewAccount -Name <String> -ResourceGroupName <String> [-SubscriptionId <String>]
 [-ManagedResourceGroupName <String>] [-PublicNetworkAccess <PublicNetworkAccess>] [-Tag <Hashtable>]
 [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### UpdateViaIdentityExpanded
```
Update-AzPurviewAccount -InputObject <IPurviewIdentity> [-ManagedResourceGroupName <String>]
 [-PublicNetworkAccess <PublicNetworkAccess>] [-Tag <Hashtable>] [-DefaultProfile <PSObject>] [-AsJob]
 [-NoWait] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Updates akun

## EXAMPLES

### Contoh 1: Memperbarui akun purview
```powershell
Update-AzPurviewAccount -Name test-pa -ResourceGroupName test-rg -Tag @{"k"="v"} | Format-List
```

```output
CloudConnectorAwsExternalId      : xxxxxxxxxx-d074-4f8f-9d7f-10811b250738
CreatedAt                        : 8/17/2021 6:18:57 AM
CreatedBy                        : xxxxx.Zhou@microsoft.com
CreatedByObjectId                : xxxxxxx-5be9-4f43-abd2-04561777c8b0
EndpointCatalog                  : https://test-pa.catalog.purview.azure.com
EndpointGuardian                 : https://test-pa.guardian.purview.azure.com
EndpointScan                     : https://test-pa.scan.purview.azure.com
FriendlyName                     : test-pa
Id                               : /subscriptions/xxxxxxxx-1bf0-4dda-aec3-cb9272f09590/resourceGroups/bez-rg/providers/Microsoft.Purview/a 
                                   ccounts/bez-pa
Identity                         : {
                                     "principalId": "xxxxxxxx-7956-4978-87e8-9ddd82cfe2b7",
                                     "tenantId": "xxxxxxxx-38d6-4fb2-bad9-b7b93a3e9c5a",
                                     "type": "SystemAssigned"
                                   }
IdentityPrincipalId              : xxxxxxxx-7956-4978-87e8-9ddd82cfe2b7
IdentityTenantId                 : xxxxxxxx-38d6-4fb2-bad9-b7b93a3e9c5a
IdentityType                     : SystemAssigned
Location                         : eastus
ManagedResourceEventHubNamespace : /subscriptions/xxxxxxxx-1bf0-4dda-aec3-cb9272f09590/resourceGroups/managed-rg-bbcpgdj/providers/Microso 
                                   ft.EventHub/namespaces/Atlas-2bb7cf0b-5348-4811-a336-759242a25d37
ManagedResourceGroup             : /subscriptions/xxxxxxxx-1bf0-4dda-aec3-cb9272f09590/resourceGroups/managed-rg-bbcpgdj
ManagedResourceGroupName         : managed-rg-bbcpgdj
ManagedResourceStorageAccount    : /subscriptions/xxxxxxxx-1bf0-4dda-aec3-cb9272f09590/resourceGroups/managed-rg-bbcpgdj/providers/Microso 
                                   ft.Storage/storageAccounts/scaneastusnkcccgc
Name                             : test-pa
PrivateEndpointConnection        : {}
ProvisioningState                : Succeeded
PublicNetworkAccess              : Enabled
ResourceGroupName                : test-rg
SkuCapacity                      : 1
SkuName                          : Standard
SystemData                       : {
                                     "createdAt": "2021-08-17T06:18:57.7274115Z",
                                     "createdBy": "xxxxx.Zhou@microsoft.com",
                                     "createdByType": "User",
                                     "lastModifiedAt": "xxxxxx-08-17T06:18:57.7274115Z",
                                     "lastModifiedBy": "Beisi.Zhou@microsoft.com",
                                     "lastModifiedByType": "User"
                                   }
SystemDataCreatedAt              : 8/17/2021 6:18:57 AM
SystemDataCreatedBy              : xxxxx.Zhou@microsoft.com
SystemDataCreatedByType          : User
SystemDataLastModifiedAt         : 8/17/2021 6:18:57 AM
SystemDataLastModifiedBy         : xxxxxx.Zhou@microsoft.com
SystemDataLastModifiedByType     : User
Tag                              : {
                                     "k": "v"
                                   }
Type                             : Microsoft.Purview/account
```

Memperbarui tag akun purview bernama 'test-pa'

### Contoh 2: Memperbarui akun purview oleh InputObject
```powershell
$get = Get-AzPurviewAccount -Name test-pa -ResourceGroupName test-rg 
Update-AzPurviewAccount -InputObject $get -Tag @{"k"="v"}
```

```output
CloudConnectorAwsExternalId      : xxxxxxxxxx-d074-4f8f-9d7f-10811b250738
CreatedAt                        : 8/17/2021 6:18:57 AM
CreatedBy                        : xxxxx.Zhou@microsoft.com
CreatedByObjectId                : xxxxxxx-5be9-4f43-abd2-04561777c8b0
EndpointCatalog                  : https://test-pa.catalog.purview.azure.com
EndpointGuardian                 : https://test-pa.guardian.purview.azure.com
EndpointScan                     : https://test-pa.scan.purview.azure.com
FriendlyName                     : test-pa
Id                               : /subscriptions/xxxxxxxx-1bf0-4dda-aec3-cb9272f09590/resourceGroups/bez-rg/providers/Microsoft.Purview/a 
                                   ccounts/bez-pa
Identity                         : {
                                     "principalId": "xxxxxxxx-7956-4978-87e8-9ddd82cfe2b7",
                                     "tenantId": "xxxxxxxx-38d6-4fb2-bad9-b7b93a3e9c5a",
                                     "type": "SystemAssigned"
                                   }
IdentityPrincipalId              : xxxxxxxx-7956-4978-87e8-9ddd82cfe2b7
IdentityTenantId                 : xxxxxxxx-38d6-4fb2-bad9-b7b93a3e9c5a
IdentityType                     : SystemAssigned
Location                         : eastus
ManagedResourceEventHubNamespace : /subscriptions/xxxxxxxx-1bf0-4dda-aec3-cb9272f09590/resourceGroups/managed-rg-bbcpgdj/providers/Microso 
                                   ft.EventHub/namespaces/Atlas-2bb7cf0b-5348-4811-a336-759242a25d37
ManagedResourceGroup             : /subscriptions/xxxxxxxx-1bf0-4dda-aec3-cb9272f09590/resourceGroups/managed-rg-bbcpgdj
ManagedResourceGroupName         : managed-rg-bbcpgdj
ManagedResourceStorageAccount    : /subscriptions/xxxxxxxx-1bf0-4dda-aec3-cb9272f09590/resourceGroups/managed-rg-bbcpgdj/providers/Microso 
                                   ft.Storage/storageAccounts/scaneastusnkcccgc
Name                             : test-pa
PrivateEndpointConnection        : {}
ProvisioningState                : Succeeded
PublicNetworkAccess              : Enabled
ResourceGroupName                : test-rg
SkuCapacity                      : 1
SkuName                          : Standard
SystemData                       : {
                                     "createdAt": "2021-08-17T06:18:57.7274115Z",
                                     "createdBy": "xxxxx.Zhou@microsoft.com",
                                     "createdByType": "User",
                                     "lastModifiedAt": "xxxxxx-08-17T06:18:57.7274115Z",
                                     "lastModifiedBy": "Beisi.Zhou@microsoft.com",
                                     "lastModifiedByType": "User"
                                   }
SystemDataCreatedAt              : 8/17/2021 6:18:57 AM
SystemDataCreatedBy              : xxxxx.Zhou@microsoft.com
SystemDataCreatedByType          : User
SystemDataLastModifiedAt         : 8/17/2021 6:18:57 AM
SystemDataLastModifiedBy         : xxxxxx.Zhou@microsoft.com
SystemDataLastModifiedByType     : User
Tag                              : {
                                     "k": "v"
                                   }
Type                             : Microsoft.Purview/account
```

Memperbarui tag akun purview bernama 'test-pa' oleh InputObject

## PARAMETERS

### -AsJob
Jalankan perintah sebagai pekerjaan

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
Parameter Identitas Untuk membangun, lihat bagian CATATAN untuk properti INPUTOBJECT dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Purview.Models.IPurviewIdentity
Parameter Sets: UpdateViaIdentityExpanded
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ManagedResourceGroupName
Mendapatkan atau mengatur nama grup sumber daya terkelola

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Nama akun.

```yaml
Type: System.String
Parameter Sets: UpdateExpanded
Aliases: AccountName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoWait
Jalankan perintah secara asinkron

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

### -PublicNetworkAccess
Mendapatkan atau mengatur akses jaringan publik.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Purview.Support.PublicNetworkAccess
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya.

```yaml
Type: System.String
Parameter Sets: UpdateExpanded
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubscriptionId
Pengidentifikasi langganan

```yaml
Type: System.String
Parameter Sets: UpdateExpanded
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### -Tag
Tag pada sumber daya azure.

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm
Meminta Anda mengonfirmasi sebelum menjalankan cmdlet.

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
Menunjukkan yang akan terjadi jika cmdlet dijalankan.
Cmdlet tidak dijalankan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Purview.Models.IPurviewIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Purview.Models.Api20210701.IAccount

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT `<IPurviewIdentity>`: Parameter Identitas
  - `[AccountName <String>]`: Nama akun.
  - `[GroupId <String>]`: Pengidentifikasi grup.
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[PrivateEndpointConnectionName <String>]`: Nama koneksi titik akhir privat.
  - `[ResourceGroupName <String>]`: Nama grup sumber daya.
  - `[SubscriptionId <String>]`: Pengidentifikasi langganan

## RELATED LINKS
