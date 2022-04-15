---
external help file: Microsoft.WindowsAzure.Commands.Profile.dll-Help.xml
ms.assetid: ABC303ED-8712-4958-B871-E95357012277
online version: ''
schema: 2.0.0
ms.openlocfilehash: 76dae8383323e132110ff8e71af446e0d102cd7a
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142244386"
---
# Remove-AzureSubscription

## SYNOPSIS
Menghapus langganan Azure dari Windows PowerShell.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

### Nama (Default)
```
Remove-AzureSubscription -SubscriptionName <String> [-Force] [-PassThru] [-Profile <AzureSMProfile>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### Id
```
Remove-AzureSubscription -SubscriptionId <String> [-Force] [-PassThru] [-Profile <AzureSMProfile>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Remove-AzureSubscription** menghapus langganan Azure dari file data langganan Anda sehingga Windows PowerShell tidak dapat menemukannya.
Cmdlet ini tidak menghapus langganan dari Microsoft Azure, atau mengubah langganan aktual dengan cara apa pun.

Topik ini menjelaskan cmdlet dalam versi 0.8.10 modul Microsoft Azure PowerShell.
Untuk mendapatkan versi modul yang Anda gunakan, di konsol Azure PowerShell, ketik .`(Get-Module -Name Azure).Version`

## EXAMPLES

### Contoh 1: Menghapus langganan
```
C:\PS> Remove-AzureSubscription -SubscriptionName Test

Confirm
Are you sure you want to perform this action?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"):
```

Perintah ini menghapus langganan "Uji" dari file data langganan default.

### Contoh 2: Hapus dari file data langganan alternatif
```
C:\PS> Remove-AzureSubscription -SubscriptionName Test -SubscriptionDataFile C:\Subs\MySubscriptions.xml -Force
```

Perintah ini menghapus Uji langganan dari file data langganan MySubscriptions.xml.
Perintah menggunakan parameter *Paksa* untuk menyembunyikan perintah konfirmasi.

### Contoh 3: Menghapus langganan dalam skrip
```
C:\PS> ...if (Remove-AzureSubscription -SubscriptionName Test -PassThru) {...}
```

Perintah ini menggunakan perintah **Hapus-AzureSubscription** dalam pernyataan **If** .
Ini menggunakan parameter *PassThru* , yang mengembalikan nilai Boolean, untuk menentukan apakah blok skrip dalam pernyataan **If** dijalankan.

## PARAMETERS

### -Paksa
Menyembunyikan perintah konfirmasi.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Mengembalikan $True jika perintah berhasil dan $False jika gagal.
Secara default, cmdlet ini tidak mengembalikan output apa pun.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Profil
Menentukan profil Azure tempat cmdlet ini dibaca. Jika Anda tidak menentukan profil, cmdlet ini akan dibaca dari profil default lokal.

```yaml
Type: AzureSMProfile
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubscriptionId
```yaml
Type: String
Parameter Sets: Id
Aliases: Id

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SubscriptionName
```yaml
Type: String
Parameter Sets: Name
Aliases: Name

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Konfirmasi
Meminta konfirmasi sebelum menjalankan cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan.
Cmdlet tidak dijalankan.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak
Anda dapat menyalurkan input ke cmdlet ini menurut nama properti, tetapi tidak menurut nilai.

## OUTPUTS

### Tidak ada atau System.Boolean
Jika Anda menggunakan parameter *PassThru* , cmdlet ini mengembalikan nilai Boolean.
Jika tidak, tidak mengembalikan output apa pun.

## CATATAN

## RELATED LINKS

[Get-AzureSubscription](./Get-AzureSubscription.md)

[Select-AzureSubscription](./Select-AzureSubscription.md)

[Set-AzureSubscription](./Set-AzureSubscription.md)


