---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
ms.assetid: DDB38A77-E5C0-47DD-BADD-94488F661CD5
online version: https://docs.microsoft.com/powershell/module/az.network/set-aznetworkinterface
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Set-AzNetworkInterface.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Set-AzNetworkInterface.md
ms.openlocfilehash: bdb8479f1a540585d86d77f58db7698361248f36
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142431044"
---
# Set-AzNetworkInterface

## SYNOPSIS
Memperbarui antarmuka jaringan.

## SYNTAX

```
Set-AzNetworkInterface -NetworkInterface <PSNetworkInterface> [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
**Set-AzNetworkInterface** memperbarui antarmuka jaringan.

## EXAMPLES

### Contoh 1: Mengonfigurasi antarmuka jaringan
```powershell
$Nic = Get-AzNetworkInterface -ResourceGroupName "ResourceGroup1" -Name "NetworkInterface1"
$Nic.IpConfigurations[0].PrivateIpAddress = "10.0.1.20"
$Nic.IpConfigurations[0].PrivateIpAllocationMethod = "Static"
$Nic.Tag = @{Name = "Name"; Value = "Value"}
Set-AzNetworkInterface -NetworkInterface $Nic
```

Contoh ini mengonfigurasi antarmuka jaringan.
Perintah pertama mendapatkan antarmuka jaringan bernama NetworkInterface1 dalam grup sumber daya ResourceGroup1.
Perintah kedua mengatur alamat IP privat konfigurasi IP.
Perintah ketiga mengatur metode alokasi IP privat ke Statis.
Perintah keempat mengatur tag pada antarmuka jaringan.
Perintah kelima menggunakan informasi yang disimpan dalam variabel $Nic untuk mengatur antarmuka jaringan.

### Contoh 2: Mengubah pengaturan DNS pada antarmuka jaringan
```powershell
$nic = Get-AzNetworkInterface -ResourceGroupName "ResourceGroup1" -Name "NetworkInterface1"
$nic.DnsSettings.DnsServers.Add("192.168.1.100")
$nic | Set-AzNetworkInterface
```

Perintah pertama mendapatkan antarmuka jaringan bernama NetworkInterface1 yang ada dalam grup sumber daya ResourceGroup1. Perintah kedua menambahkan server DNS 192.168.1.100 ke antarmuka ini. Perintah ketiga menerapkan perubahan ini ke antarmuka jaringan. Untuk menghapus server DNS, ikuti perintah yang tercantum di atas, tetapi ganti ". Tambahkan" dengan ". Hapus" di perintah kedua.

### Contoh 3: Mengaktifkan penerusan IP pada antarmuka jaringan
```powershell
$nic = Get-AzNetworkInterface -ResourceGroupName "ResourceGroup1" -Name "NetworkInterface1"
$nic.EnableIPForwarding = 1
$nic | Set-AzNetworkInterface
```

Perintah pertama mendapatkan antarmuka jaringan yang sudah ada yang disebut NetworkInterface1 dan menyimpannya dalam variabel $nic. Perintah kedua mengubah nilai penerusan IP menjadi true. Terakhir, perintah ketiga menerapkan perubahan pada antarmuka jaringan. Untuk menonaktifkan penerusan IP pada antarmuka jaringan, ikuti contoh contoh, tetapi pastikan untuk mengubah perintah kedua menjadi "$nic. EnableIPForwarding = 0".

### Contoh 4: Mengubah subnet antarmuka jaringan
```powershell
$nic = Get-AzNetworkInterface -ResourceGroupName "ResourceGroup1" -Name "NetworkInterface1"
$vnet = Get-AzVirtualNetwork -Name VNet1 -ResourceGroupName crosssubcrossversionpeering
$subnet2 = Get-AzVirtualNetworkSubnetConfig -Name Subnet2 -VirtualNetwork $vnet
$nic.IpConfigurations[0].Subnet.Id = $subnet2.Id
$nic | Set-AzNetworkInterface
```

Perintah pertama mendapatkan antarmuka jaringan NetworkInterface1 dan menyimpannya dalam variabel $nic. Perintah kedua mendapatkan jaringan virtual yang terkait dengan subnet yang akan dikaitkan dengan antarmuka jaringan. Perintah kedua mendapatkan subnet dan menyimpannya dalam variabel $subnet 2. Perintah ketiga mengaitkan alamat IP privat utama antarmuka jaringan dengan subnet baru. Akhirnya perintah terakhir menerapkan perubahan ini pada antarmuka jaringan.
>[!NOTE] 
>Konfigurasi IP harus dinamis sebelum Anda bisa mengubah subnet. Jika Anda memiliki konfigurasi IP statis, ubah ke dinamis sebelum melanjutkan. 
>[!NOTE]
>Jika antarmuka jaringan memiliki beberapa konfigurasi IP, perintah keempat harus dilakukan untuk semua konfigurasi IP ini sebelum perintah akhir Set-AzNetworkInterface dijalankan. Hal ini dapat dilakukan seperti dalam perintah keempat tetapi dengan mengganti "0" dengan angka yang sesuai. Jika antarmuka jaringan memiliki konfigurasi N IP, maka N-1 dari perintah ini harus ada.

### Contoh 5: Mengaitkan/Mengaitkan Grup Keamanan Jaringan ke antarmuka jaringan
```powershell
$nic = Get-AzNetworkInterface -ResourceGroupName "ResourceGroup1" -Name "NetworkInterface1"
$nsg = Get-AzNetworkSecurityGroup -ResourceGroupName "ResourceGroup1" -Name "MyNSG"
$nic.NetworkSecurityGroup = $nsg
$nic | Set-AzNetworkInterface
```

Perintah pertama mendapatkan antarmuka jaringan yang sudah ada yang disebut NetworkInterface1 dan menyimpannya dalam variabel $nic. Perintah kedua mendapatkan grup keamanan jaringan yang sudah ada yang disebut MyNSG dan menyimpannya dalam variabel $nsg. Perintah ketiga menetapkan $nsg ke $nic. Terakhir, perintah keempat menerapkan perubahan pada antarmuka Jaringan. Untuk memisahkan grup keamanan jaringan dari antarmuka jaringan, ganti sederhana $nsg di perintah ketiga dengan $null.

## PARAMETERS

### -AsJob
Menjalankan cmdlet di latar belakang

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure.

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

### -NetworkInterface
Menentukan objek antarmuka jaringan yang mewakili status di mana antarmuka jaringan harus disetel.

```yaml
Type: Microsoft.Azure.Commands.Network.Models.PSNetworkInterface
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Network.Models.PSNetworkInterface

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSNetworkInterface

## CATATAN

## RELATED LINKS

[Get-AzNetworkInterface](./Get-AzNetworkInterface.md)

[Get-AzNetworkInterface](./Get-AzNetworkInterface.md)

[New-AzNetworkInterface](./New-AzNetworkInterface.md)

[Remove-AzNetworkInterface](./Remove-AzNetworkInterface.md)
