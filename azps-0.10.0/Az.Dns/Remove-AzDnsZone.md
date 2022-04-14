---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Dns.dll-Help.xml
Module Name: Az.Dns
ms.assetid: A8E230A0-5057-40BC-81CD-6D397A503A84
online version: https://docs.microsoft.com/en-us/powershell/module/az.dns/remove-azdnszone
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/Azs-tzl/src/Dns/Dns/help/Remove-AzDnsZone.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/Azs-tzl/src/Dns/Dns/help/Remove-AzDnsZone.md
ms.openlocfilehash: bc77e2c69f285f0acab0bed8e6a40592374ebd18
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141917625"
---
# Remove-AzDnsZone

## SYNOPSIS
Menghapus zona DNS dari grup sumber daya.

## SYNTAX

### Bidang
```
Remove-AzDnsZone -Name <String> -ResourceGroupName <String> [-Force] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### Objek
```
Remove-AzDnsZone -Zone <DnsZone> [-Overwrite] [-Force] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Remove-AzDnsZone** menghapus zona Domain Name System (DNS) secara permanen dari grup sumber daya tertentu.
Semua kumpulan rekaman yang terdapat dalam zona juga dihapus.

Anda bisa melewati objek **DnsZone** menggunakan parameter *Nama* atau dengan menggunakan operator pipeline, atau anda bisa menentukan parameter *ZoneName* dan *ResourceGroupName* .

Anda dapat menggunakan variabel Konfirmasi parameter dan $ConfirmPreference Windows PowerShell untuk mengontrol apakah cmdlet meminta konfirmasi.

Saat menentukan zona menggunakan objek **DnsZone** (dilewatkan melalui pipeline atau parameter *Zona* ), zona tidak dihapus jika telah diubah di Azure DNS karena objek **DnsZone** lokal diambil (hanya operasi langsung pada jumlah sumber daya zona DNS sebagai perubahan, operasi pada kumpulan catatan di dalam zona tidak).
Ini menyediakan perlindungan untuk perubahan zona serentak.
Ini dapat ditekan menggunakan parameter *Timpa* , yang menghapus zona terlepas dari perubahan bersamaan.

## EXAMPLES

### Contoh 1: Menghapus zona
```
PS C:\>Remove-AzDnsZone -Name "myzone.com" -ResourceGroupName "MyResourceGroup"
```

Perintah ini menghapus zona bernama myzone.com dari grup sumber daya bernama MyResourceGroup.

## PARAMETERS

### -Paksa
Parameter ini tidak digunakan lagi untuk cmdlet ini.
Ini akan dihapus dalam rilis mendatang.

Untuk mengontrol apakah cmdlet ini meminta anda untuk konfirmasi, gunakan parameter *Konfirmasi* .

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Menentukan nama zona DNS yang dihapus cmdlet ini.
Anda juga harus menentukan parameter *ResourceGroupName* .

Alternatifnya, Anda bisa menentukan zona DNS menggunakan parameter *Zona* .

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
Saat menentukan zona menggunakan objek **DnsZone** (dilewatkan melalui pipeline atau parameter *Zona* ), zona tidak dihapus jika telah diubah di Azure DNS karena objek **DnsZone** lokal diambil (hanya operasi langsung pada jumlah sumber daya zona DNS sebagai perubahan, operasi pada kumpulan catatan di dalam zona tidak).
Ini menyediakan perlindungan untuk perubahan zona serentak.

Ini dapat ditekan menggunakan parameter *Timpa* , yang menghapus zona terlepas dari perubahan bersamaan.

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

### -PassThru
passthru

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Menentukan nama grup sumber daya yang berisi zona untuk dihapus.
Anda juga harus menentukan parameter *ZoneName* .

Alternatifnya, Anda bisa menentukan zona DNS menggunakan objek **DnsZone** , yang dilewati melalui pipeline atau parameter *Zona* .

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

### -Zona
Menentukan zona DNS untuk dihapus.
Objek **DnsZone yang** dilewati juga bisa dilewati melalui pipeline.

Alternatifnya, Anda dapat menentukan zona DNS untuk dihapus menggunakan parameter *ZoneName* dan *ResourceGroupName* .

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
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan.
Cmdlet tidak dijalankan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Dns.DnsZone
Anda dapat menyalurkan objek **DnsZone** ke cmdlet ini.

## OUTPUTS

### Tidak
Cmdlet ini tidak menghasilkan output apa pun.

## CATATAN
Karena dampak yang berpotensi tinggi untuk menghapus zona DNS, secara default, cmdlet ini meminta konfirmasi jika variabel $ConfirmPreference Windows PowerShell memiliki nilai selain Tidak Ada.

Jika Anda menentukan *Konfirmasi* atau *Konfirmasi:$True*, cmdlet ini meminta anda untuk konfirmasi sebelum berjalan.
Jika Anda menentukan *Konfirmasi:$False*, cmdlet tidak meminta konfirmasi kepada Anda. 

## RELATED LINKS

[Get-AzDnsZone](./Get-AzDnsZone.md)

[New-AzDnsZone](./New-AzDnsZone.md)

[Set-AzDnsZone](./Set-AzDnsZone.md)
