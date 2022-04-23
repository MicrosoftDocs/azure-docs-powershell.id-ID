---
external help file: Microsoft.Azure.PowerShell.Cmdlets.OperationalInsights.dll-Help.xml
Module Name: Az.OperationalInsights
ms.assetid: 54DFBB63-AE8C-4918-870F-19FAD6CC5E4A
online version: https://docs.microsoft.com/powershell/module/az.operationalinsights/set-azoperationalinsightsworkspace
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/OperationalInsights/OperationalInsights/help/Set-AzOperationalInsightsWorkspace.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/OperationalInsights/OperationalInsights/help/Set-AzOperationalInsightsWorkspace.md
ms.openlocfilehash: 6ef313462d2140730a2d52b639f65a3e8e4d54f6
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143223767"
---
# Set-AzOperationalInsightsWorkspace

## SYNOPSIS
Memperbarui ruang kerja.

## SYNTAX

### ByName (Default)
```
Set-AzOperationalInsightsWorkspace [-ResourceGroupName] <String> [-Name] <String> [[-Sku] <String>]
 [-SkuCapacity <Int32>] [[-Tag] <Hashtable>] [-RetentionInDays <Int32>]
 [-DefaultProfile <IAzureContextContainer>] [-PublicNetworkAccessForIngestion <String>]
 [-PublicNetworkAccessForQuery <String>] [-DailyQuotaGb <Int32>] [[-ForceCmkForQuery] <Boolean>]
 [[-DisableLocalAuth] <Boolean>] [<CommonParameters>]
```

### ByObject
```
Set-AzOperationalInsightsWorkspace [-Workspace] <PSWorkspace> [[-Sku] <String>] [-SkuCapacity <Int32>]
 [[-Tag] <Hashtable>] [-RetentionInDays <Int32>] [-DefaultProfile <IAzureContextContainer>]
 [-PublicNetworkAccessForIngestion <String>] [-PublicNetworkAccessForQuery <String>] [-DailyQuotaGb <Int32>]
 [[-ForceCmkForQuery] <Boolean>] [[-DisableLocalAuth] <Boolean>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzOperationalInsightsWorkspace** mengubah konfigurasi ruang kerja.

## EXAMPLES

### Contoh 1: Mengubah ruang kerja menurut nama
```powershell
Set-AzOperationalInsightsWorkspace -ResourceGroupName "ContosoResourceGroup" -Name "MyWorkspace" -Sku Standard -Tags @{ "Department" = "IT" }
```

Perintah ini mengubah SKU dan tag ruang kerja bernama MyWorkspace dalam grup sumber daya bernama ContosoResourceGroup.

### Contoh 2: Memperbarui ruang kerja menggunakan saluran
```powershell
Get-AzOperationalInsightsWorkspace -ResourceGroupName "ContosoResourceGroup" -Name "MyWorkspace" | Set-AzOperationalInsightsWorkspace -Sku "Premium"
```

Perintah ini menggunakan cmdlet Get-AzOperationalInsightsWorkspace untuk mendapatkan ruang kerja bernama MyWorkSpace, lalu mengirimkannya ke cmdlet **Set-AzOperationalInsightsWorkspace** menggunakan operator pipeline untuk mengatur SKU ke Premium.

## PARAMETERS

### -DailyQuotaGb
Batas volume harian untuk konsumsi - angka

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

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure

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
Izinkan untuk menolak autentikasi lokal dan memastikan pelanggan hanya dapat menggunakan MSI dan AAD untuk autentikasi eksklusif

```yaml
Type: System.Nullable`1[System.Boolean]
Parameter Sets: (All)
Aliases:

Required: False
Position: 10
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ForceCmkForQuery
Dapatkan atau kumpulan menunjukkan apakah penyimpanan yang dikelola pelanggan wajib untuk manajemen kueri

```yaml
Type: System.Nullable`1[System.Boolean]
Parameter Sets: (All)
Aliases:

Required: False
Position: 9
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Menentukan nama ruang kerja.

```yaml
Type: System.String
Parameter Sets: ByName
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PublicNetworkAccessForIngestion
Tipe akses jaringan untuk mengakses penyerapan ruang kerja. Nilai harus 'Diaktifkan' atau 'Dinonaktifkan'

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

### -PublicNetworkAccessForQuery
Tipe akses jaringan untuk mengakses kueri ruang kerja. Nilai harus 'Diaktifkan' atau 'Dinonaktifkan'

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
Menentukan nama grup sumber daya Azure.

```yaml
Type: System.String
Parameter Sets: ByName
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RetentionInDays
Penyimpanan data ruang kerja dalam hari. 730 hari adalah maksimum yang diperbolehkan untuk semua Sku lainnya

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

### -Sku
Tingkat layanan ruang kerja.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: free, standard, premium, pernode, standalone, pergb2018, capacityreservation, lacluster

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SkuCapacity
Kapasitas Sku, nilai perlu kelipatan 100 dan di atas 0.

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

### -Tag
Tag sumber daya untuk ruang kerja.

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Ruang Kerja
Menentukan ruang kerja yang akan diperbarui.

```yaml
Type: Microsoft.Azure.Commands.OperationalInsights.Models.PSWorkspace
Parameter Sets: ByObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.OperationalInsights.Models.PSWorkspace

### System.String

### System.Collections.Hashtable

### System.Nullable'1[[System.Int32, mscorlib, Version=4.0.0.0, Culture=netral, PublicKeyToken=b77a5c561934e089]]

## OUTPUTS

### Microsoft.Azure.Commands.OperationalInsights.Models.PSWorkspace

## NOTES

## RELATED LINKS

[Cmdlet Insights Operasional Azure](./Az.OperationalInsights.md)

[Get-AzOperationalInsightsWorkspace](./Get-AzOperationalInsightsWorkspace.md)


