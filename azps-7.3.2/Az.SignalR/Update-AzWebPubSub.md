---
external help file: ''
Module Name: Az.SignalR
online version: https://docs.microsoft.com/powershell/module/az.signalr/update-azwebpubsub
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/SignalR/SignalR/help/Update-AzWebPubSub.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/SignalR/SignalR/help/Update-AzWebPubSub.md
ms.openlocfilehash: 52664390f42f04f4df7d6141d59bc92330b8e960
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "139998726"
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
PS C:\> $wps = Update-AzWebPubSub -ResourceGroupName psdemo -Name psdemo-wps `
-IdentityType SystemAssigned -LiveTraceEnabled true `
-LiveTraceCategory @{ Name='ConnectivityLogs' ; Enabled = 'true' }, @{ Name='MessageLogs' ; Enabled = 'true' }

Name       Location SkuName
----       -------- -------
psdemo-wps eastus   Standard_S1

PS C:\> $wps | format-list

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
PS C:\> $identity = @{ ResourceGroupName = 'psdemo'
ResourceName = 'psdemo-wps'
SubscriptionId = $(Get-AzContext).Subscription.Id }
PS C:\> $identity | Update-AzWebPubSub -EnableTlsClientCert

PS C:\> $wps | format-list

DisableAadAuth               : False
DisableLocalAuth             : False
EnableTlsClientCert          : True
ExternalIP                   : 20.62.134.186
HostName                     : psdemo-wps.webpubsub.azure.com
......
Version                      : 1.0
```

Contoh ini membangun tabel hash yang mewakili identitas sumber daya PubSub Web, lalu akan pipa objek identitas ke `Update` cmdlet.
Pada akhirnya perintah tersebut akan pipa hasil `Update` cmdlet untuk `Format-List` melihat semua nilai properti.

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
DisableLocalAuthEnable atau menonaktifkan aad authKetika diatur sebagai true, koneksi dengan AuthType=aad tidak akan berfungsi.

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
DisableLocalAuthEnable atau menonaktifkan auth lokal dengan AccessKeyKetika diatur sebagai true, koneksi dengan AccessKey=xxx tidak akan berfungsi.

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
Meminta sertifikat klien selama TLS handshake jika diaktifkan

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
Menunjukkan tipe identitas: systemAssigned, userAssigned, None

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
Parameter Identitas Untuk membuat, lihat bagian CATATAN untuk properti INPUTOBJECT dan membuat tabel hash.

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
Untuk membuat, lihat bagian CATATAN untuk properti LIVETRACECATEGORY dan membuat tabel hash.

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
Menunjukkan apakah mengaktifkan atau tidak mengaktifkan jejak langsung. Bila diatur ke benar, klien jejak langsung bisa tersambung ke layanan. Jika tidak, klien jejak langsung tidak bisa tersambung ke layanan, sehingga Anda tidak dapat menerima log apa pun, apa pun yang Anda konfigurasi dalam "kategori". Nilai yang tersedia: true, false. Peka huruf besar/huruf.

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

### -NetworkAclDefaultAction
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
Menjalankan perintah secara asinkron

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
ACL untuk permintaan dari titik akhir privat Untuk dibuat, lihat bagian CATATAN untuk properti PRIVATEENDPOINTACL dan buat tabel hash.

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
Default ke "Diaktifkan". Ketika Diaktifkan, ACL jaringan masih berlaku. Ketika Dinonaktifkan, akses jaringan publik selalu dinonaktifkan apa pun yang Anda atur dalam ACL jaringan.

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
Tipe permintaan yang diperbolehkan.
Nilai dapatlah salah satu atau beberapa dari: ClientConnection, ServerConnection, RESTAPI.

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
Nilai dapatlah salah satu atau beberapa dari: ClientConnection, ServerConnection, RESTAPI.

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
Nama grup sumber daya yang berisi sumber daya tersebut.
Anda dapat memperoleh nilai ini dari API Azure Resource Manager atau portal.

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
Untuk membuat, lihat bagian CATATAN untuk properti RESOURCELOGCATEGORY dan membuat tabel hash.

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
Nilai yang diizinkan: Standard_S1, Free_F1

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
Tingkatan opsional dari SKU tertentu ini.
'Standar' atau 'Gratis'.
`Basic` sudah tidak berlaku, gunakan sebagai gantinya `Standard` .

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
Mendapatkan Id langganan yang secara unik mengidentifikasi Microsoft Azure anda.
ID langganan membentuk bagian dari URI untuk setiap panggilan layanan.

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
Tag layanan yang merupakan daftar pasangan nilai kunci yang menjelaskan sumber daya tersebut.

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
Meminta konfirmasi Anda sebelum menjalankan cmdlet.

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
Cmdlet tidak berjalan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets.WebPubSub.Models.IWebPubSubIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.WebPubSub.Models.Api20211001.IWebPubSubResource

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT <IWebPubSubIdentity>: Parameter Identitas
  - `[HubName <String>]`: Nama hub.
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[Location <String>]`: kawasan
  - `[PrivateEndpointConnectionName <String>]`: Nama koneksi titik akhir privat
  - `[ResourceGroupName <String>]`: Nama grup sumber daya yang berisi sumber daya tersebut. Anda dapat memperoleh nilai ini dari API Azure Resource Manager atau portal.
  - `[ResourceName <String>]`: Nama sumber daya.
  - `[SharedPrivateLinkResourceName <String>]`: Nama sumber daya tautan privat bersama
  - `[SubscriptionId <String>]`: Mendapatkan Id langganan yang secara unik mengidentifikasi Microsoft Azure langganan tersebut. ID langganan membentuk bagian dari URI untuk setiap panggilan layanan.

LIVETRACECATEGORY <ILiveTraceCategory[]>: Mendapatkan atau mengatur daftar konfigurasi kategori.
  - `[Enabled <String>]`: Menunjukkan apakah kategori jejak langsung diaktifkan atau tidak.         Nilai yang tersedia: true, false.         Peka huruf besar/huruf.
  - `[Name <String>]`: Mendapatkan atau mengatur nama kategori jejak langsung.         Nilai yang tersedia: ConnectivityLogs, MessagingLogs.         Peka huruf besar/huruf.

PRIVATEENDPOINTACL <IPrivateEndpointAcl[]>: ACL untuk permintaan dari titik akhir privat
  - `Name <String>`: Nama koneksi titik akhir privat
  - `[Allow <WebPubSubRequestType[]>]`: Tipe permintaan yang diperbolehkan. Nilai dapatlah salah satu atau beberapa dari: ClientConnection, ServerConnection, RESTAPI.
  - `[Deny <WebPubSubRequestType[]>]`: Tipe permintaan yang ditolak. Nilai dapatlah salah satu atau beberapa dari: ClientConnection, ServerConnection, RESTAPI.

RESOURCELOGCATEGORY <IResourceLogCategory[]>: Mendapatkan atau mengatur daftar konfigurasi kategori.
  - `[Enabled <String>]`: Menunjukkan apakah kategori log sumber daya diaktifkan atau tidak.         Nilai yang tersedia: true, false.         Peka huruf besar/huruf.
  - `[Name <String>]`: Mendapatkan atau mengatur nama kategori log sumber daya.         Nilai yang tersedia: ConnectivityLogs, MessagingLogs.         Peka huruf besar/huruf.

## RELATED LINKS

