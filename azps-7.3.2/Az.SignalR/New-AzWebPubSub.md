---
external help file: ''
Module Name: Az.SignalR
online version: https://docs.microsoft.com/powershell/module/az.signalr/new-azwebpubsub
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/SignalR/SignalR/help/New-AzWebPubSub.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/SignalR/SignalR/help/New-AzWebPubSub.md
ms.openlocfilehash: 3332891bebf6dcdc082fa6b23f34ce6578eee55c
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142482623"
---
# New-AzWebPubSub

## SYNOPSIS
Membuat atau memperbarui sumber daya.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.signalr/new-azwebpubsub) untuk informasi terbaru.

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

### Contoh 1: Buat sumber daya PubSub Web dengan parameter minimal yang diperlukan.
```powershell
PS C:\> New-AzWebPubSub -ResourceGroupName psdemo -Name psdemo-wps -Location eastus -SkuName Standard_S1

Name                Location      SkuName
----                --------      -------
psdemo-wps          eastus        Standard_S1
```



### Contoh 2: Membuat sumber daya PubSub Web dengan lebih banyak parameter dan memperlihatkan hasilnya
```powershell
PS C:\> $wps = New-AzWebPubSub -ResourceGroupName psdemo -Name psdemo-wps `
-Location eastus -SkuName Standard_S1 -IdentityType SystemAssigned -LiveTraceEnabled true `
-LiveTraceCategory @{ Name='ConnectivityLogs' ; Enabled = 'true' }, @{ Name='MessageLogs' ; Enabled = 'true' }

Name                Location      SkuName
----                --------      -------
psdemo-wps          eastus        Standard_S1

PS C:\> $wps | format-list

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

### -Lokasi
Lokasi GEO sumber daya.
misalnya | AS Barat | AS Timur | As Tengah Utara Selatan Tengah AS.

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

### -Nama
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
Mendapatkan Id langganan yang mengidentifikasi langganan Microsoft Azure secara unik.
ID langganan merupakan bagian dari URI untuk setiap panggilan layanan.

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

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.WebPubSub.Models.Api20211001.IWebPubSubResource

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


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

