---
external help file: ''
Module Name: Az.SignalR
online version: https://docs.microsoft.com/powershell/module/az.signalr/new-azwebpubsub
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/SignalR/SignalR/help/New-AzWebPubSub.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/SignalR/SignalR/help/New-AzWebPubSub.md
ms.openlocfilehash: 46bfa7bd0208d41ac1e50e32f4b8889e4988c2ca
ms.sourcegitcommit: 82b4008b76d035e4aee733727371765b0d853bed
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145629531"
---
# New-AzWebPubSub

## SYNOPSIS
Membuat atau memperbarui sumber daya.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.signalr/new-azwebpubsub) untuk informasi terbaru.

## SYNTAX

```
New-AzWebPubSub -Name <String> -ResourceGroupName <String> -Location <String> -SkuName <String>
 [-SubscriptionId <String>] [-DisableAadAuth] [-DisableLocalAuth] [-EnableTlsClientCert]
 [-IdentityType <ManagedIdentityType>] [-LiveTraceCategory <ILiveTraceCategory[]>]
 [-LiveTraceEnabled <String>] [-NetworkAcLDefaultAction <AclAction>]
 [-PrivateEndpointAcl <IPrivateEndpointAcl[]>] [-PublicNetworkAccess <String>]
 [-PublicNetworkAllow <WebPubSubRequestType[]>] [-PublicNetworkDeny <WebPubSubRequestType[]>]
 [-ResourceLogCategory <IResourceLogCategory[]>] [-SkuCapacity <Int32>] [-SkuTier <WebPubSubSkuTier>]
 [-Tag <Hashtable>] [-UserAssignedIdentity <Hashtable>] [-DefaultProfile <PSObject>] [-AsJob] [-NoWait]
 [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Membuat atau memperbarui sumber daya.

## EXAMPLES

### Contoh 1: Buat sumber daya Web PubSub dengan parameter minimal yang diperlukan.
```powershell
New-AzWebPubSub -ResourceGroupName psdemo -Name psdemo-wps -Location eastus -SkuName Standard_S1
```

```output
Name                Location      SkuName
----                --------      -------
psdemo-wps          eastus        Standard_S1
```



### Contoh 2: Buat sumber daya Web PubSub dengan lebih banyak parameter dan tampilkan hasilnya
```powershell
$wps = New-AzWebPubSub -ResourceGroupName psdemo -Name psdemo-wps `
-Location eastus -SkuName Standard_S1 -IdentityType SystemAssigned -LiveTraceEnabled true `
-LiveTraceCategory @{ Name='ConnectivityLogs' ; Enabled = 'true' }, @{ Name='MessageLogs' ; Enabled = 'true' }

Name                Location      SkuName
----                --------      -------
psdemo-wps          eastus        Standard_S1

$wps | Format-List

DisableAadAuth               : False
DisableLocalAuth             : False
EnableTlsClientCert          : False
ExternalIP                   : 20.62.134.186
HostName                     : psdemo-wps.webpubsub.azure.com
Id                           : /subscriptions/9caf2a1e-9c49-49b6-89a2-56bdec7e3f97/resourceGroups/psdemo/providers/Micr
                               osoft.SignalRService/WebPubSub/psdemo-wps
IdentityPrincipalId          :
IdentityTenantId             :
IdentityType                 :
LiveTraceCategory            :
LiveTraceEnabled             : true
Location                     : eastus
Name                         : psdemo-wps
NetworkAcLDefaultAction      : Deny
PrivateEndpointAcl           : {}
PrivateEndpointConnection    : {}
ProvisioningState            : Succeeded
PublicNetworkAccess          : Enabled
PublicNetworkAllow           : {ServerConnection, ClientConnection, RESTAPI, Trace}
PublicNetworkDeny            :
PublicPort                   : 443
ResourceLogCategory          :
ServerPort                   : 443
SharedPrivateLinkResource    : {}
SkuCapacity                  : 1
SkuFamily                    :
SkuName                      : Standard_S1
SkuSize                      : S1
SkuTier                      : Standard
SystemDataCreatedAt          : 2021-10-11 9:02:37 AM
SystemDataCreatedBy          : testuser@microsoft.com
SystemDataCreatedByType      : User
SystemDataLastModifiedAt     : 2021-10-12 7:21:58 AM
SystemDataLastModifiedBy     : testuser@microsoft.com
SystemDataLastModifiedByType : User
Tag                          : Microsoft.Azure.PowerShell.Cmdlets.WebPubSub.Models.Api20211001.TrackedResourceTags
Type                         : Microsoft.SignalRService/WebPubSub
UserAssignedIdentity         : Microsoft.Azure.PowerShell.Cmdlets.WebPubSub.Models.Api20211001.ManagedIdentityUserAssig
                               nedIdentities
Version                      : 1.0
```



## PARAMETERS

### -AsJob
Jalankan perintah sebagai pekerjaan

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
DisableLocalAuthEnable atau nonaktifkan aad authWhen diatur sebagai true, koneksi dengan AuthType=aad tidak akan berfungsi.

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
DisableLocalAuthEnable atau nonaktifkan autentikasi lokal dengan AccessKeyWhen diatur sebagai true, koneksi dengan AccessKey=xxx tidak akan berfungsi.

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
Meminta sertifikat klien selama jabat tangan TLS jika diaktifkan

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
Mewakili jenis identitas: systemAssigned, userAssigned, None

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

### -LiveTraceCategory
Mendapatkan atau mengatur daftar konfigurasi kategori.
Untuk membuat, lihat bagian CATATAN untuk properti LIVETRACECATEGORY dan buat tabel hash.

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
Menunjukkan apakah pelacakan langsung diaktifkan atau tidak. Ketika diatur ke true, klien pelacakan langsung dapat terhubung ke layanan. Jika tidak, klien pelacakan langsung tidak dapat terhubung ke layanan, sehingga Anda tidak dapat menerima log apa pun, apa pun yang Anda konfigurasi dalam "kategori". Nilai yang tersedia: true, false. Tidak peka huruf besar/kecil.

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

### -Lokasi
Lokasi GEO sumber daya.
misalnya | US Barat | AS Timur | US Tengah Utara US Tengah Selatan.

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

### -Name
Nama sumber daya.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: ResourceName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NetworkAcLDefaultAction
Tindakan default saat tidak ada aturan lain yang cocok

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
ACL untuk permintaan dari titik akhir privat Untuk membangun, lihat bagian CATATAN untuk properti PRIVATEENDPOINTACL dan membuat tabel hash.

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
Default ke "Diaktifkan". Saat Diaktifkan, ACL jaringan masih berlaku. Saat Dinonaktifkan, akses jaringan publik selalu dinonaktifkan apa pun yang Anda tetapkan di ACL jaringan.

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
Jenis permintaan yang diizinkan.
Nilainya bisa satu atau beberapa dari: ClientConnection, ServerConnection, RESTAPI.

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
Jenis permintaan yang ditolak.
Nilainya bisa satu atau beberapa dari: ClientConnection, ServerConnection, RESTAPI.

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
Anda dapat memperoleh nilai ini dari Azure Resource Manager API atau portal.

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

### -ResourceLogCategory
Mendapatkan atau mengatur daftar konfigurasi kategori.
Untuk membuat, lihat bagian CATATAN untuk properti RESOURCELOGCATEGORY dan buat tabel hash.

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
Jumlah unit sumber daya.
1 secara default. Jika ada, nilai berikut diizinkan: Gratis: 1 Standar: 1,2,5,10,20,50,100

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
Nama SKUnya.
Nilai required.allowed: Standard_S1, Free_F1

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
Mendapatkan Id langganan yang secara unik mengidentifikasi langganan Microsoft Azure.
ID langganan membentuk bagian dari URI untuk setiap panggilan layanan.

```yaml
Type: System.String
Parameter Sets: (All)
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

### -Confirm
Meminta Anda mengonfirmasi sebelum menjalankan cmdlet.

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
Menunjukkan yang akan terjadi jika cmdlet dijalankan.
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.WebPubSub.Models.Api20211001.IWebPubSubResource

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


LIVETRACECATEGORY <ILiveTraceCategory[]>: Mendapatkan atau menetapkan daftar konfigurasi kategori.
  - `[Enabled <String>]`: Menunjukkan apakah atau kategori pelacakan langsung diaktifkan.         Nilai yang tersedia: true, false.         Tidak peka huruf besar/kecil.
  - `[Name <String>]`: Mendapatkan atau mengatur nama kategori pelacakan langsung.         Nilai yang tersedia: ConnectivityLogs, MessagingLogs.         Tidak peka huruf besar/kecil.

PRIVATEENDPOINTACL <IPrivateEndpointAcl[]>: ACL untuk permintaan dari titik akhir privat
  - `Name <String>`: Nama koneksi titik akhir privat
  - `[Allow <WebPubSubRequestType[]>]`: Jenis permintaan yang diizinkan. Nilainya bisa satu atau beberapa dari: ClientConnection, ServerConnection, RESTAPI.
  - `[Deny <WebPubSubRequestType[]>]`: Jenis permintaan yang ditolak. Nilainya bisa satu atau beberapa dari: ClientConnection, ServerConnection, RESTAPI.

RESOURCELOGCATEGORY <IResourceLogCategory[]>: Mendapatkan atau menetapkan daftar konfigurasi kategori.
  - `[Enabled <String>]`: Menunjukkan apakah atau kategori log sumber daya diaktifkan.         Nilai yang tersedia: true, false.         Tidak peka huruf besar/kecil.
  - `[Name <String>]`: Mendapatkan atau mengatur nama kategori log sumber daya.         Nilai yang tersedia: ConnectivityLogs, MessagingLogs.         Tidak peka huruf besar/kecil.

## RELATED LINKS

