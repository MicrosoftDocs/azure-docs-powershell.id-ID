---
external help file: Microsoft.Azure.PowerShell.Cmdlets.CosmosDB.dll-Help.xml
Module Name: Az.CosmosDB
online version: https://docs.microsoft.com/powershell/module/az.cosmosdb/new-azcosmosdbaccount
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CosmosDB/CosmosDB/help/New-AzCosmosDBAccount.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CosmosDB/CosmosDB/help/New-AzCosmosDBAccount.md
ms.openlocfilehash: 067981ed5a516d5133f454c4584730e61cfa0595
ms.sourcegitcommit: 579224f3f35e223624deb694bceb0033c84a5856
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 12/07/2021
ms.locfileid: "136524816"
---
# New-AzCosmosDBAccount

## SYNOPSIS
Buat Akun CosmosDB baru.

## SYNTAX

```
New-AzCosmosDBAccount [-EnableAutomaticFailover] [-EnableMultipleWriteLocations] [-EnableVirtualNetwork]
 [-FromPointInTimeBackup] [-ApiKind <String>] [-DisableKeyBasedMetadataWriteAccess] [-EnableFreeTier <Boolean>]
 [-Location <String[]>] [-LocationObject <PSLocation[]>] -ResourceGroupName <String> -Name <String>
 [-DefaultConsistencyLevel <String>] [-IpRule <String[]>] [-MaxStalenessIntervalInSeconds <Int32>]
 [-MaxStalenessPrefix <Int32>] [-Tag <Hashtable>] [-VirtualNetworkRule <String[]>]
 [-VirtualNetworkRuleObject <PSVirtualNetworkRule[]>] [-PublicNetworkAccess <String>]
 [-KeyVaultKeyUri <String>] [-EnableAnalyticalStorage <Boolean>] [-AsJob] [-NetworkAclBypass <String>]
 [-NetworkAclBypassResourceId <String[]>] [-ServerVersion <String>] [-BackupIntervalInMinutes <Int32>]
 [-BackupRetentionIntervalInHours <Int32>] [-BackupStorageRedundancy <String>] [-BackupPolicyType <String>]
 [-AnalyticalStorageSchemaType <String>] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Buat Akun CosmosDB baru di ResourceGroup tertentu.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> New-AzCosmosDBAccount -ResourceGroupName resourceGroupName -Name databaseAccountName  -Location "East US"

Kind                          : GlobalDocumentDB
ProvisioningState             : Initializing
DocumentEndpoint              :
DatabaseAccountOfferType      : Standard
IpRangeFilter                 :
IsVirtualNetworkFilterEnabled : False
EnableAutomaticFailover       : False
ConsistencyPolicy             : Microsoft.Azure.Management.CosmosDB.Models.ConsistencyPolicy
Capabilities                  : {}
WriteLocations                : {databaseAccountName-eastus}
ReadLocations                 : {databaseAccountName-eastus}
FailoverPolicies              : {databaseAccountName-eastus}
VirtualNetworkRules           : {}
EnableMultipleWriteLocations  : False
Location                      : East US
Tags                          : {}
Id                            : /subscriptions/{subscriptionid}/resourceGroups/resourceGroupName/providers/Microsoft.DocumentDB/databaseAccounts/databaseAccountName
Name                          : databaseAccountName
Type                          : Microsoft.DocumentDB/databaseAccounts
NetworkAclBypass              : None
NetworkAclBypassResourceIds   : {}
```

Akun CosmosDB baru dengan nama databaseAccountName dibuat di ResourceGroup resourceGroupName.

### Contoh 2
```powershell
PS C:\> New-AzCosmosDBAccount -ResourceGroupName resourceGroupName -Name restored-account-name  -Location "West US" -FromPointInTimeBackup -RestoreSourceId /subscriptions/{subscriptionId}/providers/Microsoft.DocumentDB/restorableDatabaseAccounts/{instance-id} -RestoreTimesampInUtc 2020-07-20T17:19:25+0000


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

Akun baru dengan nama restoredDatabaseAccountName dibuat dengan memulihkan akun database yang dapat dipulihkan dari Id yang diberikan ke timestamp yang diberikan.

### Contoh 3
```powershell
PS C:\> New-AzCosmosDBAccount -ResourceGroupName resourceGroupName -Name restored-account-name  -Location "West US" -FromPointInTimeBackup -SourceDatabaseAccountName source-database-account-name -RestoreTimesampInUtc 2020-07-20T17:19:25+0000


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

Akun baru dengan nama restoredDatabaseAccountName dibuat dengan memulihkan akun database yang dapat dipulihkan dari Id yang diberikan ke timestamp yang diberikan.

## PARAMETERS

### -AnalyticalStorageSchemaType
Tipe skema untuk penyimpanan analitik. Nilai yang valid meliputi: 'WellDefined' dan 'FullFidelity'.

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

### -ApiKind
Tipe akun database Cosmos DB untuk dibuat.
Nilai yang diterima: GlobalDocumentDB, NulloDB, Databasemlin, Table, Pivot pivot.
Nilai default: GlobalDocumentDB

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

### -BackupIntervalInMinutes
Interval(dalam menit) ketika pencadangan diambil (hanya untuk akun dengan pencadangan mode berkala)

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -BackupPolicyType
Tipe cadangan pada akun Cosmos DB. Nilai yang diterima: Periodik, Berkelanjutan

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

### -BackupRetentionIntervalInHours
Waktu(dalam jam) di mana setiap cadangan dipertahankan (hanya untuk akun dengan pencadangan mode berkala)

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultConsistencyLevel
Tingkat konsistensi default akun database Cosmos DB.
Nilai yang diterima: BoundedStaleness, ConsistentPrefix, Eventual, Session, Strong

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

### -DisableKeyBasedMetadataWriteAccess
Menonaktifkan operasi penulisan pada sumber daya metadata (database, wadah, throughput) melalui kunci akun

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

### -EnableAnalyticalStorage
Bool untuk menunjukkan apakah AnalyticalStorage diaktifkan pada akun tersebut.

```yaml
Type: System.Nullable`1[System.Boolean]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableAutomaticFailover
Mengaktifkan failover otomatis wilayah penulisan pada kejadian yang jarang terjadi karena pemadaman listrik.
Failover otomatis akan menghasilkan kawasan penulisan baru untuk akun tersebut dan dipilih berdasarkan prioritas failover yang dikonfigurasi untuk akun tersebut.
Nilai yang diterima: false, true

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

### -EnableFreeTier
Bool untuk menunjukkan apakah FreeTier diaktifkan pada akun tersebut.

```yaml
Type: System.Nullable`1[System.Boolean]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableMultipleWriteLocations
Mengaktifkan Beberapa Lokasi Penulisan.
Nilai yang diterima: false, true

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

### -EnableVirtualNetwork
Mengaktifkan jaringan virtual di akun database Cosmos DB.
Nilai yang diterima: false, true

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

### -FromPointInTimeBackup
Menunjukkan bahwa permintaan akun Cosmos DB yang baru adalah permintaan pemulihan.

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

### -IpRule
Dukungan firewall. Menentukan kumpulan alamat IP atau rentang alamat IP dalam formulir CIDR untuk disertakan sebagai daftar IP klien yang diperbolehkan untuk akun database tertentu.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -KeyVaultKeyUri
URI dari KeyVault

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

### -Lokasi
Tambahkan lokasi ke akun database Cosmos DB.
Array string, di pesan menurut prioritas failover.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LocationObject
Tambahkan lokasi ke akun database Cosmos DB. Array objek PSLocation.

```yaml
Type: Microsoft.Azure.Commands.CosmosDB.Models.PSLocation[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaxStalenessIntervalInSeconds
Ketika digunakan dengan konsistensi Basi Berterikat, nilai ini menunjukkan jumlah waktu kehentikan (dalam timespan) yang diobjekkan.
Rentang yang diterima untuk nilai ini adalah 5-86400.

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaxStalenessPrefix
Ketika digunakan dengan konsistensi Staleness Terikat, nilai ini menunjukkan jumlah permintaan basi yang diobesakan.
Rentang yang diterima untuk nilai ini adalah 1 - 2.147.483.647.

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
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

### -NetworkAclBypass
Apakah Bypass Acl Jaringan atau tidak diaktifkan untuk akun ini untuk Synapse Link. Kemungkinan nilai meliputi: 'Tidak ada', 'AzureServices'.

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

### -NetworkAclBypassResourceId
Daftar Id Sumber Daya untuk memperbolehkan Bypass Acl Jaringan untuk Link Synapse.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PublicNetworkAccess
Apakah akses titik akhir publik diperbolehkan atau tidak untuk server ini. Nilai yang mungkin disertakan: 'Diaktifkan', 'Dinonaktifkan'

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

### -ResourceGroupName
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

### -ServerVersion
ServerVersion, hanya valid dalam kasus AkunAooDB.

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

### -Tag
Hashtable tag sebagai pasangan nilai kunci.
Gunakan string kosong untuk menghapus tag yang sudah ada.

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

### -VirtualNetworkRule
Array nilai string ACL untuk jaringan virtual.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualNetworkRuleObject
Array PSVirtualNetworkRuleObjects untuk jaringan virtual.

```yaml
Type: Microsoft.Azure.Commands.CosmosDB.Models.PSVirtualNetworkRule[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan.
Cmdlet tidak berjalan.

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

### -BackupStorageRedundancy
Tipe kelebihan data cadangan Storage ini

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.CosmosDB.Models.PSCorsRule[]

## OUTPUTS

### Microsoft.Azure.Commands.CosmosDB.Models.PSDatabaseAccount

## CATATAN

## RELATED LINKS
