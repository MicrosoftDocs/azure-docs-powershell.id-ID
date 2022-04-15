---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.Network.dll-Help.xml
ms.assetid: 70899AAC-BF64-4FFA-9DAF-92E859D0B271
online version: ''
schema: 2.0.0
ms.openlocfilehash: f78768e805b66fa2b020946426e36ce1cee434fb
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142334518"
---
# Set-AzureVNetGateway

## SYNOPSIS
Mengaktifkan atau menonaktifkan gateway VPN untuk jaringan virtual Azure.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

### Koneksi (Default)
```
Set-AzureVNetGateway [-Connect] -VNetName <String> -LocalNetworkSiteName <String> [-Profile <AzureSMProfile>]
 [<CommonParameters>]
```

### Lepaskan
```
Set-AzureVNetGateway [-Disconnect] -VNetName <String> -LocalNetworkSiteName <String>
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzureVNetGateway** mengaktifkan atau menonaktifkan gateway jaringan privat virtual (VPN) untuk jaringan virtual Azure.
Gateway jaringan virtual adalah titik akhir VPN untuk menyambungkan ke jaringan virtual.
Tentukan parameter *Koneksi* atau *Putuskan sambungan* untuk mengaktifkan atau menonaktifkan koneksi VPN antara situs jaringan lokal lokal dan jaringan virtual.

## EXAMPLES

### Contoh 1: Mengaktifkan gateway jaringan virtual untuk jaringan virtual
```
PS C:\> Set-AzureVNetGateway -Connect -VnetName "ContosoProdNet" -LocalNetworkSiteName "ContosoBranchOffice"
```

Perintah ini memungkinkan gateway jaringan virtual antara jaringan virtual Azure bernama ContosoProdNet dan perangkat VPN untuk situs jaringan lokal bernama ContosoBranchOffice.

### Contoh 2: Menonaktifkan gateway jaringan virtual untuk jaringan virtual
```
PS C:\> Set-AzureVNetGateway -Disconnect -VnetName "ContosoProdNet" -LocalNetworkSiteName "ContosoBranchOffice"
```

Perintah ini menonaktifkan gateway jaringan virtual antara jaringan virtual Azure bernama ContosoProdNet dan perangkat VPN untuk situs jaringan lokal bernama ContosoBranchOffice.

## PARAMETERS

### -Koneksi
Menunjukkan bahwa cmdlet ini mengaktifkan koneksi VPN antara jaringan virtual dan situs jaringan lokal.

```yaml
Type: SwitchParameter
Parameter Sets: Connect
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Putuskan sambungan
Menunjukkan bahwa cmdlet ini menonaktifkan koneksi VPN antara jaringan virtual dan situs jaringan lokal.

```yaml
Type: SwitchParameter
Parameter Sets: Disconnect
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LocalNetworkSiteName
Menentukan nama situs jaringan lokal lokal tempat cmdlet ini mengaktifkan atau menonaktifkan koneksi VPN.

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
Menentukan jaringan maya di mana cmdlet ini mengaktifkan atau menon-fungsikan sambungan VPN.

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

[AzureVNetGateway baru](./New-AzureVNetGateway.md)

[Hapus-AzureVNetGateway](./Remove-AzureVNetGateway.md)

[Mengatur ulang AzureVNetGateway](./Reset-AzureVNetGateway.md)

[Mengubah ukuran AzureVNetGateway](./Resize-AzureVNetGateway.md)


