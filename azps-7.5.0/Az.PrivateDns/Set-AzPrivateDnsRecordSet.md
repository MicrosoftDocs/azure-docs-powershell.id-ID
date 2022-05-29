---
external help file: Microsoft.Azure.PowerShell.Cmdlets.PrivateDns.dll-Help.xml
Module Name: Az.PrivateDns
online version: https://docs.microsoft.com/powershell/module/az.privatedns/Set-AzPrivateDnsRecordSet
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/PrivateDns/PrivateDns/help/Set-AzPrivateDnsRecordSet.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/PrivateDns/PrivateDns/help/Set-AzPrivateDnsRecordSet.md
ms.openlocfilehash: 3809fea9bc4ffe3f9a528aa60f1c47750097c695
ms.sourcegitcommit: 82b4008b76d035e4aee733727371765b0d853bed
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145657138"
---
# Set-AzPrivateDnsRecordSet

## SYNOPSIS
Memperbarui/Mengatur kumpulan catatan di zona DNS Privat.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.privatedns/set-azprivatednsrecordset) untuk informasi terbaru.

## SYNTAX

```
Set-AzPrivateDnsRecordSet -RecordSet <PSPrivateDnsRecordSet> [-Overwrite]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet Set-AzPrivateDnsRecordSet memperbarui kumpulan catatan di layanan DNS Privat Azure dari objek RecordSet lokal. Anda dapat meneruskan objek RecordSet sebagai parameter atau dengan menggunakan operator alur. Anda dapat menggunakan parameter Konfirmasi dan variabel $ConfirmPreference Windows PowerShell untuk mengontrol apakah cmdlet meminta konfirmasi. Kumpulan catatan tidak diperbarui jika telah diubah di Azure Private DNS sejak objek RecordSet lokal diambil. Ini memberikan perlindungan untuk perubahan bersamaan. Anda dapat menekan perilaku ini menggunakan parameter Timpa, yang memperbarui kumpulan catatan terlepas dari perubahan bersamaan.

## EXAMPLES

### Contoh 1: Memperbarui kumpulan catatan
```powershell
 $RecordSet = Get-AzPrivateDnsRecordSet -ResourceGroupName MyResourceGroup -ZoneName myzone.com -Name www -RecordType A
 Add-AzPrivateDnsRecordConfig -RecordSet $RecordSet -Ipv4Address 172.16.0.0
 Add-AzPrivateDnsRecordConfig -RecordSet $RecordSet -Ipv4Address 172.31.255.255
 Set-AzPrivateDnsRecordSet -RecordSet $RecordSet

# These cmdlets can also be piped:

 Get-AzPrivateDnsRecordSet -ResourceGroupName MyResourceGroup -ZoneName myzone.com -Name www -RecordType A | Add-AzPrivateDnsRecordConfig -Ipv4Address 172.16.0.0 | Add-AzPrivateDnsRecordConfig -Ipv4Address 172.31.255.255 | Set-AzPrivateDnsRecordSet
```

```output
Id                : /subscriptions/xxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/resourceGroups/MyResourceGroup/providers/Microsoft.Netwo
                    rk/privateDnsZones/myzone.com/A/www
Name              : www
ZoneName          : myzone.com
ResourceGroupName : MyResourceGroup
Ttl               : 3600
Etag              : xxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
RecordType        : A
Records           : {1.2.3.4, 172.16.0.0, 172.31.255.255}
Metadata          :
IsAutoRegistered  :
```

Perintah pertama menggunakan cmdlet Get-AzPrivateDnsRecordSet untuk mendapatkan kumpulan catatan yang ditentukan, lalu menyimpannya dalam variabel $RecordSet. Perintah kedua dan ketiga adalah operasi off-line untuk menambahkan dua rekaman A ke kumpulan catatan. Perintah akhir menggunakan cmdlet Set-AzPrivateDnsRecordSet untuk menerapkan pembaruan.

### Contoh 2: Memperbarui catatan SOA
```powershell
 $RecordSet = Get-AzPrivateDnsRecordSet -Name "@" -RecordType SOA -Zone $Zone
 $RecordSet.Records[0].Email = "admin.myzone.com"
 Set-AzPrivateDnsRecordSet -RecordSet $RecordSet
```

```output
Id                : /subscriptions/xxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/resourceGroups/myresourcegroup/providers/Micros
                    oft.Network/privateDnsZones/myzone.com/SOA/@
Name              : @
ZoneName          : myzone.com
ResourceGroupName : Myresourcegroup
Ttl               : 3600
Etag              : xxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
RecordType        : SOA
Records           : {[internal.cloudapp.net,admin.myzone.com,3600,300,2419200,300]}
Metadata          :
IsAutoRegistered  :
```

Perintah pertama menggunakan cmdlet Get-AzPrivateDnsRecordSet untuk mendapatkan kumpulan catatan yang ditentukan, lalu menyimpannya dalam variabel $RecordSet. Perintah kedua memperbarui rekaman SOA yang ditentukan di $RecordSet. Perintah akhir menggunakan cmdlet Set-AzPrivateDnsRecordSet untuk menyebarluaskan pembaruan dalam $RecordSet.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

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

### -Timpa
Jangan gunakan bidang ETag dari parameter RecordSet untuk pemeriksaan konkurensi optimis.

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

### -RecordSet
Kumpulan catatan untuk menambahkan catatan.

```yaml
Type: Microsoft.Azure.Commands.PrivateDns.Models.PSPrivateDnsRecordSet
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Confirm
Meminta Anda mengonfirmasi sebelum menjalankan cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Menunjukkan yang akan terjadi jika cmdlet dijalankan.
Cmdlet tidak dijalankan.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.PrivateDns.Models.PSPrivateDnsRecordSet

## OUTPUTS

### Microsoft.Azure.Commands.PrivateDns.Models.PSPrivateDnsRecordSet

## NOTES

## RELATED LINKS
