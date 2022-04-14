---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Dns.dll-Help.xml
Module Name: Az.Dns
ms.assetid: B78F3E8B-C7D2-458C-AB23-06F584FE97E0
online version: https://docs.microsoft.com/powershell/module/az.dns/new-azdnszone
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Dns/Dns/help/New-AzDnsZone.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Dns/Dns/help/New-AzDnsZone.md
ms.openlocfilehash: 5c647e2c1f3372919803214f190add2c1f79e39c
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141837843"
---
# New-AzDnsZone

## SYNOPSIS
Membuat zona DNS baru.

## SYNTAX

### Ids (Default)
```
New-AzDnsZone -Name <String> -ResourceGroupName <String> [-ZoneType <ZoneType>] [-ParentZoneId <String>]
 [-Tag <Hashtable>] [-RegistrationVirtualNetworkId <System.Collections.Generic.List`1[System.String]>]
 [-ResolutionVirtualNetworkId <System.Collections.Generic.List`1[System.String]>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Nama
```
New-AzDnsZone -Name <String> -ResourceGroupName <String> [-ZoneType <ZoneType>] [-ParentZoneName <String>]
 [-Tag <Hashtable>] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Objek
```
New-AzDnsZone -Name <String> -ResourceGroupName <String> [-ZoneType <ZoneType>] [-ParentZone <DnsZone>]
 [-Tag <Hashtable>]
 [-RegistrationVirtualNetwork <System.Collections.Generic.List`1[Microsoft.Azure.Management.Internal.Network.Common.IResourceReference]>]
 [-ResolutionVirtualNetwork <System.Collections.Generic.List`1[Microsoft.Azure.Management.Internal.Network.Common.IResourceReference]>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzDnsZone** membuat zona Domain Name System (DNS) baru dalam grup sumber daya yang ditentukan. Anda harus menentukan nama zona DNS unik untuk parameter *Nama* atau cmdlet akan mengembalikan kesalahan. Setelah zona dibuat, gunakan cmdlet New-AzDnsRecordSet untuk membuat kumpulan rekaman di zona.
Anda dapat menggunakan variabel *Konfirmasi* parameter dan $ConfirmPreference Windows PowerShell untuk mengontrol apakah cmdlet meminta konfirmasi.

## EXAMPLES

### Contoh 1: Membuat zona DNS
```powershell
$Zone = New-AzDnsZone -Name "myzone.com" -ResourceGroupName "MyResourceGroup"
```

Perintah ini membuat zona DNS baru bernama myzone.com dalam grup sumber daya tertentu, lalu menyimpannya dalam variabel $Zone.

### Contoh 2: Membuat zona DNS Pribadi dengan menentukan ID jaringan virtual
```powershell
$ResVirtualNetworkId = "/subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/testresgroup/providers/Microsoft.Network/virtualNetworks/resvnet"
$Zone = New-AzDnsZone -Name "myprivatezone.com" -ResourceGroupName "MyResourceGroup" -ZoneType Private -ResolutionVirtualNetworkId @($ResVirtualNetworkId)
```

Perintah ini membuat zona DNS Pribadi baru bernama myprivatezone.com dalam grup sumber daya tertentu dengan jaringan virtual resolusi terkait (menentukan ID-nya), lalu menyimpannya dalam variabel $Zone.

### Contoh 3: Membuat zona DNS Pribadi dengan menentukan objek jaringan virtual
```powershell
$ResVirtualNetwork = Get-AzVirtualNetwork -Name "resvnet" -ResourceGroupName "testresgroup"
$Zone = New-AzDnsZone -Name "myprivatezone.com" -ResourceGroupName "MyResourceGroup" -ZoneType Private -ResolutionVirtualNetwork @($ResVirtualNetwork)
```

Perintah ini membuat zona DNS Pribadi baru bernama myprivatezone.com dalam grup sumber daya tertentu dengan jaringan virtual resolusi terkait (dirujuk oleh variabel $ResVirtualNetwork), lalu menyimpannya dalam variabel $Zone.

### Contoh 4: Membuat zona DNS dengan delegasi dengan menentukan nama zona induk
```powershell
$Zone = New-AzDnsZone -Name "mychild.zone.com" -ResourceGroupName "MyResourceGroup" -ParentZoneName "zone.com"
```

Perintah ini membuat zona DNS anak baru bernama mychild.zone.com dalam grup sumber daya yang ditentukan dan disimpan dalam variabel $Zone.
Ini juga menambahkan delegasi di zona DNS induk bernama zone.com berada di grup langganan dan sumber daya yang sama dengan zona turunan.

### Contoh 5: Membuat zona DNS dengan delegasi dengan menentukan id zona induk
```powershell
$Zone = New-AzDnsZone -Name "mychild.zone.com" -ResourceGroupName "MyResourceGroup" -ParentZoneId "/subscriptions/**67e2/resourceGroups/other-rg/providers/Microsoft.Network/dnszones/zone.com"
```

Perintah ini membuat zona DNS anak baru bernama mychild.zone.com dalam grup sumber daya yang ditentukan dan disimpan dalam variabel $Zone.
Ini juga menambahkan delegasi di zona DNS induk bernama zone.com dalam grup sumber daya langganan lain-rg yang disediakan sama seperti zona turunan yang dibuat.

### Contoh 6: Membuat zona DNS dengan delegasi dengan menentukan objek zona induk
```powershell
$PZone = New-AzDnsZone -Name "zone.com" -ResourceGroupName "MyResourceGroup" 
$Zone = New-AzDnsZone -Name "mychild.zone.com" -ResourceGroupName "MyResourceGroup" -ParentZone @($PZone)
```

Perintah ini membuat zona DNS anak baru bernama mychild.zone.com dalam grup sumber daya yang ditentukan dan disimpan dalam variabel $Zone.
Ini juga menambahkan delegasi di zona DNS induk bernama zone.com seperti yang dikirimkan dalam objek ParentZone

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
Menentukan nama zona DNS yang akan dibuat.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ParentZone
Nama lengkap zona induk untuk menambahkan delegasi (tanpa titik penghentian).

```yaml
Type: Microsoft.Azure.Commands.Dns.DnsZone
Parameter Sets: Objects
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ParentZoneId
Id sumber daya zona induk untuk menambahkan delegasi (tanpa titik penghentian).

```yaml
Type: System.String
Parameter Sets: Ids
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ParentZoneName
Nama lengkap zona induk untuk menambahkan delegasi (tanpa titik penghentian).

```yaml
Type: System.String
Parameter Sets: Names
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RegistrationVirtualNetwork
Daftar jaringan virtual yang akan mendaftarkan catatan hostname mesin virtual di zona DNS ini, hanya tersedia untuk zona privat.

```yaml
Type: System.Collections.Generic.List`1[Microsoft.Azure.Management.Internal.Network.Common.IResourceReference]
Parameter Sets: Objects
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
Parameter Sets: Ids
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
Parameter Sets: Objects
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
Parameter Sets: Ids
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Menentukan grup sumber daya untuk membuat zona.

```yaml
Type: System.String
Parameter Sets: (All)
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
Parameter Sets: (All)
Aliases: Tags

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ZoneType
Tipe zona, Publik atau Privat. Zona tanpa tipe atau dengan tipe Publik tersedia di bidang penyajian DNS publik untuk digunakan dalam hierarki DNS. Zona dengan tipe Privat hanya terlihat dengan sekumpulan jaringan virtual terkait (fitur ini ada dalam pratinjau). Properti ini tidak dapat diubah untuk zona.

```yaml
Type: System.Nullable`1[Microsoft.Azure.Management.Dns.Models.ZoneType]
Parameter Sets: (All)
Aliases:
Accepted values: Public, Private

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### System.Nullable'1[[Microsoft.Azure.Management.Dns.Models.ZoneType, Microsoft.Azure.Management.Dns, Version=3.0.0.0, Culture=netral, PublicKeyToken=31bf3856ad364e35]]

### System.Collections.Hashtable

### System.Collections.Generic.List'1[[System.String, System.Private.CoreLib, Version=4.0.0.0, Culture=netral, PublicKeyToken=7cec85d7bea7798e]]

### System.Collections.Generic.List'1[[Microsoft.Azure.Management.Internal.Network.Common.IResourceReference, Microsoft.Azure.PowerShell.Clients.Network, Version=1.0.0.0, Culture=netral, PublicKeyToken=31bf3856ad364e35]]

## OUTPUTS

### Microsoft.Azure.Commands.Dns.DnsZone

## CATATAN
Anda dapat menggunakan parameter *Konfirmasi* untuk mengontrol apakah cmdlet ini meminta konfirmasi.
Secara default, cmdlet meminta Konfirmasi jika variabel $ConfirmPreference Windows PowerShell memiliki nilai Sedang atau lebih rendah.
Jika Anda menentukan *Konfirmasi* atau *Konfirmasi:$True*, cmdlet ini meminta anda untuk konfirmasi sebelum berjalan.
Jika Anda menentukan *Konfirmasi:$False*, cmdlet tidak meminta konfirmasi kepada Anda.

## RELATED LINKS

[Get-AzDnsZone](./Get-AzDnsZone.md)

[New-AzDnsRecordSet](./New-AzDnsRecordSet.md)

[Hapus-AzDnsZone](./Remove-AzDnsZone.md)
