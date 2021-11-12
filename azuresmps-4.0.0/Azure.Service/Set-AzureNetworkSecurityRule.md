---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.Network.dll-Help.xml
ms.assetid: 125B6865-0022-4F88-BB0F-DDDDB2EDFF00
online version: ''
schema: 2.0.0
ms.openlocfilehash: 0c969dd4a8cf5e7a48907c5c75031c85a42898a7
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132427440"
---
# Set-AzureNetworkSecurityRule

## SYNOPSIS
Menambahkan atau mengubah aturan keamanan jaringan dalam grup keamanan jaringan.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Set-AzureNetworkSecurityRule -Name <String> -Type <String> -Priority <Int32> -Action <String>
 -SourceAddressPrefix <String> -SourcePortRange <String> -DestinationAddressPrefix <String>
 -DestinationPortRange <String> -Protocol <String> -NetworkSecurityGroup <INetworkSecurityGroup>
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzureNetworkSecurityRule** menambahkan atau mengubah aturan keamanan jaringan Azure dalam grup keamanan jaringan.

## EXAMPLES

## PARAMETERS

### -Tindakan
Menentukan tindakan untuk aturan keamanan jaringan.
Nilai yang valid adalah: Izinkan dan Tolak.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DestinationAddressPrefix
Menentukan alamat Classless Interdomain Routing (CIDR) dari rentang IP tujuan untuk aturan keamanan jaringan.
Tanda bintang (*) menentukan alamat IP apa pun.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DestinationPortRange
Menentukan rentang port tujuan untuk aturan keamanan jaringan.
Nilai valid terdiri dari bilangan bulat dari 0 sampai 65535.
Anda dapat menentukan nilai individual, atau menentukan rentang dalam format LowerNumber-HigherNumber.
Tanda hubung memisahkan kedua nilai.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Menentukan nama untuk aturan keamanan jaringan yang menambahkan atau mengubah cmdlet ini.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NetworkSecurityGroup
Menentukan grup keamanan jaringan yang dimodifikasi cmdlet ini.
Untuk mendapatkan objek **INetworkSecurityGroup,** gunakan cmdlet Get-AzureNetworkSecurityGroup.

```yaml
Type: INetworkSecurityGroup
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Prioritas
Menentukan prioritas untuk aturan keamanan jaringan.
Nilai valid adalah: bilangan bulat dari 100 sampai 4096.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Profil
Menentukan profil Azure yang akan dibaca cmdlet ini. Jika Anda tidak menentukan profil, cmdlet ini akan membaca dari profil default lokal.

```yaml
Type: AzureSMProfile
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Protocol
Menentukan protokol untuk aturan keamanan jaringan.
Nilai valid adalah: 

- TCP 
- UDP 
- *

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SourceAddressPrefix
Menentukan alamat CIDR rentang IP sumber untuk aturan keamanan jaringan.
Tanda bintang (*) menentukan alamat IP apa pun.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SourcePortRange
Menentukan rentang port sumber untuk aturan keamanan jaringan.
Nilai valid terdiri dari bilangan bulat dari 0 sampai 65535.
Anda dapat menentukan nilai individual, atau menentukan rentang dalam format LowerNumber-HigherNumber.
Tanda hubung memisahkan kedua nilai.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Tipe
Menentukan tipe koneksi untuk aturan keamanan jaringan.
Nilai yang valid adalah: Masuk dan Keluar.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

## OUTPUTS

## CATATAN

## RELATED LINKS

[Remove-AzureNetworkSecurityRule](./Remove-AzureNetworkSecurityRule.md)


