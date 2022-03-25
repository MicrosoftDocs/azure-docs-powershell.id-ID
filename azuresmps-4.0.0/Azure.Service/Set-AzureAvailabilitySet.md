---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
ms.assetid: E0590AD4-F67B-48EF-8657-8890A2204CB6
online version: ''
schema: 2.0.0
ms.openlocfilehash: 798cb5759c8fcf091b0691f0d5b38530a840752a
ms.sourcegitcommit: d28d7d5f6278862d833182868a9dcde2c31e657b
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/24/2022
ms.locfileid: "132414757"
---
# Set-AzureAvailabilitySet

## SYNOPSIS
Mengatur nama ketersediaan di komputer virtual Azure.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Set-AzureAvailabilitySet [-AvailabilitySetName] <String> -VM <IPersistentVM> [-Profile <AzureSMProfile>]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzureAvailabilitySet** mengatur nama ketersediaan yang disiapkan di komputer virtual Azure setelah penyebaran.

## EXAMPLES

### Contoh 1: Mengubah nama kumpulan ketersediaan
```
PS C:\> Get-AzureVM -ServiceName "ContosoService" -Name "VirtualMachine24" | Set-AzureAvailabilitySet -AvailabilitySetName "AvailabilitySet14" | Update-AzureVM
```

Perintah pertama mendapatkan mesin virtual bernama VirtualMachine07 dalam layanan yang bernama ContosoService menggunakan cmdlet **Get-AzureVM** .
Perintah melewati objek itu ke cmdlet saat ini dengan menggunakan operator pipeline.
Cmdlet tersebut mengubah nama ketersediaan yang ditetapkan untuk mesin virtual tersebut.
Perintah memperbarui mesin virtual.

## PARAMETERS

### -AvailabilitySetName
Menentukan nama ketersediaan tempat mesin virtual tersebut berada.

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
Menentukan konfigurasi mesin virtual yang dimodifikasi cmdlet ini.

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

[Get-AzureVM](./Get-AzureVM.md)

[Remove-AzureAvailabilitySet](./Remove-AzureAvailabilitySet.md)


