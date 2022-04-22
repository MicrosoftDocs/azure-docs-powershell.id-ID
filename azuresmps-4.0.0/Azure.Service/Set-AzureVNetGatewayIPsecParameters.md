---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.Network.dll-Help.xml
ms.assetid: C85576C1-182B-467E-9620-A475728E20D2
online version: ''
schema: 2.0.0
ms.openlocfilehash: c0668373bb49f8691a947e4c4de298ab78497dab
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142979435"
---
# Set-AzureVNetGatewayIPsecParameters

## SYNOPSIS
Mengatur parameter IPsec untuk koneksi antara gateway jaringan virtual dan situs jaringan lokal.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Set-AzureVNetGatewayIPsecParameters -VNetName <String> -LocalNetworkSiteName <String>
 [-EncryptionType <String>] [-PfsGroup <String>] [-SADataSizeKilobytes <Int32>] [-SALifetimeSeconds <Int32>]
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzureVNetGatewayIPsecParameters** mengatur parameter Keamanan Protokol Internet (IPsec) dan Internet Key Exchange (IKE) untuk koneksi antara gateway jaringan virtual dan situs jaringan lokal.

## EXAMPLES

## PARAMETERS

### -EncryptionType
Menentukan tipe enkripsi untuk gateway jaringan virtual.
Nilai yang valid adalah: 

- NoEncryption 
- RequireEncryption

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LocalNetworkSiteName
Menentukan nama koneksi situs jaringan lokal tempat cmdlet ini mengonfigurasi parameter IPsec dan IKE.

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

### -PfsGroup
Menentukan grup kesempurnaan ketahanan maju (PFS).
Nilai yang valid adalah: 

- PFS1 
- Tidak

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
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

### -SADataSizeKilobytes
Menentukan ukuran, dalam kilobyte, asosiasi keamanan (SA).

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SALifetimeSeconds
Menentukan periode, dalam detik, dari asosiasi keamanan.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VNetName
Menentukan jaringan virtual di mana cmdlet ini mengatur parameter IPsec untuk koneksi.

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

[Get-AzureVNetGatewayIPsecParameters](./Get-AzureVNetGatewayIPsecParameters.md)


