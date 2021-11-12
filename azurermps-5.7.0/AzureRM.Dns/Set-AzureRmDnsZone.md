---
external help file: Microsoft.Azure.Commands.Dns.dll-Help.xml
Module Name: AzureRM.Dns
ms.assetid: E37ADC54-A37B-41BF-BE94-9E4052C234BB
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.dns/set-azurermdnszone
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Dns/Commands.Dns/help/Set-AzureRmDnsZone.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Dns/Commands.Dns/help/Set-AzureRmDnsZone.md
ms.openlocfilehash: da504f6b8110335e6297d0c7efb2a1a27106e0e1
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132424305"
---
# Set-AzureRmDnsZone

## SYNOPSIS
Memperbarui properti zona DNS.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### Bidang (Default)
```
Set-AzureRmDnsZone -Name <String> -ResourceGroupName <String> [-Tag <Hashtable>]
 [-RegistrationVirtualNetworkId <System.Collections.Generic.List`1[System.String]>]
 [-ResolutionVirtualNetworkId <System.Collections.Generic.List`1[System.String]>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### FieldsObjects
```
Set-AzureRmDnsZone -Name <String> -ResourceGroupName <String> [-Tag <Hashtable>]
 [-RegistrationVirtualNetwork <System.Collections.Generic.List`1[Microsoft.Azure.Management.Internal.Network.Common.IResourceReference]>]
 [-ResolutionVirtualNetwork <System.Collections.Generic.List`1[Microsoft.Azure.Management.Internal.Network.Common.IResourceReference]>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Object
```
Set-AzureRmDnsZone -Zone <DnsZone> [-Overwrite] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzureRmDnsZone** memperbarui zona DNS tertentu di layanan DNS Azure.
Cmdlet ini tidak memperbarui kumpulan data dalam zona.

Anda dapat melewati **objek DnsZone** sebagai parameter atau dengan menggunakan operator saluran, atau Anda juga dapat menentukan parameter *ZoneName* *dan ResourceGroupName.*

Anda dapat menggunakan *perintah* Konfirmasi parameter $ConfirmPreference Windows PowerShell variabel untuk mengontrol apakah cmdlet meminta konfirmasi Anda.

Ketika memberikan zona DNS sebagai objek (menggunakan objek Zona atau melalui saluran), catatan itu tidak diperbarui jika telah diubah di Azure DNS sejak objek DnsZone lokal diambil. Ini menyediakan perlindungan untuk perubahan serentak. Anda dapat menyembunyikan perilaku ini dengan parameter *Timpa,* yang memperbarui zona terlepas dari perubahan serentak.

## EXAMPLES

### Contoh 1: Memperbarui zona DNS
```
PS C:\>$Zone = Get-AzureRmDnsZone -Name "myzone.com" -ResourceGroupName "MyResourceGroup"
PS C:\> $Zone.Tags = @(@{"Name"="Dept"; "Value"="Electrical"})
PS C:\> Set-AzureRmDnsZone -Zone $Zone
```

Perintah pertama mendapatkan zona bernama myzone.com grup sumber daya yang ditentukan, lalu menyimpannya dalam $Zone sumber daya.

Perintah kedua memperbarui tag untuk $Zone.

Perintah akhir akan melakukan perubahan.

### Contoh 2: Memperbarui tag untuk zona
```
PS C:\>Set-AzureRmDNSZone -ResourceGroupName "MyResourceGroup" -Name "myzone.com" -Tag @(@{"Name"="Dept"; "Value"="Electrical"})
```

Perintah ini memperbarui tag untuk zona bernama myzone.com tanpa terlebih dahulu mendapatkan zona secara eksplisit.

### Contoh 3: Mengaitkan zona privat dengan jaringan virtual dengan menentukan ID-nya
```
PS C:\>$vnet = Get-AzureRmVirualNetwork -ResourceGroupName "MyResourceGroup" -Name "myvnet"
PS C:\>Set-AzureRmDNSZone -ResourceGroupName "MyResourceGroup" -Name "myprivatezone.com" -RegistrationVirtualNetworkId @($vnet.Id)
```

Perintah ini mengaitkan zona DNS privat myprivatezone.com dengan myvnet jaringan virtual sebagai jaringan pendaftaran dengan menentukan ID-nya.

### Contoh 4: Mengaitkan zona privat dengan jaringan virtual dengan menentukan objek jaringan.
```
PS C:\>$vnet = Get-AzureRmVirualNetwork -ResourceGroupName "MyResourceGroup" -Name "myvnet"
PS C:\>Set-AzureRmDNSZone -ResourceGroupName "MyResourceGroup" -Name "myprivatezone.com" -RegistrationVirtualNetwork @($vnet)
```

Perintah ini mengaitkan zona DNS privat myprivatezone.com dengan myvnet jaringan virtual sebagai jaringan pendaftaran dengan memberikan objek jaringan virtual yang diwakili oleh $vnet tersebut ke cmdlet Set-AzureRmDnsZone.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure

```yaml
Type: IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Menentukan nama zona DNS untuk diperbarui.

```yaml
Type: String
Parameter Sets: Fields, FieldsObjects
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Overwrite
Ketika memberikan zona DNS sebagai objek (menggunakan objek Zona atau melalui saluran), catatan itu tidak diperbarui jika telah diubah di Azure DNS sejak objek DnsZone lokal diambil. Ini menyediakan perlindungan untuk perubahan serentak. Anda dapat menyembunyikan perilaku ini dengan parameter *Timpa,* yang memperbarui zona terlepas dari perubahan serentak.

```yaml
Type: SwitchParameter
Parameter Sets: Object
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RegistrationVirtualNetwork
Daftar jaringan virtual yang akan mendaftarkan catatan nama host mesin virtual dalam zona DNS ini, hanya tersedia untuk zona privat.

```yaml
Type: System.Collections.Generic.List`1[Microsoft.Azure.Management.Internal.Network.Common.IResourceReference]
Parameter Sets: FieldsObjects
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RegistrationVirtualNetworkId
Daftar DNS jaringan virtual yang akan mendaftarkan catatan nama host mesin virtual di zona DNS ini, hanya tersedia untuk zona privat.

```yaml
Type: System.Collections.Generic.List`1[System.String]
Parameter Sets: Fields
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResolutionVirtualNetwork
Daftar jaringan virtual yang bisa memecahkan catatan dalam zona DNS ini, hanya tersedia untuk zona privat.

```yaml
Type: System.Collections.Generic.List`1[Microsoft.Azure.Management.Internal.Network.Common.IResourceReference]
Parameter Sets: FieldsObjects
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResolutionVirtualNetworkId
Daftar ID jaringan virtual yang bisa mengatasi catatan di zona DNS ini, hanya tersedia untuk zona privat.

```yaml
Type: System.Collections.Generic.List`1[System.String]
Parameter Sets: Fields
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Menentukan nama grup sumber daya yang berisi zona untuk diperbarui.
Anda juga harus menentukan parameter ZoneName.

Alternatifnya, Anda dapat menentukan zona menggunakan objek DnsZone dengan *parameter Zona* atau saluran.

```yaml
Type: String
Parameter Sets: Fields, FieldsObjects
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Tag
Pasangan nilai kunci dalam bentuk tabel hash. Misalnya:

@{key0="value0";key1=$null;key2="value2"}

```yaml
Type: Hashtable
Parameter Sets: Fields, FieldsObjects
Aliases: Tags

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Zone
Menentukan zona DNS yang akan diperbarui.

Alternatifnya, Anda bisa menentukan zona menggunakan parameter *ZoneName* *dan ResourceGroupName.*

```yaml
Type: DnsZone
Parameter Sets: Object
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Konfirmasi
Meminta konfirmasi Anda sebelum menjalankan cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan. Cmdlet tidak berjalan. Memperlihatkan apa yang akan terjadi jika cmdlet berjalan. Cmdlet tidak berjalan.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### Microsoft.Azure.Commands.Dns.DnsZone
Anda dapat pipa objek DnsZone ke cmdlet ini.

## OUTPUTS

### Microsoft.Azure.Commands.Dns.DnsZone
Cmdlet ini mengembalikan objek DnsZone yang mewakili zona DNS yang diperbarui dengan Etag baru.

## CATATAN
Anda dapat menggunakan parameter *Konfirmasi* untuk mengontrol apakah cmdlet ini meminta konfirmasi.
Secara default, cmdlet meminta konfirmasi Anda jika variabel $ConfirmPreference Windows PowerShell memiliki nilai Sedang atau lebih rendah.

Jika Anda menentukan *Konfirmasi* *atau Konfirmasi:$True*, cmdlet ini akan meminta konfirmasi sebelum dijalankan.
Jika Anda menentukan *Confirm:$False*, cmdlet tidak akan meminta konfirmasi Anda.

## RELATED LINKS

[Get-AzureRmDnsZone](./Get-AzureRmDnsZone.md)

[New-AzureRmDnsZone](./New-AzureRmDnsZone.md)

[Remove-AzureRmDnsZone](./Remove-AzureRmDnsZone.md)
