---
external help file: Microsoft.Azure.PowerShell.Cmdlets.HDInsight.dll-Help.xml
Module Name: Az.HDInsight
online version: https://docs.microsoft.com/powershell/module/az.hdinsight/new-azhdinsightipconfiguration
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/HDInsight/HDInsight/help/New-AzHDInsightIPConfiguration.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/HDInsight/HDInsight/help/New-AzHDInsightIPConfiguration.md
ms.openlocfilehash: 14f5a42eeecba192296aa5e593a5feb2a9cdce0d
ms.sourcegitcommit: 321c644cf2161807a71e1af318fc5c5311d22e25
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/25/2022
ms.locfileid: "145780318"
---
# New-AzHDInsightIPConfiguration

## SYNOPSIS
Membuat konfigurasi IP konfigurasi tautan privat.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.hdinsight/new-azhdinsightipconfiguration) untuk informasi terbaru.

## SYNTAX

```
New-AzHDInsightIPConfiguration [-Name <String>] [-Primary] [-PrivateIPAddress <String>]
 [-PrivateIPAllocationMethod <String>] [-SubnetId <String>] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzHDInsightIPConfiguration** ini membuat konfigurasi ip dalam memeori.

## EXAMPLES

### Contoh 1
```powershell
$vnetId="/subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/testrg/providers/Microsoft.Network/virtualNetworks/testvnet"
$subnetName="default"
$ipConfigName="ipconfig"
$privateIPAllocationMethod="dynamic"
$subnetId=$vnetId+"/subnets/"+$subnetName
# Create Private IP configuration
$ipConfiguration= New-AzHDInsightIPConfiguration -Name $ipConfigName -PrivateIPAllocationMethod $privateIPAllocationMethod -SubnetId $subnetId -Primary
```

Ini membuat objek konfigurasi ip dalam memori.

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

### -Name
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

### -Primer
Mendapatkan atau mengatur bendera menunjukkan apakah konfigurasi IP ini utama untuk NIC yang sesuai.

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
Mendapatkan atau mengatur alamat IP privat.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Tidak ada

## OUTPUTS

### Microsoft.Azure.Commands.HDInsight.Models.AzureHDInsightIPConfiguration

## NOTES

## RELATED LINKS
