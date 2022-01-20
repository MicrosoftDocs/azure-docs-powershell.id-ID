---
external help file: Microsoft.Azure.PowerShell.Cmdlets.PrivateDns.dll-Help.xml
Module Name: Az.PrivateDns
ms.assetid: A8E230A0-5057-40BC-81CD-6D397A503A84
online version: https://docs.microsoft.com/powershell/module/az.privatedns/remove-azprivatednsvirtualnetworklink
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/PrivateDns/PrivateDns/help/Remove-AzPrivateDnsVirtualNetworkLink.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/PrivateDns/PrivateDns/help/Remove-AzPrivateDnsVirtualNetworkLink.md
ms.openlocfilehash: 0f0a56784cec62068a678baf478f0c70a23a0e74
ms.sourcegitcommit: 53ef403038f665f1b3a9f616185b31f5de9bd7bb
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/03/2021
ms.locfileid: "136378834"
---
# Remove-AzPrivateDnsVirtualNetworkLink

## SYNOPSIS
Menghapus link jaringan virtual dari grup sumber daya.

## SYNTAX

### Bidang (Default)
```
Remove-AzPrivateDnsVirtualNetworkLink -ResourceGroupName <String> -ZoneName <String> -Name <String> [-PassThru]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Object
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
Cmdlet **Remove-AzPrivateDnsVirtualNetworkLink secara** permanen menghapus link Privat Domain Name System (DNS) dari grup sumber daya yang ditentukan.
Anda bisa melewati **objek PSPrivateDnsVirtualNetworkLink** menggunakan parameter *Link* atau dengan menggunakan operator  pipeline, atau Anda juga bisa menentukan parameter *Name ZoneName* dan *ResourceGroupName.*
Anda dapat menggunakan perintah Konfirmasi parameter $ConfirmPreference Windows PowerShell variabel untuk mengontrol apakah cmdlet meminta konfirmasi Anda.
Saat menentukan link menggunakan objek **PSPrivateDnsVirtualNetworkLink** (dikirim melalui saluran atau parameter *Link),* link tersebut tidak dihapus jika telah diubah dalam DNS Privat Azure sejak **objek PSPrivateDnsVirtualNetworkLink** lokal diambil. Hal ini menyediakan perlindungan untuk perubahan zona serentak. Hal ini dapat menyembunyikan penggunaan parameter *Overwrite,* yang menghapus zona terlepas dari perubahan konklarasi.

## EXAMPLES

### Contoh 1: Menghapus tautan
```
PS C:\>Remove-AzPrivateDnsVirtualNetworkLink -ResourceGroupName "MyResourceGroup" -ZoneName "myzone.com" -Name "mylink"
```

Perintah ini menghapus link bernama mylink yang ditautkan ke zona myzone.com dari grup sumber daya yang bernama MyResourceGroup.

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

### -InputObject
Objek link jaringan virtual yang akan dihapus.

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
Menentukan nama link yang akan dihapus.
Anda juga harus menentukan parameter *ResourceGroupName* *dan ZoneName.*
Alternatifnya, Anda dapat menentukan tautan menggunakan parameter *Link.*

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
Saat menentukan zona menggunakan objek **PSPrivateDnsVirtualNetworkLink** (dikirim melalui saluran atau parameter *Link),* zona tidak dihapus jika telah diubah di DNS Azure karena objek **PSPrivateDnsVirtualNetworkLink** lokal diambil.
Hal ini menyediakan perlindungan untuk perubahan zona serentak.
Hal ini dapat menyembunyikan penggunaan parameter *Overwrite,* yang menghapus zona terlepas dari perubahan konklarasi.

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
Digunakan untuk memberikan hasil (boolean) dari operasi menghapus link jaringan virtual selanjutnya ke bawah saluran.

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
Anda juga harus menentukan parameter *ZoneName* *dan Name.*
Alternatifnya, Anda bisa menentukan zona DNS menggunakan objek **PSPrivateDnsVirtualNetworkLink,** yang dikirim melalui saluran atau parameter *Link.*

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
Menentukan nama zona DNS privat yang terkait dengan tautan.
Anda juga harus menentukan parameter *ResourceGroupName* *dan Name.*
Alternatifnya, Anda dapat menentukan tautan menggunakan parameter *Link.*

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( http://go.microsoft.com/fwlink/?LinkID=113216) .

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
