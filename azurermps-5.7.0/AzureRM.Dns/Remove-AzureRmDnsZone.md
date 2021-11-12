---
external help file: Microsoft.Azure.Commands.Dns.dll-Help.xml
Module Name: AzureRM.Dns
ms.assetid: A8E230A0-5057-40BC-81CD-6D397A503A84
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.dns/remove-azurermdnszone
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Dns/Commands.Dns/help/Remove-AzureRmDnsZone.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Dns/Commands.Dns/help/Remove-AzureRmDnsZone.md
ms.openlocfilehash: ac3f65ed82f9b04eb49e26a8cb03a3dcd8c9bc34
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132427754"
---
# Remove-AzureRmDnsZone

## SYNOPSIS
Menghapus zona DNS dari grup sumber daya.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### Bidang
```
Remove-AzureRmDnsZone -Name <String> -ResourceGroupName <String> [-Force] [-PassThru]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Object
```
Remove-AzureRmDnsZone -Zone <DnsZone> [-Overwrite] [-Force] [-PassThru]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Remove-AzureRmDnsZone** secara permanen menghapus zona Domain Name System (DNS) dari grup sumber daya yang ditentukan.
Semua kumpulan catatan yang dimuat dalam zona juga dihapus.

Anda dapat memberikan objek **DnsZone** menggunakan parameter *Name* atau dengan operator pipeline, atau alternatifnya Anda dapat menentukan parameter *ZoneName* *dan ResourceGroupName.*

Anda bisa menggunakan parameter Konfirmasi dan $ConfirmPreference Windows PowerShell kontrol apakah cmdlet meminta konfirmasi Anda.

Ketika menentukan zona menggunakan objek **DnsZone** (dikirim melalui *saluran* atau parameter Zona), zona tidak dihapus jika telah diubah dalam DNS Azure karena objek **DnsZone** lokal diambil (hanya operasi langsung pada jumlah sumber daya zona DNS sebagai perubahan, operasi pada kumpulan rekaman dalam zona tidak akan digunakan).
Hal ini menyediakan perlindungan untuk perubahan zona serentak.
Hal ini dapat menyembunyikan penggunaan parameter *Overwrite,* yang menghapus zona terlepas dari perubahan konklarasi.

## EXAMPLES

### Contoh 1: Menghapus zona
```
PS C:\>Remove-AzureRmDnsZone -Name "myzone.com" -ResourceGroupName "MyResourceGroup"
```

Perintah ini menghapus zona yang bernama myzone.com grup sumber daya yang bernama MyResourceGroup.

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

### -Force
Parameter ini tidak berlaku bagi cmdlet ini.
File akan dihapus pada rilis mendatang.

Untuk mengontrol apakah cmdlet ini meminta konfirmasi Anda, gunakan parameter *Konfirmasi.*

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
Anda juga harus menentukan parameter *ResourceGroupName.*

Alternatifnya, Anda dapat menentukan zona DNS menggunakan parameter *Zone.*

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

### -Overwrite
Ketika menentukan zona menggunakan objek **DnsZone** (dikirim melalui *saluran* atau parameter Zona), zona tidak dihapus jika telah diubah dalam DNS Azure karena objek **DnsZone** lokal diambil (hanya operasi langsung pada jumlah sumber daya zona DNS sebagai perubahan, operasi pada kumpulan rekaman dalam zona tidak akan digunakan).
Hal ini menyediakan perlindungan untuk perubahan zona serentak.

Hal ini dapat menyembunyikan penggunaan parameter *Overwrite,* yang menghapus zona terlepas dari perubahan konklarasi.

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
Menentukan nama grup sumber daya yang berisi zona yang akan dihapus.
Anda juga harus menentukan parameter *ZoneName.*

Alternatifnya, Anda dapat menentukan zona DNS menggunakan objek **DnsZone,** yang dikirim melalui saluran atau *parameter Zona.*

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

### -Zone
Menentukan zona DNS yang akan dihapus.
Objek **DnsZone** yang melintas juga dapat diteruskan melalui saluran.

Alternatifnya, Anda bisa menentukan zona DNS untuk dihapus dengan menggunakan parameter *ZoneName* dan *ResourceGroupName.*

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
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan.
Cmdlet tidak berjalan.

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
Anda dapat pipa objek **DnsZone** ke cmdlet ini.

## OUTPUTS

### Tidak ada
Cmdlet ini tidak menghasilkan output apa pun.

## CATATAN
Karena dampak penghapusan zona DNS yang berpotensi tinggi, cmdlet ini meminta konfirmasi jika variabel $ConfirmPreference Windows PowerShell memiliki nilai selain Tidak Ada.

Jika Anda menentukan *Konfirmasi* *atau Konfirmasi:$True*, cmdlet ini akan meminta konfirmasi sebelum dijalankan.
Jika Anda menentukan *Confirm:$False*, cmdlet tidak akan meminta konfirmasi Anda. 

## RELATED LINKS

[Get-AzureRmDnsZone](./Get-AzureRmDnsZone.md)

[New-AzureRmDnsZone](./New-AzureRmDnsZone.md)

[Set-AzureRmDnsZone](./Set-AzureRmDnsZone.md)
