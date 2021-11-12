---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
ms.assetid: 09ABE9E2-1080-4DEF-92DD-B8FF4C8B308C
online version: ''
schema: 2.0.0
ms.openlocfilehash: 141308e5b0c4ba309fd2bee93cc155394a45e0f8b2bf0a5aba823e7988867820
ms.sourcegitcommit: 49f8ffe5d8e08ba3d22e3b2e76db0e54dd55d4f0
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/11/2021
ms.locfileid: "132417724"
---
# New-AzureStorageKey

## SYNOPSIS
Meregenerasi kunci penyimpanan untuk akun penyimpanan Azure.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
New-AzureStorageKey [-KeyType] <String> [-StorageAccountName] <String> [-Profile <AzureSMProfile>]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzureStorageKey** meregenerasi kunci primer atau sekunder untuk Azure Storage mereka.
Fungsi ini mengembalikan objek yang berisi nama akun penyimpanan, kunci primer, dan kunci sekunder sebagai properti.

## EXAMPLES

### Contoh 1: Regenerasi kunci penyimpanan utama
```
PS C:\> New-AzureStorageKey -KeyType "Primary" -StorageAccountName "ContosoStore01"
```

Perintah ini meregenerasi kunci penyimpanan utama untuk akun penyimpanan ContosoStore01.

### Contoh 2: Meregenerasi kunci penyimpanan sekunder dan menyimpannya dalam variabel
```
PS C:\> $ContosoStoreKey = New-AzureStorageKey -KeyType "Secondary" -StorageAccountName "ContosoStore01"
```

Perintah ini meregenerasi kunci penyimpanan sekunder untuk akun penyimpanan ContosoStore01 dan menyimpan informasi kunci akun penyimpanan yang diperbarui di $ContosoStoreKey.

## PARAMETERS

### -InformationAction
Menentukan bagaimana cmdlet merespons kejadian informasi.

Nilai yang dapat diterima untuk parameter ini adalah:

- Lanjutkan
- Abaikan
- Pemeriksaan
- SilentlyContinue
- Stop
- Tangguhkan

```yaml
Type: ActionPreference
Parameter Sets: (All)
Aliases: infa

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InformationVariable
Menentukan variabel informasi.

```yaml
Type: String
Parameter Sets: (All)
Aliases: iv

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -KeyType
Menentukan kunci mana yang harus digenerasi.
Nilai valid adalah: Utama dan Sekunder.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
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

### -StorageAccountName
Menentukan nama akun Azure Storage untuk meregenerasi kunci.

```yaml
Type: String
Parameter Sets: (All)
Aliases: ServiceName

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

## OUTPUTS

### StorageServiceKeys

## CATATAN

## RELATED LINKS

[Get-AzureStorageKey](./Get-AzureStorageKey.md)


