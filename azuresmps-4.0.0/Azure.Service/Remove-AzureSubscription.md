---
external help file: Microsoft.WindowsAzure.Commands.Profile.dll-Help.xml
ms.assetid: ABC303ED-8712-4958-B871-E95357012277
online version: ''
schema: 2.0.0
ms.openlocfilehash: 76dae8383323e132110ff8e71af446e0d102cd7a
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132425831"
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
Cmdlet **Remove-AzureSubscription** menghapus langganan Azure dari file data langganan Windows PowerShell tidak dapat menemukannya.
Cmdlet ini tidak menghapus langganan dari Microsoft Azure, atau mengubah langganan sebenarnya dengan cara apa pun.

Topik ini menguraikan cmdlet dalam modul Microsoft Azure PowerShell versi 0.8.10.
Untuk mendapatkan versi modul yang Anda gunakan, di konsol Azure PowerShell, ketik `(Get-Module -Name Azure).Version` .

## EXAMPLES

### Contoh 1: Menghapus langganan
```
C:\PS> Remove-AzureSubscription -SubscriptionName Test

Confirm
Are you sure you want to perform this action?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"):
```

Perintah ini akan menghapus langganan "Uji" dari file data langganan default.

### Contoh 2: Hapus dari file data langganan alternatif
```
C:\PS> Remove-AzureSubscription -SubscriptionName Test -SubscriptionDataFile C:\Subs\MySubscriptions.xml -Force
```

Perintah ini akan menghapus langganan Uji dari MySubscriptions.xml file data langganan.
Perintah menggunakan parameter *Paksa* untuk menyembunyikan perintah konfirmasi.

### Contoh 3: Menghapus langganan dalam skrip
```
C:\PS> ...if (Remove-AzureSubscription -SubscriptionName Test -PassThru) {...}
```

Perintah ini menggunakan **perintah Remove-AzureSubscription** dalam **pernyataan If.**
Skrip ini menggunakan parameter *PassThru,* yang mengembalikan nilai Boolean, untuk menentukan apakah blok skrip **dalam pernyataan If** dijalankan.

## PARAMETERS

### -Force
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
Mengembalikan $True jika perintah berhasil $False jika gagal.
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
Menentukan profil Azure yang akan dibaca cmdlet ini. Jika Anda tidak menentukan profil, cmdlet ini akan membaca dari profil default lokal.

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
Meminta konfirmasi Anda sebelum menjalankan cmdlet.

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
Cmdlet tidak berjalan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### Tidak ada
Anda dapat pipa input ke cmdlet ini berdasarkan nama properti, tetapi tidak menurut nilai.

## OUTPUTS

### Tidak Ada atau System.Boolean
Jika Anda menggunakan parameter *PassThru,* cmdlet ini mengembalikan nilai Boolean.
Jika tidak, output tidak akan dikembalikan.

## CATATAN

## RELATED LINKS

[Get-AzureSubscription](./Get-AzureSubscription.md)

[Select-AzureSubscription](./Select-AzureSubscription.md)

[Set-AzureSubscription](./Set-AzureSubscription.md)


