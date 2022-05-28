---
external help file: ''
Module Name: Az.Synapse
online version: https://docs.microsoft.com/powershell/module/az.synapse/update-azsynapsekustopooldataconnection
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Update-AzSynapseKustoPoolDataConnection.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Update-AzSynapseKustoPoolDataConnection.md
ms.openlocfilehash: 42494de4f0525819198c588d0d77ee40d4b8c866
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145546628"
---
# Update-AzSynapseKustoPoolDataConnection

## SYNOPSIS
Memperbarui koneksi data.

## SYNTAX

### UpdateExpandedEventHub (Default)
```
Update-AzSynapseKustoPoolDataConnection -DatabaseName <String> -DataConnectionName <String>
 -KustoPoolName <String> -ResourceGroupName <String> -WorkspaceName <String> -ConsumerGroup <String>
 -EventHubResourceId <String> -Kind <DataConnectionKind> -Location <String> [-SubscriptionId <String>]
 [-Compression <Compression>] [-DataFormat <EventGridDataFormat>] [-EventSystemProperty <String[]>]
 [-MappingRuleName <String>] [-TableName <String>] [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-Confirm]
 [-WhatIf] [<CommonParameters>]
```

### UpdateExpandedEventGrid
```
Update-AzSynapseKustoPoolDataConnection -DatabaseName <String> -DataConnectionName <String>
 -KustoPoolName <String> -ResourceGroupName <String> -WorkspaceName <String> -ConsumerGroup <String>
 -EventHubResourceId <String> -Kind <DataConnectionKind> -Location <String> -StorageAccountResourceId <String>
 [-SubscriptionId <String>] [-BlobStorageEventType <BlobStorageEventType>] [-DataFormat <EventGridDataFormat>]
 [-IgnoreFirstRecord] [-MappingRuleName <String>] [-TableName <String>] [-DefaultProfile <PSObject>] [-AsJob]
 [-NoWait] [-Confirm] [-WhatIf] [<CommonParameters>]
```

### UpdateExpandedIotHub
```
Update-AzSynapseKustoPoolDataConnection -DatabaseName <String> -DataConnectionName <String>
 -KustoPoolName <String> -ResourceGroupName <String> -WorkspaceName <String> -ConsumerGroup <String>
 -IotHubResourceId <String> -Kind <DataConnectionKind> -Location <String> -SharedAccessPolicyName <String>
 [-SubscriptionId <String>] [-DataFormat <EventGridDataFormat>] [-EventSystemProperty <String[]>]
 [-MappingRuleName <String>] [-TableName <String>] [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-Confirm]
 [-WhatIf] [<CommonParameters>]
```

### UpdateViaIdentityExpandedEventGrid
```
Update-AzSynapseKustoPoolDataConnection -InputObject <ISynapseIdentity> -ConsumerGroup <String>
 -EventHubResourceId <String> -Kind <DataConnectionKind> -Location <String> -StorageAccountResourceId <String>
 [-BlobStorageEventType <BlobStorageEventType>] [-DataFormat <EventGridDataFormat>] [-IgnoreFirstRecord]
 [-MappingRuleName <String>] [-TableName <String>] [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-Confirm]
 [-WhatIf] [<CommonParameters>]
```

### UpdateViaIdentityExpandedEventHub
```
Update-AzSynapseKustoPoolDataConnection -InputObject <ISynapseIdentity> -ConsumerGroup <String>
 -EventHubResourceId <String> -Kind <DataConnectionKind> -Location <String> [-Compression <Compression>]
 [-DataFormat <EventGridDataFormat>] [-EventSystemProperty <String[]>] [-MappingRuleName <String>]
 [-TableName <String>] [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-Confirm] [-WhatIf]
 [<CommonParameters>]
```

### UpdateViaIdentityExpandedIotHub
```
Update-AzSynapseKustoPoolDataConnection -InputObject <ISynapseIdentity> -ConsumerGroup <String>
 -IotHubResourceId <String> -Kind <DataConnectionKind> -Location <String> -SharedAccessPolicyName <String>
 [-DataFormat <EventGridDataFormat>] [-EventSystemProperty <String[]>] [-MappingRuleName <String>]
 [-TableName <String>] [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-Confirm] [-WhatIf]
 [<CommonParameters>]
```

## DESCRIPTION
Memperbarui koneksi data.

## EXAMPLES

### Contoh 1: Memperbarui koneksi data EventHub yang ada
```powershell
Update-AzSynapseKustoPoolDataConnection -ResourceGroupName testrg -WorkspaceName testws -KustoPoolName testkustopool -DatabaseName testdatabase -Name eventhubdc -Location eastus2 -Kind EventHub -EventHubResourceId "/subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/testrg/providers/Microsoft.EventHub/namespaces/testeventhubns/eventhubs/testeventhub" -DataFormat "JSON" -ConsumerGroup '$Default' -Compression "None" -TableName "Events" -MappingRuleName "EventsMapping"
```

```output
Kind     Location  Name                                            
----     --------  ----                                            
EventHub East US 2 testws/testkustopool/testdatabase/eventhubdc
```

Perintah di atas memperbarui koneksi data EventHub yang ada bernama "eventhubdc" untuk database "testdatabase" di kumpulan kusto "testkustopool".

### Contoh 2: Memperbarui koneksi data EventGrid yang ada
```powershell
Update-AzSynapseKustoPoolDataConnection -ResourceGroupName testrg -WorkspaceName testws -KustoPoolName testkustopool -DatabaseName testdatabase -Name eventgriddc -Location eastus2 -Kind EventGrid -EventHubResourceId "/subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/testrg/providers/Microsoft.EventHub/namespaces/testeventhubns/eventhubs/testeventhub" -StorageAccountResourceId "/subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/testrg/providers/Microsoft.Storage/storageAccounts/teststorage" -DataFormat "JSON" -ConsumerGroup '$Default' -TableName "Events" -MappingRuleName "EventsMapping"
```

```output
Kind      Location  Name
----      --------  ----                                              
EventGrid East US 2 testws/testkustopool/testdatabase/eventgriddc
```

Perintah di atas memperbarui koneksi data EventGrid yang ada bernama "eventgriddc" untuk database "testdatabase" di kumpulan kusto "testkustopool".

### Contoh 3: Memperbarui koneksi data IotHub yang ada
```powershell
Update-AzSynapseKustoPoolDataConnection -ResourceGroupName testrg -WorkspaceName testws -KustoPoolName testkustopool -DatabaseName testdatabase -Name iothubdc -Location eastus2 -Kind IotHub -IotHubResourceId "/subscriptions/051ddeca-1ed6-4d8b-ba6f-1ff561e5f3b3/resourceGroups/ywtest/providers/Microsoft.Devices/IotHubs/ywtestiothub" -SharedAccessPolicyName registryRead -DataFormat "JSON" -ConsumerGroup '$Default' -TableName "Events" -MappingRuleName "EventsMapping"
```

```output
Kind   Location  Name 
----   --------  ----                                           
IotHub East US 2 testws/testkustopool/testdatabase/iothubdc
```

Perintah di atas memperbarui koneksi data IotHub yang ada bernama "iothubdc" untuk database "testdatabase" di kumpulan kusto "testkustopool".

### Contoh 4: Memperbarui koneksi data EventHub yang ada melalui identitas
```powershell
$dataConnection = Get-AzSynapseKustoPoolDataConnection -ResourceGroupName testrg -WorkspaceName testws -KustoPoolName testkustopool -DatabaseName testdatabase -Name eventhubdc
Update-AzSynapseKustoPoolDataConnection -InputObject $dataConnection -Location eastus2 -Kind EventHub -EventHubResourceId "/subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/testrg/providers/Microsoft.EventHub/namespaces/testeventhubns/eventhubs/testeventhub" -DataFormat "JSON" -ConsumerGroup '$Default' -Compression "None" -TableName "Events" -MappingRuleName "EventsMapping"
```

```output
Kind     Location  Name                                            
----     --------  ----                                            
EventHub East US 2 testws/testkustopool/testdatabase/eventhubdc
```

Perintah di atas memperbarui koneksi data EventHub yang ada bernama "eventhubdc" untuk database "testdatabase" di kumpulan kusto "testkustopool".

### Contoh 5: Memperbarui koneksi data EventGrid yang ada melalui identitas
```powershell
$dataConnection = Get-AzSynapseKustoPoolDataConnection -ResourceGroupName testrg -WorkspaceName testws -KustoPoolName testkustopool -DatabaseName testdatabase -Name eventgriddc
Update-AzSynapseKustoPoolDataConnection -InputObject $dataConnection -Location eastus2 -Kind EventGrid -EventHubResourceId "/subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/testrg/providers/Microsoft.EventHub/namespaces/testeventhubns/eventhubs/testeventhub" -StorageAccountResourceId "/subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/testrg/providers/Microsoft.Storage/storageAccounts/teststorage" -DataFormat "JSON" -ConsumerGroup '$Default' -TableName "Events" -MappingRuleName "EventsMapping"
```

```output
Kind      Location  Name
----      --------  ----                                              
EventGrid East US 2 testws/testkustopool/testdatabase/eventgriddc
```

Perintah di atas memperbarui koneksi data EventGrid yang ada bernama "eventgriddc" untuk database "testdatabase" di kumpulan kusto "testkustopool".

### Contoh 6: Memperbarui koneksi data IotHub yang ada melalui identitas
```powershell
$dataConnection = Get-AzSynapseKustoPoolDataConnection -ResourceGroupName testrg -WorkspaceName testws -KustoPoolName testkustopool -DatabaseName testdatabase -Name iothubdc
Update-AzSynapseKustoPoolDataConnection -InputObject $dataConnection -Location eastus2 -Kind IotHub -IotHubResourceId "/subscriptions/051ddeca-1ed6-4d8b-ba6f-1ff561e5f3b3/resourceGroups/ywtest/providers/Microsoft.Devices/IotHubs/ywtestiothub" -SharedAccessPolicyName registryRead -DataFormat "JSON" -ConsumerGroup '$Default' -TableName "Events" -MappingRuleName "EventsMapping"
```

```output
Kind   Location  Name 
----   --------  ----                                           
IotHub East US 2 testws/testkustopool/testdatabase/iothubdc
```

Perintah di atas memperbarui koneksi data IotHub yang ada bernama "iothubdc" untuk database "testdatabase" di kumpulan kusto "testkustopool".

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

### -BlobStorageEventType
Nama jenis peristiwa penyimpanan blob yang akan diproses.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Synapse.Support.BlobStorageEventType
Parameter Sets: UpdateExpandedEventGrid, UpdateViaIdentityExpandedEventGrid
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Kompresi
Jenis kompresi pesan pusat aktivitas.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Synapse.Support.Compression
Parameter Sets: UpdateExpandedEventHub, UpdateViaIdentityExpandedEventHub
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ConsumerGroup
Grup konsumen event/iot hub.

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

### -DatabaseName
Nama database di kumpulan Kusto.

```yaml
Type: System.String
Parameter Sets: UpdateExpandedEventGrid, UpdateExpandedEventHub, UpdateExpandedIotHub
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DataConnectionName
Nama koneksi data.

```yaml
Type: System.String
Parameter Sets: UpdateExpandedEventGrid, UpdateExpandedEventHub, UpdateExpandedIotHub
Aliases: Name

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DataFormat
Format data pesan.
Secara opsional, format data dapat ditambahkan ke setiap pesan.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Synapse.Support.EventGridDataFormat
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

### -EventHubResourceId
ID sumber daya pusat aktivitas yang akan digunakan untuk membuat koneksi data/kisi peristiwa dikonfigurasi untuk mengirim peristiwa.

```yaml
Type: System.String
Parameter Sets: UpdateExpandedEventGrid, UpdateExpandedEventHub, UpdateViaIdentityExpandedEventGrid, UpdateViaIdentityExpandedEventHub
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EventSystemProperty
Properti sistem dari hub peristiwa/iot.

```yaml
Type: System.String[]
Parameter Sets: UpdateExpandedEventHub, UpdateExpandedIotHub, UpdateViaIdentityExpandedEventHub, UpdateViaIdentityExpandedIotHub
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IgnoreFirstRecord
Jika diatur ke true, menunjukkan bahwa penyerapan harus mengabaikan catatan pertama setiap file.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: UpdateExpandedEventGrid, UpdateViaIdentityExpandedEventGrid
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Parameter Identitas Untuk membangun, lihat bagian CATATAN untuk properti INPUTOBJECT dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Synapse.Models.ISynapseIdentity
Parameter Sets: UpdateViaIdentityExpandedEventGrid, UpdateViaIdentityExpandedEventHub, UpdateViaIdentityExpandedIotHub
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -IotHubResourceId
ID sumber daya hub Iot yang akan digunakan untuk membuat koneksi data.

```yaml
Type: System.String
Parameter Sets: UpdateExpandedIotHub, UpdateViaIdentityExpandedIotHub
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Jenis
Jenis titik akhir untuk koneksi data

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Synapse.Support.DataConnectionKind
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -KustoPoolName
Nama kumpulan Kusto.

```yaml
Type: System.String
Parameter Sets: UpdateExpandedEventGrid, UpdateExpandedEventHub, UpdateExpandedIotHub
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Lokasi
Lokasi sumber daya.

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

### -MappingRuleName
Aturan pemetaan yang akan digunakan untuk menyerap data.
Secara opsional, informasi pemetaan dapat ditambahkan ke setiap pesan.

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

### -ResourceGroupName
Nama grup sumber daya.
Nama tidak peka huruf besar/kecil.

```yaml
Type: System.String
Parameter Sets: UpdateExpandedEventGrid, UpdateExpandedEventHub, UpdateExpandedIotHub
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SharedAccessPolicyName
Nama kebijakan akses berbagi.

```yaml
Type: System.String
Parameter Sets: UpdateExpandedIotHub, UpdateViaIdentityExpandedIotHub
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageAccountResourceId
ID sumber daya akun penyimpanan tempat data berada.

```yaml
Type: System.String
Parameter Sets: UpdateExpandedEventGrid, UpdateViaIdentityExpandedEventGrid
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubscriptionId
ID langganan target.

```yaml
Type: System.String
Parameter Sets: UpdateExpandedEventGrid, UpdateExpandedEventHub, UpdateExpandedIotHub
Aliases:

Required: True
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### -TableName
Tabel tempat data harus diserap.
Secara opsional informasi tabel dapat ditambahkan ke setiap pesan.

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

### -WorkspaceName
Nama ruang kerja

```yaml
Type: System.String
Parameter Sets: UpdateExpandedEventGrid, UpdateExpandedEventHub, UpdateExpandedIotHub
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

### Microsoft.Azure.PowerShell.Cmdlets.Synapse.Models.ISynapseIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Synapse.Models.Api20210601Preview.IDataConnection

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT <ISynapseIdentity>: Parameter Identitas
  - `[AttachedDatabaseConfigurationName <String>]`: Nama konfigurasi database terlampir.
  - `[DataConnectionName <String>]`: Nama koneksi data.
  - `[DatabaseName <String>]`: Nama database di kumpulan Kusto.
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[KustoPoolName <String>]`: Nama kumpulan Kusto.
  - `[Location <String>]`: Nama wilayah Azure.
  - `[PrincipalAssignmentName <String>]`: Nama Kusto principalAssignment.
  - `[ResourceGroupName <String>]`: Nama grup sumber daya. Nama tidak peka huruf besar/kecil.
  - `[SubscriptionId <String>]`: ID langganan target.
  - `[WorkspaceName <String>]`: Nama ruang kerja

## RELATED LINKS

