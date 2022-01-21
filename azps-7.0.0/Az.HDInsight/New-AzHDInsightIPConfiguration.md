---
external help file: Microsoft.Azure.PowerShell.Cmdlets.HDInsight.dll-Help.xml
Module Name: Az.HDInsight
online version: https://docs.microsoft.com/powershell/module/az.hdinsight/new-azhdinsightipconfiguration
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/HDInsight/HDInsight/help/New-AzHDInsightIPConfiguration.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/HDInsight/HDInsight/help/New-AzHDInsightIPConfiguration.md
ms.openlocfilehash: c9e713d3dfdc7707055b7d97a43c9218bc3b1745
ms.sourcegitcommit: 579224f3f35e223624deb694bceb0033c84a5856
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 12/07/2021
ms.locfileid: "136565443"
---
# New-AzHDInsightIPConfiguration

## SYNOPSIS
Membuat konfigurasi IP dari konfigurasi tautan privat.

## SYNTAX

```
New-AzHDInsightIPConfiguration [-Name <String>] [-Primary] [-PrivateIPAddress <String>]
 [-PrivateIPAllocationMethod <String>] [-SubnetId <String>] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzHDInsightIPConfiguration** ini membuat konfigurasi ip di memeory.

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
```

Ini akan membuat objek konfigurasi ip dalam memori.

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

### -Nama
Mendapatkan atau mengatur nama konfigurasi ip.

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

### -Utama
Mendapatkan atau mengatur bendera menunjukkan apakah konfigurasi IP ini penting untuk NIC terkait.

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

### -PrivateIPAddress
Mendapatkan atau mengatur alamat ip privat.

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

### -PrivateIPAllocationMethod
Mendapatkan atau mengatur metode alokasi ip privat.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: dynamic, static

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubnetId
Mendapatkan atau mengatur id sumber daya subnet.

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

### Tidak ada

## OUTPUTS

### Microsoft.Azure.Commands.HDInsight.Models.AzureHDInsightIPConfiguration

## CATATAN

## RELATED LINKS
