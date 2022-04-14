---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
ms.assetid: 8A269A53-8FB2-4D4E-8FBB-A84BE658F75F
online version: ''
schema: 2.0.0
ms.openlocfilehash: ab8099e1707a41712e5d5f0546dad7337d2e3083
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141772754"
---
# Get-AzureOSDisk

## SYNOPSIS
Mendapatkan disk sistem operasi mesin virtual Azure.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Get-AzureOSDisk -VM <IPersistentVM> [-Profile <AzureSMProfile>] [-InformationAction <ActionPreference>]
 [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureOSDisk** mendapatkan disk sistem operasi mesin virtual Azure.

## EXAMPLES

### Contoh 1: Dapatkan disk sistem operasi
```
PS C:\> Get-AzureVM -ServiceName "ContosoService" -Name "VirtualMachine02" | Get-AzureOSDisk
```

Perintah ini mendapatkan mesin virtual bernama VirtualMachine02 dalam layanan bernama ContosoService dengan menggunakan cmdlet **Get-AzureVM** .
Perintah melewati mesin virtual ke cmdlet saat ini menggunakan operator pipeline.
Cmdlet saat ini mendapatkan disk sistem operasi dari mesin virtual itu.

## PARAMETERS

### -InformationAction
Menentukan bagaimana cmdlet ini merespons kejadian informasi.

Nilai yang dapat diterima untuk parameter ini adalah:

- Lanjutkan
- Mengabaikan
- Menanyakan
- DiamKontinue
- Stop
- Menangguhkan

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

### -VM
Menentukan mesin virtual di mana cmdlet ini mendapatkan disk sistem operasi.
Untuk mendapatkan objek mesin virtual, gunakan cmdlet **Get-AzureVM** .

```yaml
Type: IPersistentVM
Parameter Sets: (All)
Aliases: InputObject

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## CATATAN

## RELATED LINKS

[Get-AzureDataDisk](./Get-AzureDataDisk.md)

[Set-AzureOSDisk](./Set-AzureOSDisk.md)


