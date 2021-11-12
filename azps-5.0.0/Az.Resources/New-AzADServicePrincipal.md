---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Resources.dll-Help.xml
Module Name: Az.Resources
ms.assetid: D602F910-B26F-473D-B5B6-C7BDFB0A14CB
online version: https://docs.microsoft.com/en-us/powershell/module/az.resources/new-azadserviceprincipal
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/Resources/Resources/help/New-AzADServicePrincipal.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/Resources/Resources/help/New-AzADServicePrincipal.md
ms.openlocfilehash: 6d268c2378c93bcfb98e64c654880e8055bcede8
ms.sourcegitcommit: 375232b84336ef5e13052504deaa43f5bd4b7f65
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/05/2020
ms.locfileid: "132413533"
---
# New-AzADServicePrincipal

## SYNOPSIS
Membuat prinsipal layanan direktori aktif Azure yang baru.

## SINTAKS

### SimpleParameterSet (Default)

```
New-AzADServicePrincipal [-ApplicationId <Guid>] [-DisplayName <String>] [-StartDate <DateTime>]
 [-EndDate <DateTime>] [-Scope <String>] [-Role <String>] [-SkipAssignment]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ApplicationWithoutCredentialParameterSet

```
New-AzADServicePrincipal -ApplicationId <Guid> [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ApplicationWithPasswordPlainParameterSet

```
New-AzADServicePrincipal -ApplicationId <Guid> [-StartDate <DateTime>] [-EndDate <DateTime>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ApplicationWithPasswordCredentialParameterSet

```
New-AzADServicePrincipal -ApplicationId <Guid> -PasswordCredential <PSADPasswordCredential[]>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ApplicationWithKeyPlainParameterSet

```
New-AzADServicePrincipal -ApplicationId <Guid> -CertValue <String> [-StartDate <DateTime>]
 [-EndDate <DateTime>] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ApplicationWithKeyCredentialParameterSet

```
New-AzADServicePrincipal -ApplicationId <Guid> -KeyCredential <PSADKeyCredential[]>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### DisplayNameWithoutCredentialParameterSet

```
New-AzADServicePrincipal -DisplayName <String> [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### DisplayNameWithPasswordPlainParameterSet

```
New-AzADServicePrincipal -DisplayName <String> [-StartDate <DateTime>] [-EndDate <DateTime>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### DisplayNameWithPasswordCredentialParameterSet

```
New-AzADServicePrincipal -DisplayName <String> -PasswordCredential <PSADPasswordCredential[]>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### DisplayNameWithKeyPlainParameterSet

```
New-AzADServicePrincipal -DisplayName <String> -CertValue <String> [-StartDate <DateTime>]
 [-EndDate <DateTime>] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### DisplayNameWithKeyCredentialParameterSet

```
New-AzADServicePrincipal -DisplayName <String> -KeyCredential <PSADKeyCredential[]>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ApplicationObjectWithPasswordPlainParameterSet

```
New-AzADServicePrincipal -ApplicationObject <PSADApplication> [-StartDate <DateTime>] [-EndDate <DateTime>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ApplicationObjectWithPasswordCredentialParameterSet

```
New-AzADServicePrincipal -ApplicationObject <PSADApplication> -PasswordCredential <PSADPasswordCredential[]>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ApplicationObjectWithKeyPlainParameterSet

```
New-AzADServicePrincipal -ApplicationObject <PSADApplication> -CertValue <String> [-StartDate <DateTime>]
 [-EndDate <DateTime>] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ApplicationObjectWithKeyCredentialParameterSet

```
New-AzADServicePrincipal -ApplicationObject <PSADApplication> -KeyCredential <PSADKeyCredential[]>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESKRIPSI

Membuat prinsipal layanan direktori aktif Azure yang baru. Kumpulan parameter default menggunakan nilai default untuk parameter jika tidak disediakan. Untuk informasi selengkapnya tentang nilai default, lihat deskripsi untuk setiap parameter. Cmdlet ini memiliki kemampuan untuk menetapkan peran ke prinsipal layanan dengan parameter **Peran** **dan** Lingkup. Jika keduanya dihilangkan, peran kontributor ditetapkan pada prinsipal layanan. Nilai default untuk parameter **Peran dan** **Lingkup** adalah **Kontributor untuk** langganan saat ini. Cmdlet membuat aplikasi dan mengatur propertinya jika ApplicationId tidak disediakan. Untuk memperbarui parameter khusus aplikasi, gunakan cmdlet [Update-AzADApplication.](./update-azadapplication.md)

> [!WARNING]
> Ketika Anda membuat prinsipal layanan menggunakan **perintah New-AzADServicePrincipal,** output menyertakan kredensial yang harus Anda proteksi. Pastikan bahwa Anda tidak menyertakan kredensial ini dalam kode Anda atau periksa kredensial ke dalam kontrol sumber Anda. Sebagai alternatif, pertimbangkan [menggunakan identitas terkelola](/azure/active-directory/managed-identities-azure-resources/overview) untuk menghindari perlu menggunakan kredensial.
>
> Secara default, **New-AzADServicePrincipal** menetapkan peran [Kontributor](/azure/role-based-access-control/built-in-roles#contributor) pada prinsipal layanan pada lingkup langganan. Untuk mengurangi risiko prinsipal layanan yang dibobol, tetapkan peran yang lebih spesifik dan persempit lingkupnya pada grup sumber daya atau sumber daya. Lihat [Langkah-langkah untuk menambahkan penetapan peran](/azure/role-based-access-control/role-assignments-steps) untuk informasi selengkapnya.

## CONTOH

### Contoh 1: Pembuatan prinsipal layanan AD sederhana

Contoh berikut membuat prinsipal layanan AD menggunakan nilai default untuk parameter yang tidak ditentukan. Karena ID aplikasi tidak diberikan, aplikasi dibuat untuk prinsipal layanan. Karena tidak ada nilai yang **diberikan untuk** Peran **atau** Lingkup , prinsipal layanan yang dibuat ditetapkan peran **kontributor** untuk langganan saat ini.

```powershell
New-AzADServicePrincipal
```

```Output
Secret                : System.Security.SecureString
ServicePrincipalNames : {00000000-0000-0000-0000-000000000000, http://azure-powershell-05-22-2018-18-23-43}
ApplicationId         : 00000000-0000-0000-0000-000000000000
DisplayName           : azure-powershell-05-22-2018-18-23-43
Id                    : 00000000-0000-0000-0000-000000000000
Type                  : ServicePrincipal
```

### Contoh 2: Pembuatan prinsipal layanan AD sederhana dengan peran tertentu dan lingkup default

Contoh berikut membuat prinsipal layanan AD menggunakan nilai default untuk parameter yang tidak ditentukan. Karena ID aplikasi tidak diberikan, aplikasi dibuat untuk prinsipal layanan. Prinsipal layanan dibuat dengan **izin Reader** untuk langganan saat ini karena tidak ada nilai yang disediakan **untuk** parameter Lingkup.

```powershell
New-AzADServicePrincipal -Role Reader
```

```Output
Secret                : System.Security.SecureString
ServicePrincipalNames : {00000000-0000-0000-0000-000000000000, http://azure-powershell-05-22-2018-18-23-43}
ApplicationId         : 00000000-0000-0000-0000-000000000000
DisplayName           : azure-powershell-05-22-2018-18-23-43
Id                    : 00000000-0000-0000-0000-000000000000
Type                  : ServicePrincipal

WARNING: Assigning role 'Reader' over scope '/subscriptions/00000000-0000-0000-0000-000000000000' to the new service principal.
```

### Contoh 3: Pembuatan prinsipal layanan AD sederhana dengan lingkup tertentu dan peran default

Contoh berikut membuat prinsipal layanan AD menggunakan nilai default untuk parameter yang tidak ditentukan. Karena ID aplikasi tidak diberikan, aplikasi dibuat untuk prinsipal layanan. Prinsipal layanan dibuat dengan izin **Kontributor** untuk lingkup grup sumber daya yang disediakan karena tidak ada nilai yang disediakan untuk **parameter** Peran.

```powershell
New-AzADServicePrincipal -Scope /subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/myResourceGroup
```

```Output
Secret                : System.Security.SecureString
ServicePrincipalNames : {00000000-0000-0000-0000-000000000000, http://azure-powershell-05-22-2018-18-23-43}
ApplicationId         : 00000000-0000-0000-0000-000000000000
DisplayName           : azure-powershell-05-22-2018-18-23-43
Id                    : 00000000-0000-0000-0000-000000000000
Type                  : ServicePrincipal

WARNING: Assigning role 'Contributor' over scope '/subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/myResourceGroup' to the new service principal.
```

### Contoh 4: Pembuatan prinsipal layanan AD sederhana dengan lingkup dan peran tertentu

Contoh berikut membuat prinsipal layanan AD menggunakan nilai default untuk parameter yang tidak ditentukan. Karena ID aplikasi tidak diberikan, aplikasi dibuat untuk prinsipal layanan. Prinsipal layanan dibuat dengan izin **Pembaca untuk** lingkup grup sumber daya yang disediakan.

```powershell
New-AzADServicePrincipal -Role Reader -Scope /subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/myResourceGroup
```

```Output
Secret                : System.Security.SecureString
ServicePrincipalNames : {00000000-0000-0000-0000-000000000000, http://azure-powershell-05-22-2018-18-23-43}
ApplicationId         : 00000000-0000-0000-0000-000000000000
DisplayName           : azure-powershell-05-22-2018-18-23-43
Id                    : 00000000-0000-0000-0000-000000000000
Type                  : ServicePrincipal

WARNING: Assigning role 'Reader' over scope '/subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/myResourceGroup' to the new service principal.
```

### Contoh 5: Membuat pokok layanan AD baru menggunakan ID aplikasi dengan penetapan peran

Contoh berikut membuat prinsipal layanan AD baru untuk aplikasi dengan ID aplikasi '00000000-0000-0000-0000-00000000000'. Karena tidak ada nilai yang **diberikan untuk** Peran **atau** Lingkup , prinsipal layanan yang dibuat ditetapkan peran **kontributor** untuk langganan saat ini.

```powershell
New-AzADServicePrincipal -ApplicationId 00000000-0000-0000-0000-000000000000
```

```Output
ServicePrincipalNames : {00000000-0000-0000-0000-000000000000, http://my-temp-app}
ApplicationId         : 00000000-0000-0000-0000-000000000000
DisplayName           : my-temp-app
Id                    : 00000000-0000-0000-0000-000000000000
Type                  : ServicePrincipal
```

### Contoh 6: Membuat prinsipal layanan AD baru menggunakan pemipaan

Contoh berikut mengambil aplikasi dengan ID objek '3ede3c26-b443-4e0b-9efc-b05e68338dc3' menggunakan cmdlet [Get-AzADApplication.](./get-azadapplication.md) Hasilnya di pipetkan `New-AzADServicePrincipal` ke cmdlet untuk membuat prinsipal layanan AD baru untuk aplikasi tersebut.

```powershell
Get-AzADApplication -ObjectId 3ede3c26-b443-4e0b-9efc-b05e68338dc3 | New-AzADServicePrincipal
```

### Contoh 7: Membuat prinsipal layanan AD baru menggunakan DisplayName dan kredensial kata sandi

Contoh berikut membuat aplikasi baru dengan nama **ServicePrincipalName** dan kata sandi **StrongPassworld!23**. Layanan membuat prinsipal layanan berdasarkan aplikasi yang dibuat. Tanggal mulai dan tanggal berakhir ditambahkan ke kredensial kata sandi.

```powershell
$credentials = New-Object -TypeName Microsoft.Azure.Commands.ActiveDirectory.PSADPasswordCredential -Property @{
  StartDate=Get-Date; EndDate=Get-Date -Year 2024; Password='StrongPassworld!23'}
$sp = New-AzAdServicePrincipal -DisplayName ServicePrincipalName -PasswordCredential $credentials
```

```Output
ServicePrincipalNames : {00000000-0000-0000-0000-000000000000, http://ServicePrincipalName}
ApplicationId         : 00000000-0000-0000-0000-000000000000c
ObjectType            : ServicePrincipal
DisplayName           : ServicePrincipalName
Id                    : 00000000-0000-0000-0000-000000000000
Type                  :
```

### Contoh 8: Membuat prinsipal layanan AD baru menggunakan DisplayName dan kredensial kunci biasa

Contoh berikut membuat aplikasi baru dengan nama **ServicePrincipalName** dan sertifikat **$cert**. Layanan membuat prinsipal layanan berdasarkan aplikasi yang dibuat. Tanggal berakhir ditambahkan ke kredensial kunci.

```powershell
$cert = 'public certificate as Base64 encoded string'
$sp = New-AzADServicePrincipal -DisplayName ServicePrincipalName -CertValue $cert  -EndDate '2021-01-01'
```

```Output
ServicePrincipalNames : {00000000-0000-0000-0000-000000000000, http://ServicePrincipalName}
ApplicationId         : 00000000-0000-0000-0000-000000000000
ObjectType            : ServicePrincipal
DisplayName           : ServicePrincipalName
Id                    : 00000000-0000-0000-0000-000000000000
Type                  :
```

## PARAMETERS

### -ApplicationId

ID aplikasi unik untuk prinsipal layanan dalam penyewa. Setelah dibuat, properti ini tidak dapat diubah. Jika ID aplikasi untuk aplikasi yang sudah ada tidak ditentukan, aplikasi dibuat.

```yaml
Type: System.Guid
Parameter Sets: SimpleParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: System.Guid
Parameter Sets: ApplicationWithoutCredentialParameterSet, ApplicationWithPasswordPlainParameterSet, ApplicationWithPasswordCredentialParameterSet, ApplicationWithKeyPlainParameterSet, ApplicationWithKeyCredentialParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ApplicationObject

Objek yang mewakili aplikasi yang menjadi tujuan dibuatnya prinsipal layanan.

```yaml
Type: Microsoft.Azure.Commands.ActiveDirectory.PSADApplication
Parameter Sets: ApplicationObjectWithPasswordPlainParameterSet, ApplicationObjectWithPasswordCredentialParameterSet, ApplicationObjectWithKeyPlainParameterSet, ApplicationObjectWithKeyCredentialParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -CertValue

Nilai tipe kredensial asimetris. Kode ini mewakili sertifikat berkode Base64.

```yaml
Type: System.String
Parameter Sets: ApplicationWithKeyPlainParameterSet, DisplayNameWithKeyPlainParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

```yaml
Type: System.String
Parameter Sets: ApplicationObjectWithKeyPlainParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### -DisplayName

Nama prinsipal layanan yang mudah di friendly. Jika nama tampilan tidak disediakan, nilai ini akan default untuk **azure-powershell-MM-dd-yyyy-HH-mm-ss** di mana akhiran adalah waktu pembuatan aplikasi.

```yaml
Type: System.String
Parameter Sets: SimpleParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: System.String
Parameter Sets: DisplayNameWithoutCredentialParameterSet, DisplayNameWithPasswordPlainParameterSet, DisplayNameWithPasswordCredentialParameterSet, DisplayNameWithKeyPlainParameterSet, DisplayNameWithKeyCredentialParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EndDate

Tanggal berakhir efektif penggunaan kredensial. Nilai tanggal akhir default adalah satu tahun dari hari ini.
Untuk kredensial tipe asimetris, kredensial ini harus diatur ke aktif atau sebelum tanggal validnya sertifikat X509.

```yaml
Type: System.DateTime
Parameter Sets: SimpleParameterSet, ApplicationObjectWithPasswordPlainParameterSet, ApplicationObjectWithKeyPlainParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: System.DateTime
Parameter Sets: ApplicationWithPasswordPlainParameterSet, ApplicationWithKeyPlainParameterSet, DisplayNameWithPasswordPlainParameterSet, DisplayNameWithKeyPlainParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -KeyCredential

Kumpulan kredensial kunci yang terkait dengan aplikasi.

```yaml
Type: Microsoft.Azure.Commands.ActiveDirectory.PSADKeyCredential[]
Parameter Sets: ApplicationWithKeyCredentialParameterSet, DisplayNameWithKeyCredentialParameterSet
Aliases: KeyCredentials

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

```yaml
Type: Microsoft.Azure.Commands.ActiveDirectory.PSADKeyCredential[]
Parameter Sets: ApplicationObjectWithKeyCredentialParameterSet
Aliases: KeyCredentials

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PasswordCredential

Kumpulan kredensial kata sandi yang terkait dengan aplikasi.

```yaml
Type: Microsoft.Azure.Commands.ActiveDirectory.PSADPasswordCredential[]
Parameter Sets: ApplicationWithPasswordCredentialParameterSet, DisplayNameWithPasswordCredentialParameterSet
Aliases: PasswordCredentials

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

```yaml
Type: Microsoft.Azure.Commands.ActiveDirectory.PSADPasswordCredential[]
Parameter Sets: ApplicationObjectWithPasswordCredentialParameterSet
Aliases: PasswordCredentials

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Peran

Peran prinsipal layanan ada di atas lingkupnya. Jika tidak ada nilai yang **disediakan,** Peran default untuk **peran** Kontributor.

```yaml
Type: System.String
Parameter Sets: SimpleParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Lingkup

Cakupan prinsipal layanan tersebut memiliki izin. Jika tidak ada nilai yang disediakan, **Lingkup** akan default untuk langganan saat ini.

```yaml
Type: System.String
Parameter Sets: SimpleParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SkipAssignment

Jika set, lewati pembuatan penetapan peran default untuk prinsipal layanan.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: SimpleParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StartDate

Tanggal mulai efektif penggunaan kredensial. Nilai tanggal mulai default adalah hari ini. Untuk kredensial tipe asimetris, kredensial ini harus diatur ke aktif atau setelah tanggal sertifikat X509 valid.

```yaml
Type: System.DateTime
Parameter Sets: SimpleParameterSet, ApplicationObjectWithPasswordPlainParameterSet, ApplicationObjectWithKeyPlainParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: System.DateTime
Parameter Sets: ApplicationWithPasswordPlainParameterSet, ApplicationWithKeyPlainParameterSet, DisplayNameWithPasswordPlainParameterSet, DisplayNameWithKeyPlainParameterSet
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

Memperlihatkan apa yang akan terjadi jika cmdlet berjalan. Cmdlet tidak berjalan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](/powershell/module/microsoft.powershell.core/about/about_commonparameters).
## INPUT

### System.Guid

### System.String

### Microsoft.Azure.Commands.ActiveDirectory.FOLDApplication

### Microsoft.Azure.Commands.ActiveDirectory.LINUXDPasswordCredential[]

### Microsoft.Azure.Commands.ActiveDirectory.LINUXDKeyCredential[]

### System.DateTime

## OUTPUT

### Microsoft.Azure.Commands.ActiveDirectory.LINUXDServicePrincipal

### Microsoft.Azure.Commands.Resources.Models.Authorization.BURDServicePrincipalWra azure

## CATATAN

Kata kunci: azure, azurerm, arm, resource, management, manager, resource, group, template, deployment

## LINK TERKAIT

[Remove-AzADServicePrincipal](./Remove-AzADServicePrincipal.md)

[Get-AzADServicePrincipal](./Get-AzADServicePrincipal.md)

[New-AzADApplication](./New-AzADApplication.md)

[Remove-AzADApplication](./Remove-AzADApplication.md)

[Get-AzADSpCredential](./Get-AzADSpCredential.md)

[New-AzADSpCredential](./New-AzADSpCredential.md)

[Remove-AzADSpCredential](./Remove-AzADSpCredential.md)