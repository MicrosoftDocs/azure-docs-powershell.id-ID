---
external help file: Microsoft.Azure.PowerShell.Cmdlets.PrivateDns.dll-Help.xml
Module Name: Az.PrivateDns
online version: https://docs.microsoft.com/powershell/module/az.privatedns/remove-azprivatednszone
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/PrivateDns/PrivateDns/help/Remove-AzPrivateDnsZone.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/PrivateDns/PrivateDns/help/Remove-AzPrivateDnsZone.md
ms.openlocfilehash: 8d4caac0151e6120d90b4096629124ab0cf443f5
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140099765"
---
# Remove-AzPrivateDnsZone

## SYNOPSIS
Menghapus zona DNS privat dari grup sumber daya.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan [lihat versi terbaru](/powershell/module/az.privatedns/remove-azprivatednszone) untuk informasi terkini.

## SYNTAX

### Bidang (Default)
```
Remove-AzPrivateDnsZone -ResourceGroupName <String> -Name <String> [-PassThru]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Object
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
Cmdlet **Remove-AzPrivateDnsZone** secara permanen menghapus zona Domain Name System (DNS) pribadi dari grup sumber daya yang ditentukan.
Semua kumpulan catatan yang dimuat dalam zona juga dihapus.
Anda dapat melewati **objek PrivateDnsZone** menggunakan parameter *PrivateZone* atau menggunakan operator pipeline, atau menentukan parameter *Name* dan *ResourceGroupName* .
Anda bisa menggunakan parameter Konfirmasi dan $ConfirmPreference Windows PowerShell kontrol apakah cmdlet meminta konfirmasi Anda.
Ketika menentukan zona menggunakan objek **PrivateDnsZone** (disampaikan *melalui saluran atau* parameter Zona), zona tidak akan dihapus jika telah diubah dalam DNS Azure karena objek **PrivateDnsZone** lokal diambil (hanya operasi yang langsung tersedia pada jumlah sumber daya zona DNS sebagai perubahan, operasi pada kumpulan rekaman dalam zona tidak akan digunakan).
Hal ini menyediakan perlindungan untuk perubahan zona serentak.
Hal ini dapat menyembunyikan penggunaan parameter *Overwrite* , yang menghapus zona terlepas dari perubahan konklarasi.

## EXAMPLES

### Contoh 1: Hapus zona privat
```
PS C:\>Remove-AzPrivateDnsZone -Name "myzone.com" -ResourceGroupName "MyResourceGroup"
```

Perintah ini menghapus zona yang bernama myzone.com grup sumber daya yang bernama MyResourceGroup.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure

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
Alternatifnya, Anda dapat menentukan zona DNS menggunakan parameter *Zone* .

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

### -Overwrite
Ketika menentukan zona menggunakan objek **PrivateDnsZone** (disampaikan *melalui saluran atau* parameter Zona), zona tidak akan dihapus jika telah diubah dalam DNS Azure karena objek **PrivateDnsZone** lokal diambil (hanya operasi yang langsung tersedia pada jumlah sumber daya zona DNS sebagai perubahan, operasi pada kumpulan rekaman dalam zona tidak akan digunakan).
Hal ini menyediakan perlindungan untuk perubahan zona serentak.
Hal ini dapat menyembunyikan penggunaan parameter *Overwrite* , yang menghapus zona terlepas dari perubahan konklarasi.

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
Digunakan untuk memberikan hasil (boolean) dari operasi menghapus zona privat lebih jauh ke bawah saluran.

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
Objek zona privat yang akan dihapus.

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
Menentukan nama grup sumber daya yang berisi zona yang akan dihapus.
Anda juga harus menentukan parameter *ZoneName* .
Alternatifnya, Anda dapat menentukan zona DNS menggunakan objek **PrivateDnsZone** , yang dikirim melalui saluran atau *parameter Zone* .

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
Private DNS Zone ResourceID.

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
Meminta konfirmasi Anda sebelum menjalankan cmdlet.

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
Cmdlet tidak berjalan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

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
