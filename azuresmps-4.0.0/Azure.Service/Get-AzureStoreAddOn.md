---
external help file: Microsoft.WindowsAzure.Commands.dll-Help.xml
ms.assetid: 61CF7F95-F0BB-4282-A971-537CB73708B1
online version: ''
schema: 2.0.0
ms.openlocfilehash: 22a5b201288a396f8ffbfbed97975aaf062db026
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142313395"
---
# Get-AzureStoreAddOn

## SYNOPSIS
Mendapatkan add-on Azure Store yang tersedia.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

### ListAvailable
```
Get-AzureStoreAddOn [-ListAvailable] [-Country <String>] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### GetAddOn
```
Get-AzureStoreAddOn [-Name <String>] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Topik ini menjelaskan cmdlet dalam versi 0.8.10 modul Microsoft Azure PowerShell.
Untuk mendapatkan versi modul yang Anda gunakan, di konsol Azure PowerShell, ketik .`(Get-Module -Name Azure).Version`

Mendapatkan semua add-on yang tersedia untuk dibeli dari Azure Store, atau mendapatkan contoh add-on yang sudah ada untuk langganan saat ini.

## EXAMPLES

### Contoh 1
```
PS C:\> Get-AzureStoreAddOn
```

Contoh ini mendapatkan semua contoh add-on yang dibeli untuk langganan saat ini.

### Contoh 2
```
PS C:\> Get-AzureStoreAddOn -ListAvailable
```

Contoh ini mendapatkan semua add-on yang tersedia untuk dibeli di Amerika Serikat dari Azure Store.

### Contoh 3
```
PS C:\> Get-AzureStoreAddOn -Name MyAddOn
```

Contoh ini mendapatkan add-on bernama MyAddOn dari contoh add-on yang dibeli dalam langganan saat ini.

## PARAMETERS

### -Negara
Jika ditentukan, hanya mengembalikan instans add-on Azure Store yang tersedia di negara yang ditentukan.
Defaultnya adalah "US".

```yaml
Type: String
Parameter Sets: ListAvailable
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ListAvailable
Jika ditentukan, dapatkan add-on yang tersedia untuk dibeli dari Azure Store.

```yaml
Type: SwitchParameter
Parameter Sets: ListAvailable
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Nama
Mengembalikan add-on yang cocok dengan nama yang ditentukan.

```yaml
Type: String
Parameter Sets: GetAddOn
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

## CATATAN

## RELATED LINKS

[AzureStoreAddOn baru](./New-AzureStoreAddOn.md)

[Hapus-AzureStoreAddOn](./Remove-AzureStoreAddOn.md)

[Set-AzureStoreAddOn](./Set-AzureStoreAddOn.md)


