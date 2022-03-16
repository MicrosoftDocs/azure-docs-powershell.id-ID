---
external help file: Azs.AzureBridge.Admin-help.xml
Module Name: Azs.AzureBridge.Admin
online version: ''
schema: 2.0.0
ms.openlocfilehash: 83d47f93addf05af19b523db6ba454443af2c34f
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "132414385"
---
# Get-AzsAzureBridgeActivation

## SYNOPSIS
Mengembalikan Azure Bridge Activation.

## SYNTAX

### Daftar (Default)
```
Get-AzsAzureBridgeActivation -ResourceGroupName <String> [-Skip <Int32>] [-Top <Int32>] [<CommonParameters>]
```

### Dapatkan
```
Get-AzsAzureBridgeActivation -Name <String> -ResourceGroupName <String> [<CommonParameters>]
```

### ResourceId
```
Get-AzsAzureBridgeActivation -ResourceId <String> [<CommonParameters>]
```

## DESCRIPTION
Setelah Azure Stack didaftarkan, objek aktivasi berisi informasi yang menautkan penyebaran Azure Stack ke pendaftarannya di Azure, misalnya, tanggal kedaluwarsa pendaftaran, nama, dll.

## EXAMPLES

### -------------------------- CONTOH 1 --------------------------
```
Get-AzsAzureBridgeActivation -ResourceGroupName 'activationRG'
```

Dapatkan daftar Aktivasi Azure Bridge di bawah grup sumber daya "activationRG"

### -------------------------- CONTOH 2 --------------------------
```
Get-AzsAzureBridgeActivation -Name 'myActivation' -ResourceGroupName 'activationRG'
```

Dapatkan Aktivasi Bridge Azure dengan nama 'myActivation' terletak di bawah 'activationRG'

## PARAMETERS

### -Nama
Nama aktivasi.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: Get
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Grup Sumber Daya yang digunakan selama pendaftaran Tumpukan Azure; Anda juga bisa menampilkan nama Grup Sumber Daya di portal.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: List, Get
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceId
Id sumber daya.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: ResourceId
Aliases: id

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Lewati
Lewati item N pertama seperti yang ditentukan oleh nilai parameter.

```yaml
Type: Int32
Parameter Sets: List
Aliases: 

Required: False
Position: Named
Default value: -1
Accept pipeline input: False
Accept wildcard characters: False
```

### -Top
Mengembalikan item N teratas seperti yang ditentukan oleh nilai parameter.
Berlaku setelah parameter -Skip.

```yaml
Type: Int32
Parameter Sets: List
Aliases: 

Required: False
Position: Named
Default value: -1
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.AzureStack.Management.AzureBridge.Admin.Models.ActivationResource

## CATATAN

## RELATED LINKS

