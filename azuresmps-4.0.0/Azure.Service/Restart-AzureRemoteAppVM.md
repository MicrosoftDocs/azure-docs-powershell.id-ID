---
external help file: Microsoft.WindowsAzure.Commands.RemoteApp.dll-Help.xml
ms.assetid: F83D698B-DC48-4ACD-AD2E-4AAECBDA196B
online version: ''
schema: 2.0.0
ms.openlocfilehash: 4f5035b19f790cdfc39edcbaad33d1e96fe3dbb4
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142312320"
---
# Restart-AzureRemoteAppVM

## SYNOPSIS
Memulai ulang mesin virtual dalam koleksi Azure RemoteApp.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Restart-AzureRemoteAppVM -CollectionName <String> -UserUpn <String> [-LogoffMessage <String>]
 [-LogoffWaitSeconds <Int32>] [-Profile <AzureSMProfile>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Restart-AzureRemoteAppVM** memulai ulang mesin virtual dalam koleksi Azure RemoteApp tempat pengguna yang ditentukan tersambung.

## EXAMPLES

### Contoh 1: Memulai ulang mesin virtual
```
PS C:\> Restart-AzureRemoteAppVM -CollectionName "ContosoVNet" -UserUPN "PattiFuller@contoso.com"
```

Perintah ini memulai ulang mesin virtual dalam koleksi Azure RemoteApp bernama Contoso.
Pengguna PattiFuller@contoso.com tersambung ke koleksi yang berisi mesin virtual ini.

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

### -LogoffMessage
Menentukan pesan peringatan yang diperlihatkan kepada pengguna yang tersambung ke mesin virtual sebelum cmdlet ini mengeluarkannya.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -LogoffWaitSeconds
Menentukan berapa lama cmdlet ini menunggu sebelum log pengguna nonaktif.
Nilai defaultnya adalah 60 detik.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Profil
Menentukan profil Azure tempat cmdlet ini dibaca.
Jika Anda tidak menentukan profil, cmdlet ini akan dibaca dari profil default lokal.

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

### -UserUpn
Menentukan nama pokok pengguna (UPN) pengguna yang cmdlet ini memulai ulang mesin virtual.
Untuk mendapatkan mesin virtual dalam pengumpulan dan UPN yang tersambung, gunakan cmdlet **Get-AzureRemoteAppVM** .

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
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

## OUTPUTS

## CATATAN

## RELATED LINKS

[Get-AzureRemoteAppVM](./Get-AzureRemoteAppVM.md)


