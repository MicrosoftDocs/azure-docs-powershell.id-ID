---
external help file: Microsoft.WindowsAzure.Commands.TrafficManager.dll-Help.xml
ms.assetid: 700AC44E-4FD5-4516-80F3-B8C9E4DF6ABC
online version: ''
schema: 2.0.0
ms.openlocfilehash: ba1678c652eadb57739f383dcf78841a60f90dd7
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132425828"
---
# Set-AzureTrafficManagerProfile

## SYNOPSIS
Memperbarui properti profil Traffic Manager Anda.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Set-AzureTrafficManagerProfile [-Name <String>] [-LoadBalancingMethod <String>] [-MonitorPort <Int32>]
 [-MonitorProtocol <String>] [-MonitorRelativePath <String>] [-Ttl <Int32>]
 -TrafficManagerProfile <IProfileWithDefinition> [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzureTrafficManagerProfile** memperbarui properti profil Microsoft Azure Traffic Manager Anda.

Untuk profil yang telah Anda setel nilai *LoadBalancingMethod* ke "Failover", Anda dapat menentukan urutan failover titik akhir yang telah ditambahkan ke profil menggunakan cmdlet Add-AzureTrafficManagerEndpoint.
Untuk informasi selengkapnya, lihat Contoh 3 di bawah.

## EXAMPLES

### Contoh 1: Mengatur TTL untuk Traffic Manager profil
```
PS C:\>Set-AzureTrafficManagerProfile -TrafficManagerProfile $MyTrafficManagerProfile -Ttl 60
```

Perintah ini mengatur TTL ke 60 detik untuk objek Traffic Manager profil MyTrafficManagerProfile.

### Contoh 2: Mengatur beberapa nilai untuk profil
```
PS C:\>Get-AzureTrafficManagerProfile -Name "MyProfile" | Set-AzureTrafficManagerProfile -LoadBalancingMethod "RoundRobin" -Ttl 30 -MonitorProtocol "Http" -MonitorPort 80 -MonitorRelativePath "/"
```

Perintah ini memiliki profil Traffic Manager bernama MyProfile menggunakan cmdlet **Get-AzureTrafficManagerProfile.**
Profil menggunakan metode keseimbangan muat RoundRobin, TTL 30 detik, protokol monitor HTTP, port monitor, dan jalur relatif untuk Traffic Manager relatif.

### Contoh 3: Urutkan ulang titik akhir untuk urutan failover yang diinginkan
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

Required: False
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

Required: False
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

Required: False
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

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Menentukan nama profil Traffic Manager diperbarui.

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

### -TrafficManagerProfile
Menentukan objek Traffic Manager profil yang Anda gunakan untuk mengatur profil.

```yaml
Type: IProfileWithDefinition
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Ttl
Menentukan Waktu Hidup (TTL) DNS yang menginformasikan penyelesaian DNS Lokal berapa lama untuk singgahan entri DNS.
Nilai valid adalah bilangan bulat dari 30 sampai 999.999.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
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

[New-AzureTrafficManagerProfile](./New-AzureTrafficManagerProfile.md)

[Remove-AzureTrafficManagerProfile](./Remove-AzureTrafficManagerProfile.md)


