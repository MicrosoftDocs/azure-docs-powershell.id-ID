---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.Network.dll-Help.xml
ms.assetid: C7F08804-E177-4BC5-8F0E-DEC1B467C4BB
online version: ''
schema: 2.0.0
ms.openlocfilehash: a2b1b94a03d183180bbf4de7fa40f674dd1383f3
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142786816"
---
# Update-AzureApplicationGateway

## SYNOPSIS
Memperbarui gateway aplikasi.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Update-AzureApplicationGateway -Name <String> [-VnetName <String>]
 [-Subnets <System.Collections.Generic.List`1[System.String]>] [-InstanceCount <UInt32>]
 [-GatewaySize <String>] [-Description <String>] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Update-AzureApplicationGateway** memperbarui gateway aplikasi yang sudah ada.

## EXAMPLES

### Contoh 1: Mengubah gateway aplikasi dengan menggunakan namanya
```
PS C:\> Stop-AzureApplicationGateway -Name "ApplicationGateway06"
PS C:\> Update-AzureApplicationGateway -Name "ApplicationGateway06" -VnetName "VirutalNetwork18" -Subnets @("Subnet05", "Subnet06")
```

Perintah pertama menghentikan gateway aplikasi bernama ApplicationGateway06.
Gateway aplikasi harus dihentikan sebelum Anda bisa mengubah jaringan virtual atau subnet.

Perintah kedua mengubah subnet virtual dan subnet untuk gateway aplikasi bernama ApplicationGateway06.

### Contoh 2: Mengubah properti tambahan gateway aplikasi
```
PS C:\> Update-AzureApplicationGateway -Name "ApplicationGateway06" -InstanceCount 2 -GatewaySize "Large" -Description "Updated application gateway"
```

Perintah ini mengubah jumlah instans, ukuran gateway, dan deskripsi untuk gateway aplikasi bernama ApplicationGateway06.
Perintah ini tidak mengubah jaringan virtual atau subnet untuk gateway aplikasi.
Oleh karena itu, Anda tidak perlu menghentikan gateway aplikasi sebelum menjalankan perintah ini.

### Contoh 3: Memodifikasi gateway aplikasi dengan menggunakan saluran
```
PS C:\> $ApplicationGateway = Get-AzureApplicationGateway -Name "ApplicationGateway06"
PS C:\> $ApplicationGateway.GatewaySize = "Medium"
PS C:\> $ApplicationGateway | Update-AzureApplicationGateway
```

Perintah pertama mendapatkan gateway aplikasi bernama ApplicationGateway06 menggunakan cmdlet **Get-AzureApplicationGateway** .
Perintah menyimpannya dalam variabel $ApplicationGateway.

Perintah kedua menetapkan properti **GatewaySize** nilai Medium.

Perintah akhir melewati $ApplicationGateway yang diperbarui ke cmdlet saat ini.

## PARAMETERS

### -Deskripsi
Menentukan deskripsi yang ditetapkan cmdlet ini ke gateway aplikasi.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -GatewaySize
Menentukan ukuran yang ditetapkan cmdlet ini ke gateway aplikasi.
Nilai yang valid adalah:

- Kecil
- Menengah
- Besar

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InstanceCount
Menentukan jumlah instans yang ditetapkan cmdlet ini ke gateway aplikasi.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Nama
Menentukan nama gateway aplikasi yang diperbarui cmdlet ini.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Profil
Menentukan profil Azure tempat cmdlet ini dibaca.
Jika Anda tidak menentukan profil, cmdlet ini akan dibaca dari profil default lokal.

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

### -Subnets
Menentukan array subnet tempat cmdlet ini menyebarkan gateway aplikasi.

Anda tidak bisa memperbarui subnet saat gateway aplikasi sedang berjalan.
Untuk menghentikan gateway aplikasi, gunakan cmdlet Stop-AzureApplicationGateway.

```yaml
Type: System.Collections.Generic.List`1[System.String]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VnetName
Menentukan jaringan virtual tempat cmdlet ini menyebarkan gateway aplikasi.

Anda tidak bisa memperbarui jaringan virtual saat gateway aplikasi sedang berjalan.
Untuk menghentikan gateway aplikasi, gunakan **Stop-AzureApplicationGateway**.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.WindowsAzure.Management.ApplicationGateway.Models.ApplicationGatewayOperationResponse

## NOTES

## RELATED LINKS

[Get-AzureApplicationGateway](./Get-AzureApplicationGateway.md)

[AzureApplicationGateway baru](./New-AzureApplicationGateway.md)

[Hapus-AzureApplicationGateway](./Remove-AzureApplicationGateway.md)

[Start-AzureApplicationGateway](./Start-AzureApplicationGateway.md)

[Stop-AzureApplicationGateway](./Stop-AzureApplicationGateway.md)
