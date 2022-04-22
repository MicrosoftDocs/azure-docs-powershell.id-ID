---
external help file: Microsoft.WindowsAzure.Commands.dll-Help.xml
ms.assetid: 7190C668-6A0C-4E1D-9B5A-0CEEF53E3F85
online version: ''
schema: 2.0.0
ms.openlocfilehash: baa781938cfb3d0a89f38cb1a727f329bb295c79
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142982045"
---
# Add-AzureNodeWorkerRole

## SYNOPSIS
Membuat file dan folder yang diperlukan agar aplikasi Node.js dapat dihosting di awan melalui node.exe

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Add-AzureNodeWorkerRole [-Name <String>] [-Instances <Int32>] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Topik ini menjelaskan cmdlet dalam versi 0.8.10 modul Microsoft Azure PowerShell.
Untuk mendapatkan versi modul yang Anda gunakan, di konsol Azure PowerShell, ketik .`(Get-Module -Name Azure).Version`

Cmdlet **Add-AzureNodeWorkerRole** membuat file dan folder yang diperlukan, terkadang disebut sebagai perancah, agar aplikasi Node.js dihosting di awan melalui node.exe.

## EXAMPLES

### Contoh 1: Peran pekerja instans tunggal
```
PS C:\> Add-AzureWorkerRole MyWorkerRole
```

Contoh ini menambahkan perancah untuk peran pekerja tunggal bernama **MyWorkerRole** ke aplikasi saat ini.

### Contoh 2: Peran beberapa contoh pekerja
```
PS C:\> Add-AzureNodeWorkerRole MyWorkerRole -I 2
```

Contoh ini menambahkan perancah untuk peran pekerja tunggal bernama **MyWorkerRole** ke aplikasi saat ini, dengan jumlah contoh peran 2.

## PARAMETERS

### -Instances
Menentukan jumlah contoh peran untuk peran pekerja ini.
Defaultnya adalah 1.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: i

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Menentukan nama peran pekerja.
Nilai menentukan nama folder yang berisi perancah untuk layanan node.js yang dihosting dalam peran pekerja.
Defaultnya adalah WorkerRole1.

```yaml
Type: String
Parameter Sets: (All)
Aliases: n

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Add-AzureNodeWebRole](./Add-AzureNodeWebRole.md)

[New-AzureServiceProject](./New-AzureServiceProject.md)


