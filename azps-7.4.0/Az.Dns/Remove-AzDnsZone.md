---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Dns.dll-Help.xml
Module Name: Az.Dns
ms.assetid: A8E230A0-5057-40BC-81CD-6D397A503A84
online version: https://docs.microsoft.com/powershell/module/az.dns/remove-azdnszone
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Dns/Dns/help/Remove-AzDnsZone.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Dns/Dns/help/Remove-AzDnsZone.md
ms.openlocfilehash: 11097d73bea0d146652646a4fe489baadbcc119c
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142748476"
---
# Remove-AzDnsZone

## SYNOPSIS
Menghapus zona DNS dari grup sumber daya.

## SYNTAX

### Bidang
```
Remove-AzDnsZone -Name <String> -ResourceGroupName <String> [-PassThru]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Objek
```
Remove-AzDnsZone -Zone <DnsZone> [-Overwrite] [-PassThru] [-DefaultProfile <IAzureContextContainer>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
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
```powershell
Remove-AzDnsZone -Name "myzone.com" -ResourceGroupName "MyResourceGroup"
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
Menentukan nama zona DNS yang dihapus cmdlet ini.
Anda juga harus menentukan parameter *ResourceGroupName* .
Alternatifnya, Anda bisa menentukan zona DNS menggunakan parameter *Zona* .

```yaml
Type: System.String
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
passthru

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
Menentukan nama grup sumber daya yang berisi zona untuk dihapus.
Anda juga harus menentukan parameter *ZoneName* .
Alternatifnya, Anda bisa menentukan zona DNS menggunakan objek **DnsZone** , yang dilewati melalui pipeline atau parameter *Zona* .

```yaml
Type: System.String
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

### System.String

### Microsoft.Azure.Commands.Dns.DnsZone

## OUTPUTS

### System.Boolean

## NOTES
Karena dampak yang berpotensi tinggi untuk menghapus zona DNS, secara default, cmdlet ini meminta konfirmasi jika variabel $ConfirmPreference Windows PowerShell memiliki nilai selain Tidak Ada.
Jika Anda menentukan *Konfirmasi* atau *Konfirmasi:$True*, cmdlet ini meminta anda untuk konfirmasi sebelum berjalan.
Jika Anda menentukan *Konfirmasi:$False*, cmdlet tidak meminta konfirmasi kepada Anda. 

## RELATED LINKS

[Get-AzDnsZone](./Get-AzDnsZone.md)

[New-AzDnsZone](./New-AzDnsZone.md)

[Set-AzDnsZone](./Set-AzDnsZone.md)
