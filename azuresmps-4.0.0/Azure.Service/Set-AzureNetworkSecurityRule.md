---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.Network.dll-Help.xml
ms.assetid: 125B6865-0022-4F88-BB0F-DDDDB2EDFF00
online version: ''
schema: 2.0.0
ms.openlocfilehash: 0c969dd4a8cf5e7a48907c5c75031c85a42898a7
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142787176"
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
Nilai yang valid terdiri dari bilangan bulat dari 0 hingga 65535.
Anda dapat menentukan nilai individual, atau menentukan rentang dalam format LowerNumber-HigherNumber.
Tanda hubung memisahkan dua nilai.

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
Menentukan nama untuk aturan keamanan jaringan yang ditambahkan atau diubah cmdlet ini.

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
Menentukan grup keamanan jaringan yang diubah cmdlet ini.
Untuk mendapatkan objek **INetworkSecurityGroup** , gunakan cmdlet Get-AzureNetworkSecurityGroup.

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
Nilai yang valid adalah: bilangan bulat dari 100 hingga 4096.

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
Menentukan profil Azure tempat cmdlet ini dibaca. Jika Anda tidak menentukan profil, cmdlet ini akan dibaca dari profil default lokal.

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

### -Protokol
Menentukan protokol untuk aturan keamanan jaringan.
Nilai yang valid adalah: 

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
Menentukan alamat CIDR dari rentang IP sumber untuk aturan keamanan jaringan.
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
Nilai yang valid terdiri dari bilangan bulat dari 0 hingga 65535.
Anda dapat menentukan nilai individual, atau menentukan rentang dalam format LowerNumber-HigherNumber.
Tanda hubung memisahkan dua nilai.

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
Menentukan tipe sambungan untuk aturan keamanan jaringan.
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Hapus-AzureNetworkSecurityRule](./Remove-AzureNetworkSecurityRule.md)


