---
external help file: ''
Module Name: Az.LabServices
online version: https://docs.microsoft.com/powershell/module/az.labservices/add-azlabservicesuserquota
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/LabServices/help/Add-AzLabServicesUserQuota.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/LabServices/help/Add-AzLabServicesUserQuota.md
ms.openlocfilehash: 650adc4587662b268f60ba0386811eeaac52ebb1
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140402243"
---
# Add-AzLabServicesUserQuota

## SYNOPSIS
API untuk menambahkan kuota pengguna tambahan.

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

### Contoh 1: Tambah kuota penggunaan pelajar.
```powershell
PS C:\> Add-AzLabUserQuota -ResourceGroupName "group name" -LabName "lab name" -Email 'student@contoso.com' -UsageQuotaToAddToExisting $(New-Timespan -Hours 4)

Name           Type
----           ----
testuser       Microsoft.LabServices/labs/users
```

Perintah ini akan menambah kuota siswa selama 4 jam.

### Contoh 2: Tambah kuota penggunaan pelajar dengan objek Pengguna.
```powershell
PS C:\> $user = Get-AzLabUser -ResourceGroupName "group name" -LabName "lab name" -UserName 'ContosoUser12345'
PS C:\> $user | Add-AzLabUserQuota -UsageQuotaToAddToExisting $(New-Timespan -Hours 5)

Name                 Type
----                 ----
ContosoUser12345     Microsoft.LabServices/labs/users
```

Menambah kuota siswa sebesar 5 jam.

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

### -Email
Nama pengguna yang secara tidak pasti mengidentifikasinya di dalam berisi lab.
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
Jumlah waktu kuota penggunaan yang akan diberikan pengguna selain kuota pengguna saat ini.

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

### -Pengguna
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

### Microsoft.Azure.PowerShell.Cmdlets.LabServices.Models.Api20211001Preview.User

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.LabServices.Models.Api20211001Preview.IUser

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


PENGGUNA <User>: 
  - `Email <String>`: Alamat email pengguna.
  - `[AdditionalUsageQuota <TimeSpan?>]`: Jumlah waktu kuota penggunaan yang akan diberikan pengguna selain kuota penggunaan lab.
  - `[SystemDataCreatedAt <DateTime?>]`: Timestamp pembuatan sumber daya (UTC).
  - `[SystemDataCreatedBy <String>]`: Identitas yang membuat sumber daya.
  - `[SystemDataCreatedByType <CreatedByType?>]`: Tipe identitas yang membuat sumber daya.
  - `[SystemDataLastModifiedAt <DateTime?>]`: Timestamp sumber daya modifikasi terakhir (UTC)
  - `[SystemDataLastModifiedBy <String>]`: Identitas yang terakhir diubah sumber daya.
  - `[SystemDataLastModifiedByType <CreatedByType?>]`: Tipe identitas yang terakhir diubah sumber daya.

## RELATED LINKS

