---
external help file: Microsoft.Azure.Commands.TrafficManager.dll-Help.xml
Module Name: AzureRM.TrafficManager
ms.assetid: DE31891A-0EF7-44D7-B955-A3279D27CC21
online version: ''
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/TrafficManager/Commands.TrafficManager2/help/New-AzureRmTrafficManagerProfile.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/TrafficManager/Commands.TrafficManager2/help/New-AzureRmTrafficManagerProfile.md
ms.openlocfilehash: 8b88ee761ab9ee136777fb29e7726a2f72110553
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132426789"
---
# New-AzureRmTrafficManagerProfile

## SYNOPSIS
Membuat profil Traffic Manager anda.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
New-AzureRmTrafficManagerProfile -Name <String> -ResourceGroupName <String> [-ProfileStatus <String>]
 -RelativeDnsName <String> -Ttl <UInt32> -TrafficRoutingMethod <String> -MonitorProtocol <String>
 -MonitorPort <UInt32> [-MonitorPath <String>] [-MonitorIntervalInSeconds <Int32>]
 [-MonitorTimeoutInSeconds <Int32>] [-MonitorToleratedNumberOfFailures <Int32>] [-Tag <Hashtable>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzureRmTrafficManagerProfile** membuat Azure Traffic Manager profil.
Tentukan parameter *Nama* dan pengaturan yang diperlukan.
Cmdlet ini mengembalikan objek lokal yang mewakili profil baru.

Cmdlet ini tidak mengonfigurasi Traffic Manager titik akhir.
Anda dapat memperbarui objek profil lokal menggunakan cmdlet Add-AzureRmTrafficManagerEndpointConfig.
Lalu unggah perubahan Traffic Manager dengan menggunakan cmdlet Set-AzureRmTrafficManagerProfile.
Sebagai alternatif, Anda dapat menambahkan titik akhir menggunakan cmdlet New-AzureRmTrafficManagerEndpoint cmdlet.

## EXAMPLES

### Contoh 1: Membuat profil
```
PS C:\>New-AzureRmTrafficManagerProfile -Name "ContosoProfile" -ResourceGroupName "ResourceGroup11" -ProfileStatus Enabled -TrafficRoutingMethod Performance -RelativeDnsName "contosoapp" -TTL 30 -MonitorProtocol HTTP -MonitorPort 80 -MonitorPath "/default.aspx"
```

Perintah ini membuat profil Azure Traffic Manager bernama ContosoProfile dalam grup sumber daya ResourceGroup11.
FQDN DNS tidak contosoapp.trafficmanager.net.

## PARAMETERS

### -MonitorIntervalInSeconds
Interval (dalam detik) ketika Traffic Manager akan memeriksa kesehatan setiap titik akhir di profil ini. Defaultnya adalah 30.

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases: IntervalInSecondsForMonitor

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MonitorPath
Menentukan jalur yang digunakan untuk memantau kesehatan titik akhir.
Tentukan nilai yang terkait dengan nama domain titik akhir.
Nilai ini harus dimulai dengan garis miring (/).

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: PathForMonitor

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MonitorPort
Menentukan port TCP yang digunakan untuk memantau kesehatan titik akhir.
Nilai valid adalah bilangan bulat dari 1 sampai 65535.

```yaml
Type: System.UInt32
Parameter Sets: (All)
Aliases: PortForMonitor

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MonitorProtocol
Menentukan protokol yang akan digunakan untuk memantau kesehatan titik akhir.
Nilai valid adalah:

- HTTP
- HTTPS

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: ProtocolForMonitor
Accepted values: HTTP, HTTPS, TCP

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MonitorTimeoutInSeconds
Waktu (dalam detik) Traffic Manager memungkinkan titik akhir di profil ini untuk merespons pemeriksaan kesehatan. Nilai default adalah 10.

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases: TimeoutInSecondsForMonitor

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MonitorToleratedNumberOfFailures
Jumlah pemeriksaan kesehatan gagal berurutan yang dilakukan Traffic Manager sebelum mendeklarasi titik akhir di profil ini Menurun setelah pemeriksaan kesehatan berurutan berikutnya gagal. Defaultnya adalah 3.

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases: ToleratedNumberOfFailuresForMonitor

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Menentukan nama untuk profil Traffic Manager dibuat cmdlet ini.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProfileStatus
Menentukan status profil.
Nilai yang valid adalah: Diaktifkan dan Dinonaktifkan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: 
Accepted values: Enabled, Disabled

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RelativeDnsName
Menentukan nama DNS relatif yang telah Traffic Manager profil.
Traffic Manager menggabungkan nilai ini dan nama domain DNS yang digunakan Azure Traffic Manager untuk membentuk nama domain yang sepenuhnya memenuhi syarat (FQDN, Fully Qualified Domain Name) dari profil.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Menentukan nama grup sumber daya.
Cmdlet ini membuat Traffic Manager profil dalam grup yang ditentukan parameter ini.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Tag
Pasangan nilai kunci dalam bentuk tabel hash yang diatur sebagai tag di server. Misalnya:

@{key0="value0";key1=$null;key2="value2"}

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases: Tags

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TrafficRoutingMethod
Menentukan metode perutean lalu lintas.
Metode ini menentukan titik akhir Traffic Manager kembali sebagai respons ke kueri DNS yang masuk.
Nilai valid adalah:

- Kinerja
- Ditimbang
- Prioritas

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: 
Accepted values: Performance, Weighted, Priority, Geographic

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Ttl
Menentukan nilai Waktu DNS hingga Langsung (TTL).

```yaml
Type: System.UInt32
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
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

## OUTPUTS

### Microsoft.Azure.Commands.Network.TrafficManagerProfile
Cmdlet ini mengembalikan objek TrafficManagerProfile baru.

## CATATAN

## RELATED LINKS

[Add-AzureRmTrafficManagerEndpointConfig](./Add-AzureRmTrafficManagerEndpointConfig.md)

[Disable-AzureRmTrafficManagerProfile](./Disable-AzureRmTrafficManagerProfile.md)

[Enable-AzureRmTrafficManagerProfile](./Enable-AzureRmTrafficManagerProfile.md)

[Get-AzureRmTrafficManagerProfile](./Get-AzureRmTrafficManagerProfile.md)

[Remove-AzureRmTrafficManagerProfile](./Remove-AzureRmTrafficManagerProfile.md)

[Set-AzureRmTrafficManagerProfile](./Set-AzureRmTrafficManagerProfile.md)


