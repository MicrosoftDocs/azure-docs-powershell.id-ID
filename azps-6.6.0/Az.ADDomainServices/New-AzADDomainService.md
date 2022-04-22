---
external help file: ''
Module Name: Az.ADDomainServices
online version: https://docs.microsoft.com/powershell/module/az.addomainservices/new-azaddomainservice
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ADDomainServices/help/New-AzADDomainService.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ADDomainServices/help/New-AzADDomainService.md
ms.openlocfilehash: a0195984890d7b3716a7e7649c902f706339cc90
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142972091"
---
# New-AzADDomainService

## SYNOPSIS
Operasi Buat Layanan Domain membuat layanan domain baru dengan parameter yang ditentukan.
Jika layanan tertentu sudah ada, properti patchable apa pun akan diperbarui dan properti yang tidak dapat diubah akan tetap tidak berubah.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.addomainservices/new-azaddomainservice) untuk informasi terbaru.

## SYNTAX

```
New-AzADDomainService -Name <String> -ResourceGroupName <String> -DomainName <String>
 -ReplicaSet <IReplicaSet[]> [-SubscriptionId <String>] [-DomainConfigurationType <String>]
 [-DomainSecuritySettingNtlmV1 <String>] [-DomainSecuritySettingSyncKerberosPassword <String>]
 [-DomainSecuritySettingSyncNtlmPassword <String>] [-DomainSecuritySettingSyncOnPremPassword <String>]
 [-DomainSecuritySettingTlsV1 <String>] [-FilteredSync <String>] [-ForestTrust <IForestTrust[]>]
 [-LdapSettingExternalAccess <String>] [-LdapSettingLdaps <String>] [-LdapSettingPfxCertificate <String>]
 [-LdapSettingPfxCertificatePassword <SecureString>] [-NotificationSettingAdditionalRecipient <String[]>]
 [-NotificationSettingNotifyDcAdmin <String>] [-NotificationSettingNotifyGlobalAdmin <String>]
 [-ResourceForest <String>] [-Sku <String>] [-Tag <Hashtable>] [-DefaultProfile <PSObject>] [-AsJob] [-NoWait]
 [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Operasi Buat Layanan Domain membuat layanan domain baru dengan parameter yang ditentukan.
Jika layanan tertentu sudah ada, properti patchable apa pun akan diperbarui dan properti yang tidak dapat diubah akan tetap tidak berubah.

## EXAMPLES

### Contoh 1: Membuat ADDomainService baru
```powershell
PS C:\> $replicaSet = New-AzADDomainServiceReplicaSetObject -Location westus -SubnetId /subscriptions/********-****-****-****-**********/resourceGroups/yishitest/providers/Microsoft.Network/virtualNetworks/aadds-vnet/subnets/default
New-AzADDomainService -name youriADdomain -ResourceGroupName youriAddomain -DomainName youriAddomain.com -ReplicaSet $replicaSet -debug

Name          Domain Name       Location Sku
----          -----------       -------- ---
youriADdomain youriAddomain.com westus   Enterprise
```

Membuat ADDomainService baru

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

### -DomainName
Nama domain Azure yang ingin digunakan pengguna untuk menyebarkan Layanan Domain.

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
Parameter Sets: (All)
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

Required: True
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
Parameter Sets: (All)
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
Parameter Sets: (All)
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

REPLICASET <IReplicaSet[]>: Daftar ReplicaSet
  - `[Location <String>]`: Lokasi jaringan virtual
  - `[SubnetId <String>]`: Nama jaringan virtual tempat Layanan Domain akan digunakan. Id subnet tempat Layanan Domain akan digunakan. /virtualNetwork/vnetName/subnets/subnetName.

## RELATED LINKS

