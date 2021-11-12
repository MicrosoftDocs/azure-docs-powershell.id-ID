---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
ms.assetid: 73CEA6A8-46C9-4772-9A67-03F532696CFD
online version: ''
schema: 2.0.0
ms.openlocfilehash: ddf9948c20f439b3129b7352be2cf975225ae717e93e14a8b1c5d27ea14e8245
ms.sourcegitcommit: 49f8ffe5d8e08ba3d22e3b2e76db0e54dd55d4f0
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/11/2021
ms.locfileid: "132419306"
---
# Get-AzureSubnet

## SYNOPSIS
Mendapatkan daftar subnet yang terkait dengan komputer virtual Azure yang ditentukan.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Get-AzureSubnet -VM <IPersistentVM> [-Profile <AzureSMProfile>] [-InformationAction <ActionPreference>]
 [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureSubnet** mengembalikan daftar subnet yang terkait dengan mesin virtual yang ditentukan.
Gunakan **Get-AzureVM** untuk menentukan mesin virtual.

## EXAMPLES

### Contoh 1: Mendapatkan subnet untuk mesin virtual
```
PS C:\> $VM = Get-AzureVM -ServiceName "ContosoService03" -Name "VirtualMachine01"
C:\PS> Get-AzureSubnet -VM $VM
```

Perintah pertama mendapatkan mesin virtual bernama VirtualMachine01 di layanan yang bernama ContosoService03, lalu menyimpannya di $VM lain.

Perintah kedua mendapatkan subnet Azure untuk komputer virtual pada $VM.

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

### -VM
Menentukan objek mesin virtual untuk mendapatkan daftar subnet.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

## OUTPUTS

## CATATAN

## RELATED LINKS

[Get-AzureVM](./Get-AzureVM.md)

[Set-AzureSubnet](./Set-AzureSubnet.md)


