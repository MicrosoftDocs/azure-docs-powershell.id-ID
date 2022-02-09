---
external help file: Microsoft.Azure.PowerShell.Cmdlets.HDInsight.dll-Help.xml
Module Name: Az.HDInsight
online version: https://docs.microsoft.com/powershell/module/az.hdinsight/new-azhdinsightprivatelinkconfiguration
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/HDInsight/HDInsight/help/New-AzHDInsightPrivateLinkConfiguration.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/HDInsight/HDInsight/help/New-AzHDInsightPrivateLinkConfiguration.md
ms.openlocfilehash: 761da1c9a795e1ccf2d50e282a392c8144df3980
ms.sourcegitcommit: 7e47562b11e670049c3a18af7498414da853a921
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/09/2022
ms.locfileid: "138166545"
---
# New-AzHDInsightPrivateLinkConfiguration

## SYNOPSIS
Membuat konfigurasi tautan privat dari kluster HDInsight.

## SYNTAX

```
New-AzHDInsightPrivateLinkConfiguration [-Name <String>] [-GroupId <String>]
 [-IpConfiguration <AzureHDInsightIPConfiguration[]>] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzHDInsightPrivateLinkConfiguration** membuat konfigurasi link privat di memeory

## EXAMPLES

### Contoh 1
```powershell
PS C:\> $vnetId="/subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/testrg/providers/Microsoft.Network/virtualNetworks/testvnet"
PS C:\> $subnetName="default"
PS C:\> $ipConfigName="ipconfig"
PS C:\> $privateIPAllocationMethod="dynamic"
PS C:\> $subnetId=$vnetId+"/subnets/"+$subnetName
PS C:\> # Create Private IP configuration
PS C:\> $ipConfiguration= New-AzHDInsightIPConfiguration -Name $ipConfigName PrivateIPAllocationMethod $privateIPAllocationMethod -SubnetId $subnetId -Primary

PS C:\> $privateLinkConfigurationName="plconfig"
PS C:\> $groupId="headnode"
PS C:\> # Create private link configuration
PS C:\> $privateLinkConfiguration= New-AzHDInsightPrivateLinkConfiguration -Name $privateLinkConfigurationName -GroupId $groupId -IPConfiguration $ipConfiguration
```

Cmdlet ini membuat konfigurasi tautan pribadi dalam memori.

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

### -GroupId
Mendapatkan atau mengatur id grup dari tautan pribadi.

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

### -IpConfiguration
Mendapatkan atau mengatur konfigurasi ip tautan pribadi.

```yaml
Type: Microsoft.Azure.Commands.HDInsight.Models.AzureHDInsightIPConfiguration[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Mendapatkan atau mengatur nama konfigurasi tautan pribadi.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak ada

## OUTPUTS

### Microsoft.Azure.Commands.HDInsight.Models.AzureHDInsightPrivateLinkConfiguration

## CATATAN

## RELATED LINKS
