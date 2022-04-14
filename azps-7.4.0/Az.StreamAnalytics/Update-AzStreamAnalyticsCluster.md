---
external help file: ''
Module Name: Az.StreamAnalytics
online version: https://docs.microsoft.com/powershell/module/az.streamanalytics/update-azstreamanalyticscluster
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/StreamAnalytics/help/Update-AzStreamAnalyticsCluster.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/StreamAnalytics/help/Update-AzStreamAnalyticsCluster.md
ms.openlocfilehash: c47ebacd35876bbe7a336ec61828f0568fff4928
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142000809"
---
# Update-AzStreamAnalyticsCluster

## SYNOPSIS
Memperbarui kluster yang sudah ada.
Hal ini dapat digunakan untuk memperbarui sebagian (yaitu.
memperbarui satu atau dua properti) kluster tanpa memengaruhi definisi kluster lainnya.

## SYNTAX

### UpdateExpanded (Default)
```
Update-AzStreamAnalyticsCluster -Name <String> -ResourceGroupName <String> [-SubscriptionId <String>]
 [-IfMatch <String>] [-Location <String>] [-SkuCapacity <Int32>] [-SkuName <ClusterSkuName>]
 [-Tag <Hashtable>] [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-Confirm] [-WhatIf] [<CommonParameters>]
```

### UpdateViaIdentityExpanded
```
Update-AzStreamAnalyticsCluster -InputObject <IStreamAnalyticsIdentity> [-IfMatch <String>]
 [-Location <String>] [-SkuCapacity <Int32>] [-SkuName <ClusterSkuName>] [-Tag <Hashtable>]
 [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Memperbarui kluster yang sudah ada.
Hal ini dapat digunakan untuk memperbarui sebagian (yaitu.
memperbarui satu atau dua properti) kluster tanpa memengaruhi definisi kluster lainnya.

## EXAMPLES

### Contoh 1: Memperbarui kluster analitik stream berdasarkan nama
```powershell
Update-AzStreamAnalyticsCluster -ResourceGroupName pwshaz-rg-test -Name sac-m-test01 -Tag @{'key4'=4}
```
```output
Location        Name         Type                               Etag
--------        ----         ----                               ----
West Central US sac-m-test01 Microsoft.StreamAnalytics/clusters
```

Perintah ini memperbarui kluster analitik streaming berdasarkan nama.

### Contoh 2: Memperbarui kluster analitik streaming menurut pipeline
```powershell
$sac = Get-AzStreamAnalyticsCluster -ResourceGroupName pwshaz-rg-test -Name sac-m-test01
Update-AzStreamAnalyticsCluster -InputObject $sac -Tag @{'key2'=2;'key3'=3}
```
```output
Location        Name         Type                               Etag
--------        ----         ----                               ----
West Central US sac-m-test01 Microsoft.StreamAnalytics/clusters
```

Perintah ini memperbarui kluster analitik streaming menurut saluran.

## PARAMETERS

### -AsJob
Menjalankan perintah sebagai pekerjaan

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

### -IfMatch
ETag sumber daya.
Hilangkan nilai ini untuk selalu menimpa kumpulan rekaman saat ini.
Tentukan nilai ETag yang terakhir terlihat untuk mencegah timpa perubahan bersamaan secara tidak sengaja.

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

### -InputObject
Parameter Identitas Untuk membangun, lihat bagian CATATAN untuk properti INPUTOBJECT dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.StreamAnalytics.Models.IStreamAnalyticsIdentity
Parameter Sets: UpdateViaIdentityExpanded
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Lokasi
Lokasi geografis tempat sumber daya berada

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

### -Nama
Nama kluster.

```yaml
Type: System.String
Parameter Sets: UpdateExpanded
Aliases: ClusterName

Required: True
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
Nama ini tidak peka huruf besar kecil.

```yaml
Type: System.String
Parameter Sets: UpdateExpanded
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SkuCapacity
Menunjukkan jumlah unit streaming yang dapat didukung oleh kluster.
Nilai valid untuk properti ini adalah kelipatan 36 dengan nilai minimum 36 dan nilai maksimum 216.
Diperlukan pada permintaan PUT (CreateOrUpdate).

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SkuName
Menentukan nama SKU kluster.
Diperlukan pada permintaan PUT (CreateOrUpdate).

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.StreamAnalytics.Support.ClusterSkuName
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubscriptionId
ID langganan target.

```yaml
Type: System.String
Parameter Sets: UpdateExpanded
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### -Tag
Tag sumber daya.

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

### -Konfirmasi
Meminta konfirmasi sebelum menjalankan cmdlet.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets.StreamAnalytics.Models.IStreamAnalyticsIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.StreamAnalytics.Models.Api20200301Preview.ICluster

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT <IStreamAnalyticsIdentity>: Parameter Identitas
  - `[ClusterName <String>]`: Nama kluster.
  - `[FunctionName <String>]`: Nama fungsi.
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[InputName <String>]`: Nama input.
  - `[JobName <String>]`: Nama pekerjaan streaming.
  - `[Location <String>]`: Kawasan tempat untuk mengambil informasi kuota langganan. Anda dapat mengetahui kawasan mana Azure Stream Analytics didukung di sini: https://azure.microsoft.com/en-us/regions/
  - `[OutputName <String>]`: Nama output.
  - `[ResourceGroupName <String>]`: Nama grup sumber daya. Nama ini tidak peka huruf besar kecil.
  - `[SubscriptionId <String>]`: ID langganan target.
  - `[TransformationName <String>]`: Nama transformasi.

## RELATED LINKS

