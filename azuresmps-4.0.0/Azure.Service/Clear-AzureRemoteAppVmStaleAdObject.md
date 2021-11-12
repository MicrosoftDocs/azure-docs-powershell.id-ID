---
external help file: Microsoft.WindowsAzure.Commands.RemoteApp.dll-Help.xml
ms.assetid: DA8EC1BD-1219-4B98-B661-40A28897271F
online version: ''
schema: 2.0.0
ms.openlocfilehash: 144a7be6f6ec8ffdd4c6f94dc8d883e71e5aa8ce
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132419496"
---
# Clear-AzureRemoteAppVmStaleAdObject

## SYNOPSIS
Menghapus objek di Azure Active Directory yang terkait dengan komputer virtual Azure RemoteApp yang tidak lagi ada.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Clear-AzureRemoteAppVmStaleAdObject -CollectionName <String> [-Credential <PSCredential>]
 [-Profile <AzureSMProfile>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Clear-AzureRemoteAppVmStaleAdObject** menghapus objek Azure Active Directory yang terkait dengan komputer virtual Azure RemoteApp yang sudah tidak ada lagi.
Anda harus menggunakan kredensial yang memiliki hak untuk menghapus Azure Active Directory tersebut.
Jika Anda menentukan parameter *umum Verbose,* cmdlet ini menampilkan nama setiap objek yang dihapusnya.

## EXAMPLES

### Contoh 1: Hapus objek basi untuk koleksi
```
PS C:\> $AdminCredentials = Get-Credential
PS C:\> Clear-AzureRemoteAppVmStaleAdObject -CollectionName "Contoso" -Credential $AdminCredentials
```

Perintah pertama meminta nama pengguna dan kata sandi menggunakan **Get-Credential.**
Perintah menyimpan hasil dalam $AdminCredentials variabel.

Perintah kedua menghapus objek basi untuk koleksi bernama Contoso.
Perintah menggunakan kredensial yang disimpan dalam $AdminCredentials variabel.
Agar perintah berhasil, kredensial tersebut harus memiliki hak yang tepat.

## PARAMETERS

### -CollectionName
Menentukan nama koleksi Azure RemoteApp.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Name

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Credential
Menentukan kredensial yang memiliki hak untuk melakukan tindakan ini.
Untuk mendapatkan objek **PSCredential,** gunakan cmdlet **Get-Credential.**
Jika Anda tidak menentukan parameter ini, cmdlet ini menggunakan kredensial pengguna saat ini.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Profil
Menentukan profil Azure yang akan dibaca cmdlet ini.
Jika Anda tidak menentukan profil, cmdlet ini akan membaca dari profil default lokal.

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

## OUTPUTS

## CATATAN

## RELATED LINKS

[Get-AzureRemoteAppVmStaleAdObject](./Get-AzureRemoteAppVmStaleAdObject.md)


