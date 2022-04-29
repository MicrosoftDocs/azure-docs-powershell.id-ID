---
external help file: ''
Module Name: Az.EdgeOrder
online version: https://docs.microsoft.com/powershell/module/az.EdgeOrder/new-AzEdgeOrderShippingAddressObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/EdgeOrder/help/New-AzEdgeOrderShippingAddressObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/EdgeOrder/help/New-AzEdgeOrderShippingAddressObject.md
ms.openlocfilehash: 0168b1fc9b2235d0dca70b37f18db0709e0a7c6c
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144239872"
---
# New-AzEdgeOrderShippingAddressObject

## SYNOPSIS
Buat objek dalam memori untuk ShippingAddress.

## SYNTAX

```
New-AzEdgeOrderShippingAddressObject -Country <String> -StreetAddress1 <String> [-AddressType <AddressType>]
 [-City <String>] [-CompanyName <String>] [-PostalCode <String>] [-StateOrProvince <String>]
 [-StreetAddress2 <String>] [-StreetAddress3 <String>] [-ZipExtendedCode <String>] [<CommonParameters>]
```

## DESCRIPTION
Buat objek dalam memori untuk ShippingAddress.

## EXAMPLES

### Contoh 1: Membuat objek alamat pengiriman
```powershell
$ShippingDetails = New-AzEdgeOrderShippingAddressObject -StreetAddress1 "101 TOWNSEND ST" -StateOrProvince "CA" -Country "US" -City "San Francisco" -PostalCode "94107" -AddressType "Commercial"

$ShippingDetails | Format-List
```

```output
AddressType     : Commercial
City            : San Francisco
CompanyName     :
Country         : US
PostalCode      : 94107
StateOrProvince : CA
StreetAddress1  : 101 TOWNSEND ST
StreetAddress2  :
StreetAddress3  :
ZipExtendedCode :
```

Membuat objek alamat pengiriman dalam memori

## PARAMETERS

### -AddressType
Jenis alamat.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.EdgeOrder.Support.AddressType
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Kota
Nama Kota.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CompanyName
Nama perusahaan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Negara
Nama Negara.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PostalCode
Kode pos.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StateOrProvince
Nama Negara Bagian atau Provinsi.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StreetAddress1
Alamat Jalan baris 1.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StreetAddress2
Alamat Jalan baris 2.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StreetAddress3
Alamat Jalan baris 3.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ZipExtendedCode
Kode Pos yang diperluas.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.EdgeOrder.Models.Api20211201.ShippingAddress

## NOTES

ALIAS

## RELATED LINKS

