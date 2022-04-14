---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
ms.assetid: 1E1F98E9-FC45-4BEF-90F6-A21D7DB7C82F
online version: ''
schema: 2.0.0
ms.openlocfilehash: be85efdd47a8f52e09697d762ce52fcd2f85edf2
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142381895"
---
# Remove-AzureVMImageOSDiskConfig

## SYNOPSIS
Menghapus konfigurasi disk sistem operasi dari objek DiskConfigSet.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Remove-AzureVMImageOSDiskConfig [-DiskConfig] <VirtualMachineImageDiskConfigSet>
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Remove-AzureVMImageOSDiskConfig** menghapus konfigurasi disk sistem operasi dari objek DiskConfigSet.

## EXAMPLES

### Contoh 1: Hapus konfigurasi disk sistem operasi dari DiskConfigSet
```
PS C:\> $Disk = New-AzureDiskConfigSet
PS C:\> $Disk = Set-AzureOSDiskConfig -DiskConfig $Disk -HostCaching ReadWrite
PS C:\> Remove-AzureVMImageOSDiskConfig -DiskConfig $Disk
```

Perintah ini menghapus konfigurasi disk sistem operasi dari objek DiskConfigSet

## PARAMETERS

### -DiskConfig
Menentukan objek konfigurasi disk yang merangkum disk sistem operasi dan objek Disk Data.

```yaml
Type: VirtualMachineImageDiskConfigSet
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.WindowsAzure.Commands.ServiceManagement.Model.VirtualMachineImageDiskConfigSet

## CATATAN

## RELATED LINKS

[Set-AzureVMImageOSDiskConfig](./Set-AzureVMImageOSDiskConfig.md)


