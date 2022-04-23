---
external help file: Microsoft.Azure.Commands.Dns.dll-Help.xml
ms.assetid: E37ADC54-A37B-41BF-BE94-9E4052C234BB
online version: ''
schema: 2.0.0
ms.openlocfilehash: 347f590ecd6e2825264e6bb0b980dd94450b0f06
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143053775"
---
# Set-AzureRmDnsZone

## SYNOPSIS
Memperbarui properti zona DNS.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### Bidang
```
Set-AzureRmDnsZone -Name <String> -ResourceGroupName <String> [-Tag <Hashtable>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### Objek
```
Set-AzureRmDnsZone -Zone <DnsZone> [-Overwrite] [-WhatIf] [-Confirm] [<CommonParameters>]
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

## PARAMETERS

### -Nama
Menentukan nama zona DNS yang akan diperbarui.

```yaml
Type: String
Parameter Sets: Fields
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
Type: SwitchParameter
Parameter Sets: Object
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Menentukan nama grup sumber daya yang berisi zona untuk diperbarui.
Anda juga harus menentukan parameter ZoneName.

Atau, Anda dapat menentukan zona menggunakan objek DnsZone dengan parameter *Zona* atau pipeline.

```yaml
Type: String
Parameter Sets: Fields
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
Parameter Sets: Fields
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
Meminta konfirmasi sebelum menjalankan cmdlet.

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
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan. Cmdlet tidak dijalankan. Memperlihatkan apa yang akan terjadi jika cmdlet berjalan. Cmdlet tidak dijalankan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Dns.DnsZone
Anda dapat menyalurkan objek DnsZone ke cmdlet ini.

## OUTPUTS

### Microsoft.Azure.Commands.Dns.DnsZone
Cmdlet ini mengembalikan objek DnsZone yang mewakili zona DNS yang diperbarui dengan Etag baru.

## NOTES
Anda dapat menggunakan parameter *Konfirmasi* untuk mengontrol apakah cmdlet ini meminta konfirmasi.
Secara default, cmdlet meminta Konfirmasi jika variabel $ConfirmPreference Windows PowerShell memiliki nilai Sedang atau lebih rendah.

Jika Anda menentukan *Konfirmasi* atau *Konfirmasi:$True*, cmdlet ini meminta anda untuk konfirmasi sebelum berjalan.
Jika Anda menentukan *Konfirmasi:$False*, cmdlet tidak meminta konfirmasi kepada Anda.

## RELATED LINKS

[Get-AzureRmDnsZone](./Get-AzureRmDnsZone.md)

[AzureRmDnsZone baru](./New-AzureRmDnsZone.md)

[Hapus-AzureRmDnsZone](./Remove-AzureRmDnsZone.md)
