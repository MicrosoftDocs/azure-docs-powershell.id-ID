---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
ms.assetid: A9E43722-DEE2-4A5C-A3F6-8DA6612735AC
online version: ''
schema: 2.0.0
ms.openlocfilehash: 7259fd96e1a58a6e9498ad7059d6b3fd13046e3502b3d7c9e8c3bbc5d431a08b
ms.sourcegitcommit: 49f8ffe5d8e08ba3d22e3b2e76db0e54dd55d4f0
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/11/2021
ms.locfileid: "132417716"
---
# Set-AzureAclConfig

## SYNOPSIS
Mengubah objek konfigurasi ACL.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

### AddRule
```
Set-AzureAclConfig [-AddRule] [-Action] <String> [-RemoteSubnet] <String> [[-Order] <Int32>]
 [[-Description] <String>] -ACL <NetworkAclObject> [-InformationAction <ActionPreference>]
 [-InformationVariable <String>] [<CommonParameters>]
```

### RemoveRule
```
Set-AzureAclConfig [-RemoveRule] [-RuleId] <Int32> -ACL <NetworkAclObject>
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

### SetRule
```
Set-AzureAclConfig [-SetRule] [-RuleId] <Int32> [[-Action] <String>] [[-RemoteSubnet] <String>]
 [[-Order] <Int32>] [[-Description] <String>] -ACL <NetworkAclObject> [-InformationAction <ActionPreference>]
 [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzureAclConfig** mengubah objek konfigurasi daftar kontrol akses (ACL, Access Control List) dari konfigurasi komputer virtual Azure yang sudah ada.

## EXAMPLES

### Contoh 1: Menambahkan aturan ke konfigurasi ACL baru
```
PS C:\> $Acl = New-AzureAclConfig
PS C:\> Set-AzureAclConfig -AddRule -ACL $Acl -Action Permit -RemoteSubnet "172.0.0.0/8" -Order 100 -Description "Permit ACL rule"
```

Perintah pertama membuat konfigurasi ACL, lalu menyimpannya di $Acl variabel.

Perintah kedua menambahkan aturan baru ke konfigurasi yang disimpan di $Acl.
Perintah menentukan tindakan, subnet, urutan, dan deskripsi untuk aturan.

### Contoh 2: Mengubah aturan dalam konfigurasi ACL
```
PS C:\> $Acl = Get-AzureVM -ServiceName "ContosoService" -Name "VirtualMachine07" | Get-AzureAclConfig -EndpointName "Web"
PS C:\> Set-AzureAclConfig -SetRule -RuleId 0 -ACL $Acl -Order 102 -Description "Web endpoint rule"
PS C:\> Get-AzureVM -ServiceName "ContosoService" -Name "VirtualMachine07" | Set-AzureEndpoint -ACL $Acl -Name "Web" | Update-AzureVM
```

Perintah pertama mendapatkan mesin virtual bernama VirtualMachine07 dalam layanan yang bernama ContosoService menggunakan cmdlet **Get-AzureVM.**
Perintah melewati objek itu ke cmdlet **Get-AzureAclConfig** menggunakan operator pipeline.
Cmdlet tersebut mendapatkan konfigurasi ACL untuk titik akhir yang bernama Web.
Perintah menyimpan objek konfigurasi ACL di $Acl berbeda.

Perintah kedua mengubah aturan yang memiliki ID 0.
Perintah mengubah urutan dan deskripsi aturan.

Perintah terakhir mengatur objek konfigurasi ACL untuk komputer virtual tersebut menggunakan cmdlet **Set-AzureEndpoint.**
Perintah juga memperbarui mesin virtual tersebut.

### Contoh 3: Menghapus aturan dari konfigurasi ACL
```
PS C:\> $Acl = Get-AzureVM -ServiceName "ContosoService" -Name "VirtualMachine07" | Get-AzureAclConfig -EndpointName "Web"
PS C:\> Set-AzureAclConfig -RemoveRule -ID 0 -ACL $Acl
PS C:\> Get-AzureVM -ServiceName "ContosoService" -Name "VirtualMachine07" | Set-AzureEndpoint -ACL $Acl -Name "Web" | Update-AzureVM
```

Perintah pertama menyimpan objek konfigurasi ACL di $Acl lain.
Ini sama seperti contoh sebelumnya.

Perintah kedua menghapus aturan yang memiliki ID 0 dari konfigurasi ACL dalam $Acl.

Perintah terakhir mengatur objek konfigurasi ACL untuk mesin virtual dan memperbarui mesin virtual tersebut.
Ini sama seperti contoh sebelumnya.

## PARAMETERS

### -ACL
Menentukan objek konfigurasi ACL yang ditentukan cmdlet ini.

```yaml
Type: NetworkAclObject
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Tindakan
Menentukan tindakan untuk aturan yang menambahkan atau mengubah cmdlet ini.
Nilai valid adalah: Izinkan dan Tolak.

```yaml
Type: String
Parameter Sets: AddRule
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: SetRule
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AddRule
Mengindikasikan bahwa cmdlet ini menambahkan aturan pada konfigurasi ACL.

```yaml
Type: SwitchParameter
Parameter Sets: AddRule
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Deskripsi
Menentukan deskripsi untuk aturan yang menambahkan atau mengubah cmdlet ini.

```yaml
Type: String
Parameter Sets: AddRule, SetRule
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InformationAction
Menentukan bagaimana cmdlet merespons kejadian informasi.

Nilai yang dapat diterima untuk parameter ini adalah:

- Lanjutkan
- Abaikan
- Pemeriksaan
- SilentlyContinue
- Stop
- Tangguhkan

```yaml
Type: ActionPreference
Parameter Sets: (All)
Aliases: infa

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InformationVariable
Menentukan variabel informasi.

```yaml
Type: String
Parameter Sets: (All)
Aliases: iv

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Pesanan
Menentukan urutan pemrosesan untuk aturan yang menambahkan atau mengubah cmdlet ini.

```yaml
Type: Int32
Parameter Sets: AddRule, SetRule
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemoteSubnet
Menentukan subnet jarak jauh untuk aturan yang menambahkan atau mengubah cmdlet ini.
Menentukan alamat dalam format Classless Interdomain Routing (CIDR).

```yaml
Type: String
Parameter Sets: AddRule
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: SetRule
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemoveRule
Mengindikasikan bahwa cmdlet ini menghapus aturan dari konfigurasi ACL.

```yaml
Type: SwitchParameter
Parameter Sets: RemoveRule
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RuleId
Menentukan ID aturan yang dihapus atau dimodifikasi cmdlet ini untuk konfigurasi ACL.

```yaml
Type: Int32
Parameter Sets: RemoveRule, SetRule
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SetRule
Menunjukkan bahwa cmdlet ini mengubah aturan dalam konfigurasi ACL.

```yaml
Type: SwitchParameter
Parameter Sets: SetRule
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

[Get-AzureAclConfig](./Get-AzureAclConfig.md)

[Get-AzureVM](./Get-AzureVM.md)

[New-AzureAclConfig](./New-AzureAclConfig.md)

[Remove-AzureAclConfig](./Remove-AzureAclConfig.md)

[Set-AzureEndpoint](./Set-AzureEndpoint.md)

[Update-AzureVM](./Update-AzureVM.md)


