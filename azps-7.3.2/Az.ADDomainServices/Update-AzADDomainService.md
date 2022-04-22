---
external help file: ''
Module Name: Az.ADDomainServices
online version: https://docs.microsoft.com/powershell/module/az.addomainservices/update-azaddomainservice
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ADDomainServices/help/Update-AzADDomainService.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ADDomainServices/help/Update-AzADDomainService.md
ms.openlocfilehash: 9bec586e2d0e39ab4b1976cafdd8aba729b9ce83
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142894150"
---
# Update-AzADDomainService

## SYNOPSIS
Operasi Perbarui Layanan Domain dapat digunakan untuk memperbarui penyebaran yang sudah ada.
Panggilan pembaruan hanya mendukung properti yang tercantum dalam isi PATCH.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.addomainservices/update-azaddomainservice) untuk informasi terbaru.

## SYNTAX

### UpdateExpanded (Default)
```
Update-AzADDomainService -Name <String> -ResourceGroupName <String> [-SubscriptionId <String>]
 [-DomainConfigurationType <String>] [-DomainSecuritySettingNtlmV1 <String>]
 [-DomainSecuritySettingSyncKerberosPassword <String>] [-DomainSecuritySettingSyncNtlmPassword <String>]
 [-DomainSecuritySettingSyncOnPremPassword <String>] [-DomainSecuritySettingTlsV1 <String>]
 [-FilteredSync <String>] [-ForestTrust <IForestTrust[]>] [-LdapSettingExternalAccess <String>]
 [-LdapSettingLdaps <String>] [-LdapSettingPfxCertificate <String>]
 [-LdapSettingPfxCertificatePassword <SecureString>] [-NotificationSettingAdditionalRecipient <String[]>]
 [-NotificationSettingNotifyDcAdmin <String>] [-NotificationSettingNotifyGlobalAdmin <String>]
 [-ReplicaSet <IReplicaSet[]>] [-ResourceForest <String>] [-Sku <String>] [-Tag <Hashtable>]
 [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-Confirm] [-WhatIf] [<CommonParameters>]
```

### UpdateViaIdentityExpanded
```
Update-AzADDomainService -InputObject <IAdDomainServicesIdentity> [-DomainConfigurationType <String>]
 [-DomainSecuritySettingNtlmV1 <String>] [-DomainSecuritySettingSyncKerberosPassword <String>]
 [-DomainSecuritySettingSyncNtlmPassword <String>] [-DomainSecuritySettingSyncOnPremPassword <String>]
 [-DomainSecuritySettingTlsV1 <String>] [-FilteredSync <String>] [-ForestTrust <IForestTrust[]>]
 [-LdapSettingExternalAccess <String>] [-LdapSettingLdaps <String>] [-LdapSettingPfxCertificate <String>]
 [-LdapSettingPfxCertificatePassword <SecureString>] [-NotificationSettingAdditionalRecipient <String[]>]
 [-NotificationSettingNotifyDcAdmin <String>] [-NotificationSettingNotifyGlobalAdmin <String>]
 [-ReplicaSet <IReplicaSet[]>] [-ResourceForest <String>] [-Sku <String>] [-Tag <Hashtable>]
 [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Operasi Perbarui Layanan Domain dapat digunakan untuk memperbarui penyebaran yang sudah ada.
Panggilan pembaruan hanya mendukung properti yang tercantum dalam isi PATCH.

## EXAMPLES

### Contoh 1: Update AzADDomainService By ResourceGroupName and Name
```powershell
$ADDomainSetting = New-AzADDomainServiceDomainSecuritySettingObject -TlsV1 Disabled
Update-AzADDomainService -Name youriADdomain -ResourceGroupName youriADdomain -DomainSecuritySetting $ADDomainSetting
```

```output
Name          Domain Name       Location Sku
----          -----------       -------- ---
youriADdomain youriAddomain.com westus   Enterprise
```

Perbarui AzADDomainService Menurut ResourceGroupName dan Name

### Contoh 2: Update AzADDomainService By InputObject
```powershell
$getAzAddomain = Get-AzADDomainService -Name youriADdomain -ResourceGroupName youriADdomain
$ADDomainSetting = New-AzADDomainServiceDomainSecuritySettingObject -TlsV1 Disabled
Update-AzADDomainService -InputObject $getAzAddomain -DomainSecuritySetting $ADDomainSetting
```

```output
Name          Domain Name       Location Sku
----          -----------       -------- ---
youriADdomain youriAddomain.com westus   Enterprise
```

Perbarui AzADDomainService Dengan InputObject

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

### -DomainConfigurationType
Tipe Konfigurasi Domain

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

### -DomainSecuritySettingNtlmV1
Bendera untuk menentukan apakah NtlmV1 diaktifkan atau tidak dinonaktifkan.

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

### -DomainSecuritySettingSyncKerberosPassword
Bendera untuk menentukan apakah SyncKerberosPasswords diaktifkan atau dinonaktifkan.

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

### -DomainSecuritySettingSyncNtlmPassword
Bendera untuk menentukan apakah SyncNtlmPasswords diaktifkan atau tidak.

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

### -DomainSecuritySettingSyncOnPremPassword
Bendera untuk menentukan apakah SyncOnPremPasswords diaktifkan atau dinonaktifkan.

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

### -DomainSecuritySettingTlsV1
Bendera untuk menentukan apakah TlsV1 diaktifkan atau tidak dinonaktifkan.

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

### -FilteredSync
Bendera Diaktifkan atau Dinonaktifkan untuk mengaktifkan sinkronisasi terfilter berbasis grup

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

### -ForestTrust
Daftar pengaturan untuk Hutan Sumber Daya Untuk membangun, lihat bagian CATATAN untuk properti FORESTTRUST dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ADDomainServices.Models.Api202001.IForestTrust[]
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
Type: Microsoft.Azure.PowerShell.Cmdlets.ADDomainServices.Models.IAdDomainServicesIdentity
Parameter Sets: UpdateViaIdentityExpanded
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -LdapSettingExternalAccess
Bendera untuk menentukan apakah akses LDAP Aman atau tidak melalui internet diaktifkan atau dinonaktifkan.

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

### -LdapSettingLdaps
Bendera untuk menentukan apakah LDAP Aman diaktifkan atau tidak dinonaktifkan.

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

### -LdapSettingPfxCertificate
Sertifikat yang diperlukan untuk mengonfigurasi LDAP Aman.
Parameter yang lolos di sini harus berupa representasi base64encoded dari file pfx sertifikat.

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

### -LdapSettingPfxCertificatePassword
Kata sandi untuk mendekripsi file pfx sertifikat LDAP Aman yang disediakan.

```yaml
Type: System.Security.SecureString
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Nama layanan domain.

```yaml
Type: System.String
Parameter Sets: UpdateExpanded
Aliases: DomainServiceName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NotificationSettingAdditionalRecipient
Daftar penerima tambahan

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NotificationSettingNotifyDcAdmin
Haruskah admin pengontrol domain diberi tahu

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

### -NotificationSettingNotifyGlobalAdmin
Haruskah admin global diberi tahu

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

### -ReplicaSet
Daftar ReplicaSet Untuk dibangun, lihat bagian CATATAN untuk properti REPLICASET dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ADDomainServices.Models.Api202001.IReplicaSet[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceForest
Hutan Sumber Daya

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

### -ResourceGroupName
Nama grup sumber daya dalam langganan pengguna.
Nama ini tidak peka huruf besar kecil.

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

### -Sku
Tipe Sku

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

### -SubscriptionId
Mendapatkan kredensial langganan yang mengidentifikasi langganan Microsoft Azure secara unik.
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
Tag sumber daya

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

### Microsoft.Azure.PowerShell.Cmdlets.ADDomainServices.Models.IAdDomainServicesIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ADDomainServices.Models.Api202001.IDomainService

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


FORESTTRUST <IForestTrust[]>: Daftar pengaturan untuk Hutan Sumber Daya
  - `[FriendlyName <String>]`: Nama bersahabat
  - `[RemoteDnsIP <String>]`: Ip Dns Jarak Jauh
  - `[TrustDirection <String>]`: Arah Kepercayaan
  - `[TrustPassword <String>]`: Kata Sandi Kepercayaan
  - `[TrustedDomainFqdn <String>]`: FQDN Domain Tepercaya

INPUTOBJECT <IAdDomainServicesIdentity>: Parameter Identitas
  - `[DomainServiceName <String>]`: Nama layanan domain.
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[ResourceGroupName <String>]`: Nama grup sumber daya dalam langganan pengguna. Nama ini tidak peka huruf besar kecil.
  - `[SubscriptionId <String>]`: Mendapatkan kredensial langganan yang mengidentifikasi langganan Microsoft Azure secara unik. ID langganan merupakan bagian dari URI untuk setiap panggilan layanan.

REPLICASET <IReplicaSet[]>: Daftar ReplicaSet
  - `[Location <String>]`: Lokasi jaringan virtual
  - `[SubnetId <String>]`: Nama jaringan virtual tempat Layanan Domain akan digunakan. Id subnet tempat Layanan Domain akan digunakan. /virtualNetwork/vnetName/subnets/subnetName.

## RELATED LINKS

