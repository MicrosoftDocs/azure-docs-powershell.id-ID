---
external help file: Microsoft.WindowsAzure.Commands.dll-Help.xml
ms.assetid: 61CF7F95-F0BB-4282-A971-537CB73708B1
online version: ''
schema: 2.0.0
ms.openlocfilehash: 22a5b201288a396f8ffbfbed97975aaf062db026
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132421570"
---
# Get-AzureStoreAddOn

## SYNOPSIS
Dapatkan add-on Azure Store yang tersedia.

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
Topik ini menguraikan cmdlet dalam modul Microsoft Azure PowerShell versi 0.8.10.
Untuk mendapatkan versi modul yang Anda gunakan, di konsol Azure PowerShell, ketik `(Get-Module -Name Azure).Version` .

Mendapatkan semua add-on yang tersedia untuk pembelian dari Azure Store, atau mendapatkan contoh add-on yang ada untuk langganan saat ini.

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

Contoh ini mendapatkan semua add-on yang tersedia untuk pembelian di Amerika Serikat dari Bursa Azure.

### Contoh 3
```
PS C:\> Get-AzureStoreAddOn -Name MyAddOn
```

Contoh ini mendapatkan add-on bernama MyAddOn dari contoh add-on yang dibeli dalam langganan saat ini.

## PARAMETERS

### -Negara
Jika ditentukan, hanya mengembalikan instans add-on Azure Store yang tersedia di negara tertentu.
Defaultnya adalah "AS".

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
Jika ditentukan, akan tersedia add-on untuk pembelian dari Bursa Azure.

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

## OUTPUTS

## CATATAN

## RELATED LINKS

[New-AzureStoreAddOn](./New-AzureStoreAddOn.md)

[Remove-AzureStoreAddOn](./Remove-AzureStoreAddOn.md)

[Set-AzureStoreAddOn](./Set-AzureStoreAddOn.md)


