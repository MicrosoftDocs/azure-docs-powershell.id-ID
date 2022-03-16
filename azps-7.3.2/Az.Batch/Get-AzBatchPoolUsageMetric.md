---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Batch.dll-Help.xml
Module Name: Az.Batch
ms.assetid: 4B373447-3078-4C1F-932E-8337AB170DEB
online version: https://docs.microsoft.com/powershell/module/az.batch/get-azbatchpoolusagemetric
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Batch/Batch/help/Get-AzBatchPoolUsageMetric.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Batch/Batch/help/Get-AzBatchPoolUsageMetric.md
ms.openlocfilehash: 768bf10e474eee28519cf55945e6240f145b172d
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140202646"
---
# Get-AzBatchPoolUsageMetric

## SYNOPSIS
Mendapatkan metrik penggunaan kumpulan untuk akun Batch.

## SYNTAX

```
Get-AzBatchPoolUsageMetric [-StartTime <DateTime>] [-EndTime <DateTime>] [-Filter <String>]
 -BatchContext <BatchAccountContext> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzBatchPoolUsageMetric** mendapatkan metrik penggunaan, yang diagregatkan menurut kumpulan antar interval waktu individual, untuk akun yang ditentukan.
Anda bisa mendapatkan statistik untuk kelompok tertentu dan untuk rentang waktu.

## EXAMPLES

### Contoh 1: Dapatkan metrik penggunaan pool untuk rentang waktu
```powershell
$Context = Get-AzBatchAccountKey -AccountName "ContosoBatchAccount"
$StartTime = Get-Date -Date "2016-05-16 00:00:00Z"
$EndTime = Get-Date -Date "2016-05-16 01:00:00Z"
Get-AzBatchPoolUsageMetric -StartTime $StartTime -EndTime $EndTime -BatchContext $context
```

```output
DataEgressGiB      : 6.68875873088837E-06
DataIngressGiB     : 1.9485130906105E-05
EndTime            : 5/16/2016 12:30:00 AM
PoolId             : testpool1
StartTime          : 5/16/2016 12:00:00 AM
TotalCoreHours     : 8
VirtualMachineSize : standard_d4

DataEgressGiB      : 5.61587512493134E-06
DataIngressGiB     : 1.76150351762772E-05
EndTime            : 5/16/2016 12:30:00 AM
PoolId             : testpool2
StartTime          : 5/16/2016 12:00:00 AM
TotalCoreHours     : 12
VirtualMachineSize : standard_d4

DataEgressGiB      : 7.36676156520844E-06
DataIngressGiB     : 2.10804864764214E-05
EndTime            : 5/16/2016 1:00:00 AM
PoolId             : testpool1
StartTime          : 5/16/2016 12:30:00 AM
TotalCoreHours     : 7.99999999955555
VirtualMachineSize : standard_d4

DataEgressGiB      : 5.80586493015289E-06
DataIngressGiB     : 1.80602073669434E-05
EndTime            : 5/16/2016 1:00:00 AM
PoolId             : testpool2
StartTime          : 5/16/2016 12:30:00 AM
TotalCoreHours     : 11.9999999993333
VirtualMachineSize : standard_d4
```

Perintah pertama membuat referensi objek ke tombol akun untuk akun kumpulan bernama ContosoBatchAccount dengan menggunakan **Get-AzBatchAccountKey**.
Perintah menyimpan referensi objek ini di $Context variabel.
Dua perintah berikutnya membuat **objek DateTime** menggunakan cmdlet Get-Date.
Perintah menyimpan nilai ini dalam $StartTime $EndTime variabel untuk digunakan dengan perintah akhir.
Perintah final mengembalikan semua metrik penggunaan kumpulan, yang diagregasi menurut kumpulan, antar interval waktu antara waktu mulai dan akhir yang ditentukan.

### Contoh 2: Dapatkan metrik penggunaan pool dengan menggunakan filter
```powershell
Get-AzBatchPoolUsageMetric -Filter "poolId eq 'ContosoPool'" -BatchContext $Context
```

```output
DataEgressGiB      : 9.0496614575386E-06
DataIngressGiB     : 2.60043889284134E-05
EndTime            : 5/16/2016 5:30:00 PM
PoolId             : MyPool
StartTime          : 5/16/2016 5:00:00 PM
TotalCoreHours     : 12
VirtualMachineSize : standard_d4
```

Perintah ini mengembalikan metrik penggunaan untuk pool bernama ContosoPool.
Perintah menentukan string filter untuk menentukan pool tersebut, dan menggunakan nilai $Context yang sama seperti contoh sebelumnya.

## PARAMETERS

### -BatchContext
Menentukan contoh **BatchAccountContext** yang digunakan cmdlet untuk berinteraksi dengan layanan Batch.
Jika Anda menggunakan cmdlet Get-AzBatchAccount untuk mendapatkan BatchAccountContext, autentikasi Azure Active Directory akan digunakan saat berinteraksi dengan layanan Batch. Untuk menggunakan autentikasi kunci bersama, gunakan cmdlet Get-AzBatchAccountKey untuk mendapatkan objek BatchAccountContext dengan tombol aksesnya diisi. Saat menggunakan autentikasi kunci bersama, kunci akses utama digunakan secara default. Untuk mengubah kunci yang akan digunakan, atur properti BatchAccountContext.KeyInUse.

```yaml
Type: Microsoft.Azure.Commands.Batch.BatchAccountContext
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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

### -EndTime
Menentukan akhir rentang waktu di mana cmdlet ini mendapatkan metrik penggunaan.
Menentukan waktu setidaknya dua jam sebelumnya.
Jika Anda tidak menentukan waktu akhir, cmdlet ini menggunakan interval agregasi terakhir yang saat ini tersedia.

```yaml
Type: System.Nullable`1[System.DateTime]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Filter
Menentukan klausul filter OData untuk digunakan memfilter metrik yang dikembalikan cmdlet ini.
Satu-satunya properti yang **valid adalah poolId** dengan nilai string.
Operasi yang memungkinkan adalah sebagai berikut: eq, ge, gt, le, lt, startswith.

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

### -StartTime
Menentukan awal rentang waktu di mana cmdlet ini mendapatkan metrik penggunaan.
Tentukan waktu setidaknya dua dan setengah jam sebelumnya.
Jika Anda tidak menentukan waktu mulai, cmdlet ini menggunakan interval agregasi terakhir yang saat ini tersedia.

```yaml
Type: System.Nullable`1[System.DateTime]
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

### Microsoft.Azure.Commands.Batch.BatchAccountContext

## OUTPUTS

### Microsoft.Azure.Commands.Batch.Models.PSPoolUsageMetrics

## CATATAN

## RELATED LINKS

[Get-AzBatchAccountKey](./Get-AzBatchAccountKey.md)

[Get-AzBatchPoolStatistics](./Get-AzBatchPoolStatistic.md)

[Get-AzBatchJobStatistics](./Get-AzBatchJobStatistic.md)
