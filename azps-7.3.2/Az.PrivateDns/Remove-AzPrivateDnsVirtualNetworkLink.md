---
external help file: Microsoft.Azure.PowerShell.Cmdlets.PrivateDns.dll-Help.xml
Module Name: Az.PrivateDns
ms.assetid: A8E230A0-5057-40BC-81CD-6D397A503A84
online version: https://docs.microsoft.com/powershell/module/az.privatedns/remove-azprivatednsvirtualnetworklink
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/PrivateDns/PrivateDns/help/Remove-AzPrivateDnsVirtualNetworkLink.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/PrivateDns/PrivateDns/help/Remove-AzPrivateDnsVirtualNetworkLink.md
ms.openlocfilehash: a7611df5907564d68475b3fdea069d3ad238883e
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142485125"
---
# Remove-AzPrivateDnsVirtualNetworkLink

## SYNOPSIS
Menghapus tautan jaringan virtual dari grup sumber daya.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.privatedns/remove-azprivatednsvirtualnetworklink) untuk informasi terbaru.

## SYNTAX

### Bidang (Default)
```
Remove-AzPrivateDnsVirtualNetworkLink -ResourceGroupName <String> -ZoneName <String> -Name <String> [-PassThru]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Objek
```
Remove-AzPrivateDnsVirtualNetworkLink -InputObject <PSPrivateDnsVirtualNetworkLink> [-Overwrite] [-PassThru]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ResourceId
```
Remove-AzPrivateDnsVirtualNetworkLink -ResourceId <String> [-PassThru]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Remove-AzPrivateDnsVirtualNetworkLink** menghapus tautan Domain Name System (DNS) pribadi secara permanen dari grup sumber daya tertentu.
Anda dapat melewati objek **PSPrivateDnsVirtualNetworkLink** menggunakan parameter *Link* atau menggunakan operator pipeline, atau menentukan parameter *Name* *ZoneName* dan *ResourceGroupName* .
Anda dapat menggunakan variabel Konfirmasi parameter dan $ConfirmPreference Windows PowerShell untuk mengontrol apakah cmdlet meminta konfirmasi.
Saat menentukan tautan menggunakan objek **PSPrivateDnsVirtualNetworkLink** (dilewatkan melalui pipeline atau parameter *Link* ), tautan tidak dihapus jika telah diubah dalam DNS Pribadi Azure sejak objek **PSPrivateDnsVirtualNetworkLink** lokal diambil. Ini menyediakan perlindungan untuk perubahan zona serentak. Ini dapat ditekan menggunakan parameter *Timpa* , yang menghapus zona terlepas dari perubahan bersamaan.

## EXAMPLES

### Contoh 1: Menghapus tautan
```
PS C:\>Remove-AzPrivateDnsVirtualNetworkLink -ResourceGroupName "MyResourceGroup" -ZoneName "myzone.com" -Name "mylink"
```

Perintah ini menghapus tautan bernama mylink yang ditautkan ke zona myzone.com dari grup sumber daya bernama MyResourceGroup.

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

### -InputObject
Objek tautan jaringan virtual untuk dihapus.

```yaml
Type: Microsoft.Azure.Commands.PrivateDns.Models.PSPrivateDnsVirtualNetworkLink
Parameter Sets: Object
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Nama
Menentukan nama tautan yang akan dihapus.
Anda juga harus menentukan parameter *ResourceGroupName* dan *ZoneName* .
Atau, Anda dapat menentukan tautan menggunakan parameter *Tautan* .

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
Saat menentukan zona menggunakan objek **PSPrivateDnsVirtualNetworkLink** (yang dilewatkan melalui parameter pipeline atau *Link* ), zona tidak dihapus jika telah diubah di Azure DNS sejak objek **PSPrivateDnsVirtualNetworkLink** lokal diambil.
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
Digunakan untuk melewati hasil (boolean) operasi hapus tautan jaringan virtual lebih jauh ke bawah pipeline.

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

### -ResourceGroupName
Menentukan nama grup sumber daya yang berisi tautan untuk dihapus.
Anda juga harus menentukan parameter *ZoneName* dan *Name* .
Alternatifnya, Anda dapat menentukan zona DNS menggunakan objek **PSPrivateDnsVirtualNetworkLink** , yang dilewati melalui pipeline atau parameter *Link* .

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
Menentukan ID sumber daya ARM dari tautan.

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

### -ZoneName
Menentukan nama zona DNS privat yang dikaitkan dengan link.
Anda juga harus menentukan parameter *ResourceGroupName* dan *Name* .
Atau, Anda dapat menentukan tautan menggunakan parameter *Tautan* .

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

### Microsoft.Azure.Commands.PrivateDns.Models.PSPrivateDnsVirtualNetworkLink

### System.String

## OUTPUTS

### System.Boolean

## CATATAN

## RELATED LINKS

[Get-AzPrivateDnsVirtualNetworkLink](./Get-AzPrivateDnsVirtualNetworkLink.md)

[New-AzPrivateDnsVirtualNetworkLink](./New-AzPrivateDnsVirtualNetworkLink.md)

[Set-AzPrivateDnsVirtualNetworkLink](./Set-AzPrivateDnsVirtualNetworkLink.md)
