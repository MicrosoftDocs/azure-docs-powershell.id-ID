---
external help file: Microsoft.Azure.PowerShell.Cmdlets.CosmosDB.dll-Help.xml
Module Name: Az.CosmosDB
online version: https://docs.microsoft.com/powershell/module/az.cosmosdb/restore-azcosmosdbaccount
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CosmosDB/CosmosDB/help/Restore-AzCosmosDBAccount.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CosmosDB/CosmosDB/help/Restore-AzCosmosDBAccount.md
ms.openlocfilehash: f7dacbac59b2f836eb132dc7e630b998627f723c
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144592362"
---
# Restore-AzCosmosDBAccount

## SYNOPSIS
Memulihkan akun CosmosDB yang ada (langsung atau dihapus) ke tanda waktu tertentu ke akun baru

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.cosmosdb/restore-azcosmosdbaccount) untuk informasi terbaru.

## SYNTAX

```
Restore-AzCosmosDBAccount -RestoreTimestampInUtc <DateTime> -SourceDatabaseAccountName <String>
 -Location <String> -TargetResourceGroupName <String> -TargetDatabaseAccountName <String>
 [-DatabasesToRestore <PSDatabaseToRestore[]>] [-AsJob] [-DefaultProfile <IAzureContextContainer>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Membuat akun CosmosDB baru dengan memulihkan akun yang ada dengan nama dan tanda waktu yang diberikan.

## EXAMPLES

### Contoh 1
```powershell
Restore-AzCosmosDBAccount -TargetResourceGroupName resourceGroupName -TargetDatabaseAccountName restored-account-name  -SourceDatabaseAccountName sourceDatabaseAccountName -RestoreTimestampInUtc 2020-07-20T17:19:25+0000 -Location "West US"
```

```output
Id                                 : /subscriptions/259fbb24-9bcd-4cfc-865c-fc33b22fe38a/resourceGroups/resourceGroupName/providers/Microsoft.DocumentDB/databaseAccounts/restored-account-name
Name                               : restored-account-name
InstanceId                         : eeb45f7f-4c05-4b52-9f42-6807d8eb8703
Location                           : West US
Tags                               : {}
EnableCassandraConnector           :
EnableMultipleWriteLocations       : False
VirtualNetworkRules                : {}
FailoverPolicies                   : {restored-account-name-westus}
Locations                          : {restored-account-name-westus}
ReadLocations                      : {restored-account-name-westus}
WriteLocations                     : {restored-account-name-westus}
Capabilities                       : {}
ConsistencyPolicy                  : Microsoft.Azure.Management.CosmosDB.Models.ConsistencyPolicy
EnableAutomaticFailover            : False
IsVirtualNetworkFilterEnabled      : False
IpRules                            : {}
DatabaseAccountOfferType           : Standard
DocumentEndpoint                   : https://restored-account-name.documents.azure.com:443/
ProvisioningState                  : Succeeded
Kind                               : GlobalDocumentDB
ConnectorOffer                     :
DisableKeyBasedMetadataWriteAccess : False
PublicNetworkAccess                : Enabled
KeyVaultKeyUri                     :
PrivateEndpointConnections         :
EnableFreeTier                     : False
ApiProperties                      : Microsoft.Azure.Commands.CosmosDB.Models.PSApiProperties
EnableAnalyticalStorage            : False
BackupPolicy                       : Microsoft.Azure.Commands.CosmosDB.Models.PSBackupPolicy
RestoreParameters                  : Microsoft.Azure.Commands.CosmosDB.Models.PSRestoreParameters
CreateMode                         : Restore
```

{{ Membuat akun CosmosDB baru dengan memulihkan akun yang sudah ada dengan nama dan tanda waktu yang diberikan. }}

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

### -DatabasesToRestore
Daftar objek PSDatabaseToRestore yang menentukan subset database dan koleksi untuk dipulihkan dari akun sumber. (Jika tidak disediakan, semua database akan dipulihkan)

```yaml
Type: Microsoft.Azure.Commands.CosmosDB.Models.PSDatabaseToRestore[]
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

### -Lokasi
Lokasi akun sumber tempat pemulihan dipicu.
Ini juga akan menjadi wilayah tulis dari akun yang dipulihkan

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RestoreTimestampInUtc
Tanda waktu tempat akun sumber harus dipulihkan.

```yaml
Type: System.DateTime
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SourceDatabaseAccountName
Nama akun database sumber pemulihan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetDatabaseAccountName
Nama akun database Cosmos DB.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetResourceGroupName
Nama grup sumber daya.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
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

### Tidak ada

## OUTPUTS

### Microsoft.Azure.Commands.CosmosDB.Models.PSDatabaseAccountGetResults

## NOTES

## RELATED LINKS
