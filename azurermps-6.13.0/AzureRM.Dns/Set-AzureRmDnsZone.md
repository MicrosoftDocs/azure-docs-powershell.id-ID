---
external help file: Microsoft.Azure.Commands.Dns.dll-Help.xml
Module Name: AzureRM.Dns
ms.assetid: E37ADC54-A37B-41BF-BE94-9E4052C234BB
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.dns/set-azurermdnszone
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Dns/Commands.Dns/help/Set-AzureRmDnsZone.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Dns/Commands.Dns/help/Set-AzureRmDnsZone.md
ms.openlocfilehash: 67997145a327d7f9e47f4cf346cbfd5e3a6bf0f7
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142141634"
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

### Objek
```
Set-AzureRmDnsZone -Zone <DnsZone> [-Overwrite] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzureRmDnsZone** memperbarui zona DNS tertentu di layanan DNS Azure.
Cmdlet ini tidak memperbarui kumpulan catatan dalam zona.
Anda bisa melewati objek **DnsZone** sebagai parameter atau dengan menggunakan operator pipeline, atau anda bisa menentukan parameter *ZoneName* dan *ResourceGroupName* .
Anda dapat menggunakan variabel *Konfirmasi* parameter dan $ConfirmPreference Windows PowerShell untuk mengontrol apakah cmdlet meminta konfirmasi.
Saat melewati zona DNS sebagai objek (menggunakan objek Zona atau melalui pipeline), zona DNS tidak diperbarui jika telah diubah di AZURE DNS sejak objek DnsZone lokal diambil. Ini memberikan perlindungan untuk perubahan serentak. Anda dapat menyembunyikan perilaku ini dengan parameter *Timpa* , yang memperbarui zona terlepas dari perubahan bersamaan.

## EXAMPLES

### Contoh 1: Memperbarui zona DNS
```
PS C:\>$Zone = Get-AzureRmDnsZone -Name "myzone.com" -ResourceGroupName "MyResourceGroup"
PS C:\> $Zone.Tags = @(@{"Name"="Dept"; "Value"="Electrical"})
PS C:\> Set-AzureRmDnsZone -Zone $Zone
```

Perintah pertama mendapatkan zona bernama myzone.com dari grup sumber daya yang ditentukan, lalu menyimpannya dalam variabel $Zone.
Perintah kedua memperbarui tag untuk $Zone.
Perintah terakhir melakukan perubahan.

### Contoh 2: Memperbarui tag untuk zona
```
PS C:\>Set-AzureRmDNSZone -ResourceGroupName "MyResourceGroup" -Name "myzone.com" -Tag @(@{"Name"="Dept"; "Value"="Electrical"})
```

Perintah ini memperbarui tag untuk zona bernama myzone.com tanpa terlebih dahulu secara eksplisit mendapatkan zona.

### Contoh 3: Mengasosiasikan zona privat dengan jaringan virtual dengan menentukan ID-nya
```
PS C:\>$vnet = Get-AzureRmVirualNetwork -ResourceGroupName "MyResourceGroup" -Name "myvnet"
PS C:\>Set-AzureRmDNSZone -ResourceGroupName "MyResourceGroup" -Name "myprivatezone.com" -RegistrationVirtualNetworkId @($vnet.Id)
```

Perintah ini mengaitkan zona DNS Pribadi myprivatezone.com dengan myvnet jaringan virtual sebagai jaringan registrasi dengan menentukan ID-nya.

### Contoh 4: Mengasosiasikan zona privat dengan jaringan virtual dengan menentukan objek jaringan.
```
PS C:\>$vnet = Get-AzureRmVirualNetwork -ResourceGroupName "MyResourceGroup" -Name "myvnet"
PS C:\>Set-AzureRmDNSZone -ResourceGroupName "MyResourceGroup" -Name "myprivatezone.com" -RegistrationVirtualNetwork @($vnet)
```

Perintah ini mengaitkan zona DNS Pribadi myprivatezone.com dengan myvnet jaringan virtual sebagai jaringan registrasi dengan meneruskan objek jaringan virtual yang diwakili oleh variabel $vnet ke cmdlet Set-AzureRmDnsZone.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Menentukan nama zona DNS yang akan diperbarui.

```yaml
Type: System.String
Parameter Sets: Fields, FieldsObjects
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Timpa
Saat melewati zona DNS sebagai objek (menggunakan objek Zona atau melalui pipeline), zona DNS tidak diperbarui jika telah diubah di AZURE DNS sejak objek DnsZone lokal diambil. Ini memberikan perlindungan untuk perubahan serentak. Anda dapat menyembunyikan perilaku ini dengan parameter *Timpa* , yang memperbarui zona terlepas dari perubahan bersamaan.

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

### -RegistrationVirtualNetwork
Daftar jaringan virtual yang akan mendaftarkan catatan hostname mesin virtual di zona DNS ini, hanya tersedia untuk zona privat.

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
Daftar ID jaringan virtual yang akan mendaftarkan catatan nama host mesin virtual di zona DNS ini, hanya tersedia untuk zona privat.

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
Daftar jaringan virtual yang bisa mengatasi catatan di zona DNS ini, hanya tersedia untuk zona privat.

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
Daftar ID jaringan virtual dapat mengatasi catatan di zona DNS ini, hanya tersedia untuk zona privat.

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
Atau, Anda dapat menentukan zona menggunakan objek DnsZone dengan parameter *Zona* atau pipeline.

```yaml
Type: System.String
Parameter Sets: Fields, FieldsObjects
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Tag
Pasangan nilai kunci dalam bentuk tabel hash. Misalnya: @{key0="value0";key1=$null;key2="value2"}

```yaml
Type: System.Collections.Hashtable
Parameter Sets: Fields, FieldsObjects
Aliases: Tags

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Zona
Menentukan zona DNS untuk diperbarui.
Atau, Anda dapat menentukan zona menggunakan parameter *ZoneName* dan *ResourceGroupName* .

```yaml
Type: Microsoft.Azure.Commands.Dns.DnsZone
Parameter Sets: Object
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan. Cmdlet tidak dijalankan. Memperlihatkan apa yang akan terjadi jika cmdlet berjalan. Cmdlet tidak dijalankan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### System.Collections.Hashtable

### System.Collections.Generic.List'1[[System.String, mscorlib, Version=4.0.0.0, Culture=netral, PublicKeyToken=b77a5c561934e089]]

### System.Collections.Generic.List'1[[Microsoft.Azure.Management.Internal.Network.Common.IResourceReference, Microsoft.Azure.Commands.Common.Network, Version=1.0.0.0, Culture=netral, PublicKeyToken=null]]

### Microsoft.Azure.Commands.Dns.DnsZone
Parameter: Zona (ByValue)

## OUTPUTS

### Microsoft.Azure.Commands.Dns.DnsZone

## CATATAN
Anda dapat menggunakan parameter *Konfirmasi* untuk mengontrol apakah cmdlet ini meminta konfirmasi.
Secara default, cmdlet meminta Konfirmasi jika variabel $ConfirmPreference Windows PowerShell memiliki nilai Sedang atau lebih rendah.
Jika Anda menentukan *Konfirmasi* atau *Konfirmasi:$True*, cmdlet ini meminta anda untuk konfirmasi sebelum berjalan.
Jika Anda menentukan *Konfirmasi:$False*, cmdlet tidak meminta konfirmasi kepada Anda.

## RELATED LINKS

[Get-AzureRmDnsZone](./Get-AzureRmDnsZone.md)

[AzureRmDnsZone baru](./New-AzureRmDnsZone.md)

[Hapus-AzureRmDnsZone](./Remove-AzureRmDnsZone.md)
