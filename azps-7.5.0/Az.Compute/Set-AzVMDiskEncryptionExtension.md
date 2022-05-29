---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Compute.dll-Help.xml
Module Name: Az.Compute
ms.assetid: 6BCB36BC-F5E6-4EDD-983C-8BDE7A9B004D
online version: https://docs.microsoft.com/powershell/module/az.compute/set-azvmdiskencryptionextension
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Set-AzVMDiskEncryptionExtension.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Set-AzVMDiskEncryptionExtension.md
ms.openlocfilehash: de2f213db28017ff003b535146877f0127aa32e5
ms.sourcegitcommit: 82b4008b76d035e4aee733727371765b0d853bed
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145732816"
---
# Set-AzVMDiskEncryptionExtension

## SYNOPSIS
Mengaktifkan enkripsi pada komputer virtual IaaS yang sedang berjalan di Azure.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.compute/set-azvmdiskencryptionextension) untuk informasi terbaru.

## SYNTAX

### SinglePassParameterSet (Default)
```
Set-AzVMDiskEncryptionExtension [-ResourceGroupName] <String> [-VMName] <String>
 [-DiskEncryptionKeyVaultUrl] <String> [-DiskEncryptionKeyVaultId] <String> [[-KeyEncryptionKeyUrl] <String>]
 [[-KeyEncryptionKeyVaultId] <String>] [[-KeyEncryptionAlgorithm] <String>] [[-VolumeType] <String>]
 [[-SequenceVersion] <String>] [[-TypeHandlerVersion] <String>] [[-Name] <String>] [[-Passphrase] <String>]
 [-Force] [-DisableAutoUpgradeMinorVersion] [-SkipVmBackup] [-ExtensionType <String>]
 [-ExtensionPublisherName <String>] [-EncryptFormatAll] [-DefaultProfile <IAzureContextContainer>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### AADClientSecretParameterSet
```
Set-AzVMDiskEncryptionExtension [-ResourceGroupName] <String> [-VMName] <String> [-AadClientID] <String>
 [-AadClientSecret] <String> [-DiskEncryptionKeyVaultUrl] <String> [-DiskEncryptionKeyVaultId] <String>
 [[-KeyEncryptionKeyUrl] <String>] [[-KeyEncryptionKeyVaultId] <String>] [[-KeyEncryptionAlgorithm] <String>]
 [[-VolumeType] <String>] [[-SequenceVersion] <String>] [[-TypeHandlerVersion] <String>] [[-Name] <String>]
 [[-Passphrase] <String>] [-Force] [-DisableAutoUpgradeMinorVersion] [-SkipVmBackup] [-ExtensionType <String>]
 [-ExtensionPublisherName <String>] [-EncryptFormatAll] [-DefaultProfile <IAzureContextContainer>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### AADClientCertParameterSet
```
Set-AzVMDiskEncryptionExtension [-ResourceGroupName] <String> [-VMName] <String> [-AadClientID] <String>
 [-AadClientCertThumbprint] <String> [-DiskEncryptionKeyVaultUrl] <String> [-DiskEncryptionKeyVaultId] <String>
 [[-KeyEncryptionKeyUrl] <String>] [[-KeyEncryptionKeyVaultId] <String>] [[-KeyEncryptionAlgorithm] <String>]
 [[-VolumeType] <String>] [[-SequenceVersion] <String>] [[-TypeHandlerVersion] <String>] [[-Name] <String>]
 [[-Passphrase] <String>] [-Force] [-DisableAutoUpgradeMinorVersion] [-SkipVmBackup] [-ExtensionType <String>]
 [-ExtensionPublisherName <String>] [-EncryptFormatAll] [-DefaultProfile <IAzureContextContainer>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### MigrasiADEVersionParameterSet
```
Set-AzVMDiskEncryptionExtension [-ResourceGroupName] <String> [-VMName] <String> [-Migrate]
```

### MigrasiADEVersionRecoveryParameterSet
```
Set-AzVMDiskEncryptionExtension [-ResourceGroupName] <String> [-VMName] <String> [-MigrationRecovery]
```

## DESCRIPTION
Cmdlet **Set-AzVMDiskEncryptionExtension** memungkinkan enkripsi pada komputer virtual infrastruktur sebagai layanan (IaaS) yang sedang berjalan di Azure.  Ini memungkinkan enkripsi dengan menginstal ekstensi enkripsi disk pada komputer virtual. 

Cmdlet ini memerlukan konfirmasi dari pengguna sebagai salah satu langkah untuk mengaktifkan enkripsi memerlukan mulai ulang komputer virtual.

Disarankan agar Anda menyimpan pekerjaan Anda di komputer virtual sebelum menjalankan cmdlet ini.

Linux: Parameter **VolumeType** diperlukan saat mengenkripsi komputer virtual Linux, dan harus diatur ke nilai ("Os", "Data", atau "Semua") yang didukung oleh distribusi Linux. 

Windows: Parameter **VolumeType** dapat dihilangkan, dalam hal ini operasi default ke Semua; jika parameter VolumeType ada untuk komputer virtual Windows, parameter tersebut harus diatur ke Semua atau OS.

## EXAMPLES

### Contoh 1: Mengaktifkan enkripsi
```powershell
$RGName = "MyResourceGroup"
$VMName = "MyTestVM"
$VaultName= "MyKeyVault"
$KeyVault = Get-AzKeyVault -VaultName $VaultName -ResourceGroupName $RGName
$DiskEncryptionKeyVaultUrl = $KeyVault.VaultUri
$KeyVaultResourceId = $KeyVault.ResourceId
$VolumeType = "All"
Set-AzVMDiskEncryptionExtension -ResourceGroupName $RGName -VMName $VMName -DiskEncryptionKeyVaultUrl $DiskEncryptionKeyVaultUrl -DiskEncryptionKeyVaultId $KeyVaultResourceId -VolumeType $VolumeType
```

Contoh ini memungkinkan enkripsi pada VM tanpa menentukan kredensial AD.

### Contoh 2: Mengaktifkan enkripsi dengan input yang disalurkan
```powershell
$params = New-Object PSObject -Property @{
    ResourceGroupName = "[resource-group-name]"
    VMName = "[vm-name]"
    DiskEncryptionKeyVaultId = "/subscriptions/[subscription-id-guid]/resourceGroups/[resource-group-name]/providers/Microsoft.KeyVault/vaults/[keyvault-name]"
    DiskEncryptionKeyVaultUrl = "https://[keyvault-name].vault.azure.net"
    KeyEncryptionKeyVaultId = "/subscriptions/[subscription-id-guid]/resourceGroups/[resource-group-name]/providers/Microsoft.KeyVault/vaults/[keyvault-name]"
    KeyEncryptionKeyUrl = "https://[keyvault-name].vault.azure.net/keys/[kekname]/[kek-unique-id]"
    VolumeType = "All"
}

$params | Set-AzVmDiskEncryptionExtension
```

Contoh ini mengirim parameter menggunakan input yang disalurkan untuk mengaktifkan enkripsi pada VM, tanpa menentukan kredensial AD.

### Contoh 3: Mengaktifkan enkripsi menggunakan Azure AD ID Klien dan Rahasia Klien
```powershell
$RGName = "MyResourceGroup"
$VMName = "MyTestVM"
$AADClientID = "<clientID of your Azure AD app>"
$AADClientSecret = "<clientSecret of your Azure AD app>"
$VaultName= "MyKeyVault"
$KeyVault = Get-AzKeyVault -VaultName $VaultName -ResourceGroupName $RGName
$DiskEncryptionKeyVaultUrl = $KeyVault.VaultUri
$KeyVaultResourceId = $KeyVault.ResourceId
$VolumeType = "All"
Set-AzVMDiskEncryptionExtension -ResourceGroupName $RGName -VMName $VMName -AadClientID $AADClientID -AadClientSecret $AADClientSecret -DiskEncryptionKeyVaultUrl $DiskEncryptionKeyVaultUrl -DiskEncryptionKeyVaultId $KeyVaultResourceId -VolumeType $VolumeType
```

Contoh ini menggunakan Azure AD ID klien dan rahasia klien untuk mengaktifkan enkripsi pada VM.

### Contoh 4: Mengaktifkan enkripsi menggunakan ID klien Azure AD dan thumbprint sertifikasi klien
```powershell
$RGName = "MyResourceGroup"
$VMName = "MyTestVM"
#The KeyVault must have enabledForDiskEncryption property set on it
$VaultName= "MyKeyVault"
$KeyVault = Get-AzKeyVault -VaultName $VaultName -ResourceGroupName $RGName
$DiskEncryptionKeyVaultUrl = $KeyVault.VaultUri
$KeyVaultResourceId = $KeyVault.ResourceId
$VolumeType = "All"

# create Azure AD application and associate the certificate
$CertPath = "C:\certificates\examplecert.pfx"
$CertPassword = "Password"
$Cert = New-Object System.Security.Cryptography.X509Certificates.X509Certificate2($CertPath, $CertPassword)
$CertValue = [System.Convert]::ToBase64String($cert.GetRawCertData())
$AzureAdApplication = New-AzADApplication -DisplayName "<Your Application Display Name>" -HomePage "<https://YourApplicationHomePage>" -IdentifierUris "<https://YouApplicationUri>" -CertValue $CertValue 
$ServicePrincipal = New-AzADServicePrincipal -ApplicationId $AzureAdApplication.ApplicationId

$AADClientID = $AzureAdApplication.ApplicationId
$aadClientCertThumbprint= $cert.Thumbprint

#Upload pfx to KeyVault 
$KeyVaultSecretName = "MyAADCert"
$FileContentBytes = get-content $CertPath -Encoding Byte
$FileContentEncoded = [System.Convert]::ToBase64String($fileContentBytes)
$JSONObject = @"
    { 
        "data" : "$filecontentencoded", 
        "dataType" : "pfx", 
        "password" : "$CertPassword" 
    } 
"@
$JSONObjectBytes = [System.Text.Encoding]::UTF8.GetBytes($jsonObject)
$JSONEncoded = [System.Convert]::ToBase64String($jsonObjectBytes)

$Secret = ConvertTo-SecureString -String $JSONEncoded -AsPlainText -Force
Set-AzKeyVaultSecret -VaultName $VaultName -Name $KeyVaultSecretName -SecretValue $Secret
Set-AzKeyVaultAccessPolicy -VaultName $VaultName -ResourceGroupName $RGName -EnabledForDeployment

#deploy cert to VM
$CertUrl = (Get-AzKeyVaultSecret -VaultName $VaultName -Name $KeyVaultSecretName).Id
$SourceVaultId = (Get-AzKeyVault -VaultName $VaultName -ResourceGroupName $RGName).ResourceId
$VM = Get-AzVM -ResourceGroupName $RGName -Name $VMName 
$VM = Add-AzVMSecret -VM $VM -SourceVaultId $SourceVaultId -CertificateStore "My" -CertificateUrl $CertUrl
Update-AzVM -VM $VM -ResourceGroupName $RGName 

#Enable encryption on the virtual machine using Azure AD client ID and client cert thumbprint
Set-AzVMDiskEncryptionExtension -ResourceGroupName $RGName -VMName $VMName -AadClientID $AADClientID -AadClientCertThumbprint $AADClientCertThumbprint -DiskEncryptionKeyVaultUrl $DiskEncryptionKeyVaultUrl -DiskEncryptionKeyVaultId $KeyVaultResourceId -VolumeType $VolumeType
```

Contoh ini menggunakan Azure AD ID klien dan thumbprint sertifikasi klien untuk mengaktifkan enkripsi pada VM.

### Contoh 5: Mengaktifkan enkripsi menggunakan Azure AD ID klien, rahasia klien, dan membungkus kunci enkripsi disk dengan menggunakan kunci enkripsi kunci
```powershell
$RGName = "MyResourceGroup"
$VMName = "MyTestVM"

$AADClientID = "<clientID of your Azure AD app>"
$AADClientSecret = "<clientSecret of your Azure AD app>"

$VaultName= "MyKeyVault"
$KeyVault = Get-AzKeyVault -VaultName $VaultName -ResourceGroupName $RGName
$DiskEncryptionKeyVaultUrl = $KeyVault.VaultUri
$KeyVaultResourceId = $KeyVault.ResourceId
$VolumeType = "All"

$KEKName = "MyKeyEncryptionKey"
$KEK = Add-AzKeyVaultKey -VaultName $VaultName -Name $KEKName -Destination "Software"
$KeyEncryptionKeyUrl = $KEK.Key.kid

Set-AzVMDiskEncryptionExtension -ResourceGroupName $RGName -VMName $VMName -AadClientID $AADClientID -AadClientSecret $AADClientSecret -DiskEncryptionKeyVaultUrl $DiskEncryptionKeyVaultUrl -DiskEncryptionKeyVaultId $KeyVaultResourceId -KeyEncryptionKeyUrl $KeyEncryptionKeyUrl -KeyEncryptionKeyVaultId $KeyVaultResourceId -VolumeType $VolumeType
```

Contoh ini menggunakan Azure AD ID klien dan rahasia klien untuk mengaktifkan enkripsi pada VM, dan membungkus kunci enkripsi disk menggunakan kunci enkripsi kunci.

### Contoh 6: Aktifkan enkripsi menggunakan ID klien Azure AD, thumbprint sertifikasi klien, dan bungkus kunci enkripsi disk dengan menggunakan kunci enkripsi kunci
```powershell
$RGName = "MyResourceGroup"
$VMName = "MyTestVM"
#The KeyVault must have enabledForDiskEncryption property set on it
$VaultName= "MyKeyVault"
$KeyVault = Get-AzKeyVault -VaultName $VaultName -ResourceGroupName $RGName
$DiskEncryptionKeyVaultUrl = $KeyVault.VaultUri
$KeyVaultResourceId = $KeyVault.ResourceId
$KEKName = "MyKeyEncryptionKey"
$KEK = Add-AzKeyVaultKey -VaultName $VaultName -Name $KEKName -Destination "Software"
$KeyEncryptionKeyUrl = $KEK.Key.kid
$VolumeType = "All"

# create Azure AD application and associate the certificate
$CertPath = "C:\certificates\examplecert.pfx"
$CertPassword = "Password"
$Cert = New-Object System.Security.Cryptography.X509Certificates.X509Certificate2($CertPath, $CertPassword)
$CertValue = [System.Convert]::ToBase64String($cert.GetRawCertData())
$AzureAdApplication = New-AzADApplication -DisplayName "<Your Application Display Name>" -HomePage "<https://YourApplicationHomePage>" -IdentifierUris "<https://YouApplicationUri>" -CertValue $CertValue
$ServicePrincipal = New-AzADServicePrincipal -ApplicationId $AzureAdApplication.ApplicationId

$AADClientID = $AzureAdApplication.ApplicationId
$AADClientCertThumbprint= $Cert.Thumbprint

#Upload pfx to KeyVault 
$KeyVaultSecretName = "MyAADCert"
$FileContentBytes = get-content $CertPath -Encoding Byte
$FileContentEncoded = [System.Convert]::ToBase64String($FileContentBytes)
$JSONObject = @"
    { 
        "data" : "$filecontentencoded", 
        "dataType" : "pfx", 
        "password" : "$CertPassword" 
    } 
"@
$JSONObjectBytes = [System.Text.Encoding]::UTF8.GetBytes($JSONObject)
$JsonEncoded = [System.Convert]::ToBase64String($JSONObjectBytes)
$Secret = ConvertTo-SecureString -String $JSONEncoded -AsPlainText -Force
Set-AzKeyVaultSecret -VaultName $VaultName-Name $KeyVaultSecretName -SecretValue $Secret
Set-AzKeyVaultAccessPolicy -VaultName $VaultName -ResourceGroupName $RGName -EnabledForDeployment

#deploy cert to VM
$CertUrl = (Get-AzKeyVaultSecret -VaultName $VaultName -Name $KeyVaultSecretName).Id
$SourceVaultId = (Get-AzKeyVault -VaultName $VaultName -ResourceGroupName $RGName).ResourceId
$VM = Get-AzVM -ResourceGroupName $RGName -Name $VMName 
$VM = Add-AzVMSecret -VM $VM -SourceVaultId $SourceVaultId -CertificateStore "My" -CertificateUrl $CertUrl 
Update-AzVM -VM $VM -ResourceGroupName $RGName 

#Enable encryption on the virtual machine using Azure AD client ID and client cert thumbprint
Set-AzVMDiskEncryptionExtension -ResourceGroupName $RGname -VMName $VMName -AadClientID $AADClientID -AadClientCertThumbprint $AADClientCertThumbprint -DiskEncryptionKeyVaultUrl $DiskEncryptionKeyVaultUrl -DiskEncryptionKeyVaultId $KeyVaultResourceId -KeyEncryptionKeyUrl $KeyEncryptionKeyUrl -KeyEncryptionKeyVaultId $KeyVaultResourceId -VolumeType $VolumeType
```

Contoh ini menggunakan Azure AD ID klien dan thumbprint sertifikasi klien untuk mengaktifkan enkripsi pada VM, dan membungkus kunci enkripsi disk menggunakan kunci enkripsi kunci.

## PARAMETERS

### -AadClientCertThumbprint
Menentukan thumbprint sertifikat klien aplikasi AzureActive Directory (Azure AD) yang memiliki izin untuk menulis rahasia ke **KeyVault**.
Sebagai prasyarat, sertifikat klien Azure AD sebelumnya harus disebarkan ke penyimpanan sertifikat komputer `my` lokal komputer virtual.
Cmdlet Add-AzVMSecret dapat digunakan untuk menyebarkan sertifikat ke komputer virtual di Azure.
Untuk detail selengkapnya, lihat bantuan cmdlet **Add-AzVMSecret** .
Sertifikat sebelumnya harus disebarkan ke komputer lokal komputer virtual penyimpanan sertifikat saya.

```yaml
Type: System.String
Parameter Sets: AADClientCertParameterSet
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -AadClientID
Menentukan ID klien dari aplikasi Azure AD yang memiliki izin untuk menulis rahasia ke **KeyVault**.

```yaml
Type: System.String
Parameter Sets: AADClientSecretParameterSet, AADClientCertParameterSet
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -AadClientSecret
Menentukan rahasia klien dari aplikasi Azure AD yang memiliki izin untuk menulis rahasia ke **KeyVault**.

```yaml
Type: System.String
Parameter Sets: AADClientSecretParameterSet
Aliases:

Required: True
Position: 3
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

### -DisableAutoUpgradeMinorVersion
Menunjukkan bahwa cmdlet ini menonaktifkan peningkatan otomatis versi minor ekstensi.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: 14
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DiskEncryptionKeyVaultId
Menentukan ID sumber daya **KeyVault** tempat kunci enkripsi komputer virtual harus diunggah.

```yaml
Type: System.String
Parameter Sets: AADClientSecretParameterSet, AADClientCertParameterSet, SinglePassParameterSet
Aliases:

Required: True
Position: 5
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DiskEncryptionKeyVaultUrl
Menentukan URL **KeyVault** tempat kunci enkripsi komputer virtual harus diunggah.

```yaml
Type: System.String
Parameter Sets: AADClientSecretParameterSet, AADClientCertParameterSet, SinglePassParameterSet
Aliases:

Required: True
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EncryptFormatAll
Encrypt-Format semua drive data yang belum dienkripsi

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

### -ExtensionPublisherName
Nama penerbit ekstensi. Tentukan parameter ini hanya untuk mengambil alih nilai default "Microsoft.Azure.Security".

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ExtensionType
Jenis ekstensi. Tentukan parameter ini untuk mengambil alih nilai default "AzureDiskEncryption" untuk VM Windows dan "AzureDiskEncryptionForLinux" untuk VM Linux.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Force
Memaksa perintah untuk berjalan tanpa meminta konfirmasi pengguna.

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

### -Migrasi
Memulai migrasi VM ke versi ekstensi Azure Disk Encryption terbaru (ADE tanpa kredensial AAD).

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: MigrateADEVersionParameterSet
Aliases:

Required: true
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MigrationRecovery
Memulai pemulihan migrasi untuk kegagalan selama migrasi versi ekstensi ADE dengan versi ekstensi AAD ke ADE tanpa AAD.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: MigrateADEVersionRecoveryParameterSet
Aliases:

Required: true
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -KeyEncryptionAlgorithm
Menentukan algoritma yang digunakan untuk membungkus dan membongkar kunci enkripsi kunci komputer virtual.
Nilai defaultnya adalah RSA-OAEP.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: RSA-OAEP, RSA1_5

Required: False
Position: 8
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -KeyEncryptionKeyUrl
Menentukan URL kunci enkripsi kunci yang digunakan untuk membungkus dan membongkar kunci enkripsi komputer virtual.
Ini harus berupa URL versi lengkap.

```yaml
Type: System.String
Parameter Sets: AADClientSecretParameterSet, AADClientCertParameterSet, SinglePassParameterSet
Aliases:

Required: False
Position: 6
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -KeyEncryptionKeyVaultId
Menentukan ID sumber daya **KeyVault** yang berisi kunci enkripsi kunci yang digunakan untuk membungkus dan membongkar kunci enkripsi komputer virtual.
Ini harus berupa URL versi lengkap.

```yaml
Type: System.String
Parameter Sets: AADClientSecretParameterSet, AADClientCertParameterSet, SinglePassParameterSet
Aliases:

Required: False
Position: 7
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Menentukan nama sumber daya Azure Resource Manager yang mewakili ekstensi. Jika parameter *Nama* dihilangkan, ekstensi yang diinstal akan diberi nama AzureDiskEncryption pada komputer virtual Windows dan AzureDiskEncryptionForLinux pada komputer virtual Linux.


```yaml
Type: System.String
Parameter Sets: (All)
Aliases: ExtensionName

Required: False
Position: 12
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Frase sandi
Menentukan frasa sandi yang digunakan hanya untuk mengenkripsi komputer virtual Linux.
Parameter ini tidak digunakan untuk komputer virtual yang menjalankan sistem operasi Windows.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 13
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Menentukan nama grup sumber daya komputer virtual.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SequenceVersion
Menentukan nomor urut operasi enkripsi untuk komputer virtual.
Ini unik per setiap operasi enkripsi yang dilakukan pada komputer virtual yang sama.
Cmdlet Get-AzVMExtension dapat digunakan untuk mengambil nomor urutan sebelumnya yang digunakan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 10
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SkipVmBackup
Lewati pembuatan cadangan untuk VM Linux

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: 15
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TypeHandlerVersion
Menentukan versi ekstensi enkripsi.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: HandlerVersion, Version

Required: False
Position: 11
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VMName
Menentukan nama komputer virtual.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: ResourceName

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VolumeType
Menentukan jenis volume komputer virtual untuk melakukan operasi enkripsi: OS, Data, atau Semua. 

Linux: Parameter **VolumeType** diperlukan saat mengenkripsi komputer virtual Linux, dan harus diatur ke nilai ("Os", "Data", atau "Semua") yang didukung oleh distribusi Linux. 

Windows: Parameter **VolumeType** dapat dihilangkan, dalam hal ini operasi default ke Semua; jika parameter VolumeType ada untuk komputer virtual Windows, parameter tersebut harus diatur ke Semua atau OS.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: OS, Data, All

Required: False
Position: 9
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Menunjukkan yang akan terjadi jika cmdlet dijalankan.
Cmdlet tidak dijalankan.

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

### System.Management.Automation.SwitchParameter

## OUTPUTS

### Microsoft.Azure.Commands.Compute.Models.PSAzureOperationResponse

## NOTES

## RELATED LINKS

[Add-AzVMSecret](./Add-AzVMSecret.md)

[Get-AzVMDiskEncryptionStatus](./Get-AzVMDiskEncryptionStatus.md)

[Remove-AzVMDiskEncryptionExtension](./Remove-AzVMDiskEncryptionExtension.md)


