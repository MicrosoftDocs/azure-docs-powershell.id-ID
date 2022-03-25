---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
ms.assetid: A513B7CA-182E-46A2-8181-020C5DFC7DE9
online version: ''
schema: 2.0.0
ms.openlocfilehash: 758025d6f452f1578cf0c3a9bd0bb9e479002446
ms.sourcegitcommit: d28d7d5f6278862d833182868a9dcde2c31e657b
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/24/2022
ms.locfileid: "132414773"
---
# Remove-AzureVMDiagnosticsExtension

## SYNOPSIS
Menghapus ekstensi Azure Diagnostics dari komputer virtual.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Remove-AzureVMDiagnosticsExtension -VM <IPersistentVM> [-Profile <AzureSMProfile>]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Remove-AzureVMDiagnosticsExtension** menghapus Microsoft Azure Diagnostik dari komputer virtual.
Anda harus menyampaikan output cmdlet ini ke cmdlet **Update-AzureVM** .

## EXAMPLES

### Contoh 1: Hapus ekstensi Azure Diagnostics dari komputer virtual
```
PS C:\> Remove-AzureVMDiagnosticsExtension -VM $VM | Update-AzureVM
```

Perintah ini akan menghapus ekstensi Azure Diagnostics dari komputer virtual.

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
Menentukan objek mesin virtual persisten.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## CATATAN

## RELATED LINKS

[Get-AzureVMDiagnosticsExtension](./Get-AzureVMDiagnosticsExtension.md)

[Set-AzureVMDiagnosticsExtension](./Set-AzureVMDiagnosticsExtension.md)

[Update-AzureVM](./Update-AzureVM.md)


