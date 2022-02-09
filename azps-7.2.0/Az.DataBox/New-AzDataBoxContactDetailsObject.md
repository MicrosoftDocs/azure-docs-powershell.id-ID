---
external help file: ''
Module Name: Az.DataBox
online version: https://docs.microsoft.com/powershell/module/az.DataBox/new-AzDataBoxContactDetailsObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataBox/help/New-AzDataBoxContactDetailsObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataBox/help/New-AzDataBoxContactDetailsObject.md
ms.openlocfilehash: e7769bae045715018179fd98820257c8a6ca3513
ms.sourcegitcommit: 7e47562b11e670049c3a18af7498414da853a921
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/09/2022
ms.locfileid: "138269339"
---
# New-AzDataBoxContactDetailsObject

## SYNOPSIS
Membuat objek dalam memori untuk ContactDetails.

## SYNTAX

```
New-AzDataBoxContactDetailsObject -ContactName <String> -EmailList <String[]> -Phone <String>
 [-Mobile <String>] [-NotificationPreference <INotificationPreference[]>] [-PhoneExtension <String>]
 [<CommonParameters>]
```

## DESCRIPTION
Membuat objek dalam memori untuk ContactDetails.

## EXAMPLES

### Contoh 1: Membuat objek dalam memori untuk ContactDetails 
```powershell
PS C:\> $contactDetail = New-AzDataBoxContactDetailsObject -ContactName "random" -EmailList @("emailId") -Phone "1234567891"
PS C:\>  $contactDetail

ContactName EmailList            Mobile Phone      PhoneExtension
----------- ---------            ------ -----      --------------
random      {emailId}        1234567891
```

Membuat objek dalam memori untuk ContactDetails

## PARAMETERS

### -ContactName
Nama kontak orang tersebut.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EmailList
Daftar Id-email untuk diberi tahu tentang kemajuan pekerjaan.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Seluler
Nomor ponsel orang kontak.

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

### -NotificationPreference
Preferensi pemberitahuan untuk tahap pekerjaan.
Untuk membuat, lihat bagian CATATAN untuk properti NOTIFICATIONPREFERENCE dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.DataBox.Models.Api20210301.INotificationPreference[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Telepon
Telepon nomor kontak.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PhoneExtension
Telepon nomor ekstensi orang kontak.

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

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.DataBox.Models.Api20210301.ContactDetails

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


NOTIFICATIONPREFERENCE <INotificationPreference[]>: Preferensi pemberitahuan untuk tahap pekerjaan.
  - `SendNotification <Boolean>`: Pemberitahuan diperlukan atau tidak.
  - `StageName <NotificationStageName>`: Nama tahapan.

## RELATED LINKS

