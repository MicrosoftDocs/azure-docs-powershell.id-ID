---
external help file: Microsoft.Azure.PowerShell.Cmdlets.EventHub.dll-Help.xml
Module Name: Az.EventHub
online version: https://docs.microsoft.com/powershell/module/az.eventhub/set-azeventhubnamespace
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/EventHub/EventHub/help/Set-AzEventHubNamespace.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/EventHub/EventHub/help/Set-AzEventHubNamespace.md
ms.openlocfilehash: 9f6987823df433b63272959f50fe3c56a4a6a3c0
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144627240"
---
# Set-AzEventHubNamespace

## SYNOPSIS
Memperbarui namespace layanan Azure Event Hubs yang ditentukan.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.eventhub/set-azeventhubnamespace) untuk informasi terbaru.

## SYNTAX

### NamespaceParameterSet (Default)
```
Set-AzEventHubNamespace [-ResourceGroupName] <String> [-Name] <String> [[-Location] <String>]
 [[-SkuName] <String>] [[-SkuCapacity] <Int32>] [[-State] <NamespaceState>] [[-Tag] <Hashtable>] [-EnableKafka]
 [-DisableLocalAuth] [-IdentityType <String>] [-IdentityId <String[]>]
 [-EncryptionConfig <PSEncryptionConfigAttributes[]>] [-Identity] [-IdentityUserDefined <String>]
 [-KeySource <String>] [-KeyProperty <System.Collections.Generic.List`1[System.String[]]>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### AutoInflateParameterSet
```
Set-AzEventHubNamespace [-ResourceGroupName] <String> [-Name] <String> [[-Location] <String>]
 [[-SkuName] <String>] [[-SkuCapacity] <Int32>] [[-State] <NamespaceState>] [[-Tag] <Hashtable>]
 [-EnableAutoInflate] [-MaximumThroughputUnits <Int32>] [-EnableKafka] [-DisableLocalAuth]
 [-IdentityType <String>] [-IdentityId <String[]>] [-EncryptionConfig <PSEncryptionConfigAttributes[]>]
 [-Identity] [-IdentityUserDefined <String>] [-KeySource <String>]
 [-KeyProperty <System.Collections.Generic.List`1[System.String[]]>] [-DefaultProfile <IAzureContextContainer>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### IdentityUpdateParameterSet
```
Set-AzEventHubNamespace [-ResourceGroupName] <String> [-Name] <String> [[-Location] <String>]
 [[-SkuName] <String>] [[-SkuCapacity] <Int32>] [[-Tag] <Hashtable>] [-EnableAutoInflate]
 [-MaximumThroughputUnits <Int32>] [-EnableKafka] [-Identity] [-DefaultProfile <IAzureContextContainer>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet Set-AzEventHubNamespace memperbarui properti namespace Layanan Pusat Aktivitas yang ditentukan.

## EXAMPLES

### Contoh 1
```powershell
Set-AzEventHubNamespace -ResourceGroupName MyResourceGroupName -NamespaceName MyNamespaceName -Location "WestUS" -Tag @{Tag1='TagValue1'; Tag2='TagValue2'}
```

```output
Name                   : MyNamespaceName
Id                     : /subscriptions/{subscriptionId}/resourceGroups/Default-EventHub-WestCentralUS/providers/Microsoft.EventHub/namespaces/MyNamespaceName
ResourceGroupName      : Default-EventHub-WestCentralUS
Location               : West US
Sku                    : Name : Standard , Capacity : 1 , Tier : Standard
Tags                   : {Tag2, TagValue2, Tag1, TagValue1}
ProvisioningState      : Succeeded
Status                 : Active
CreatedAt              : 5/24/2019 12:47:27 AM
UpdatedAt              : 5/24/2019 12:48:14 AM
ServiceBusEndpoint     : #########
Enabled                : True
KafkaEnabled           : True
IsAutoInflateEnabled   : True
MaximumThroughputUnits : 10

```

Memperbarui Tag untuk namespace \`MyNamespaceName\` menjadi Dibuat.

### Contoh 2
```powershell
Set-AzEventHubNamespace -ResourceGroupName MyResourceGroupName -NamespaceName MyNamespaceName -Location "WestUS" -State Created -EnableAutoInflate -MaximumThroughputUnits 10 
```

```output
Name                   : MyNamespaceName
Id                     : /subscriptions/{subscriptionId}/resourceGroups/Default-EventHub-WestCentralUS/providers/Microsoft.EventHub/namespaces/MyNamespaceName
ResourceGroup          : Default-EventHub-WestCentralUS
ResourceGroupName      : Default-EventHub-WestCentralUS
Location               : West US
Sku                    : Name : Standard , Capacity : 1 , Tier : Standard
Tags                   :
ProvisioningState      : Succeeded
Status                 : Active
CreatedAt              : 5/24/2019 12:47:27 AM
UpdatedAt              : 5/24/2019 12:48:14 AM
ServiceBusEndpoint     : #########
Enabled                : True
KafkaEnabled           : True
IsAutoInflateEnabled   : True
MaximumThroughputUnits : 10
```

Memperbarui status namespace \`MyNamespaceName\` dengan AutoInflate = diaktifkan dan MaximumThroughputUnits = 10

### Contoh 3

Memperbarui namespace layanan Azure Event Hubs yang ditentukan. (dibuat otomatis)

```powershell <!-- Aladdin Generated Example --> 
Set-AzEventHubNamespace -Location 'WestUS' -Name MyNamespaceName -ResourceGroupName MyResourceGroupName -SkuName Basic
```

### Contoh 4: Mengaktifkan enkripsi identitas yang ditetapkan sistem pada namespace

```powershell
New-AzEventHubNamespace -ResourceGroupName myresourcegroup -Name MyNamespaceName -Location northeurope -SkuName Premium -IdentityType SystemAssigned

$ec1 = New-AzEventHubEncryptionConfig -KeyName key1 -KeyVaultUri https://myvaultname.vault.azure.net

$ec2 = New-AzEventHubEncryptionConfig -KeyName key2 -KeyVaultUri https://myvaultname.vault.azure.net

Set-AzEventHubNamespace -ResourceGroupName myresourcegroup -Name MyNamespaceName -EncryptionConfig $ec1,$ec2
```

```output
Name                          : MyNamespaceName
Id                            : /subscriptions/{subscriptionId}/resourceGroups/myresourcegroup/providers/Microsoft.EventHub/namespaces/MyNamespaceName
ResourceGroupName             : Default-EventHub-WestCentralUS
Location                      : West US
Sku                           : Name : Standard , Capacity : 1 , Tier : Standard
Tags                          :
ProvisioningState             : Succeeded
Status                        : Active
CreatedAt                     : 6/12/2020 4:00:29 AM
UpdatedAt                     : 6/14/2020 11:33:12 PM
ServiceBusEndpoint            : #########
Enabled                       : True
KafkaEnabled                  : True
IsAutoInflateEnabled          : True
MaximumThroughputUnits        : 10
ZoneRedundant                 : False
ClusterArmId                  : /subscriptions/{subscriptionId}/resourceGroups/Default-EventHub-WestCentralUS/providers/Microsoft.EventHub/clusters/TestCluster
Encryption                    : Microsoft.Azure.Commands.EventHub.Models.PSEncryptionAttributes
Encryption.KeySource          : MicrosoftKeyVault
Identity                      : PrinicipalId : 000000,
                                TenantId: 000000,
                                Type: SystemAssigned,
                                UserAssignedIdentity: 
IdentityType                  : SystemAssigned
IdentityId                    : 
EncryptionConfig              : {{ KeyName: key1,
                                   KeyVaultUri: https://myvaultname.vault.azure.net,
                                   KeyVersion: ,
                                   UserAssignedIdentity: 
                                 },
                                 {
                                   KeyName: key2,
                                   KeyVaultUri: https://myvaultname.vault.azure.net,
                                   KeyVersion: ,
                                   UserAssignedIdentity: 
                                 }}
```

Buat namespace layanan dengan Identitas yang Ditetapkan Sistem diaktifkan lalu gunakan Perintah Set untuk menambahkan konfigurasi enkripsi.

### Contoh 5: Menambahkan konfigurasi enkripsi lain ke namespace layanan di Contoh 4

```powershell
$namespace = Get-AzEventHubNamespace -ResourceGroupName myresourcegroup -Name MyNamespaceName

$ec3 = New-AzEventHubEncryptionConfig -KeyName key3 -KeyVaultUri https://myvaultname.vault.azure.net

$namespace.EncryptionConfig += $ec3

Set-AzEventHubNamespace -ResourceGroupName myresourcegroup -Name MyNamespaceName -EncryptionConfig $namespace.EncryptionConfig
```

```output
Name                          : MyNamespaceName
Id                            : /subscriptions/{subscriptionId}/resourceGroups/myresourcegroup/providers/Microsoft.EventHub/namespaces/MyNamespaceName
ResourceGroupName             : Default-EventHub-WestCentralUS
Location                      : West US
Sku                           : Name : Standard , Capacity : 1 , Tier : Standard
Tags                          :
ProvisioningState             : Succeeded
Status                        : Active
CreatedAt                     : 6/12/2020 4:00:29 AM
UpdatedAt                     : 6/14/2020 11:33:12 PM
ServiceBusEndpoint            : #########
Enabled                       : True
KafkaEnabled                  : True
IsAutoInflateEnabled          : True
MaximumThroughputUnits        : 10
ZoneRedundant                 : False
ClusterArmId                  : /subscriptions/{subscriptionId}/resourceGroups/Default-EventHub-WestCentralUS/providers/Microsoft.EventHub/clusters/TestCluster
Encryption                    : Microsoft.Azure.Commands.EventHub.Models.PSEncryptionAttributes
Encryption.KeySource          : MicrosoftKeyVault
Identity                      : PrinicipalId : 000000,
                                TenantId: 000000,
                                Type: SystemAssigned,
                                UserAssignedIdentity: 
IdentityType                  : SystemAssigned
IdentityId                    : 
EncryptionConfig              : {{ KeyName: key1,
                                   KeyVaultUri: https://myvaultname.vault.azure.net,
                                   KeyVersion: ,
                                   UserAssignedIdentity: 
                                 },
                                 {
                                   KeyName: key2,
                                   KeyVaultUri: https://myvaultname.vault.azure.net,
                                   KeyVersion: ,
                                   UserAssignedIdentity: 
                                 },
                                 {
                                   KeyName: key3,
                                   KeyVaultUri: https://myvaultname.vault.azure.net,
                                   KeyVersion: ,
                                   UserAssignedIdentity: 
                                 }}
```

Jika Anda harus menambahkan konfigurasi enkripsi ke namespace. Lakukan Dapatkan di namespace layanan dan kueri hasilnya untuk menyertakan konfigurasi enkripsi baru.


## PARAMETERS

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

### -DisableLocalAuth
mengaktifkan atau menonaktifkan autentikasi SAS untuk namespace

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NamespaceParameterSet, AutoInflateParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableAutoInflate
Menunjukkan apakah AutoInflate diaktifkan

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: AutoInflateParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: IdentityUpdateParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableKafka
mengaktifkan atau menonaktifkan Kafka untuk namespace

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

### -EncryptionConfig
Properti Kunci

```yaml
Type: Microsoft.Azure.Commands.EventHub.Models.PSEncryptionConfigAttributes[]
Parameter Sets: NamespaceParameterSet, AutoInflateParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Identitas
mengaktifkan atau menonaktifkan Identitas untuk namespace

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NamespaceParameterSet, AutoInflateParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: IdentityUpdateParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IdentityId
Daftar Id Identitas yang ditetapkan pengguna

```yaml
Type: System.String[]
Parameter Sets: NamespaceParameterSet, AutoInflateParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IdentityType
Jenis Identitas ('SystemAssigned', 'UserAssigned', 'SystemAssigned', 'UserAssigned', 'None')

```yaml
Type: System.String
Parameter Sets: NamespaceParameterSet, AutoInflateParameterSet
Aliases:
Accepted values: SystemAssigned, UserAssigned, SystemAssigned, UserAssigned, None

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IdentityUserDefined
Identitas yang Ditentukan Pengguna atau Tidak Ada

```yaml
Type: System.String
Parameter Sets: NamespaceParameterSet, AutoInflateParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -KeyProperty
Daftar Properti Kunci, @(@(KeyName,KeyVaultUri,Keyversion),@(KeyName,KeyVaultUri,Keyversion))

```yaml
Type: System.Collections.Generic.List`1[System.String[]]
Parameter Sets: NamespaceParameterSet, AutoInflateParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -KeySource
Sumber Kunci

```yaml
Type: System.String
Parameter Sets: NamespaceParameterSet, AutoInflateParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Lokasi
Lokasi Namespace EventHub.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MaximumThroughputUnits
Batas atas unit throughput saat AutoInflate diaktifkan, nilai harus berada dalam 0 hingga 20 unit throughput.

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: AutoInflateParameterSet, IdentityUpdateParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Nama Namespace EventHub.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: NamespaceName

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Nama Grup Sumber Daya.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SkuCapacity
Unit throughput eventhub.

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases:

Required: False
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SkuName
Nama Sku Namespace.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Basic, Standard, Premium

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -State
Nonaktifkan/Aktifkan Namespace.

```yaml
Type: System.Nullable`1[Microsoft.Azure.Commands.EventHub.Models.NamespaceState]
Parameter Sets: NamespaceParameterSet, AutoInflateParameterSet
Aliases:
Accepted values: Unknown, Active, Disabled

Required: False
Position: 5
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Tag
Hashtable yang mewakili Tag sumber daya.

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: 6
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### System.String

### System.Nullable'1[[System.Int32, mscorlib, Version=4.0.0.0, Culture=netral, PublicKeyToken=b77a5c561934e089]]

### System.Nullable'1[[Microsoft.Azure.Commands.EventHub.Models.NamespaceState, Microsoft.Azure.PowerShell.Cmdlets.EventHub, Version=1.9.1.0, Culture=neutral, PublicKeyToken=null]]

### System.Collections.Hashtable

### System.String[]

### Microsoft.Azure.Commands.EventHub.Models.PSEncryptionConfigAttributes[]

## OUTPUTS

### Microsoft.Azure.Commands.EventHub.Models.PSNamespaceAttributes

## NOTES

## RELATED LINKS
