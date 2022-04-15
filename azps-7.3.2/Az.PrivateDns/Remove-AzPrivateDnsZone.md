---
external help file: Microsoft.Azure.PowerShell.Cmdlets.PrivateDns.dll-Help.xml
Module Name: Az.PrivateDns
online version: https://docs.microsoft.com/powershell/module/az.privatedns/remove-azprivatednszone
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/PrivateDns/PrivateDns/help/Remove-AzPrivateDnsZone.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/PrivateDns/PrivateDns/help/Remove-AzPrivateDnsZone.md
ms.openlocfilehash: 8d4caac0151e6120d90b4096629124ab0cf443f5
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142343213"
---
# Remove-AzPrivateDnsZone

## SYNOPSIS
Menghapus zona DNS pribadi dari grup sumber daya.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.privatedns/remove-azprivatednszone) untuk informasi terbaru.

## SYNTAX

### Bidang (Default)
```
Remove-AzPrivateDnsZone -ResourceGroupName <String> -Name <String> [-PassThru]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Objek
```
Remove-AzPrivateDnsZone -PrivateZone <PSPrivateDnsZone> [-Overwrite] [-PassThru]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ResourceId
```
Remove-AzPrivateDnsZone -ResourceId <String> [-PassThru] [-DefaultProfile <IAzureContextContainer>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Remove-AzPrivateDnsZone** menghapus zona Domain Name System (DNS) pribadi secara permanen dari grup sumber daya tertentu.
Semua kumpulan rekaman yang terdapat dalam zona juga dihapus.
Anda dapat melewati objek **PrivateDnsZone** menggunakan parameter *PrivateZone* atau menggunakan operator pipeline, atau anda dapat menentukan parameter *Name* and *ResourceGroupName* .
Anda dapat menggunakan variabel Konfirmasi parameter dan $ConfirmPreference Windows PowerShell untuk mengontrol apakah cmdlet meminta konfirmasi.
Saat menentukan zona menggunakan objek **PrivateDnsZone** (yang dilewati melalui pipeline atau parameter *Zona* ), zona tidak dihapus jika telah diubah di Azure DNS karena objek **PrivateDnsZone** lokal diambil (hanya operasi langsung pada jumlah sumber daya zona DNS sebagai perubahan, operasi pada kumpulan catatan di dalam zona tidak).
Ini menyediakan perlindungan untuk perubahan zona serentak.
Ini dapat ditekan menggunakan parameter *Timpa* , yang menghapus zona terlepas dari perubahan bersamaan.

## EXAMPLES

### Contoh 1: Menghapus zona privat
```
PS C:\>Remove-AzPrivateDnsZone -Name "myzone.com" -ResourceGroupName "MyResourceGroup"
```

Perintah ini menghapus zona bernama myzone.com dari grup sumber daya bernama MyResourceGroup.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Menentukan nama zona DNS privat yang dihapus cmdlet ini.
Anda juga harus menentukan parameter *ResourceGroupName* .
Alternatifnya, Anda bisa menentukan zona DNS menggunakan parameter *Zona* .

```yaml
Type: System.String
Parameter Sets: Fields
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Timpa
Saat menentukan zona menggunakan objek **PrivateDnsZone** (yang dilewati melalui pipeline atau parameter *Zona* ), zona tidak dihapus jika telah diubah di Azure DNS karena objek **PrivateDnsZone** lokal diambil (hanya operasi langsung pada jumlah sumber daya zona DNS sebagai perubahan, operasi pada kumpulan catatan di dalam zona tidak).
Ini menyediakan perlindungan untuk perubahan zona serentak.
Ini dapat ditekan menggunakan parameter *Timpa* , yang menghapus zona terlepas dari perubahan bersamaan.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Object
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Digunakan untuk melewati hasil (boolean) operasi menghapus zona privat lebih jauh ke bawah saluran.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PrivateZone
Objek zona privat untuk dihapus.

```yaml
Type: Microsoft.Azure.Commands.PrivateDns.Models.PSPrivateDnsZone
Parameter Sets: Object
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ResourceGroupName
Menentukan nama grup sumber daya yang berisi zona untuk dihapus.
Anda juga harus menentukan parameter *ZoneName* .
Alternatifnya, Anda dapat menentukan zona DNS menggunakan objek **PrivateDnsZone** , yang dilewati melalui pipeline atau parameter *Zone* .

```yaml
Type: System.String
Parameter Sets: Fields
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceId
ID Sumber Daya Zona DNS Pribadi.

```yaml
Type: System.String
Parameter Sets: ResourceId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Konfirmasi
Meminta konfirmasi sebelum menjalankan cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan.
Cmdlet tidak dijalankan.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.PrivateDns.Models.PSPrivateDnsZone

### System.String

## OUTPUTS

### System.Boolean

## CATATAN

## RELATED LINKS

[Get-AzPrivateDnsZone](./Get-AzPrivateDnsZone.md)

[New-AzPrivateDnsZone](./New-AzPrivateDnsZone.md)

[Set-AzPrivateDnsZone](./Set-AzPrivateDnsZone.md)
