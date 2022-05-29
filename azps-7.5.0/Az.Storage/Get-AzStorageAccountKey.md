---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Storage.Management.dll-Help.xml
Module Name: Az.Storage
ms.assetid: A57A9EFA-47AC-44D8-BFA7-CDE0E2A612B3
online version: https://docs.microsoft.com/powershell/module/az.storage/get-azstorageaccountkey
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Storage/Storage.Management/help/Get-AzStorageAccountKey.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Storage/Storage.Management/help/Get-AzStorageAccountKey.md
ms.openlocfilehash: db510fc0b343bc4a0b78aa460baddf2838654e1c
ms.sourcegitcommit: 82b4008b76d035e4aee733727371765b0d853bed
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145718002"
---
# Get-AzStorageAccountKey

## SYNOPSIS
Mendapatkan kunci akses untuk akun Azure Storage.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.storage/get-azstorageaccountkey) untuk informasi terbaru.

## SYNTAX

```
Get-AzStorageAccountKey [-ResourceGroupName] <String> [-Name] <String> [-ListKerbKey]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzStorageAccountKey** mendapatkan kunci akses untuk akun Azure Storage.

## EXAMPLES

### Contoh 1: Mendapatkan kunci akses untuk akun Storage
```
PS C:\>Get-AzStorageAccountKey -ResourceGroupName "RG01" -AccountName "mystorageaccount"
```

Perintah ini mendapatkan kunci untuk akun Azure Storage yang ditentukan.

### Contoh 2: Mendapatkan kunci akses tertentu untuk akun Storage
```
This command gets a specific key for a Storage account. This command works for Azure PowerShell version 1.4, and later versions.
PS C:\>(Get-AzStorageAccountKey -ResourceGroupName "RG01" -AccountName "mystorageaccount")| Where-Object {$_.KeyName -eq "key1"}

This command gets a specific key for a Storage account. This command works for Azure PowerShell version 1.3.2, and previous versions.
PS C:\>(Get-AzStorageAccountKey -ResourceGroupName "RG01" -AccountName "mystorageaccount").Key1
```

### Contoh 3: Mencantumkan kunci akses untuk akun Storage, sertakan kunci Kerberos (jika direktori aktif diaktifkan)
```
PS C:\>Get-AzStorageAccountKey -ResourceGroupName "RG01" -AccountName "mystorageaccount" -ListKerbKey
```

Perintah ini mendapatkan kunci untuk akun Azure Storage yang ditentukan.

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
Mencantumkan kunci Kerberos (jika direktori aktif diaktifkan) untuk akun penyimpanan yang ditentukan.
Kunci Kerberos dihasilkan per akun penyimpanan untuk autentikasi berbasis identitas Azure Files baik dengan Azure Active Directory Domain Service (Azure AD DS) atau Active Directory Domain Service (AD DS). Ini digunakan sebagai kata sandi identitas yang terdaftar di layanan domain yang mewakili akun penyimpanan. Kunci Kerberos tidak menyediakan izin akses untuk melakukan kontrol atau operasi baca atau tulis sarana data terhadap akun penyimpanan.

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

### -Name
Menentukan nama akun Storage tempat cmdlet ini mendapatkan kunci.

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
Menentukan nama grup sumber daya yang berisi akun Storage.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Management. Storage. Models.StorageAccountKey

## NOTES

## RELATED LINKS

[New-AzStorageAccountKey](./New-AzStorageAccountKey.md)


