---
external help file: ''
Module Name: Az.LabServices
online version: https://docs.microsoft.com/powershell/module/az.labservices/send-azlabservicesuserinvite
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/LabServices/help/Send-AzLabServicesUserInvite.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/LabServices/help/Send-AzLabServicesUserInvite.md
ms.openlocfilehash: a43d6d1eb212fa65535d885303899de084aa428c
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142432355"
---
# Send-AzLabServicesUserInvite

## SYNOPSIS
Operasi untuk mengundang pengguna ke laboratorium.

## SYNTAX

### ResourceId (Default)
```
Send-AzLabServicesUserInvite -ResourceId <String> [-SubscriptionId <String>] [-Text <String>]
 [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [<CommonParameters>]
```

### InviteExpanded
```
Send-AzLabServicesUserInvite -LabName <String> -ResourceGroupName <String> -UserName <String>
 [-SubscriptionId <String>] [-Text <String>] [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-PassThru]
 [-Confirm] [-WhatIf] [<CommonParameters>]
```

### Pengguna
```
Send-AzLabServicesUserInvite -User <User> [-SubscriptionId <String>] [-Text <String>]
 [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [<CommonParameters>]
```

## DESCRIPTION
Operasi untuk mengundang pengguna ke laboratorium.

## EXAMPLES

### Contoh 1: Kirim undangan lab kepada pengguna.
```powershell
Send-AzLabServicesUserInvite -ResourceGroupName "Group Name" -LabName "Lab Name" -Name "User Name" -Text "Welcome to the lab."
```

Tindakan ini mengirimkan undangan email kepada pengguna dengan teks kustom "Selamat datang di lab" dalam isi email.

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

### -LabName
Nama lab yang mengidentifikasinya secara unik di dalamnya berisi akun lab.
Digunakan dalam URI sumber daya.

```yaml
Type: System.String
Parameter Sets: InviteExpanded
Aliases:

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

### -PassThru
Mengembalikan true ketika perintah berhasil

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: InviteExpanded
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
Parameter Sets: InviteExpanded
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceId


```yaml
Type: System.String
Parameter Sets: ResourceId
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

### -Teks
Teks kustom untuk email undangan.

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

### -Pengguna
Untuk membangun, lihat bagian CATATAN untuk properti PENGGUNA dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.LabServices.Models.Api20211001Preview.User
Parameter Sets: Users
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -NamaPengguna
Nama pengguna yang mengidentifikasinya secara unik di dalam lab.
Digunakan dalam URI sumber daya.

```yaml
Type: System.String
Parameter Sets: InviteExpanded
Aliases:

Required: True
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

### Microsoft.Azure.PowerShell.Cmdlets.LabServices.Models.Api20211001Preview.User

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.LabServices.Models.Api20211001Preview.IVirtualMachine

### System.Boolean

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


PENGGUNA <User>: 
  - `Email <String>`: Alamat email pengguna.
  - `[AdditionalUsageQuota <TimeSpan?>]`: Jumlah waktu kuota penggunaan yang didapatkan pengguna selain kuota penggunaan lab.
  - `[SystemDataCreatedAt <DateTime?>]`: Stempel waktu pembuatan sumber daya (UTC).
  - `[SystemDataCreatedBy <String>]`: Identitas yang membuat sumber daya.
  - `[SystemDataCreatedByType <CreatedByType?>]`: Tipe identitas yang membuat sumber daya.
  - `[SystemDataLastModifiedAt <DateTime?>]`: Cap waktu modifikasi terakhir sumber daya (UTC)
  - `[SystemDataLastModifiedBy <String>]`: Identitas yang terakhir mengubah sumber daya.
  - `[SystemDataLastModifiedByType <CreatedByType?>]`: Tipe identitas yang terakhir mengubah sumber daya.

## RELATED LINKS

