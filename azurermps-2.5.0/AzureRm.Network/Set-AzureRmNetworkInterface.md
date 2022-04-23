---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
Module Name: AzureRM.Network
ms.assetid: DDB38A77-E5C0-47DD-BADD-94488F661CD5
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.network/set-azurermnetworkinterface
schema: 2.0.0
ms.openlocfilehash: 978db7296b9789f738f5b277a4bf3731803fdcd8
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143051741"
---
# Set-AzureRmNetworkInterface

## SYNOPSIS
Mengatur status tujuan untuk antarmuka jaringan.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Set-AzureRmNetworkInterface -NetworkInterface <PSNetworkInterface> [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
**Set-AzureRmNetworkInterface** menetapkan status tujuan untuk antarmuka jaringan Azure.

## EXAMPLES

### Contoh 1: Mengonfigurasi antarmuka jaringan
```
$Nic = Get-AzureRmNetworkInterface -ResourceGroupName "ResourceGroup1" -Name "NetworkInterface1"
$Nic.IpConfigurations[0].PrivateIpAddress = "10.0.1.20"
$Nic.IpConfigurations[0].PrivateIpAllocationMethod = "Static"
$Nic.Tag = @{Name = "Name"; Value = "Value"}
Set-AzureRmNetworkInterface -NetworkInterface $Nic
```

Contoh ini mengonfigurasi antarmuka jaringan.
Perintah pertama mendapatkan antarmuka jaringan bernama NetworkInterface1 dalam grup sumber daya ResourceGroup1.
Perintah kedua mengatur alamat IP privat konfigurasi IP.
Perintah ketiga mengatur metode alokasi IP privat ke Statis.
Perintah keempat mengatur tag pada antarmuka jaringan.
Perintah kelima menggunakan informasi yang disimpan dalam variabel $Nic untuk mengatur antarmuka jaringan.

### Contoh 2: Mengubah pengaturan DNS pada antarmuka jaringan
```
$nic = Get-AzureRmNetworkInterface -ResourceGroupName "ResourceGroup1" -Name "NetworkInterface1"
$nic.DnsSettings.DnsServers.Add("192.168.1.100")
$nic | Set-AzureRmNetworkInterface
```

Perintah pertama mendapatkan antarmuka jaringan bernama NetworkInterface1 yang ada dalam grup sumber daya ResourceGroup1. Perintah kedua menambahkan server DNS 192.168.1.100 ke antarmuka ini. Perintah ketiga menerapkan perubahan ini ke antarmuka jaringan. Untuk menghapus server DNS, ikuti perintah yang tercantum di atas, tetapi ganti ". Tambahkan" dengan ". Hapus" di perintah kedua.

### Contoh 3: Mengaktifkan IP forwading pada antarmuka jaringan
```
$nic = Get-AzureRmNetworkInterface -ResourceGroupName "ResourceGroup1" -Name "NetworkInterface1"
$nic.EnableIPForwarding = 1
$nic | Set-AzureRmNetworkInterface
```

Perintah pertama mendapatkan antarmuka jaringan yang sudah ada yang disebut NetworkInterface1 dan menyimpannya dalam variabel $nic. Perintah kedua mengubah nilai penerusan IP menjadi true. Terakhir, perintah ketiga menerapkan perubahan pada antarmuka jaringan. Untuk menonaktifkan penerusan IP pada antarmuka jaringan, ikuti contoh contoh, tetapi pastikan untuk mengubah perintah kedua menjadi "$nic. EnableIPForwarding = 0".

### Contoh 4: Mengubah subnet antarmuka jaringan
```
$nic = Get-AzureRmNetworkInterface -ResourceGroupName "ResourceGroup1" -Name "NetworkInterface1"
$vnet = Get-AzureRmVirtualNetwork -Name VNet1 -ResourceGroupName crosssubcrossversionpeering
$subnet2 = Get-AzureRmVirtualNetworkSubnetConfig -Name Subnet2 -VirtualNetwork $vnet
$nic.IpConfigurations[0].Subnet.Id = $subnet2.Id
$nic | Set-AzureRmNetworkInterface
```

Perintah pertama mendapatkan antarmuka jaringan NetworkInterface1 dan menyimpannya dalam variabel $nic. Perintah kedua mendapatkan jaringan virtual yang terkait dengan subnet yang akan dikaitkan dengan antarmuka jaringan. Perintah kedua mendapatkan subnet dan menyimpannya dalam variabel $subnet 2. Perintah ketiga mengaitkan alamat IP privat utama antarmuka jaringan dengan subnet baru. Akhirnya perintah terakhir menerapkan perubahan ini pada antarmuka jaringan.

>[!NOTE] 
>Konfigurasi IP harus dinamis sebelum Anda bisa mengubah subnet. Jika Anda memiliki konfigurasi IP statis, ubah ke dinamis sebelum melanjutkan. 

>[!NOTE]
>Jika antarmuka jaringan memiliki beberapa konfigurasi IP, perintah forth harus dilakukan untuk semua konfigurasi IP ini sebelum perintah akhir Set-AzureRmNetworkInterface dijalankan. Hal ini dapat dilakukan seperti dalam perintah ke depan tetapi dengan mengganti "0" dengan angka yang sesuai. Jika antarmuka jaringan memiliki konfigurasi N IP, maka N-1 dari perintah ini harus ada.

### Contoh 5: Mengaitkan/Mengaitkan Grup Keamanan Jaringan ke antarmuka jaringan
```
$nic = Get-AzureRmNetworkInterface -ResourceGroupName "ResourceGroup1" -Name "NetworkInterface1"
$nsg = Get-AzureRmNetworkSecurityGroup -ResourceGroupName "ResourceGroup1" -Name "MyNSG"
$nic.NetworkSecurityGroup = $nsg
$nic | Set-AzureRmNetworkInterface
```

Perintah pertama mendapatkan antarmuka jaringan yang sudah ada yang disebut NetworkInterface1 dan menyimpannya dalam variabel $nic. Perintah kedua mendapatkan grup keamanan jaringan yang sudah ada yang disebut MyNSG dan menyimpannya dalam variabel $nsg. Perintah keempat menetapkan $nsg ke $nic. Akhirnya, perintah kelima menerapkan perubahan pada antarmuka Jaringan. Untuk memisahkan grup keamanan jaringan dari antarmuka jaringan, ganti sederhana $nsg dalam perintah keempat dengan $null.

## PARAMETERS

### -AsJob
Menjalankan cmdlet di latar belakang

```yaml
Type: SwitchParameter
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
Type: IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NetworkInterface
Menentukan objek **NetworkInterface** yang mewakili status tujuan untuk antarmuka jaringan.

```yaml
Type: PSNetworkInterface
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### PSNetworkInterface
Parameter 'NetworkInterface' menerima nilai tipe 'PSNetworkInterface' dari pipeline

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSNetworkInterface

## NOTES

## RELATED LINKS

[Get-AzureRmNetworkInterface](./Get-AzureRmNetworkInterface.md)

[Get-AzureRmNetworkInterface](./Get-AzureRmNetworkInterface.md)

[Baru-AzureRmNetworkInterface](./New-AzureRmNetworkInterface.md)

[Hapus-AzureRmNetworkInterface](./Remove-AzureRmNetworkInterface.md)
