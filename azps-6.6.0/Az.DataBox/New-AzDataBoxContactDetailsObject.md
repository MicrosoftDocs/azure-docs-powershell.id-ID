---
external help file: ''
Module Name: Az.DataBox
online version: https://docs.microsoft.com/powershell/module/az.DataBox/new-AzDataBoxContactDetailsObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataBox/help/New-AzDataBoxContactDetailsObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataBox/help/New-AzDataBoxContactDetailsObject.md
ms.openlocfilehash: d0482c9234dc242e0260609f4c8d788d46d9d840
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142306861"
---
# New-AzDataBoxContactDetailsObject

## SYNOPSIS
Membuat objek dalam memori untuk ContactDetails

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.databox/new-azdataboxcontactdetailsobject) untuk informasi terbaru.

## SYNTAX

```
New-AzDataBoxContactDetailsObject -ContactName <String> -EmailList <String[]> -Phone <String>
 [-Mobile <String>] [-NotificationPreference <INotificationPreference[]>] [-PhoneExtension <String>]
 [<CommonParameters>]
```

## DESCRIPTION
Membuat objek dalam memori untuk ContactDetails

## EXAMPLES

### Contoh 1: {{ Buat objek dalam memori untuk ContactDetails }}
```powershell
PS C:\> $contactDetail = New-AzDataBoxContactDetailsObject -ContactName "random" -EmailList @("emailId") -Phone "1234567891"
PS C:\>  $contactDetail

ContactName EmailList            Mobile Phone      PhoneExtension
----------- ---------            ------ -----      --------------
random      {emailId}        1234567891
```

{{ Buat objek dalam memori untuk ContactDetails }}

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
Nomor ponsel orang yang dihubungi.

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
Untuk membangun, lihat bagian CATATAN untuk properti NOTIFICATIONPREFERENCE dan membuat tabel hash.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.DataBox.Models.Api20210301.ContactDetails

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


NOTIFICATIONPREFERENCE <INotificationPreference[]>: Preferensi pemberitahuan untuk tahap pekerjaan.
  - `SendNotification <Boolean>`: Pemberitahuan diperlukan atau tidak.
  - `StageName <NotificationStageName>`: Nama panggung.

## RELATED LINKS

