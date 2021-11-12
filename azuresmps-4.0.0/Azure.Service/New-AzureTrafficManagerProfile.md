---
external help file: Microsoft.WindowsAzure.Commands.TrafficManager.dll-Help.xml
ms.assetid: 2287E103-442D-47FB-8279-0AE5936412C9
online version: ''
schema: 2.0.0
ms.openlocfilehash: 72c0a9de4abce4a19ffbd9ec9006be1949b39436
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132424116"
---
# New-AzureTrafficManagerProfile

## SYNOPSIS
Membuat profil Traffic Manager anda.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
New-AzureTrafficManagerProfile -Name <String> -DomainName <String> -LoadBalancingMethod <String>
 -MonitorPort <Int32> -MonitorProtocol <String> -MonitorRelativePath <String> -Ttl <Int32>
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzureTrafficManagerProfile** membuat Microsoft Azure Traffic Manager profil.

Setelah membuat profil tempat Anda mengatur nilai *LoadBalancingMethod* ke "Failover", Anda dapat menentukan urutan failover titik akhir yang ditambahkan ke profil menggunakan cmdlet Add-AzureTrafficManagerEndpoint.
Untuk informasi selengkapnya, lihat Contoh 2 di bawah.

## EXAMPLES

### Contoh 1: Membuat Traffic Manager profil
```
PS C:\>New-AzureTrafficManagerProfile -Name "MyProfile" -DomainName "My.profile.trafficmanager.net" -LoadBalancingMethod "RoundRobin" -Ttl 30 -MonitorProtocol "Http" -MonitorPort 80 -MonitorRelativePath "/"
```

Perintah ini akan membuat profil Traffic Manager bernama MyProfile pada domain Traffic Manager tertentu dengan metode penyeimbangan beban Pekerjaan Bulat, TTL 30 detik, protokol pemantauan HTTP, memantau port 80, dan dengan jalur yang ditentukan.

### Contoh 2: Urutkan ulang titik akhir untuk urutan failover yang diinginkan
```
PS C:\>$Profile = Get-AzureTrafficManagerProfile -Name "MyProfile"
PS C:\> $Profile.Endpoints[0],$Profile.Endpoints[1] = $Profile.Endpoints[1],$Profile.Endpoints[0]
PS C:\> $Profile = Set-AzureTrafficManagerProfile
```

Contoh ini mengurutkan ulang titik akhir yang ditambahkan ke MyProfile ke urutan failover yang diinginkan.

Perintah pertama akan mendapatkan Traffic Manager profil bernama MyProfile dan menyimpan objek dalam $Profile variabel.

Perintah kedua akan memesan kembali titik akhir dari larik titik akhir ke urutan seharusnya failover terjadi.

Perintah terakhir memperbarui profil Traffic Manager yang disimpan di $Profile dengan urutan titik akhir baru.

## PARAMETERS

### -DomainName
Menentukan nama domain dari Traffic Manager mereka.
Ini harus merupakan subdomain dari trafficmanager.net.

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

### -LoadBalancingMethod
Menentukan metode keseimbangan muat untuk digunakan untuk mendistribusikan koneksi.
Nilai valid adalah: 

- Kinerja
- Failover
- RoundRobin

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

### -MonitorPort
Menentukan port yang digunakan untuk memantau kesehatan titik akhir.
Nilai valid adalah nilai bilangan bulat yang lebih besar dari 0 dan kurang dari atau sama dengan 65.535.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MonitorProtocol
Menentukan protokol yang akan digunakan untuk memantau kesehatan titik akhir.
Nilai valid adalah: 

- Http

- Https

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

### -MonitorRelativePath
Menentukan jalur terkait nama domain titik akhir bagi status kesehatan.
Jalur harus memenuhi batasan berikut ini: 

- Jalur harus memiliki karakter dari 1 sampai 1000.

- Langkah ini harus dimulai dengan garis miring, /.

- Ini harus berisi tidak ada elemen XML, \<\> .

- Harus berisi garis miring ganda, //.

- Ini harus berisi tidak ada karakter escape HTML yang tidak valid.
Misalnya, %XY.

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

### -Nama
Menentukan nama profil Traffic Manager akan dibuat.

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
Menentukan profil Azure yang akan dibaca cmdlet ini. Jika Anda tidak menentukan profil, cmdlet ini akan membaca dari profil default lokal.

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

### -Ttl
Menentukan Waktu Hidup (TTL) DNS yang menginformasikan penyelesaian DNS Lokal berapa lama untuk singgahan entri DNS.
Nilai valid adalah bilangan bulat dari 30 sampai 999.999.

```yaml
Type: Int32
Parameter Sets: (All)
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

### Microsoft.WindowsAzure.Commands.Utilities.TrafficManager.Models.IProfileWithDefinition
Cmdlet ini menghasilkan objek Traffic Manager profil.

## CATATAN

## RELATED LINKS

[Disable-AzureTrafficManagerProfile](./Disable-AzureTrafficManagerProfile.md)

[Enable-AzureTrafficManagerProfile](./Enable-AzureTrafficManagerProfile.md)

[Get-AzureTrafficManagerProfile](./Get-AzureTrafficManagerProfile.md)

[Remove-AzureTrafficManagerProfile](./Remove-AzureTrafficManagerProfile.md)

[Set-AzureTrafficManagerProfile](./Set-AzureTrafficManagerProfile.md)


