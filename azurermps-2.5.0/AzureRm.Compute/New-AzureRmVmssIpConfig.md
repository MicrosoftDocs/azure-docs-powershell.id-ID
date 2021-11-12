---
external help file: Microsoft.Azure.Commands.Compute.dll-Help.xml
Module Name: AzureRM.Compute
ms.assetid: 92F192A5-F75E-4EFE-B2D2-B0DF0B78D3B5
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.compute/new-azurermvmssipconfig
schema: 2.0.0
ms.openlocfilehash: ac825a59f952fe27c1145d41692b8241e62de08f727792c1f369ca3c7037c257
ms.sourcegitcommit: 49f8ffe5d8e08ba3d22e3b2e76db0e54dd55d4f0
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/11/2021
ms.locfileid: "132416150"
---
# New-AzureRmVmssIpConfig

## SYNOPSIS
Membuat konfigurasi IP untuk antarmuka jaringan VMSS.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
New-AzureRmVmssIpConfig [[-Name] <String>] [[-Id] <String>] [[-SubnetId] <String>]
 [[-ApplicationGatewayBackendAddressPoolsId] <String[]>] [[-LoadBalancerBackendAddressPoolsId] <String[]>]
 [[-LoadBalancerInboundNatPoolsId] <String[]>] [-Primary] [-PrivateIPAddressVersion <String>]
 [-PublicIPAddressConfigurationName <String>] [-PublicIPAddressConfigurationIdleTimeoutInMinutes <Int32>]
 [-DnsSetting <String>] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzureRmVmssIpConfig** membuat objek konfigurasi IP untuk antarmuka jaringan Virtual Machine Scale Set (VMSS).
Tentukan konfigurasi dari cmdlet ini sebagai parameter *IPConfiguration* cmdlet Add-AzureRmVmssNetworkInterfaceConfiguration.

## EXAMPLES

### Contoh 1: Membuat objek konfigurasi IP untuk antarmuka VMSS
```
PS C:\> $IPConfiguration = New-AzureRmVmssIPConfig -Name "ContosoVmssInterface02" -SubnetId $SubnetId
```

Perintah ini membuat objek konfigurasi IP bernama ContosoVmssInterface02.
Perintah menggunakan ID subnet yang ditentukan sebelumnya yang disimpan di $SubnetId.
Perintah menyimpan pengaturan konfigurasi di variabel $IPConfiguration digunakan nanti dengan **Add-AzureRmVmssNetworkInterfaceConfiguration**.

### Contoh 2: Buat objek konfigurasi IP yang mencakup pengaturan pool NAT
```
PS C:\> $IPConfiguration = New-AzureRmVmssIPConfig -Name "ContosoVmssInterface03" -LoadBalancerInboundNatPoolsId $expectedLb.InboundNatPools[0].Id -LoadBalancerBackendAddressPoolsId $expectedLb.BackendAddressPools[0].Id -SubnetId $SubnetId
```

Perintah ini akan membuat objek konfigurasi IP bernama ContosoVmssInterface03, lalu menyimpannya dalam variabel $IPConfiguration untuk digunakan nanti.
Perintah menggunakan ID subnet yang ditentukan sebelumnya yang disimpan di $SubnetId.
Perintah menyimpan pengaturan konfigurasi di variabel $IPConfiguration digunakan nanti.
Perintah menentukan nilai untuk parameter *LoadBalancerInboundNatPoolsId* dan *LoadBalancerBackendAddressPoolsId.*

## PARAMETERS

### -ApplicationGatewayBackendAddressPoolsId
Menentukan array referensi ke alamat backend yang memuat keseimbangan.
Kumpulan skala bisa merujuk ke kolam renang alamat backend dari satu publik dan satu penyeimbang muat internal.
Beberapa kumpulan skala tidak dapat menggunakan penyeimbang muat yang sama.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

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

### -DnsSetting
Pengaturan dns yang akan diterapkan pada alamat publicIP.
Label nama domain dari pengaturan Dns yang akan diterapkan pada alamat publicIP.
Penggabungan label nama domain dan indeks vm akan menjadi label nama domain dari sumber daya Alamat IP Publik yang akan dibuat.

```yaml
Type: String
Parameter Sets: (All)
Aliases: PublicIPAddressDomainNameLabel

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Id
Menentukan ID.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -LoadBalancerBackendAddressPoolsId
Menentukan array referensi ke kolam renang nat alamat jaringan masuk (NAT, Incoming Network Address Translation) dari keseimbangan muat.
Kumpulan skala dapat merujuk ke kolam renang NAT yang masuk dari satu publik dan satu penyeimbang muat internal.
Beberapa kumpulan skala tidak dapat menggunakan penyeimbang muat yang sama.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -LoadBalancerInboundNatPoolsId
Menentukan array referensi ke kolam renang NAT yang masuk dari keseimbangan muat.
Kumpulan skala dapat merujuk ke kolam renang NAT yang masuk dari satu publik dan satu penyeimbang muat internal.
Beberapa kumpulan skala tidak dapat menggunakan penyeimbang muat yang sama.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 5
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Nama
Menentukan nama konfigurasi IP.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Utama
Menentukan Konfigurasi IP utama jika antarmuka jaringan memiliki lebih dari satu Konfigurasi IP.

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

### -PrivateIPAddressVersion
Tentukan konfigurasi ip adalah IPv4 atau IPv6. Default dianggap sebagai IPv4.  Nilai yang mungkin adalah: 'IPv4' dan 'IPv6'.

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

### -PublicIPAddressConfigurationIdleTimeoutInMinutes
Waktu diam habis dari alamat IP publik.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: PublicIPAddressIdleTimeoutInMinutes

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PublicIPAddressConfigurationName
Nama konfigurasi alamat publicIP.

```yaml
Type: String
Parameter Sets: (All)
Aliases: PublicIPAddressName

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SubnetId
Menentukan ID subnet yang digunakan untuk membuat antarmuka jaringan VMSS.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Konfirmasi
Meminta konfirmasi Anda sebelum menjalankan cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan. Cmdlet tidak berjalan.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### Tidak ada
Cmdlet ini tidak menerima input apa pun.

## OUTPUTS

### Microsoft.Azure.Management.Compute.Models.VirtualMachineScaleSetIPConfiguration

## CATATAN

## RELATED LINKS

[Add-AzureRmVmssNetworkInterfaceConfiguration](./Add-AzureRmVmssNetworkInterfaceConfiguration.md)


