---
external help file: ''
Module Name: Az.DataBox
online version: https://docs.microsoft.com/powershell/module/az.DataBox/new-AzDataBoxShippingAddressObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataBox/help/New-AzDataBoxShippingAddressObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataBox/help/New-AzDataBoxShippingAddressObject.md
ms.openlocfilehash: 37bdab35ef1ad09fbe5942b416f6a8b2e553a811
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144205079"
---
# New-AzDataBoxShippingAddressObject

## SYNOPSIS
Buat objek dalam memori untuk ShippingAddress.

## SYNTAX

```
New-AzDataBoxShippingAddressObject -Country <String> -StreetAddress1 <String> [-AddressType <AddressType>]
 [-City <String>] [-CompanyName <String>] [-PostalCode <String>] [-StateOrProvince <String>]
 [-StreetAddress2 <String>] [-StreetAddress3 <String>] [-ZipExtendedCode <String>] [<CommonParameters>]
```

## DESCRIPTION
Buat objek dalam memori untuk ShippingAddress.

## EXAMPLES

### Contoh 1: Objek Alamat Pengiriman 
```powershell
$ShippingDetails = New-AzDataBoxShippingAddressObject -StreetAddress1 "101 TOWNSEND ST" -StateOrProvince "CA" -Country "US" -City "San Francisco" -PostalCode "94107" -AddressType "Commercial"
$ShippingDetails
```

```output
AddressType City          CompanyName Country PostalCode StateOrProvince StreetAddress1  StreetAddress2 StreetAddress3 ZipExtendedCode
----------- ----          ----------- ------- ---------- --------------- --------------  -------------- -------------- ---------------
Commercial  San Francisco             US      94107      CA              101 TOWNSEND ST
```

Membuat objek alamat pengiriman dalam memori

## PARAMETERS

### -AddressType
Jenis alamat.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.DataBox.Support.AddressType
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

### Microsoft.Azure.PowerShell.Cmdlets.DataBox.Models.Api20210301.ShippingAddress

## NOTES

ALIAS

## RELATED LINKS

