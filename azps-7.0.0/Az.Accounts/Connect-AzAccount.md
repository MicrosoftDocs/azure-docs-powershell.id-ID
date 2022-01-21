---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Accounts.dll-Help.xml
Module Name: Az.Accounts
online version: https://docs.microsoft.com/powershell/module/az.accounts/connect-azaccount
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Accounts/Accounts/help/Connect-AzAccount.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Accounts/Accounts/help/Connect-AzAccount.md
ms.openlocfilehash: 22a0a4da498feccf9292a1e61c21ec8767ba5dad
ms.sourcegitcommit: 579224f3f35e223624deb694bceb0033c84a5856
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 12/07/2021
ms.locfileid: "136557603"
---
# Connect-AzAccount

## SYNOPSIS
Koneksi ke Azure dengan akun terautentikasi untuk digunakan dengan cmdlet dari modul Az PowerShell.

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

### ClientApertionParameterSet
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

Cmdlet `Connect-AzAccount` menghubungkan ke Azure dengan akun terautentikasi untuk digunakan dengan cmdlet dari modul Az PowerShell. Anda dapat menggunakan akun terautentikasi ini hanya dengan permintaan Azure Resource Manager. Untuk menambahkan akun terautentikasi untuk digunakan dengan Manajemen Layanan, gunakan `Add-AzureAccount` cmdlet dari Azure PowerShell layanan. Jika tidak ada konteks untuk pengguna saat ini, daftar konteks pengguna akan diisi dengan konteks untuk setiap 25 langganan pertama mereka.
Daftar konteks yang dibuat untuk pengguna bisa ditemukan dengan menjalankan `Get-AzContext -ListAvailable` . Untuk melewati populasi konteks ini, tentukan parameter **sakelar SkipContextPopulation.** Setelah menjalankan cmdlet ini, Anda dapat memutuskan sambungan dari akun Azure menggunakan `Disconnect-AzAccount` .

## EXAMPLES

### Contoh 1: Koneksi ke akun Azure

Contoh ini terhubung ke akun Azure. Anda harus menyediakan akun Microsoft atau kredensial ID organisasi. Jika multi-factor authentication diaktifkan untuk kredensial, Anda harus masuk menggunakan opsi interaktif atau menggunakan autentikasi prinsipal layanan.

```powershell
Connect-AzAccount
```

```Output
Account                SubscriptionName TenantId                Environment
-------                ---------------- --------                -----------
azureuser@contoso.com  Subscription1    xxxx-xxxx-xxxx-xxxx     AzureCloud
```

### Contoh 2: Koneksi ke Azure menggunakan kredensial ID organisasi

Skenario ini hanya berfungsi jika pengguna tidak mengaktifkan multi-factor auth. Perintah pertama meminta kredensial pengguna dan menyimpannya dalam `$Credential` variabel. Perintah kedua tersambung ke akun Azure menggunakan kredensial yang disimpan di `$Credential` . Akun ini mengautentikasi dengan Azure menggunakan kredensial ID organisasi.

```powershell
$Credential = Get-Credential
Connect-AzAccount -Credential $Credential
```

```Output
Account                SubscriptionName TenantId                Environment
-------                ---------------- --------                -----------
azureuser@contoso.com  Subscription1    xxxx-xxxx-xxxx-xxxx     AzureCloud
```

### Contoh 3: Koneksi ke Azure menggunakan akun prinsipal layanan

Perintah pertama menyimpan kredensial prinsipal layanan dalam `$Credential` variabel. Perintah kedua menyambungkan penyewa Azure tertentu menggunakan kredensial prinsipal layanan yang disimpan dalam `$Credential` variabel. Parameter **sakelar ServicePrincipal** menunjukkan bahwa akun diautentikasi sebagai prinsipal layanan.

```powershell
$Credential = New-Object -TypeName System.Management.Automation.PSCredential -ArgumentList $ApplicationId, $SecuredPassword
Connect-AzAccount -ServicePrincipal -TenantId $TenantId -Credential $Credential
```

```Output
Account                SubscriptionName TenantId                Environment
-------                ---------------- --------                -----------
xxxx-xxxx-xxxx-xxxx    Subscription1    xxxx-xxxx-xxxx-xxxx     AzureCloud
```

### Contoh 4: Gunakan masuk interaktif untuk menyambungkan ke penyewa dan langganan tertentu

Contoh ini terhubung ke akun Azure dengan penyewa dan langganan tertentu.

```powershell
Connect-AzAccount -Tenant 'xxxx-xxxx-xxxx-xxxx' -SubscriptionId 'yyyy-yyyy-yyyy-yyyy'
```

```Output
Account                SubscriptionName TenantId                Environment
-------                ---------------- --------                -----------
azureuser@contoso.com  Subscription1    xxxx-xxxx-xxxx-xxxx     AzureCloud
```

### Contoh 5: Koneksi menggunakan Identitas Layanan Terkelola

Contoh ini tersambung menggunakan lingkungan host Managed Service Identity (MSI). Misalnya, Anda masuk ke Azure dari komputer virtual yang memiliki MSI yang ditetapkan.

```powershell
Connect-AzAccount -Identity
```

```Output
Account                SubscriptionName TenantId                Environment
-------                ---------------- --------                -----------
MSI@50342              Subscription1    xxxx-xxxx-xxxx-xxxx     AzureCloud
```

### Contoh 6: Koneksi menggunakan login Identitas Layanan Terkelola dan ClientId

Contoh ini tersambung menggunakan Managed Service Identity of **myUserAssignedIdentity**. Tambahkan identitas yang ditetapkan pengguna ke komputer virtual, lalu tersambung menggunakan ClientId identitas yang ditetapkan pengguna. Untuk informasi selengkapnya, [lihat Mengonfigurasi identitas terkelola untuk sumber daya Azure pada Azure VM](/azure/active-directory/managed-identities-azure-resources/qs-configure-powershell-windows-vm).

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

Contoh ini tersambung ke akun Azure menggunakan autentikasi prinsipal layanan berbasis sertifikat.
Prinsipal layanan yang digunakan untuk autentikasi harus dibuat dengan sertifikat yang ditentukan. Untuk informasi selengkapnya tentang membuat sertifikat yang ditandatangani sendiri dan menetapkannya izin, lihat [Azure PowerShell untuk membuat prinsipal layanan dengan sertifikat](/azure/active-directory/develop/howto-authenticate-service-principal-powershell)

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
AuthScope digunakan untuk mendukung skenario bahwa sumber daya bidang data memiliki autentikasi yang disempurnakan daripada sumber daya ARM, misalnya penyimpanan memerlukan MFA tetapi ARM tidak.
Setelah AuthScope ditentukan, misalnya Storage, Connect-AzAccount masuk terlebih dahulu dengan lingkup penyimpanan , lalu secara diam-diam memerlukan `https://storage.azure.com/` token untuk ARM.

```powershell
Connect-AzAccount -AuthScope Storage
```

```Output
Account                SubscriptionName TenantId                Environment
-------                ---------------- --------                -----------
yyyy-yyyy-yyyy-yyyy    Subscription1    xxxx-xxxx-xxxx-xxxx     AzureCloud
```

### Contoh 9: Koneksi menggunakan file sertifikat

Contoh ini tersambung ke akun Azure menggunakan autentikasi prinsipal layanan berbasis sertifikat.
File sertifikat, yang ditentukan oleh `CertficatePath` , harus berisi sertifikat dan kunci privat sebagai input.

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
> Token akses merupakan satu jenis kredensial. Anda harus melakukan tindakan pengamanan yang sesuai untuk menjaga kerahasiaannya. Token akses juga dapat membuat waktu habis dan mungkin mencegah penyelesaian tugas yang berjalan lama.

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

Id Akun / Id Pengguna / Nama Pengguna untuk masuk dalam kumpulan parameter **Default (UserWithSubscriptionId);** ID Akun untuk token akses di kumpulan parameter **AccessToken;** ID Akun untuk layanan terkelola dalam kumpulan parameter **ManagedService.** Can be a managed service resource ID, or the associated client ID.
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

ID Aplikasi prinsipal layanan.

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
Lingkup OAuth opsional untuk masuk, nilai yang didukung sebelumnya: AadGraph, AnalysisServices, Attestation, Batch, DataLake, KeyVault, OperationalInsights, Storage, Synapse. Id sumber daya juga mendukung id sumber daya seperti `https://storage.azure.com/` .

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
Kata sandi yang diperlukan untuk mengakses file sertifikat pkcs#12.

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
Jalur file sertifikat dalam format pkcs#12.

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

Nama konteks default Azure untuk masuk ini. Untuk informasi selengkapnya tentang konteks Azure, lihat [Azure PowerShell objek konteks](/powershell/azure/context-persistence).

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

Menentukan objek **PSCredential.** Untuk informasi selengkapnya tentang **objek PSCredential,** ketik `Get-Help Get-Credential` . Objek **PSCredential** menyediakan ID pengguna dan kata sandi untuk kredensial ID organisasi, atau ID aplikasi dan rahasia untuk kredensial prinsipal layanan.

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
Menentukan token yang disediakan oleh penyedia identitas lain. Penerbit dan subjek dalam token ini harus dikonfigurasi terlebih dahulu agar dapat dipercaya oleh ApplicationId.

> [!CAUTION]
> Token gabungan adalah jenis kredensial. Anda harus melakukan tindakan pengamanan yang sesuai untuk menjaga kerahasiaannya. Token gabungan juga akan habis waktu dan mungkin mencegah penyelesaian tugas yang lama.

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

Timpa konteks yang sudah ada dengan nama yang sama tanpa memberikan perintah.

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

AccessToken untuk Graph Baru.

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

### -Identity

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

AccessToken untuk KeyVault Service.

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

Max nomor langganan untuk mengisi konteks setelah masuk. Defaultnya adalah 25. Untuk mengisi semua langganan ke konteks, atur ke -1.

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

### -Lingkup

Menentukan lingkup perubahan konteks, misalnya, apakah perubahan diterapkan hanya pada proses saat ini, atau untuk semua sesi yang dimulai oleh pengguna ini.

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
Menentukan apakah klaim x5c (kunci publik sertifikat) harus dikirimkan ke STS untuk mendapatkan peluncuran sertifikat yang mudah di Azure AD.

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

Menunjukkan bahwa akun ini mengautentikasi dengan menyediakan kredensial prinsipal layanan.

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

Melewatkan populasi konteks jika tidak ada konteks yang ditemukan.

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

Nama Langganan atau ID.

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

Nama penyewa atau ID opsional.

> [!NOTE]
> Karena batasan API saat ini, Anda harus menggunakan ID penyewa, bukan nama penyewa saat menyambungkan dengan akun bisnis ke bisnis (B2B).

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

Gunakan autentikasi kode perangkat dan bukan kontrol browser.

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

### -Konfirmasi

Meminta konfirmasi Anda sebelum menjalankan cmdlet.

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

Memperlihatkan apa yang akan terjadi jika cmdlet berjalan. Cmdlet tidak berjalan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Profile.Models.Core.PSAzureProfile

## CATATAN

## RELATED LINKS
