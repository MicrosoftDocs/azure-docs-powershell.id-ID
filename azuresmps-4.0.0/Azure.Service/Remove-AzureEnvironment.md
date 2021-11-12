---
external help file: Microsoft.WindowsAzure.Commands.Profile.dll-Help.xml
ms.assetid: 4B8B56B4-511B-45BD-9595-B47187C76E03
online version: ''
schema: 2.0.0
ms.openlocfilehash: a446e329f64357598793532cb27319e11d078ab2
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132422479"
---
# Remove-AzureEnvironment

## SYNOPSIS
Menghapus lingkungan Azure dari Windows PowerShell.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Remove-AzureEnvironment -Name <String> [-Force] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Remove-AzureEnvironment** menghapus lingkungan Azure dari profil jelajah Windows PowerShell tidak dapat menemukannya.
Cmdlet ini tidak menghapus lingkungan dari lingkungan Microsoft Azure, atau mengubah lingkungan sebenarnya dengan cara apa pun.

Lingkungan Azure, penyebaran independen dari Microsoft Azure, seperti AzureCloud untuk global Azure dan AzureChinaCloud untuk Azure yang dioperasikan oleh 21Vianet di Tiongkok.
Anda juga bisa membuat lingkungan Azure lokal dengan menggunakan Paket Azure dan cmdlet WAPack.
Untuk informasi selengkapnya, lihat [Paket Azure.](/previous-versions/azure/windows-server-azure-pack/)

## EXAMPLES

### Contoh 1: Menghapus lingkungan
```
PS C:\> Remove-AzureEnvironment -Name ContosoEnv
```

Perintah ini menghapus lingkungan ContosoEnv dari Windows PowerShell.

### Contoh 2: Menghapus beberapa lingkungan
```
PS C:\> Get-AzureEnvironment | Where-Object EnvironmentName -like "Contoso*" | ForEach-Object {Remove-AzureEnvironment -Name $_.EnvironmentName }
```

Perintah ini menghapus lingkungan yang namanya dimulai dengan "Contoso" dari Windows PowerShell.

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

### -Nama
Menentukan nama lingkungan yang akan dihapus.
Parameter ini diperlukan.
Nilai parameter ini bersifat peka huruf besar-kecil.
Karakter wildcard tidak diizinkan.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

[Add-AzureEnvironment](./Add-AzureEnvironment.md)

[Get-AzureEnvironment](./Get-AzureEnvironment.md)

[Set-AzureEnvironment](./Set-AzureEnvironment.md)


