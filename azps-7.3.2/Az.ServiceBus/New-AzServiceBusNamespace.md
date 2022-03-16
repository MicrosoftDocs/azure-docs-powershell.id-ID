---
external help file: Microsoft.Azure.PowerShell.Cmdlets.ServiceBus.dll-Help.xml
Module Name: Az.ServiceBus
online version: https://docs.microsoft.com/powershell/module/az.servicebus/new-azservicebusnamespace
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ServiceBus/ServiceBus/help/New-AzServiceBusNamespace.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ServiceBus/ServiceBus/help/New-AzServiceBusNamespace.md
ms.openlocfilehash: ed93f8789c252227ed78dc53990f8258c2db2c81
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140195623"
---
# New-AzServiceBusNamespace

## SYNOPSIS
Membuat ruang nama Bus Layanan baru.

## SYNTAX

```
New-AzServiceBusNamespace [-ResourceGroupName] <String> [-Location] <String> [-Name] <String>
 [-SkuName <String>] [-SkuCapacity <Int32>] [-Tag <Hashtable>] [-ZoneRedundant] [-DisableLocalAuth]
 [-IdentityType <String>] [-IdentityId <String[]>] [-EncryptionConfig <PSEncryptionConfigAttributes[]>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzServiceBusNamespace** membuat kumpulan Bus Layanan nama baru. Setelah dibuat, kumpulan nama manifes sumber daya akan tetap ada. Operasi ini idempok.

## EXAMPLES

### Contoh 1
```
PS C:\> New-AzServiceBusNamespace -ResourceGroupName Default-ServiceBus-WestUS -Name SB-Example1 -Location WestUS -SkuName "Standard" -Tag @{Tag1="Tag1Value"}

Name               : SB-Example1
Id                 : /subscriptions/{SubscriptionId}/resourceGroups/Default-ServiceBus-WestUS/providers/Microsoft.ServiceBus/namespaces/SB-Example1
ResourceGroupName  : Default-ServiceBus-WestUS
Location           : West US
Tags               : {TesttingTags, TestingTagValue, TestTag, TestTagValue}
Sku                : Name : Standard , Tier : Standard
ProvisioningState  : Succeeded
CreatedAt          : 1/20/2017 2:07:33 AM
UpdatedAt          : 1/20/2017 2:07:56 AM
ServiceBusEndpoint : https://SB-Example1.servicebus.windows.net:443/
```

Membuat ruang nama Bus Layanan di dalam grup sumber daya yang ditentukan.

### Contoh 2 - ZoneRedundant dan DisableLocalAuth
```
PS C:\> New-AzServiceBusNamespace -ResourceGroupName Default-ServiceBus-WestUS -Name SB-Example1 -Location WestUS2 -SkuName "Premium" -Tag @{Tag1="Tag1Value"} -ZoneRedundant - DisableLocalAuth

Name               : SB-Example1
Id                 : /subscriptions/{SubscriptionId}/resourceGroups/Default-ServiceBus-WestUS/providers/Microsoft.ServiceBus/namespaces/SB-Example1
ResourceGroupName  : Default-ServiceBus-WestUS
Location           : West US
Tags               : {TesttingTags, TestingTagValue, TestTag, TestTagValue}
Sku                : Name : Premium , Tier : Premium
ProvisioningState  : Succeeded
CreatedAt          : 9/27/2021 2:07:33 AM
UpdatedAt          : 9/27/2021 2:07:56 AM
ServiceBusEndpoint : https://SB-Example1.servicebus.windows.net:443/
```

Membuat ruang nama Bus Layanan di dalam grup sumber daya yang ditentukan.

### Contoh 3 - Buat ruang nama dengan enkripsi identitas ditetapkan pengguna diaktifkan
```
PS C:\> $config1 = New-AzServiceBusEncryptionConfig -KeyName key1 -KeyVaultUri https://myvaultname.vault.azure.net -UserAssignedIdentity /subscriptions/{subscriptionId}/resourceGroups/{resourcegroup}/providers/Microsoft.ManagedIdentity/userAssignedIdentities/MSIName

PS C:\> $config1 = New-AzServiceBusEncryptionConfig -KeyName key2 -KeyVaultUri https://myvaultname.vault.azure.net -UserAssignedIdentity /subscriptions/{subscriptionId}/resourceGroups/{resourcegroup}/providers/Microsoft.ManagedIdentity/userAssignedIdentities/MSIName

PS C:\> $id1 = '/subscriptions/{subscriptionId}/resourceGroups/{resourcegroup}/providers/Microsoft.ManagedIdentity/userAssignedIdentities/MSIName'

PS C:\> $id2 = '/subscriptions/{subscriptionId}/resourceGroups/{resourcegroup}/providers/Microsoft.ManagedIdentity/userAssignedIdentities/MSIName2'

PS C:\> New-AzServiceBusNamespace -ResourceGroupName Default-ServiceBus-WestUS -Name SB-Example1 -Location WestUS2 -SkuName "Premium" -IdentityType UserAssigned -IdentityId $id1,$id2 -EncryptionConfig $ec1,$ec2

Name               : SB-Example1
Id                 : /subscriptions/{subscriptionId}/resourceGroups/Default-ServiceBus-WestUS/providers/Microsoft.ServiceBus/namespaces/SB-Example1
ResourceGroupName  : Default-ServiceBus-WestUS
Location           : WestUS2
Sku                : Name : Premium , Tier : Premium, Capacity : 1
Tags               :
ProvisioningState  : Succeeded
CreatedAt          : 1/4/2022 7:36:35 AM
UpdatedAt          : 2/5/2022 6:44:14 AM
ServiceBusEndpoint : https://SB-Example1.servicebus.windows.net:443/
ZoneRedundant      : False
DisableLocalAuth   : False
Identity           : PrinicipalId : , TenantId:
IdentityType       : UserAssigned
IdentityId         : /subscriptions/{subscriptionId}/resourceGroups/{resourceGroup}/providers/Microsoft.ManagedIdentity/userAssignedIdentities/MSIName,
                     /subscriptions/{subscriptionId}/resourceGroups/{resourceGroup}/providers/Microsoft.ManagedIdentity/userAssignedIdentities/MSIName2
EncryptionConfigs  : {{ KeyName: key1,
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

Membuat ruang nama Bus Layanan dengan UserAssigned Encryption Enabled. IdentityType bisa mengambil nilai "SystemAssigned", "UserAssigned", "SystemAssigned, UserAssigned", "None"

### Contoh 4 - Buat ruang nama dengan identitas ditetapkan sistem diaktifkan.
```
PS C:\> New-AzServiceBusNamespace -ResourceGroupName Default-ServiceBus-WestUS -Name SB-Example1 -Location WestUS2 -SkuName "Premium" -IdentityType SystemAssigned

Name               : SB-Example1
Id                 : /subscriptions/{subscriptionId}/resourceGroups/Default-ServiceBus-WestUS/providers/Microsoft.ServiceBus/namespaces/SB-Example1
ResourceGroupName  : Default-ServiceBus-WestUS
Location           : WestUS2
Sku                : Name : Premium , Tier : Premium, Capacity : 1
Tags               :
ProvisioningState  : Succeeded
CreatedAt          : 1/4/2022 7:36:35 AM
UpdatedAt          : 2/5/2022 6:44:14 AM
ServiceBusEndpoint : https://SB-Example1.servicebus.windows.net:443/
ZoneRedundant      : False
DisableLocalAuth   : False
Identity           : PrinicipalId : 000000000, TenantId: 00000000
IdentityType       : SystemAssigned
IdentityId         :
EncryptionConfigs  :
```

Membuat ruang nama Bus Layanan dengan SystemAssigned identity diaktifkan. IdentityType bisa mengambil nilai "SystemAssigned", "UserAssigned", "SystemAssigned, UserAssigned", "None"

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
mengaktifkan atau menonaktifkan autentikasi SAS untuk Bus Layanan nama

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EncryptionConfig
Properti Key

```yaml
Type: Microsoft.Azure.Commands.ServiceBus.Models.PSEncryptionConfigAttributes[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Tipe Identitas

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
Lokasi Ruang Nama ServiceBus

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Nama
Nama Ruang Nama ServiceBus

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: NamespaceName

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Nama Grup Sumber Daya

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: ResourceGroup

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SkuCapacity
Kumpulan Bus Layanan premium unit throughput, yang diperbolehkan nilai 1 atau 2 atau 4

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SkuName
Nama Kumpulan Nama Sku

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Basic, Standard, Premium

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Tag
Hashtable yang mewakili Tag sumber daya

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
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

### System.Management.Automation.SwitchParameter

### System.String[]

### Microsoft.Azure.Commands.ServiceBus.Models.PSEncryptionConfigAttributes[]

## OUTPUTS

### Microsoft.Azure.Commands.ServiceBus.Models.PSNamespaceAttributes

## CATATAN

## RELATED LINKS
