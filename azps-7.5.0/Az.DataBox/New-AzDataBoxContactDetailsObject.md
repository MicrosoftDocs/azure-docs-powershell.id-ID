---
external help file: ''
Module Name: Az.DataBox
online version: https://docs.microsoft.com/powershell/module/az.DataBox/new-AzDataBoxContactDetailsObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataBox/help/New-AzDataBoxContactDetailsObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataBox/help/New-AzDataBoxContactDetailsObject.md
ms.openlocfilehash: e325f283e69d5052f6ffce165377e00de287dcf5
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144205154"
---
# New-AzDataBoxContactDetailsObject

## SYNOPSIS
Buat objek dalam memori untuk ContactDetails.

## SYNTAX

```
New-AzDataBoxContactDetailsObject -ContactName <String> -EmailList <String[]> -Phone <String>
 [-Mobile <String>] [-NotificationPreference <INotificationPreference[]>] [-PhoneExtension <String>]
 [<CommonParameters>]
```

## DESCRIPTION
Buat objek dalam memori untuk ContactDetails.

## EXAMPLES

### Contoh 1: Membuat objek dalam memori untuk ContactDetails 
```powershell
$contactDetail = New-AzDataBoxContactDetailsObject -ContactName "random" -EmailList @("emailId") -Phone "1234567891"
$contactDetail
```

```output
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
Daftar Email-id yang akan diberi tahu tentang kemajuan pekerjaan.

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

### -Mobile
Nomor ponsel kontak.

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
Untuk membuat, lihat bagian CATATAN untuk properti NOTIFICATIONPREFERENCE dan buat tabel hash.

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
Telepon nomor ekstensi kontak.

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

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.DataBox.Models.Api20210301.ContactDetails

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


NOTIFICATIONPREFERENCE <INotificationPreference[]>: Preferensi pemberitahuan untuk tahap pekerjaan.
  - `SendNotification <Boolean>`: Pemberitahuan diperlukan atau tidak.
  - `StageName <NotificationStageName>`: Nama panggung.

## RELATED LINKS

