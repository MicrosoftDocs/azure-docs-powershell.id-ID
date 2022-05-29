---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Accounts.dll-Help.xml
Module Name: Az.Accounts
online version: https://docs.microsoft.com/powershell/module/az.accounts/connect-azaccount
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Accounts/Accounts/help/Connect-AzAccount.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Accounts/Accounts/help/Connect-AzAccount.md
ms.openlocfilehash: 116ea8f6529bbd80d178764e08acf01abeed0ee5
ms.sourcegitcommit: 321c644cf2161807a71e1af318fc5c5311d22e25
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/25/2022
ms.locfileid: "145809345"
---
# Connect-AzAccount

## SYNOPSIS
Koneksi ke Azure dengan akun terautentikasi untuk digunakan dengan cmdlet dari modul Az PowerShell.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.accounts/connect-azaccount) untuk informasi terbaru.

## SYNTAX

### UserWithSubscriptionId (Default)
```
Connect-AzAccount [-Environment <String>] [-Tenant <String>] [-AccountId <String>] [-Subscription <String>]
 [-AuthScope <String>] [-ContextName <String>] [-SkipContextPopulation] [-MaxContextPopulation <Int32>]
 [-UseDeviceAuthentication] [-Force] [-Scope <ContextModificationScope>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ServicePrincipalWithSubscriptionId
```
Connect-AzAccount [-Environment <String>] -Credential <PSCredential> [-ServicePrincipal] -Tenant <String>
 [-Subscription <String>] [-AuthScope <String>] [-ContextName <String>] [-SkipContextPopulation]
 [-MaxContextPopulation <Int32>] [-Force] [-Scope <ContextModificationScope>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### UserWithCredential
```
Connect-AzAccount [-Environment <String>] -Credential <PSCredential> [-Tenant <String>]
 [-Subscription <String>] [-AuthScope <String>] [-ContextName <String>] [-SkipContextPopulation]
 [-MaxContextPopulation <Int32>] [-Force] [-Scope <ContextModificationScope>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ServicePrincipalCertificateWithSubscriptionId
```
Connect-AzAccount [-Environment <String>] -CertificateThumbprint <String> -ApplicationId <String>
 [-ServicePrincipal] -Tenant <String> [-Subscription <String>] [-AuthScope <String>] [-ContextName <String>]
 [-SkipContextPopulation] [-MaxContextPopulation <Int32>] [-Force] [-SendCertificateChain]
 [-Scope <ContextModificationScope>] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ClientAssertionParameterSet
```
Connect-AzAccount [-Environment <String>] -ApplicationId <String> [-ServicePrincipal] -Tenant <String>
 [-Subscription <String>] [-ContextName <String>] [-SkipContextPopulation] [-MaxContextPopulation <Int32>]
 [-Force] -FederatedToken <String> [-Scope <ContextModificationScope>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ServicePrincipalCertificateFileWithSubscriptionId
```
Connect-AzAccount [-Environment <String>] -ApplicationId <String> [-ServicePrincipal] -Tenant <String>
 [-Subscription <String>] [-ContextName <String>] [-SkipContextPopulation] [-MaxContextPopulation <Int32>]
 [-Force] [-SendCertificateChain] -CertificatePath <String> [-CertificatePassword <SecureString>]
 [-Scope <ContextModificationScope>] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### AccessTokenWithSubscriptionId
```
Connect-AzAccount [-Environment <String>] [-Tenant <String>] -AccessToken <String> [-GraphAccessToken <String>]
 [-MicrosoftGraphAccessToken <String>] [-KeyVaultAccessToken <String>] -AccountId <String>
 [-Subscription <String>] [-ContextName <String>] [-SkipValidation] [-SkipContextPopulation]
 [-MaxContextPopulation <Int32>] [-Force] [-Scope <ContextModificationScope>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ManagedServiceLogin
```
Connect-AzAccount [-Environment <String>] [-Tenant <String>] [-AccountId <String>] [-Identity]
 [-Subscription <String>] [-AuthScope <String>] [-ContextName <String>] [-SkipContextPopulation]
 [-MaxContextPopulation <Int32>] [-Force] [-Scope <ContextModificationScope>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

`Connect-AzAccount` Cmdlet terhubung ke Azure dengan akun terautentikasi untuk digunakan dengan cmdlet dari modul Az PowerShell. Anda hanya dapat menggunakan akun terautentikasi ini dengan permintaan Azure Resource Manager. Untuk menambahkan akun terautentikasi untuk digunakan dengan Manajemen Layanan, gunakan `Add-AzureAccount` cmdlet dari modul Azure PowerShell. Jika tidak ada konteks yang ditemukan untuk pengguna saat ini, daftar konteks pengguna diisi dengan konteks untuk masing-masing dari 25 langganan pertama mereka.
Daftar konteks yang dibuat untuk pengguna dapat ditemukan dengan menjalankan `Get-AzContext -ListAvailable`. Untuk melewati populasi konteks ini, tentukan parameter sakelar **SkipContextPopulation** . Setelah menjalankan cmdlet ini, Anda dapat memutuskan sambungan dari akun Azure menggunakan `Disconnect-AzAccount`.

## EXAMPLES

### Contoh 1: Koneksi ke akun Azure

Contoh ini tersambung ke akun Azure. Anda harus menyediakan akun Microsoft atau kredensial ID organisasi. Jika autentikasi multifaktor diaktifkan untuk kredensial Anda, Anda harus masuk menggunakan opsi interaktif atau menggunakan autentikasi perwakilan layanan.

```powershell
Connect-AzAccount
```

```Output
Account                SubscriptionName TenantId                Environment
-------                ---------------- --------                -----------
azureuser@contoso.com  Subscription1    xxxx-xxxx-xxxx-xxxx     AzureCloud
```

### Contoh 2: Koneksi ke Azure menggunakan kredensial ID organisasi

Skenario ini hanya berfungsi ketika pengguna tidak mengaktifkan autentikasi multifaktor. Perintah pertama meminta kredensial pengguna dan menyimpannya dalam `$Credential` variabel. Perintah kedua tersambung ke akun Azure menggunakan kredensial yang disimpan di `$Credential`. Akun ini mengautentikasi dengan Azure menggunakan kredensial ID organisasi.

```powershell
$Credential = Get-Credential
Connect-AzAccount -Credential $Credential
```

```Output
Account                SubscriptionName TenantId                Environment
-------                ---------------- --------                -----------
azureuser@contoso.com  Subscription1    xxxx-xxxx-xxxx-xxxx     AzureCloud
```

### Contoh 3: Koneksi ke Azure menggunakan akun perwakilan layanan

Perintah pertama menyimpan kredensial perwakilan layanan dalam `$Credential` variabel . Perintah kedua menyambungkan penyewa Azure yang ditentukan menggunakan kredensial perwakilan layanan yang disimpan dalam `$Credential` variabel. Parameter sakelar **ServicePrincipal** menunjukkan bahwa akun mengautentikasi sebagai perwakilan layanan.

```powershell
$Credential = New-Object -TypeName System.Management.Automation.PSCredential -ArgumentList $ApplicationId, $SecuredPassword
Connect-AzAccount -ServicePrincipal -TenantId $TenantId -Credential $Credential
```

```Output
Account                SubscriptionName TenantId                Environment
-------                ---------------- --------                -----------
xxxx-xxxx-xxxx-xxxx    Subscription1    xxxx-xxxx-xxxx-xxxx     AzureCloud
```

### Contoh 4: Gunakan login interaktif untuk menyambungkan ke penyewa dan langganan tertentu

Contoh ini tersambung ke akun Azure dengan penyewa dan langganan yang ditentukan.

```powershell
Connect-AzAccount -Tenant 'xxxx-xxxx-xxxx-xxxx' -SubscriptionId 'yyyy-yyyy-yyyy-yyyy'
```

```Output
Account                SubscriptionName TenantId                Environment
-------                ---------------- --------                -----------
azureuser@contoso.com  Subscription1    xxxx-xxxx-xxxx-xxxx     AzureCloud
```

### Contoh 5: Koneksi menggunakan Identitas Layanan Terkelola

Contoh ini terhubung menggunakan Identitas Layanan Terkelola (MSI) lingkungan host. Misalnya, Anda masuk ke Azure dari komputer virtual yang memiliki MSI yang ditetapkan.

```powershell
Connect-AzAccount -Identity
Set-AzContext -Subscription Subscription1
```

```Output
Account                SubscriptionName TenantId                Environment
-------                ---------------- --------                -----------
MSI@50342              Subscription1    xxxx-xxxx-xxxx-xxxx     AzureCloud
```

### Contoh 6: Koneksi menggunakan login Identitas Layanan Terkelola dan ClientId

Contoh ini tersambung menggunakan Identitas Layanan Terkelola **dari myUserAssignedIdentity**. Ini menambahkan identitas yang ditetapkan pengguna ke mesin virtual, lalu menghubungkan menggunakan ClientId dari identitas yang ditetapkan pengguna. Untuk informasi selengkapnya, lihat [Mengonfigurasi identitas terkelola untuk sumber daya Azure di Azure VM](/azure/active-directory/managed-identities-azure-resources/qs-configure-powershell-windows-vm).

```powershell
$identity = Get-AzUserAssignedIdentity -ResourceGroupName 'myResourceGroup' -Name 'myUserAssignedIdentity'
Get-AzVM -ResourceGroupName contoso -Name testvm | Update-AzVM -IdentityType UserAssigned -IdentityId $identity.Id
Connect-AzAccount -Identity -AccountId $identity.ClientId # Run on the virtual machine
```

```Output
Account                SubscriptionName TenantId                Environment
-------                ---------------- --------                -----------
yyyy-yyyy-yyyy-yyyy    Subscription1    xxxx-xxxx-xxxx-xxxx     AzureCloud
```

### Contoh 7: Koneksi menggunakan sertifikat

Contoh ini tersambung ke akun Azure menggunakan autentikasi perwakilan layanan berbasis sertifikat.
Perwakilan layanan yang digunakan untuk autentikasi harus dibuat dengan sertifikat yang ditentukan. Untuk informasi selengkapnya tentang membuat sertifikat yang ditandatangani sendiri dan menetapkannya izin, lihat [Menggunakan Azure PowerShell untuk membuat perwakilan layanan dengan sertifikat](/azure/active-directory/develop/howto-authenticate-service-principal-powershell)

```powershell
$Thumbprint = 'XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX'
$TenantId = 'yyyyyyyy-yyyy-yyyy-yyyy-yyyyyyy'
$ApplicationId = '00000000-0000-0000-0000-00000000'
Connect-AzAccount -CertificateThumbprint $Thumbprint -ApplicationId $ApplicationId -Tenant $TenantId -ServicePrincipal
```

```Output
Account                      SubscriptionName TenantId                        Environment
-------                      ---------------- --------                        -----------
xxxxxxxx-xxxx-xxxx-xxxxxxxxx Subscription1    yyyyyyyy-yyyy-yyyy-yyyy-yyyyyyy AzureCloud

Account          : xxxxxxxx-xxxx-xxxx-xxxxxxxx
SubscriptionName : MyTestSubscription
SubscriptionId   : zzzzzzzz-zzzz-zzzz-zzzz-zzzzzzzz
TenantId         : yyyyyyyy-yyyy-yyyy-yyyy-yyyyyyy
Environment      : AzureCloud
```

### Contoh 8: Koneksi dengan AuthScope
AuthScope digunakan untuk mendukung skenario bahwa sumber daya sarana data telah meningkatkan autentikasi daripada sumber daya ARM, misalnya penyimpanan membutuhkan MFA tetapi ARM tidak.
Setelah AuthScope ditentukan, misalnya Storage, Connect-AzAccount akan terlebih dahulu masuk dengan cakupan `https://storage.azure.com/`penyimpanan , lalu secara diam-diam memerlukan token untuk ARM.

```powershell
Connect-AzAccount -AuthScope Storage
```

```Output
Account                SubscriptionName TenantId                Environment
-------                ---------------- --------                -----------
yyyy-yyyy-yyyy-yyyy    Subscription1    xxxx-xxxx-xxxx-xxxx     AzureCloud
```

### Contoh 9: Koneksi menggunakan file sertifikat

Contoh ini tersambung ke akun Azure menggunakan autentikasi perwakilan layanan berbasis sertifikat.
File sertifikat, yang ditentukan oleh `CertficatePath`, harus berisi sertifikat dan kunci privat sebagai input.

```powershell
$securePassword = $plainPassword | ConvertTo-SecureString -AsPlainText -Force
$TenantId = 'yyyyyyyy-yyyy-yyyy-yyyy-yyyyyyy'
$ApplicationId = 'zzzzzzzz-zzzz-zzzz-zzzz-zzzzzzzz'
Connect-AzAccount -ServicePrincipal -ApplicationId $ApplicationId -TenantId $TenantId -CertificatePath './certificatefortest.pfx' -CertificatePassword $securePassword
```

```Output
Account                     SubscriptionName TenantId                        Environment
-------                     ---------------- --------                        -----------
xxxxxxxx-xxxx-xxxx-xxxxxxxx Subscription1    yyyyyyyy-yyyy-yyyy-yyyy-yyyyyyy AzureCloud
```

## PARAMETERS

### -AccessToken

Menentukan token akses.

> [!CAUTION]
> Token akses adalah jenis kredensial. Anda harus mengambil tindakan pencegahan keamanan yang sesuai untuk menjaga kerahasiaannya. Token akses juga kehabisan waktu dan dapat mencegah penyelesaian tugas jangka panjang.

```yaml
Type: System.String
Parameter Sets: AccessTokenWithSubscriptionId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AccountId

Id Akun / Id Pengguna / Nama Pengguna untuk masuk dengan parameter **Default (UserWithSubscriptionId)** yang ditetapkan; ID Akun untuk token akses dalam set parameter **AccessToken** ; ID akun untuk layanan **terkelola dalam kumpulan parameter ManagedService** . Dapat berupa ID sumber daya layanan terkelola, atau ID klien terkait.
Untuk menggunakan identitas yang ditetapkan sistem, biarkan bidang ini kosong.

```yaml
Type: System.String
Parameter Sets: UserWithSubscriptionId, ManagedServiceLogin
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: System.String
Parameter Sets: AccessTokenWithSubscriptionId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ApplicationId

ID aplikasi perwakilan layanan.

```yaml
Type: System.String
Parameter Sets: ServicePrincipalCertificateWithSubscriptionId, ClientAssertionParameterSet, ServicePrincipalCertificateFileWithSubscriptionId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AuthScope
Cakupan OAuth opsional untuk masuk, nilai yang telah ditentukan sebelumnya yang didukung: AadGraph, AnalysisServices, Attestation, Batch, DataLake, KeyVault, OperationalInsights, Storage, Synapse. Ini juga mendukung id sumber daya seperti `https://storage.azure.com/`.

```yaml
Type: System.String
Parameter Sets: UserWithSubscriptionId, ServicePrincipalWithSubscriptionId, UserWithCredential, ServicePrincipalCertificateWithSubscriptionId, ManagedServiceLogin
Aliases: AuthScopeTypeName

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CertificatePassword
Kata sandi diperlukan untuk mengakses file sertifikat pkcs#12.

```yaml
Type: System.Security.SecureString
Parameter Sets: ServicePrincipalCertificateFileWithSubscriptionId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CertificatePath
Jalur file sertifikasi dalam format pkcs#12.

```yaml
Type: System.String
Parameter Sets: ServicePrincipalCertificateFileWithSubscriptionId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CertificateThumbprint

Hash Sertifikat atau Thumbprint.

```yaml
Type: System.String
Parameter Sets: ServicePrincipalCertificateWithSubscriptionId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ContextName

Nama konteks Azure default untuk login ini. Untuk informasi selengkapnya tentang konteks Azure, lihat [Azure PowerShell objek konteks](/powershell/azure/context-persistence).

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

### -Credential

Menentukan objek **PSCredential** . Untuk informasi selengkapnya tentang objek **PSCredential** , ketik `Get-Help Get-Credential`. Objek **PSCredential** menyediakan ID pengguna dan kata sandi untuk kredensial ID organisasi, atau ID aplikasi dan rahasia untuk kredensial perwakilan layanan.

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: ServicePrincipalWithSubscriptionId, UserWithCredential
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
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Lingkungan

Lingkungan yang berisi akun Azure.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: EnvironmentName

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FederatedToken
Menentukan token yang disediakan oleh penyedia identitas lain. Penerbit dan subjek dalam token ini harus terlebih dahulu dikonfigurasi agar dipercaya oleh ApplicationId.

> [!CAUTION]
> Token gabungan adalah jenis kredensial. Anda harus mengambil tindakan pencegahan keamanan yang sesuai untuk menjaga kerahasiaannya. Token federasi juga kehabisan waktu dan dapat mencegah tugas jangka panjang selesai.

```yaml
Type: System.String
Parameter Sets: ClientAssertionParameterSet
Aliases: ClientAssertion

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force

Timpa konteks yang ada dengan nama yang sama tanpa meminta.

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

### -GraphAccessToken

AccessToken untuk Layanan Graph.

```yaml
Type: System.String
Parameter Sets: AccessTokenWithSubscriptionId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Identitas

Masuk menggunakan Identitas Layanan Terkelola.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ManagedServiceLogin
Aliases: MSI, ManagedService

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -KeyVaultAccessToken

AccessToken untuk Layanan KeyVault.

```yaml
Type: System.String
Parameter Sets: AccessTokenWithSubscriptionId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaxContextPopulation

Nomor langganan maksimum untuk mengisi konteks setelah masuk. Defaultnya adalah 25. Untuk mengisi semua langganan ke konteks, atur ke -1.

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

### -MicrosoftGraphAccessToken
Token akses ke Microsoft Graph

```yaml
Type: System.String
Parameter Sets: AccessTokenWithSubscriptionId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Cakupan

Menentukan cakupan perubahan konteks, misalnya, apakah perubahan hanya berlaku untuk proses saat ini, atau untuk semua sesi yang dimulai oleh pengguna ini.

```yaml
Type: Microsoft.Azure.Commands.Profile.Common.ContextModificationScope
Parameter Sets: (All)
Aliases:
Accepted values: Process, CurrentUser

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SendCertificateChain
Menentukan apakah klaim x5c (kunci umum sertifikat) harus dikirim ke STS untuk mencapai rollover sertifikat yang mudah dalam Azure AD.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ServicePrincipalCertificateWithSubscriptionId, ServicePrincipalCertificateFileWithSubscriptionId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServicePrincipal

Menunjukkan bahwa akun ini mengautentikasi dengan memberikan kredensial perwakilan layanan.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ServicePrincipalWithSubscriptionId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ServicePrincipalCertificateWithSubscriptionId, ClientAssertionParameterSet, ServicePrincipalCertificateFileWithSubscriptionId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SkipContextPopulation

Melompati populasi konteks jika tidak ada konteks yang ditemukan.

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

### -SkipValidation

Lewati validasi untuk token akses.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: AccessTokenWithSubscriptionId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Langganan

Nama langganan atau ID.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: SubscriptionName, SubscriptionId

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Penyewa

Nama atau ID penyewa opsional.

> [!NOTE]
> Karena keterbatasan API saat ini, Anda harus menggunakan ID penyewa alih-alih nama penyewa saat menyambungkan dengan akun business-to-business (B2B).

```yaml
Type: System.String
Parameter Sets: UserWithSubscriptionId, UserWithCredential, AccessTokenWithSubscriptionId, ManagedServiceLogin
Aliases: Domain, TenantId

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: System.String
Parameter Sets: ServicePrincipalWithSubscriptionId, ServicePrincipalCertificateWithSubscriptionId, ClientAssertionParameterSet, ServicePrincipalCertificateFileWithSubscriptionId
Aliases: Domain, TenantId

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UseDeviceAuthentication

Gunakan autentikasi kode perangkat alih-alih kontrol browser.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: UserWithSubscriptionId
Aliases: DeviceCode, DeviceAuth, Device

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
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf

Menunjukkan yang akan terjadi jika cmdlet dijalankan. Cmdlet tidak dijalankan.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Profile.Models.Core.PSAzureProfile

## NOTES

## RELATED LINKS
