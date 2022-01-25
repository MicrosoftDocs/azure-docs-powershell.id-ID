---
external help file: Microsoft.Azure.PowerShell.Cmdlets.PrivateDns.dll-Help.xml
Module Name: Az.PrivateDns
ms.assetid: A8E230A0-5057-40BC-81CD-6D397A503A84
online version: https://docs.microsoft.com/en-us/powershell/module/az.privatedns/Set-AzPrivateDnsVirtualNetworkLink
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/PrivateDns/PrivateDns/help/Set-AzPrivateDnsVirtualNetworkLink.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/PrivateDns/PrivateDns/help/Set-AzPrivateDnsVirtualNetworkLink.md
ms.openlocfilehash: 3ffcc30dc0291be06c27ee53ee0ee7ea14f3e2c1
ms.sourcegitcommit: d81c3b0f0f7289104be03869eb675128b61db7d3
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/17/2020
ms.locfileid: "136028863"
---
# Set-AzPrivateDnsVirtualNetworkLink

## SYNOPSIS
Pembaruan/Mengatur tautan jaringan virtual yang terkait dengan zona privat dan grup sumber daya.

## SINTAKS

### Bidang (Default)
```
Set-AzPrivateDnsVirtualNetworkLink -ResourceGroupName <String> -ZoneName <String> -Name <String>
 [-IsRegistrationEnabled <Boolean>] [-Tag <Hashtable>] [-DefaultProfile <IAzureContextContainer>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### Object
```
Set-AzPrivateDnsVirtualNetworkLink -InputObject <PSPrivateDnsVirtualNetworkLink>
 [-IsRegistrationEnabled <Boolean>] [-Tag <Hashtable>] [-Overwrite] [-DefaultProfile <IAzureContextContainer>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ResourceId
```
Set-AzPrivateDnsVirtualNetworkLink -ResourceId <String> [-IsRegistrationEnabled <Boolean>] [-Tag <Hashtable>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESKRIPSI
Cmdlet **Set-AzPrivateDnsVirtualNetworkLink** memperbarui link yang terkait dengan zona dari grup sumber daya yang ditentukan.
Anda bisa melewati **objek PSPrivateDnsVirtualNetworkLink** menggunakan parameter *Link* atau dengan menggunakan operator  pipeline, atau Anda juga bisa menentukan parameter *Name ZoneName* dan *ResourceGroupName.*
Anda dapat menggunakan perintah Konfirmasi parameter $ConfirmPreference Windows PowerShell variabel untuk mengontrol apakah cmdlet meminta konfirmasi Anda.
Saat menentukan zona menggunakan objek **PSPrivateDnsVirtualNetworkLink** (dikirim melalui saluran atau parameter *Link),* link tersebut tidak diperbarui jika telah diubah di DNS Azure karena objek **PSPrivateDnsVirtualNetworkLink** lokal diambil. Ini menyediakan perlindungan untuk perubahan link bersamaan. Hal ini dapat menyembunyikan penggunaan parameter *Timpa,* yang memperbarui tautan terlepas dari perubahan serentak.

## CONTOH

### Contoh 1: Mengatur tautan
```
PS C:\>Set-AzPrivateDnsVirtualNetworkLink -ZoneName "myzone.com" -ResourceGroupName "MyResourceGroup" -Name "mylink" -Tag @{} -IsRegistrationEnabled $true

Name                    : mylink
ResourceId              : /subscriptions/xxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/resourceGroups/MyResourceGroup/providers/Microsoft.N
                          etwork/privateDnsZones/myzone.com/virtualNetworkLinks/mylink
ResourceGroupName       : MyResourceGroup
ZoneName                : myzone.com
VirtualNetworkId        : /subscriptions/xxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/resourceGroups/MyResourceGroup/providers/Microsoft.N
                          etwork/virtualNetworks/myvirtualnetwork
Location                :
Etag                    : "xxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx"
Tags                    : {}
RegistrationEnabled     : True
VirtualNetworkLinkState : Completed
ProvisioningState       : Succeeded
```

Kumpulan perintah ini IsRegistrationEnabled ke True untuk tautan bernama mylink, yang ditautkan ke zona myzone.com dari grup sumber daya bernama MyResourceGroup.

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
Objek link jaringan virtual yang akan diatur.

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

### -IsRegistrationEnabled
Boolean yang menyatakan jika pendaftaran diaktifkan pada link jaringan virtual.

```yaml
Type: System.Nullable`1[System.Boolean]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Menentukan nama tautan yang dihapus cmdlet ini.
Anda juga harus menentukan parameter *ResourceGroupName* *dan ZoneName.*
Alternatifnya, Anda bisa menentukan link DNS privat menggunakan parameter *link.*

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
Saat menentukan link menggunakan objek **PSPrivateDnsVirtualNetworkLink** (dikirim melalui saluran atau parameter *Link),* link tersebut tidak dihapus jika telah diubah di DNS Azure karena objek **PSPrivateDnsVirtualNetworkLink** lokal diambil.
Ini menyediakan perlindungan untuk perubahan link bersamaan.
Hal ini dapat dilihat menggunakan parameter *Timpa,* yang menghapus tautan terlepas dari perubahan serentak.

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

### -ResourceGroupName
Menentukan nama grup sumber daya yang berisi tautan untuk dihapus.
Anda juga harus menentukan parameter *ZoneName* *dan Name.*
Alternatifnya, Anda bisa menentukan link jaringan virtual menggunakan objek **PSPrivateDnsVirtualNetworkLink,** yang dikirim melalui saluran *atau* parameter Link.

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

### -Tag
Tabel hash yang mewakili tag sumber daya.

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ZoneName
Menentukan nama zona DNS yang dihapus cmdlet ini.
Anda juga harus menentukan *parameter Name* *dan ResourceGroupName.*
Alternatifnya, Anda bisa menentukan link DNS privat menggunakan parameter *link.*

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

## INPUT

### Microsoft.Azure.Commands.PrivateDns.Models.PSPrivateDnsVirtualNetworkLink

### System.String

## OUTPUT

### Microsoft.Azure.Commands.PrivateDns.Models.PSPrivateDnsVirtualNetworkLink

## CATATAN

## LINK TERKAIT

[Get-AzPrivateDnsVirtualNetworkLink](./Get-AzPrivateDnsVirtualNetworkLink.md)

[New-AzPrivateDnsVirtualNetworkLink](./New-AzPrivateDnsVirtualNetworkLink.md)

[Set-AzPrivateDnsVirtualNetworkLink](./Set-AzPrivateDnsVirtualNetworkLink.md)
