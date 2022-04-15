---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
ms.assetid: D767F017-6545-4BC6-927E-E7A99A08D5D2
online version: ''
schema: 2.0.0
ms.openlocfilehash: fc35509fc5e492d36537d0c3f28618880c5630e8
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142335839"
---
# Add-AzureEndpoint

## SYNOPSIS
Menambahkan titik akhir ke mesin virtual.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

### NoLB (Default)
```
Add-AzureEndpoint [-Name] <String> [-Protocol] <String> [-LocalPort] <Int32> [-PublicPort <Int32>]
 [-DirectServerReturn <Boolean>] [-ACL <NetworkAclObject>] [-InternalLoadBalancerName <String>]
 [-IdleTimeoutInMinutes <Int32>] [-LoadBalancerDistribution <String>] [-VirtualIPName <String>]
 -VM <IPersistentVM> [-Profile <AzureSMProfile>] [-InformationAction <ActionPreference>]
 [-InformationVariable <String>] [<CommonParameters>]
```

### LBNoProbe
```
Add-AzureEndpoint [-Name] <String> [-Protocol] <String> [-LocalPort] <Int32> [-PublicPort <Int32>]
 [-DirectServerReturn <Boolean>] [-ACL <NetworkAclObject>] -LBSetName <String> [-NoProbe]
 [-InternalLoadBalancerName <String>] [-IdleTimeoutInMinutes <Int32>] [-LoadBalancerDistribution <String>]
 [-VirtualIPName <String>] -VM <IPersistentVM> [-Profile <AzureSMProfile>]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

### LBDefaultProbe
```
Add-AzureEndpoint [-Name] <String> [-Protocol] <String> [-LocalPort] <Int32> [-PublicPort <Int32>]
 [-DirectServerReturn <Boolean>] [-ACL <NetworkAclObject>] -LBSetName <String> [-DefaultProbe]
 [-InternalLoadBalancerName <String>] [-IdleTimeoutInMinutes <Int32>] [-LoadBalancerDistribution <String>]
 [-VirtualIPName <String>] -VM <IPersistentVM> [-Profile <AzureSMProfile>]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

### LBCustomProbe
```
Add-AzureEndpoint [-Name] <String> [-Protocol] <String> [-LocalPort] <Int32> [-PublicPort <Int32>]
 [-DirectServerReturn <Boolean>] [-ACL <NetworkAclObject>] -LBSetName <String> -ProbePort <Int32>
 -ProbeProtocol <String> [-ProbePath <String>] [-ProbeIntervalInSeconds <Int32>]
 [-ProbeTimeoutInSeconds <Int32>] [-InternalLoadBalancerName <String>] [-IdleTimeoutInMinutes <Int32>]
 [-LoadBalancerDistribution <String>] [-VirtualIPName <String>] -VM <IPersistentVM> [-Profile <AzureSMProfile>]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Add-AzureEndpoint** menambahkan titik akhir ke objek mesin virtual Azure.

## EXAMPLES

### Contoh 1: Menambahkan titik akhir
```
PS C:\> Get-AzureVM -ServiceName "ContosoService" -Name "VirutalMachine01" | Add-AzureEndpoint -Name "HttpIn" -Protocol "tcp" -PublicPort 80 -LocalPort 8080 | Update-AzureVM
```

Perintah ini mengambil konfigurasi mesin virtual bernama VirtualMachine01 menggunakan cmdlet **Get-AzureVM** .
Perintah meneruskannya ke cmdlet saat ini menggunakan operator pipeline.
Cmdlet ini menambahkan titik akhir bernama HttpIn.
Titik akhir memiliki port publik 80 dan port lokal 8080.
Perintah melewati objek mesin virtual ke cmdlet **Update-AzureVM** , yang mengimplementasikan perubahan Anda.

### Contoh 2: Menambahkan titik akhir yang tergabung dalam grup seimbang beban
```
PS C:\> Get-AzureVM -ServiceName "LoadBalancedService" -Name "VirtualMachine12" | Add-AzureEndpoint -Name "HttpIn" -Protocol "tcp" -PublicPort 80 -LocalPort 8080 -LBSetName "WebFarm" -ProbePort 80 -ProbeProtocol "http" -ProbePath '/' | Update-AzureVM
```

Perintah ini mengambil konfigurasi mesin virtual bernama VirtualMachine07.
Cmdlet saat ini menambahkan titik akhir bernama HttpIn.
Titik akhir memiliki port publik 80 dan port lokal 8080.
Titik akhir termasuk dalam grup muatan bersama yang seimbang bernama WebFarm.
Probe HTTP pada port 80 dengan jalur '/' memantau ketersediaan titik akhir.
Perintah mengimplementasikan perubahan Anda.

### Contoh 3: Mengaitkan IP virtual ke titik akhir
```
PS C:\> Get-AzureVM -ServiceName "ContosoService" -Name "VirtualMachine25" | Add-AzureEndpoint -Name "HttpIn" -Protocol "tcp" -LocalPort 8080 -PublicPort 80 -VirtualIPName "ContosoVip11" | Update-AzureVM
```

Perintah ini mengambil konfigurasi mesin virtual bernama VirtualMachine25.
Cmdlet saat ini menambahkan titik akhir bernama HttpIn.
Titik akhir memiliki port publik 80 dan port lokal 8080.
Perintah ini mengaitkan IP virtual ke titik akhir.
Perintah mengimplementasikan perubahan Anda.

## PARAMETERS

### -ACL
Menentukan objek konfigurasi daftar kontrol akses (ACL) untuk titik akhir.

```yaml
Type: NetworkAclObject
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultProbe
Menunjukkan bahwa cmdlet ini menggunakan pengaturan probe default.

```yaml
Type: SwitchParameter
Parameter Sets: LBDefaultProbe
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DirectServerReturn
Menentukan apakah cmdlet ini mengaktifkan pengembalian server langsung.
Tentukan $True untuk diaktifkan, atau $False untuk dinonaktifkan.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IdleTimeoutInMinutes
Menentukan periode waktu habis diam TCP, dalam menit, untuk titik akhir.

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

### -InformationAction
Menentukan bagaimana cmdlet ini merespons kejadian informasi.

Nilai yang dapat diterima untuk parameter ini adalah:

- Lanjutkan
- Mengabaikan
- Menanyakan
- DiamKontinue
- Stop
- Menangguhkan

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

### -InternalLoadBalancerName
Menentukan nama penyeimbang muatan internal.

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

### -LBSetName
Menentukan nama kumpulan load balancer untuk titik akhir.

```yaml
Type: String
Parameter Sets: LBNoProbe, LBDefaultProbe, LBCustomProbe
Aliases: LoadBalancedEndpointSetName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LoadBalancerDistribution
Menentukan algoritma distribusi penyeimbang beban.
Nilai yang valid adalah: 

- sourceIP.
Affinity dua rangkap: IP Sumber, IP Tujuan 
- sourceIPProtocol.
Affinity tiga rangkap: IP Sumber, IP Tujuan, Protokol 
- Tidak.
Affinity five tuple: Source IP, Source Port, Destination IP, Destination Port, Protocol 

Nilai default tidak ada.

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

### -LocalPort
Menentukan port lokal, privat, yang digunakan titik akhir ini.
Aplikasi dalam mesin virtual mendengarkan port ini untuk permintaan input layanan untuk titik akhir ini.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Menentukan nama untuk titik akhir.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoProbe
Menunjukkan bahwa cmdlet ini menggunakan pengaturan tanpa probe.

```yaml
Type: SwitchParameter
Parameter Sets: LBNoProbe
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProbeIntervalInSeconds
Menentukan interval polling probe, dalam detik, untuk titik akhir.

```yaml
Type: Int32
Parameter Sets: LBCustomProbe
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProbePath
Menentukan jalur relatif ke probe HTTP.

```yaml
Type: String
Parameter Sets: LBCustomProbe
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProbePort
Menentukan port yang digunakan titik akhir.

```yaml
Type: Int32
Parameter Sets: LBCustomProbe
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProbeProtocol
Menentukan protokol porta.
Nilai yang valid adalah: 

- Tcp 
- http

```yaml
Type: String
Parameter Sets: LBCustomProbe
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProbeTimeoutInSeconds
Menentukan periode batas waktu polling probe dalam hitungan detik.

```yaml
Type: Int32
Parameter Sets: LBCustomProbe
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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

### -Protokol
Menentukan protokol titik akhir.
Nilai yang valid adalah: 

- Tcp 
- Udp

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PublicPort
Menentukan port publik yang digunakan titik akhir.
Jika Anda tidak menentukan nilai, Azure menetapkan port yang tersedia.

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

### -VirtualIPName
Menentukan nama alamat IP virtual yang dikaitkan Azure ke titik akhir.
Layanan Anda dapat memiliki beberapa IP virtual.
Untuk membuat IP virtual, gunakan cmdlet **Add-AzureVirtualIP** .

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

### -VM
Menentukan mesin virtual tempat titik akhir berada.

```yaml
Type: IPersistentVM
Parameter Sets: (All)
Aliases: InputObject

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### System.Object

## CATATAN

## RELATED LINKS

[Add-AzureVirtualIP](./Add-AzureVirtualIP.md)

[Get-AzureEndpoint](./Get-AzureEndpoint.md)

[Get-AzureVM](./Get-AzureVM.md)

[Hapus-AzureEndpoint](./Remove-AzureEndpoint.md)

[Set-AzureEndpoint](./Set-AzureEndpoint.md)

[Perbarui-AzureVM](./Update-AzureVM.md)


