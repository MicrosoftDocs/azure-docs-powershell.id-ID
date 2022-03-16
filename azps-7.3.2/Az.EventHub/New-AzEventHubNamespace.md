---
external help file: Microsoft.Azure.PowerShell.Cmdlets.EventHub.dll-Help.xml
Module Name: Az.EventHub
online version: https://docs.microsoft.com/powershell/module/az.eventhub/new-azeventhubnamespace
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/EventHub/EventHub/help/New-AzEventHubNamespace.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/EventHub/EventHub/help/New-AzEventHubNamespace.md
ms.openlocfilehash: 812918a2aefcb87bd7ae2e5716347f3268d8ebc1
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140000845"
---
# New-AzEventHubNamespace

## SYNOPSIS
Membuat ruang nama Hub Acara.

## SYNTAX

### NamespaceParameterSet (Default)
```
New-AzEventHubNamespace [-ResourceGroupName] <String> [-Name] <String> [-Location] <String>
 [[-SkuName] <String>] [[-SkuCapacity] <Int32>] [[-Tag] <Hashtable>] [-EnableKafka] [-ZoneRedundant]
 [[-ClusterARMId] <String>] [-Identity] [-DisableLocalAuth] [-IdentityType <String>] [-IdentityId <String[]>]
 [-EncryptionConfig <PSEncryptionConfigAttributes[]>] [-DefaultProfile <IAzureContextContainer>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### AutoInparameterSet
```
New-AzEventHubNamespace [-ResourceGroupName] <String> [-Name] <String> [-Location] <String>
 [[-SkuName] <String>] [[-SkuCapacity] <Int32>] [[-Tag] <Hashtable>] [-EnableAutoInflate]
 [[-MaximumThroughputUnits] <Int32>] [-EnableKafka] [-ZoneRedundant] [[-ClusterARMId] <String>] [-Identity]
 [-DisableLocalAuth] [-IdentityType <String>] [-IdentityId <String[]>]
 [-EncryptionConfig <PSEncryptionConfigAttributes[]>] [-DefaultProfile <IAzureContextContainer>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet New-AzEventHubNamespace membuat ruang nama baru tipe Hub Kejadian.

## EXAMPLES
### Contoh 1                                           
```powershell
PS C:\> New-AzEventHubNamespace -ResourceGroupName MyResourceGroupName -NamespaceName MyNamespaceName -Location MyLocation

Name                          : MyNamespaceName
Id                            : /subscriptions/{subscriptionId}/resourceGroups/Default-EventHub-WestCentralUS/providers/Microsoft.EventHub/namespaces/MyNamespaceName
ResourceGroupName             : Default-EventHub-WestCentralUS
Location                      : West US
Sku                           : Name : Standard , Capacity : 1 , Tier : Standard
Tags                          :
ProvisioningState             : Succeeded
Status                        : Active
CreatedAt                     : 6/14/2020 9:02:16 PM
UpdatedAt                     : 6/14/2020 9:03:04 PM
ServiceBusEndpoint            : https://testingnew2018.servicebus.windows.net:443/
Enabled                       : True
KafkaEnabled                  : True
IsAutoInflateEnabled          : False
MaximumThroughputUnits        : 0
ZoneRedundant                 : False
ClusterArmId                  :
Identity                      : Microsoft.Azure.Commands.EventHub.Models.PSIdentityAttributes
Identity.PrincipalId          :
Identity.TenantId             :
Identity.Type                 :
Encryption                    : Microsoft.Azure.Commands.EventHub.Models.PSEncryptionAttributes
Encryption.KeySource          :
Encryption.KeyVaultProperties :
```

Membuat ruang nama Hub Kejadian \`MyNamespaceName di\` lokasi geografis \`tertentu MyLocation\`, di grup sumber daya \`MyResourceGroupName\`.

### Contoh 2
```powershell
PS C:\> New-AzEventHubNamespace -ResourceGroupName MyResourceGroupName -NamespaceName MyNamespaceName -Location MyLocation -EnableAutoInflate -MaximumThroughputUnits 10

Name                          : MyNamespaceName
Id                            : /subscriptions/{subscriptionId}/resourceGroups/Default-EventHub-WestCentralUS/providers/Microsoft.EventHub/namespaces/MyNamespaceName
ResourceGroupName             : Default-EventHub-WestCentralUS
Location                      : West US
Sku                           : Name : Standard , Capacity : 1 , Tier : Standard
Tags                          :
ProvisioningState             : Succeeded
Status                        : Active
CreatedAt                     : 5/24/2019 12:47:27 AM
UpdatedAt                     : 5/24/2019 12:48:14 AM
ServiceBusEndpoint            : #########
Enabled                       : True
IsAutoInflateEnabled          : True
MaximumThroughputUnits        : 10
ZoneRedundant                 : False
ClusterArmId                  :
Identity                      : Microsoft.Azure.Commands.EventHub.Models.PSIdentityAttributes
Identity.PrincipalId          :
Identity.TenantId             :
Identity.Type                 :
Encryption                    : Microsoft.Azure.Commands.EventHub.Models.PSEncryptionAttributes
Encryption.KeySource          :
Encryption.KeyVaultProperties :
```

Membuat ruang nama Hub Kejadian \`MyNamespaceName \`\` di lokasi geografis tertentu MyLocation\`, \`di grup sumber daya MyResourceGroupName\` dan AutoInsourcee diaktifkan dengan MaximumThroughputUnits 10.

### Contoh 3: Ruang nama Junii yang diaktifkan
```powershell
PS C:\> New-AzEventHubNamespace -ResourceGroupName MyResourceGroupName -NamespaceName MyNamespaceName -Location MyLocation -EnableAutoInflate -EnableKafka

Name                          : MyNamespaceName
Id                            : /subscriptions/{subscriptionId}/resourceGroups/Default-EventHub-WestCentralUS/providers/Microsoft.EventHub/namespaces/MyNamespaceName
ResourceGroupName             : Default-EventHub-WestCentralUS
Location                      : West US
Sku                           : Name : Standard , Capacity : 1 , Tier : Standard
Tags                          :
ProvisioningState             : Succeeded
Status                        : Active
CreatedAt                     : 5/24/2019 12:47:27 AM
UpdatedAt                     : 5/24/2019 12:48:14 AM
ServiceBusEndpoint            : #########
Enabled                       : True
IsAutoInflateEnabled          : True
MaximumThroughputUnits        : 10
ZoneRedundant                 : False
ClusterArmId                  :
Identity                      : Microsoft.Azure.Commands.EventHub.Models.PSIdentityAttributes
Identity.PrincipalId          :
Identity.TenantId             :
Identity.Type                 :
Encryption                    : Microsoft.Azure.Commands.EventHub.Models.PSEncryptionAttributes
Encryption.KeySource          :
Encryption.KeyVaultProperties :
```

Membuat ruang nama Hub Kejadian \`MyNamespaceName \`\` di lokasi geografis tertentu MyLocation\`, \`di grup sumber daya MyResourceGroupName\` denganIguka dan AutoInsourcee diaktifkan.

### Contoh 4: Ruang nama yang diaktifkan ZonaRedundant
```powershell
PS C:\> New-AzEventHubNamespace -ResourceGroupName MyResourceGroupName -NamespaceName MyNamespaceName -Location MyLocation -EnableAutoInflate -ZoneRedundant

Name                          : MyNamespaceName
Id                            : /subscriptions/{subscriptionId}/resourceGroups/Default-EventHub-WestCentralUS/providers/Microsoft.EventHub/namespaces/MyNamespaceName
ResourceGroupName             : Default-EventHub-WestCentralUS
Location                      : West US
Sku                           : Name : Standard , Capacity : 1 , Tier : Standard
Tags                          :
ProvisioningState             : Succeeded
Status                        : Active
CreatedAt                     : 5/24/2019 12:47:27 AM
UpdatedAt                     : 5/24/2019 12:48:14 AM
ServiceBusEndpoint            : #########
Enabled                       : True
IsAutoInflateEnabled          : True
MaximumThroughputUnits        : 10
ZoneRedundant                 : True
ClusterArmId                  :
Identity                      : Microsoft.Azure.Commands.EventHub.Models.PSIdentityAttributes
Identity.PrincipalId          :
Identity.TenantId             :
Identity.Type                 :
Encryption                    : Microsoft.Azure.Commands.EventHub.Models.PSEncryptionAttributes
Encryption.KeySource          :
Encryption.KeyVaultProperties :
```

Membuat ruang nama Hub Kejadian \`MyNamespaceName \`\` di lokasi geografis tertentu MyLocation\`, \`di grup sumber daya MyResourceGroupName\` denganIguka dan AutoInsourcee diaktifkan.

### Contoh 5: Membuat Ruang Nama dengan Kelola Identitas di kluster 
```powershell
PS C:\> New-AzEventHubNamespace -ResourceGroupName MyResourceGroupName -NamespaceName MyNamespaceName -Location MyLocation --EnableAutoInflate -MaximumThroughputUnits 12 -EnableKafka -ZoneRedundant -IdentityType SystemAssigned

Name                          : MyNamespaceName
Id                            : /subscriptions/{subscriptionId}/resourceGroups/Default-EventHub-WestCentralUS/providers/Microsoft.EventHub/namespaces/MyNamespaceName
ResourceGroupName             : Default-EventHub-WestCentralUS
Location                      : West US
Sku                           : Name : Standard , Capacity : 1 , Tier : Standard
Tags                          :
ProvisioningState             : Succeeded
Status                        : Active
CreatedAt                     : 5/24/2019 12:47:27 AM
UpdatedAt                     : 5/24/2019 12:48:14 AM
ServiceBusEndpoint            : #########
Enabled                       : True
IsAutoInflateEnabled          : True
MaximumThroughputUnits        : 12
ZoneRedundant                 : True
ClusterArmId                  : /subscriptions/{subscriptionId}/resourceGroups/Default-EventHub-WestCentralUS/providers/Microsoft.EventHub/clusters/TestCluster
Identity.PrincipalId          : ##########
Identity.TenantId             : ##########
Identity.Type                 : SystemAssigned
Encryption                    : Microsoft.Azure.Commands.EventHub.Models.PSEncryptionAttributes
Encryption.KeySource          :
Encryption.KeyVaultProperties :
```

### Contoh 6: Membuat Namespace dengan UserAssigned identity encryption diaktifkan


```

# Create encryption config that will create an in memory config object
PS C:\> $config1 = New-AzEventHubEncryptionConfig -KeyName key1 -KeyVaultUri https://myvaultname.vault.azure.net -UserAssignedIdentity /subscriptions/{subscriptionId}/resourceGroups/{resourcegroup}/providers/Microsoft.ManagedIdentity/userAssignedIdentities/MSIName

# Create encryption config that will create an in memory config object
PS C:\> $config2 = New-AzEventHubEncryptionConfig -KeyName key2 -KeyVaultUri https://myvaultname.vault.azure.net -UserAssignedIdentity /subscriptions/{subscriptionId}/resourceGroups/{resourcegroup}/providers/Microsoft.ManagedIdentity/userAssignedIdentities/MSIName

PS C:\>$id1 = '/subscriptions/{subscriptionId}/resourceGroups/{resourcegroup}/providers/Microsoft.ManagedIdentity/userAssignedIdentities/MSIName'

PS C:\>$id2 = '/subscriptions/{subscriptionId}/resourceGroups/{resourcegroup}/providers/Microsoft.ManagedIdentity/userAssignedIdentities/MSIName'

# Update Namespace with KeyVault properties
PS C:\> New-AzEventHubNamespace -ResourceGroupName MyResourceGroupName -Name MyNamespaceName -Location westus -IdentityType "UserAssigned" -IdentityId $id1,$id2 -EncryptionConfig $config1,$config2

Name                          : MyNamespaceName
Id                            : /subscriptions/{subscriptionId}/resourceGroups/Default-EventHub-WestCentralUS/providers/Microsoft.EventHub/namespaces/MyNamespaceName
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
Identity                      : PrinicipalId : ,
                                TenantId: ,
                                Type: UserAssigned,
                                UserAssignedIdentity: /subscriptions/{subscriptionId}/resourceGroups/{resourcegroup}/providers/Microsoft.ManagedIdentity/userAssignedIdentities/MSIName 
                                                      /subscriptions/{subscriptionId}/resourceGroups/{resourcegroup}/providers/Microsoft.ManagedIdentity/userAssignedIdentities/MSIName2
IdentityType                  : UserAssigned
IdentityId                    : /subscriptions/{subscriptionId}/resourceGroups/{resourcegroup}/providers/Microsoft.ManagedIdentity/userAssignedIdentities/MSIName
                                /subscriptions/{subscriptionId}/resourceGroups/{resourcegroup}/providers/Microsoft.ManagedIdentity/userAssignedIdentities/MSIName2
EncryptionConfig              : {{ KeyName: key1,
                                   KeyVaultUri: https://myvaultname.vault.azure.net,
                                   KeyVersion: ,
                                   UserAssignedIdentity: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroup}/providers/Microsoft.ManagedIdentity/userAssignedIdentities/MSIName
                                 },
                                 {
                                   KeyName: key2,
                                   KeyVaultUri: https://myvaultname.vault.azure.net,
                                   KeyVersion: ,
                                   UserAssignedIdentity: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroup}/providers/Microsoft.ManagedIdentity/userAssignedIdentities/MSIName2
                                 }}
```

## PARAMETERS

### -ClusterARMId
ID ARM dari Kluster tempat ruang nama akan dibuat

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### -DisableLocalAuth
mengaktifkan atau menonaktifkan autentikasi SAS untuk ruang nama

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

### -EnableAutoInotomatise
Menunjukkan apakah PengaturanOtomatis diaktifkan

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

### -EnableKafka
mengaktifkan atau menonaktifkan NamespaceKa untuk

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
Properti Key

```yaml
Type: Microsoft.Azure.Commands.EventHub.Models.PSEncryptionConfigAttributes[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Identity
mengaktifkan atau menonaktifkan Identitas untuk ruang nama

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

### -IdentityId
Daftar ID Identitas yang ditetapkan pengguna

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

### -IdentityType
Tipe Identitas ('SystemAssigned', 'UserAssigned', 'SystemAssigned', 'UserAssigned', 'None')

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: SystemAssigned, UserAssigned, SystemAssigned, UserAssigned, None

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Lokasi
Lokasi Ruang Nama EventHub.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MaximumThroughputUnits
Batas atas satuan throughput ketika FileOtomatis diaktifkan, nilai harus berada dalam 0 hingga 20 unit throughput.

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: AutoInflateParameterSet
Aliases:

Required: False
Position: 7
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Nama
Nama Ruang Nama EventHub.

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
Nama Grup Sumber Daya

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
Nama Ruang Nama Sku.

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

### -Tag
Hashtable yang mewakili Tag sumber daya.

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: 5
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ZoneRedundant
mengaktifkan atau menonaktifkan Kelebihan Zona untuk ruang nama

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### System.Nullable'1[[System.Int32, mscorlib, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089]]

### System.Collections.Hashtable

### System.String[]

### Microsoft.Azure.Commands.EventHub.Models.PSEncryptionConfigAttributes[]

## OUTPUTS

### Microsoft.Azure.Commands.EventHub.Models.PSNamespaceAttributes

## CATATAN

## RELATED LINKS
