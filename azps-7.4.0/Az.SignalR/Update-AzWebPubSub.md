---
external help file: ''
Module Name: Az.SignalR
online version: https://docs.microsoft.com/powershell/module/az.signalr/update-azwebpubsub
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/SignalR/SignalR/help/Update-AzWebPubSub.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/SignalR/SignalR/help/Update-AzWebPubSub.md
ms.openlocfilehash: 924392b330be8876453fa2feaee3c1db5f545783
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142738936"
---
# Update-AzWebPubSub

## SYNOPSIS
Operasi untuk memperbarui sumber daya keluar.

## SYNTAX

### UpdateExpanded (Default)
```
Update-AzWebPubSub -Name <String> -ResourceGroupName <String> [-SubscriptionId <String>] [-DisableAadAuth]
 [-DisableLocalAuth] [-EnableTlsClientCert] [-IdentityType <ManagedIdentityType>]
 [-LiveTraceCategory <ILiveTraceCategory[]>] [-LiveTraceEnabled <String>]
 [-NetworkAcLDefaultAction <AclAction>] [-PrivateEndpointAcl <IPrivateEndpointAcl[]>]
 [-PublicNetworkAccess <String>] [-PublicNetworkAllow <WebPubSubRequestType[]>]
 [-PublicNetworkDeny <WebPubSubRequestType[]>] [-ResourceLogCategory <IResourceLogCategory[]>]
 [-SkuCapacity <Int32>] [-SkuName <String>] [-SkuTier <WebPubSubSkuTier>] [-Tag <Hashtable>]
 [-UserAssignedIdentity <Hashtable>] [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-Confirm] [-WhatIf]
 [<CommonParameters>]
```

### UpdateViaIdentityExpanded
```
Update-AzWebPubSub -InputObject <IWebPubSubIdentity> [-DisableAadAuth] [-DisableLocalAuth]
 [-EnableTlsClientCert] [-IdentityType <ManagedIdentityType>] [-LiveTraceCategory <ILiveTraceCategory[]>]
 [-LiveTraceEnabled <String>] [-NetworkAcLDefaultAction <AclAction>]
 [-PrivateEndpointAcl <IPrivateEndpointAcl[]>] [-PublicNetworkAccess <String>]
 [-PublicNetworkAllow <WebPubSubRequestType[]>] [-PublicNetworkDeny <WebPubSubRequestType[]>]
 [-ResourceLogCategory <IResourceLogCategory[]>] [-SkuCapacity <Int32>] [-SkuName <String>]
 [-SkuTier <WebPubSubSkuTier>] [-Tag <Hashtable>] [-UserAssignedIdentity <Hashtable>]
 [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Operasi untuk memperbarui sumber daya keluar.

## EXAMPLES

### Contoh 1: Memperbarui sumber daya PubSub Web
```powershell
$wps = Update-AzWebPubSub -ResourceGroupName psdemo -Name psdemo-wps `
-IdentityType SystemAssigned -LiveTraceEnabled true `
-LiveTraceCategory @{ Name='ConnectivityLogs' ; Enabled = 'true' }, @{ Name='MessageLogs' ; Enabled = 'true' }

Name       Location SkuName
----       -------- -------
psdemo-wps eastus   Standard_S1

$wps | format-list

DisableAadAuth               : False
DisableLocalAuth             : False
EnableTlsClientCert          : False
ExternalIP                   : 20.62.134.186
HostName                     : psdemo-wps.webpubsub.azure.com
......
Version                      : 1.0
```



### Contoh 2: Memperbarui sumber daya PubSub Web melalui identitas
```powershell
$identity = @{ ResourceGroupName = 'psdemo'
ResourceName = 'psdemo-wps'
SubscriptionId = $(Get-AzContext).Subscription.Id }
$identity | Update-AzWebPubSub -EnableTlsClientCert

$wps | format-list
```

```output
DisableAadAuth               : False
DisableLocalAuth             : False
EnableTlsClientCert          : True
ExternalIP                   : 20.62.134.186
HostName                     : psdemo-wps.webpubsub.azure.com
......
Version                      : 1.0
```

Contoh ini menyusun tabel hash yang mewakili identitas sumber daya PubSub Web, lalu menyalurkan objek identitas ke `Update` cmdlet.
Akhirnya menyalurkan hasil `Update` cmdlet untuk `Format-List` melihat semua nilai properti.

## PARAMETERS

### -AsJob
Menjalankan perintah sebagai pekerjaan

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
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases: AzureRMContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisableAadAuth
DisableLocalAuthEnable atau disable aad authWhen diatur sebagai true, koneksi dengan AuthType=aad tidak akan berfungsi.

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

### -DisableLocalAuth
DisableLocalAuthEnable atau menonaktifkan auth lokal dengan AccessKeyWhen diatur sebagai true, koneksi dengan AccessKey=xxx tidak akan berfungsi.

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

### -EnableTlsClientCert
Minta sertifikat klien selama jabat tangan TLS jika diaktifkan

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

### -IdentityType
Mewakili tipe identitas: systemAssigned, userAssigned, None

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.WebPubSub.Support.ManagedIdentityType
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Parameter Identitas Untuk membangun, lihat bagian CATATAN untuk properti INPUTOBJECT dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.WebPubSub.Models.IWebPubSubIdentity
Parameter Sets: UpdateViaIdentityExpanded
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -LiveTraceCategory
Mendapatkan atau mengatur daftar konfigurasi kategori.
Untuk membangun, lihat bagian CATATAN untuk properti LIVETRACECATEGORY dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.WebPubSub.Models.Api20211001.ILiveTraceCategory[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LiveTraceEnabled
Menunjukkan apakah jejak langsung diaktifkan atau tidak. Ketika diatur ke true, klien jejak langsung dapat tersambung ke layanan. Jika tidak, klien jejak langsung tidak dapat tersambung ke layanan, sehingga Anda tidak dapat menerima log apa pun, apa pun yang Anda konfigurasi dalam "kategori". Nilai yang tersedia: true, false. Tidak peka huruf besar kecil.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Nama sumber daya.

```yaml
Type: System.String
Parameter Sets: UpdateExpanded
Aliases: ResourceName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NetworkAcLDefaultAction
Tindakan default ketika tidak ada aturan lain yang cocok

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.WebPubSub.Support.AclAction
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoWait
Jalankan perintah secara asinkron

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

### -PrivateEndpointAcl
AKL untuk permintaan dari titik akhir privat Untuk membangun, lihat bagian CATATAN untuk properti PRIVATEENDPOINTACL dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.WebPubSub.Models.Api20211001.IPrivateEndpointAcl[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PublicNetworkAccess
Mengaktifkan atau menonaktifkan akses jaringan publik.
Default ke "Diaktifkan". Saat Diaktifkan, AKL jaringan masih berlaku. Saat Dinonaktifkan, akses jaringan publik selalu dinonaktifkan apa pun yang Anda atur di AKL jaringan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PublicNetworkAllow
Tipe permintaan yang diizinkan.
Nilainya bisa berupa satu atau beberapa dari: ClientConnection, ServerConnection, RESTAPI.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.WebPubSub.Support.WebPubSubRequestType[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PublicNetworkDeny
Tipe permintaan yang ditolak.
Nilainya bisa berupa satu atau beberapa dari: ClientConnection, ServerConnection, RESTAPI.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.WebPubSub.Support.WebPubSubRequestType[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya yang berisi sumber daya.
Anda dapat memperoleh nilai ini dari API azure Resource Manager atau portal.

```yaml
Type: System.String
Parameter Sets: UpdateExpanded
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceLogCategory
Mendapatkan atau mengatur daftar konfigurasi kategori.
Untuk membangun, lihat bagian CATATAN untuk properti RESOURCELOGCATEGORY dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.WebPubSub.Models.Api20211001.IResourceLogCategory[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SkuCapacity
Opsional, bilangan bulat.
Hitungan unit sumber daya.
1 secara default. Jika ada, nilai berikut diperbolehkan: Gratis: 1 Standar: 1,2,5,10,20,50,100

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SkuName
Nama SKU.
Nilai yang diperlukan.Diizinkan: Standard_S1, Free_F1

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SkuTier
Tingkat opsional SKU khusus ini.
'Standar' atau 'Gratis'.
`Basic` tidak digunakan lagi, gunakan `Standard` sebagai gantinya.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.WebPubSub.Support.WebPubSubSkuTier
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubscriptionId
Mendapatkan Id langganan yang mengidentifikasi langganan Microsoft Azure secara unik.
ID langganan merupakan bagian dari URI untuk setiap panggilan layanan.

```yaml
Type: System.String
Parameter Sets: UpdateExpanded
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### -Tag
Tag layanan yang merupakan daftar pasangan nilai kunci yang menjelaskan sumber daya.

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UserAssignedIdentity
Mendapatkan atau mengatur identitas yang ditetapkan pengguna

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Konfirmasi
Meminta konfirmasi sebelum menjalankan cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan.
Cmdlet tidak dijalankan.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets.WebPubSub.Models.IWebPubSubIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.WebPubSub.Models.Api20211001.IWebPubSubResource

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT <IWebPubSubIdentity>: Parameter Identitas
  - `[HubName <String>]`: Nama hub.
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[Location <String>]`: kawasan
  - `[PrivateEndpointConnectionName <String>]`: Nama koneksi titik akhir privat
  - `[ResourceGroupName <String>]`: Nama grup sumber daya yang berisi sumber daya. Anda dapat memperoleh nilai ini dari API azure Resource Manager atau portal.
  - `[ResourceName <String>]`: Nama sumber daya.
  - `[SharedPrivateLinkResourceName <String>]`: Nama sumber daya tautan pribadi bersama
  - `[SubscriptionId <String>]`: Mendapatkan Id langganan yang mengidentifikasi langganan Microsoft Azure secara unik. ID langganan merupakan bagian dari URI untuk setiap panggilan layanan.

LIVETRACECATEGORY <ILiveTraceCategory[]>: Mendapatkan atau mengatur daftar konfigurasi kategori.
  - `[Enabled <String>]`: Menunjukkan apakah atau kategori jejak langsung diaktifkan.         Nilai yang tersedia: true, false.         Tidak peka huruf besar kecil.
  - `[Name <String>]`: Mendapatkan atau mengatur nama kategori jejak langsung.         Nilai yang tersedia: ConnectivityLogs, MessagingLogs.         Tidak peka huruf besar kecil.

PRIVATEENDPOINTACL <IPrivateEndpointAcl[]>: ABI untuk permintaan dari titik akhir privat
  - `Name <String>`: Nama koneksi titik akhir privat
  - `[Allow <WebPubSubRequestType[]>]`: Tipe permintaan yang diizinkan. Nilainya bisa berupa satu atau beberapa dari: ClientConnection, ServerConnection, RESTAPI.
  - `[Deny <WebPubSubRequestType[]>]`: Tipe permintaan yang ditolak. Nilainya bisa berupa satu atau beberapa dari: ClientConnection, ServerConnection, RESTAPI.

RESOURCELOGCATEGORY <IResourceLogCategory[]>: Mendapatkan atau mengatur daftar konfigurasi kategori.
  - `[Enabled <String>]`: Menunjukkan apakah atau kategori log sumber daya diaktifkan.         Nilai yang tersedia: true, false.         Tidak peka huruf besar kecil.
  - `[Name <String>]`: Mendapatkan atau mengatur nama kategori log sumber daya.         Nilai yang tersedia: ConnectivityLogs, MessagingLogs.         Tidak peka huruf besar kecil.

## RELATED LINKS

