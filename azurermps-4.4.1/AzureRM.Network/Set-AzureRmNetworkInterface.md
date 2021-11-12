---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
Module Name: AzureRM.Network
ms.assetid: DDB38A77-E5C0-47DD-BADD-94488F661CD5
online version: ''
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Network/Commands.Network/help/Set-AzureRmNetworkInterface.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Network/Commands.Network/help/Set-AzureRmNetworkInterface.md
ms.openlocfilehash: 8403a2e26bbc149db35c9c20cdea3075adb88492
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132427868"
---
# Set-AzureRmNetworkInterface

## SYNOPSIS
Menetapkan status tujuan untuk antarmuka jaringan.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Set-AzureRmNetworkInterface -NetworkInterface <PSNetworkInterface> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
**Set-AzureRmNetworkInterface** mengatur status tujuan untuk antarmuka jaringan Azure.

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
Perintah pertama mendapatkan antarmuka jaringan yang bernama NetworkInterface1 dalam grup sumber daya ResourceGroup1.
Perintah kedua mengatur alamat IP privat konfigurasi IP.
Perintah ketiga mengatur metode alokasi IP privat menjadi Statis.
Perintah keempat mengatur tag pada antarmuka jaringan.
Perintah kelima menggunakan informasi yang disimpan di $Nic variabel untuk mengatur antarmuka jaringan.

### Contoh 2: Mengubah pengaturan DNS pada antarmuka jaringan
```
$nic = Get-AzureRmNetworkInterface -ResourceGroupName "ResourceGroup1" -Name "NetworkInterface1"
$nic.DnsSettings.DnsServers.Add("192.168.1.100")
$nic | Set-AzureRmNetworkInterface
```

Perintah pertama mendapatkan antarmuka jaringan bernama NetworkInterface1 yang ada di dalam grup sumber daya ResourceGroup1. Perintah kedua menambahkan SERVER DNS 192.168.1.100 ke antarmuka ini. Perintah ketiga menerapkan perubahan ini ke antarmuka jaringan. Untuk menghapus server DNS, ikuti perintah yang tercantum di atas, tetapi ganti ". Tambahkan" dengan ". Hapus" di perintah kedua.

### Contoh 3: Enable IP for enkripsi on a network interface
```
$nic = Get-AzureRmNetworkInterface -ResourceGroupName "ResourceGroup1" -Name "NetworkInterface1"
$nic.EnableIPForwarding = 1
$nic | Set-AzureRmNetworkInterface
```

Perintah pertama mendapatkan antarmuka jaringan yang sudah ada yang disebut NetworkInterface1 dan menyimpannya dalam $nic variabel. Perintah kedua akan mengubah nilai penerusan IP menjadi true. Terakhir, perintah ketiga menerapkan perubahan pada antarmuka jaringan. Untuk menonaktifkan penerusan IP pada antarmuka jaringan, ikuti contoh contoh, namun pastikan untuk mengubah perintah kedua ke "$nic. EnableIPForwarding = 0".

### Contoh 4: Mengubah subnet antarmuka jaringan
```
$nic = Get-AzureRmNetworkInterface -ResourceGroupName "ResourceGroup1" -Name "NetworkInterface1"
$vnet = Get-AzureRmVirtualNetwork -Name VNet1 -ResourceGroupName crosssubcrossversionpeering
$subnet2 = Get-AzureRmVirtualNetworkSubnetConfig -Name Subnet2 -VirtualNetwork $vnet
$nic.IpConfigurations[0].Subnet.Id = $subnet2.Id
$nic | Set-AzureRmNetworkInterface
```

Perintah pertama mendapatkan antarmuka jaringan NetworkInterface1 dan menyimpannya di $nic variabel. Perintah kedua mendapatkan jaringan virtual yang terkait dengan subnet yang akan dikaitkan dengan antarmuka jaringan. Perintah kedua akan mendapatkan subnet dan menyimpannya dalam $subnet 2. Perintah ketiga terkait alamat IP privat utama antarmuka jaringan dengan subnet baru. Akhirnya perintah terakhir menerapkan perubahan ini pada antarmuka jaringan.

>[!NOTE] 
>Konfigurasi IP harus dinamis sebelum Anda dapat mengubah subnet. Jika Anda memiliki konfigurasi IP statis, ubah lalu menjadi dinamis sebelum melanjutkan. 

>[!NOTE]
>Jika antarmuka jaringan memiliki beberapa konfigurasi IP, perintah sebagai contoh harus dilakukan untuk semua konfigurasi IP ini sebelum Set-AzureRmNetworkInterface akhir dijalankan. Ini bisa dilakukan seperti di dalam perintah maju tapi dengan mengganti "0" dengan angka yang tepat. Jika antarmuka jaringan memiliki konfigurasi IP N, N-1 dari perintah ini harus ada.

### Contoh 5: Kaitkan/Dissociate Grup Keamanan Jaringan ke antarmuka jaringan
```
$nic = Get-AzureRmNetworkInterface -ResourceGroupName "ResourceGroup1" -Name "NetworkInterface1"
$nsg = Get-AzureRmNetworkSecurityGroup -ResourceGroupName "ResourceGroup1" -Name "MyNSG"
$nic.NetworkSecurityGroup = $nsg
$nic | Set-AzureRmNetworkInterface
```

Perintah pertama mendapatkan antarmuka jaringan yang sudah ada yang disebut NetworkInterface1 dan menyimpannya dalam $nic variabel. Perintah kedua mendapatkan grup keamanan jaringan yang sudah ada yang disebut MyNSG dan menyimpannya di $nsg jaringan. Perintah di depannya menetapkan $nsg ke $nic. Terakhir, perintah kelima menerapkan perubahan pada antarmuka Jaringan. Untukssociate grup keamanan jaringan dari antarmuka jaringan, sederhana ganti $nsg di baris sebagainya dengan $null.

## PARAMETERS

### -NetworkInterface
Menentukan objek **NetworkInterface** yang mewakili status tujuan untuk antarmuka jaringan.

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

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### PSNetworkInterface
Parameter 'NetworkInterface' menerima nilai tipe 'PSNetworkInterface' dari saluran

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSNetworkInterface

## CATATAN

## RELATED LINKS

[Get-AzureRmNetworkInterface](./Get-AzureRmNetworkInterface.md)

[Get-AzureRmNetworkInterface](./Get-AzureRmNetworkInterface.md)

[New-AzureRmNetworkInterface](./New-AzureRmNetworkInterface.md)

[Remove-AzureRmNetworkInterface](./Remove-AzureRmNetworkInterface.md)
