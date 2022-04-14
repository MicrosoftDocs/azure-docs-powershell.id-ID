---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.Network.dll-Help.xml
ms.assetid: 36DA2BF9-091E-4A2C-B5E1-07B4D2E482FC
online version: ''
schema: 2.0.0
ms.openlocfilehash: 9e056d87d340ace547a15d62e9cca3062a067fdb
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141816548"
---
# New-AzureVNetGateway

## SYNOPSIS
Membuat gateway VPN di jaringan virtual.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
New-AzureVNetGateway -VNetName <String> [-GatewayType <String>] [-GatewaySKU <String>]
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzureVNetGateway** membuat gateway jaringan privat virtual (VPN) dalam jaringan virtual.
Anda juga bisa menentukan SKU gateway, baik Default, Standar, atau HighPerformance.
Anda dapat menentukan tipe, baik StaticRouting atau DynamicRouting.

## EXAMPLES

### Contoh 1: Membuat gateway jaringan virtual
```
PS C:\> New-AzureVNetGateway -VNetName "ContosoVN07" -GatewayType "DynamicRouting" -GatewaySKU "Default"
```

Perintah ini membuat gateway jaringan virtual untuk jaringan virtual bernama ContosoVN07.
Gateway adalah SKU Default dan menggunakan perutean dinamis.

## PARAMETERS

### -GatewaysKU
Menentukan SKU gateway jaringan virtual yang dibuat cmdlet ini.
Nilai yang valid adalah: 

- Default 
- Standar 
- HighPerformance

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

### -GatewayType
Menentukan tipe gateway yang dibuat cmdlet ini.
Nilai yang valid adalah: 

- StaticRouting 
- DynamicRouting

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

### -VNetName
Menentukan jaringan virtual tempat cmdlet ini menambahkan gateway jaringan virtual.

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

## CATATAN

## RELATED LINKS

[Get-AzureVNetGateway](./Get-AzureVNetGateway.md)

[Hapus-AzureVNetGateway](./Remove-AzureVNetGateway.md)

[Mengatur ulang AzureVNetGateway](./Reset-AzureVNetGateway.md)

[Mengubah ukuran AzureVNetGateway](./Resize-AzureVNetGateway.md)

[Set-AzureVNetGatewayKey](./Set-AzureVNetGatewayKey.md)


