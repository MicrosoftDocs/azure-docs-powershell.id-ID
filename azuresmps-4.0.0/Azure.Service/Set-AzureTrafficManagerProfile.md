---
external help file: Microsoft.WindowsAzure.Commands.TrafficManager.dll-Help.xml
ms.assetid: 700AC44E-4FD5-4516-80F3-B8C9E4DF6ABC
online version: ''
schema: 2.0.0
ms.openlocfilehash: ba1678c652eadb57739f383dcf78841a60f90dd7
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143041557"
---
# Set-AzureTrafficManagerProfile

## SYNOPSIS
Memperbarui properti profil Traffic Manager.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Set-AzureTrafficManagerProfile [-Name <String>] [-LoadBalancingMethod <String>] [-MonitorPort <Int32>]
 [-MonitorProtocol <String>] [-MonitorRelativePath <String>] [-Ttl <Int32>]
 -TrafficManagerProfile <IProfileWithDefinition> [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzureTrafficManagerProfile** memperbarui properti profil Microsoft Azure Traffic Manager.

Untuk profil yang telah Anda atur nilai *LoadBalancingMethod* ke "Failover", Anda dapat menentukan urutan failover titik akhir yang telah ditambahkan ke profil dengan cmdlet Add-AzureTrafficManagerEndpoint.
Untuk informasi selengkapnya, lihat Contoh 3 di bawah ini.

## EXAMPLES

### Contoh 1: Mengatur TTL untuk profil Traffic Manager
```
PS C:\>Set-AzureTrafficManagerProfile -TrafficManagerProfile $MyTrafficManagerProfile -Ttl 60
```

Perintah ini mengatur TTL ke 60 detik untuk objek profil Traffic Manager MyTrafficManagerProfile.

### Contoh 2: Mengatur beberapa nilai untuk profil
```
PS C:\>Get-AzureTrafficManagerProfile -Name "MyProfile" | Set-AzureTrafficManagerProfile -LoadBalancingMethod "RoundRobin" -Ttl 30 -MonitorProtocol "Http" -MonitorPort 80 -MonitorRelativePath "/"
```

Perintah ini mendapatkan profil Traffic Manager bernama MyProfile menggunakan cmdlet **Get-AzureTrafficManagerProfile**.
Profil menggunakan metode penyeimbangan muatan RoundRobin, TTL 30 detik, http protokol monitor, port monitor, dan jalur relatif untuk profil Traffic Manager.

### Contoh 3: Mengurutkan ulang titik akhir ke urutan failover yang diinginkan
```
PS C:\>$Profile = Get-AzureTrafficManagerProfile -Name "MyProfile"
PS C:\> $Profile.Endpoints[0],$Profile.Endpoints[1] = $Profile.Endpoints[1],$Profile.Endpoints[0]
PS C:\> $Profile = Set-AzureTrafficManagerProfile
```

Contoh ini mengurutkan ulang titik akhir yang ditambahkan ke MyProfile ke urutan failover yang diinginkan.

Perintah pertama mendapatkan objek profil Traffic Manager bernama MyProfile dan menyimpan objek dalam variabel $Profile.

Perintah kedua mengurutkan ulang titik akhir dari array titik akhir ke urutan kegagalan yang akan terjadi.

Perintah terakhir memperbarui profil Traffic Manager yang disimpan di $Profile dengan urutan titik akhir baru.

## PARAMETERS

### -LoadBalancingMethod
Menentukan metode penyeimbangan beban yang digunakan untuk mendistribusikan koneksi.
Nilai yang valid adalah: 

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
Nilai yang valid adalah nilai bilangan bulat yang lebih besar dari 0 dan kurang dari atau sama dengan 65.535.

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
Menentukan protokol yang digunakan untuk memantau kesehatan titik akhir.
Nilai yang valid adalah: 

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
Menentukan jalur relatif terhadap nama domain titik akhir ke probe untuk status kesehatan.
Jalur harus memenuhi batasan berikut: 

- Jalur harus dari 1 sampai 1000 karakter.
- Ini harus dimulai dengan garis miring, /.
- Ini harus berisi tidak ada elemen XML, \<\>.
- Tidak boleh berisi garis miring ganda, //.
- Tidak boleh berisi karakter escape HTML yang tidak valid.
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
Menentukan nama profil Traffic Manager untuk diperbarui.

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

### -TrafficManagerProfile
Menentukan objek profil Traffic Manager yang Anda gunakan untuk mengatur profil.

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
Menentukan DNS Time-to-Live (TTL) yang menginformasikan penyelesaian DNS lokal berapa lama untuk menyinggahkan entri DNS.
Nilai yang valid adalah bilangan bulat dari 30 hingga 999.999.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.WindowsAzure.Commands.Utilities.TrafficManager.Models.IProfileWithDefinition
Cmdlet ini menghasilkan objek profil Traffic Manager.

## NOTES

## RELATED LINKS

[Nonaktifkan-AzureTrafficManagerProfile](./Disable-AzureTrafficManagerProfile.md)

[Enable-AzureTrafficManagerProfile](./Enable-AzureTrafficManagerProfile.md)

[Get-AzureTrafficManagerProfile](./Get-AzureTrafficManagerProfile.md)

[New-AzureTrafficManagerProfile](./New-AzureTrafficManagerProfile.md)

[Hapus-AzureTrafficManagerProfile](./Remove-AzureTrafficManagerProfile.md)


