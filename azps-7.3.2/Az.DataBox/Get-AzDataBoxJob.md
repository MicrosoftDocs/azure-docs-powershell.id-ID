---
external help file: ''
Module Name: Az.DataBox
online version: https://docs.microsoft.com/powershell/module/az.databox/get-azdataboxjob
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataBox/help/Get-AzDataBoxJob.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataBox/help/Get-AzDataBoxJob.md
ms.openlocfilehash: 6f2a637c5f0dbc8e37f5633bb8f65c66f819c08f
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141896175"
---
# Get-AzDataBoxJob

## SYNOPSIS
Mendapatkan informasi tentang pekerjaan yang ditentukan.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.databox/get-azdataboxjob) untuk informasi terbaru.

## SYNTAX

### Daftar (Default)
```
Get-AzDataBoxJob [-SubscriptionId <String[]>] [-SkipToken <String>] [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

### Mendapatkan
```
Get-AzDataBoxJob -Name <String> -ResourceGroupName <String> [-SubscriptionId <String[]>] [-Expand <String>]
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### Daftar1
```
Get-AzDataBoxJob -ResourceGroupName <String> [-SubscriptionId <String[]>] [-SkipToken <String>]
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan informasi tentang pekerjaan yang ditentukan.

## EXAMPLES

### Contoh 1: Mendapatkan pekerjaan tertentu 
```powershell
Get-AzDataBoxJob -Name "Powershell10" -ResourceGroupName "resourceGroupName"  -SubscriptionId "SubscriptionId"
```

```output
Name         Location Status        TransferType  SkuName IdentityType DeliveryType Detail
----         -------- ------        ------------  ------- ------------ ------------ ------
Powershell10 WestUS   DeviceOrdered ImportToAzure DataBox None         NonScheduled Microsoft.Azure.PowerShell.Cmdlets.DataBox.Models.Api20210301.DataBoxJobDetails
```

Mendapatkan pekerjaan tertentu

### Contoh 2: Daftar semua pekerjaan di bawah langganan 
```powershell
Get-AzDataBoxJob -SubscriptionId "SubscriptionId"
```

```output
Name        Location      Status        TransferType    SkuName    IdentityType  DeliveryType Detail
----        --------      ------        ------------    -------    ------------  ------------ ------
brtestdbd  brazilsouth   DeviceOrdered ImportToAzure   DataBoxDisk None          NonScheduled Microsoft.Azure.PowerShell.Cmdlets.DataBox.Models.Api20210301.DataBoxDiskJobDetails
testorder  uksouth       Cancelled     ImportToAzure   DataBoxDisk None          NonScheduled Microsoft.Azure.PowerShell.Cmdlets.DataBox.Models.Api20210301.DataBoxDiskJobDetails
```

Mencantumkan semua pekerjaan di bawah langganan

### Contoh 3: Mencantumkan semua pekerjaan di bawah grup sumber daya 
```powershell
Get-AzDataBoxJob -ResourceGroupName "resourceGroupName"
```

```output
Name                   Location Status        TransferType    SkuName IdentityType   DeliveryType Detail
----                   -------- ------        ------------    ------- ------------   ------------ ------
abcbnkndnkndn          westus   DeviceOrdered ImportToAzure   DataBox None           NonScheduled Microsoft.Azure.PowerShell.Cmdlets.DataBox.Models.Api20210301.DataBoxJobDetails
abcbnkndnkndn-Clone    westus   DeviceOrdered ImportToAzure   DataBox None           NonScheduled Microsoft.Azure.PowerShell.Cmdlets.DataBox.Models.Api20210301.DataBoxJobDetails
abcOrder               westus   Cancelled     ImportToAzure   DataBox None           NonScheduled Microsoft.Azure.PowerShell.Cmdlets.DataBox.Models.Api20210301.DataBoxJobDetails
```

Mencantumkan semua pekerjaan di bawah grup sumber daya

## PARAMETERS

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

### -Perluas
$expand didukung pada parameter detail untuk pekerjaan, yang menyediakan detail tentang tahapan pekerjaan.

```yaml
Type: System.String
Parameter Sets: Get
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Nama sumber daya pekerjaan dalam grup sumber daya yang ditentukan.
nama pekerjaan harus panjangnya antara 3 dan 24 karakter dan hanya menggunakan alfanumerik dan garis bawah

```yaml
Type: System.String
Parameter Sets: Get
Aliases: JobName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama Grup Sumber Daya

```yaml
Type: System.String
Parameter Sets: Get, List1
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SkipToken
$skipToken didukung di Dapatkan daftar pekerjaan, yang menyediakan halaman berikutnya dalam daftar pekerjaan.

```yaml
Type: System.String
Parameter Sets: List, List1
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubscriptionId
Id Langganan

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.DataBox.Models.Api20210301.IJobResource

## CATATAN

ALIAS

## RELATED LINKS

