---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Dns.dll-Help.xml
Module Name: Az.Dns
ms.assetid: A8E230A0-5057-40BC-81CD-6D397A503A84
online version: https://docs.microsoft.com/en-us/powershell/module/az.dns/remove-azdnszone
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/Dns/Dns/help/Remove-AzDnsZone.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/Dns/Dns/help/Remove-AzDnsZone.md
ms.openlocfilehash: 633a71788bb9578438053f7a296422e99e7c488e
ms.sourcegitcommit: b4a38bcb0501a9016a4998efd377aa75d3ef9ce8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 10/27/2020
ms.locfileid: "132408023"
---
# Remove-AzDnsZone

## SYNOPSIS
Menghapus zona DNS dari grup sumber daya.

## SINTAKS

### Bidang
```
Remove-AzDnsZone -Name <String> -ResourceGroupName <String> [-PassThru]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Object
```
Remove-AzDnsZone -Zone <DnsZone> [-Overwrite] [-PassThru] [-DefaultProfile <IAzureContextContainer>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESKRIPSI
Cmdlet **Remove-AzDnsZone** secara permanen menghapus zona Domain Name System (DNS) dari grup sumber daya yang ditentukan.
Semua kumpulan catatan yang dimuat dalam zona juga dihapus.
Anda dapat memberikan objek **DnsZone** menggunakan parameter *Name* atau dengan operator pipeline, atau alternatifnya Anda dapat menentukan parameter *ZoneName* *dan ResourceGroupName.*
Anda dapat menggunakan parameter Konfirmasi dan $ConfirmPreference Windows PowerShell variabel untuk mengontrol apakah cmdlet meminta konfirmasi Anda.
Ketika menentukan zona menggunakan objek **DnsZone** (dikirim melalui *saluran* atau parameter Zona), zona tidak dihapus jika zona diubah dalam DNS Azure karena objek **DnsZone** lokal diambil (hanya operasi langsung pada jumlah sumber daya zona DNS sebagai perubahan, operasi pada kumpulan rekaman dalam zona tidak akan digunakan).
Hal ini menyediakan perlindungan untuk perubahan zona serentak.
Hal ini dapat menyembunyikan penggunaan parameter *Overwrite,* yang menghapus zona terlepas dari perubahan konklarasi.

## CONTOH

### Contoh 1: Menghapus zona
```
PS C:\>Remove-AzDnsZone -Name "myzone.com" -ResourceGroupName "MyResourceGroup"
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
Menentukan nama zona DNS yang dihapus cmdlet ini.
Anda juga harus menentukan parameter *ResourceGroupName.*
Alternatifnya, Anda dapat menentukan zona DNS menggunakan parameter *Zone.*

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

### -Overwrite
Ketika menentukan zona menggunakan objek **DnsZone** (dikirim melalui *saluran* atau parameter Zona), zona tidak dihapus jika zona diubah dalam DNS Azure karena objek **DnsZone** lokal diambil (hanya operasi langsung pada jumlah sumber daya zona DNS sebagai perubahan, operasi pada kumpulan rekaman dalam zona tidak akan digunakan).
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
Menentukan nama grup sumber daya yang berisi zona yang akan dihapus.
Anda juga harus menentukan parameter *ZoneName.*
Alternatifnya, Anda dapat menentukan zona DNS menggunakan objek **DnsZone,** yang dikirim melalui saluran atau *parameter Zona.*

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

### -Zone
Menentukan zona DNS yang akan dihapus.
Objek **DnsZone** yang melintas juga dapat diteruskan melalui saluran.
Alternatifnya, Anda bisa menentukan zona DNS untuk dihapus dengan menggunakan parameter *ZoneName* dan *ResourceGroupName.*

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

### System.String

### Microsoft.Azure.Commands.Dns.DnsZone

## OUTPUT

### System.Boolean

## CATATAN
Karena dampak penghapusan zona DNS yang berpotensi tinggi, cmdlet ini meminta konfirmasi jika variabel $ConfirmPreference Windows PowerShell memiliki nilai selain Tidak Ada.
Jika Anda menetapkan *Konfirmasi* *atau Konfirmasi:$True*, cmdlet ini akan meminta konfirmasi sebelum dijalankan.
Jika Anda menentukan *Confirm:$False*, cmdlet tidak akan meminta konfirmasi Anda. 

## LINK TERKAIT

[Get-AzDnsZone](./Get-AzDnsZone.md)

[New-AzDnsZone](./New-AzDnsZone.md)

[Set-AzDnsZone](./Set-AzDnsZone.md)
