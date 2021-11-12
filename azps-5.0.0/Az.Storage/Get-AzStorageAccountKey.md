---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Storage.Management.dll-Help.xml
Module Name: Az.Storage
ms.assetid: A57A9EFA-47AC-44D8-BFA7-CDE0E2A612B3
online version: https://docs.microsoft.com/en-us/powershell/module/az.storage/get-azstorageaccountkey
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/Storage/Storage.Management/help/Get-AzStorageAccountKey.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/Storage/Storage.Management/help/Get-AzStorageAccountKey.md
ms.openlocfilehash: 3a681f2df128979ad79d678101b400b040fa994c
ms.sourcegitcommit: b4a38bcb0501a9016a4998efd377aa75d3ef9ce8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 10/27/2020
ms.locfileid: "132410311"
---
# Get-AzStorageAccountKey

## SYNOPSIS
Dapatkan kunci akses untuk akun Azure Storage Anda.

## SINTAKS

```
Get-AzStorageAccountKey [-ResourceGroupName] <String> [-Name] <String> [-ListKerbKey]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESKRIPSI
Cmdlet **Get-AzStorageAccountKey** mendapatkan kunci akses untuk akun Azure Storage Anda.

## CONTOH

### Contoh 1: Dapatkan kunci akses untuk Storage anda
```
PS C:\>Get-AzStorageAccountKey -ResourceGroupName "RG01" -AccountName "mystorageaccount"
```

Perintah ini mendapatkan tombol untuk akun Azure Storage tertentu.

### Contoh 2: Dapatkan kunci akses tertentu untuk Storage Anda
```
This command gets a specific key for a Storage account. This command works for Azure PowerShell version 1.4, and later versions.
PS C:\>(Get-AzStorageAccountKey -ResourceGroupName "RG01" -AccountName "mystorageaccount")| Where-Object {$_.KeyName -eq "key1"}

This command gets a specific key for a Storage account. This command works for Azure PowerShell version 1.3.2, and previous versions.
PS C:\>(Get-AzStorageAccountKey -ResourceGroupName "RG01" -AccountName "mystorageaccount").Key1
```

### Contoh 3: Mencantumkan kunci akses untuk akun Storage Anda, sertakan tombol Kerberos (jika direktori aktif diaktifkan)
```
PS C:\>Get-AzStorageAccountKey -ResourceGroupName "RG01" -AccountName "mystorageaccount" -ListKerbKey
```

Perintah ini mendapatkan tombol untuk akun Azure Storage tertentu.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ListKerbKey
Mencantumkan tombol Kerberos (jika direktori aktif diaktifkan) untuk akun penyimpanan tertentu.
Tombol Kerberos dihasilkan per akun penyimpanan untuk autentikasi berbasis identitas File Azure baik dengan Azure Active Directory Domain Service (Azure AD DS) atau Active Directory Domain Service (AD DS). Ini digunakan sebagai kata sandi dari identitas yang terdaftar di layanan domain yang mewakili akun penyimpanan. Tombol Kerberos tidak menyediakan izin akses untuk melakukan operasi baca dan tulis kontrol atau bidang data apa pun terhadap akun penyimpanan.

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

### -Nama
Menentukan nama akun Storage yang mendapatkan kunci cmdlet ini.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: StorageAccountName, AccountName

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Menentukan nama grup sumber daya yang berisi akun Storage tersebut.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( http://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUT

### System.String

## OUTPUT

### Microsoft.Azure.Management. Storage. Models.StorageAccountKey

## CATATAN

## LINK TERKAIT

[New-AzStorageAccountKey](./New-AzStorageAccountKey.md)


