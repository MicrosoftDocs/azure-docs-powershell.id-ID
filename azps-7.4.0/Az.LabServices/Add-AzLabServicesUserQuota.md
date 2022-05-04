---
external help file: ''
Module Name: Az.LabServices
online version: https://docs.microsoft.com/powershell/module/az.labservices/add-azlabservicesuserquota
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/LabServices/help/Add-AzLabServicesUserQuota.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/LabServices/help/Add-AzLabServicesUserQuota.md
ms.openlocfilehash: c3704b7cfdae28f75395974fa7bd6dc160b026f5
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144625332"
---
# Add-AzLabServicesUserQuota

## SYNOPSIS
API untuk menambahkan kuota pengguna tambahan.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.labservices/add-azlabservicesuserquota) untuk informasi terbaru.

## SYNTAX

### Pengguna (Default)
```
Add-AzLabServicesUserQuota -UsageQuotaToAddToExisting <TimeSpan> -User <User> [-SubscriptionId <String>]
 [-DefaultProfile <PSObject>] [-AsJob] [-Confirm] [-WhatIf] [<CommonParameters>]
```

### Email
```
Add-AzLabServicesUserQuota -Email <String> -LabName <String> -ResourceGroupName <String>
 -UsageQuotaToAddToExisting <TimeSpan> [-SubscriptionId <String>] [-DefaultProfile <PSObject>] [-AsJob]
 [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
API untuk menambahkan kuota pengguna tambahan.

## EXAMPLES

### Contoh 1: Menambah kuota penggunaan siswa.
```powershell
Add-AzLabUserQuota -ResourceGroupName "group name" -LabName "lab name" -Email 'student@contoso.com' -UsageQuotaToAddToExisting $(New-Timespan -Hours 4)
```

```output
Name           Type
----           ----
testuser       Microsoft.LabServices/labs/users
```

Perintah ini menambah kuota siswa hingga 4 jam.

### Contoh 2: Meningkatkan kuota penggunaan siswa dengan objek Pengguna.
```powershell
$user = Get-AzLabUser -ResourceGroupName "group name" -LabName "lab name" -UserName 'ContosoUser12345'
$user | Add-AzLabUserQuota -UsageQuotaToAddToExisting $(New-Timespan -Hours 5)
```

```output
Name                 Type
----                 ----
ContosoUser12345     Microsoft.LabServices/labs/users
```

Tambah kuota siswa 5 jam.

## PARAMETERS

### -AsJob
Jalankan perintah sebagai pekerjaan

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

### -Email
Nama pengguna yang secara uniqely mengidentifikasinya di dalam lab yang berisi.
Digunakan dalam URI sumber daya.

```yaml
Type: System.String
Parameter Sets: Email
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LabName


```yaml
Type: System.String
Parameter Sets: Email
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName


```yaml
Type: System.String
Parameter Sets: Email
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubscriptionId
ID langganan target.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### -UsageQuotaToAddToExisting
Jumlah waktu kuota penggunaan yang didapat pengguna selain kuota pengguna saat ini.

```yaml
Type: System.TimeSpan
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -User
Untuk membuat, lihat bagian CATATAN untuk properti USER dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.LabServices.Models.Api20211001Preview.User
Parameter Sets: User
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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

### Microsoft.Azure.PowerShell.Cmdlets.LabServices.Models.Api20211001Preview.User

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.LabServices.Models.Api20211001Preview.IUser

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


USER <User>: 
  - `Email <String>`: Alamat email pengguna.
  - `[AdditionalUsageQuota <TimeSpan?>]`: Jumlah waktu kuota penggunaan yang didapat pengguna selain kuota penggunaan lab.
  - `[SystemDataCreatedAt <DateTime?>]`: Tanda waktu pembuatan sumber daya (UTC).
  - `[SystemDataCreatedBy <String>]`: Identitas yang membuat sumber daya.
  - `[SystemDataCreatedByType <CreatedByType?>]`: Jenis identitas yang membuat sumber daya.
  - `[SystemDataLastModifiedAt <DateTime?>]`: Tanda waktu modifikasi terakhir sumber daya (UTC)
  - `[SystemDataLastModifiedBy <String>]`: Identitas yang terakhir memodifikasi sumber daya.
  - `[SystemDataLastModifiedByType <CreatedByType?>]`: Jenis identitas yang terakhir memodifikasi sumber daya.

## RELATED LINKS

