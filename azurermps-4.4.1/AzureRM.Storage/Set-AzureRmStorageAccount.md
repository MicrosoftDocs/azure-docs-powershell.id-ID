---
external help file: Microsoft.Azure.Commands.Management.Storage.dll-Help.xml
Module Name: AzureRM.Storage
ms.assetid: 4D7EEDD7-89D4-4B1E-A9A1-B301E759CE72
online version: ''
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Storage/Stack/Commands.Management.Storage/help/Set-AzureRmStorageAccount.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Storage/Stack/Commands.Management.Storage/help/Set-AzureRmStorageAccount.md
ms.openlocfilehash: 5ca65c09746f6bb9a050c14fe10987702465b484
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132422311"
---
# Set-AzureRmStorageAccount

## SYNOPSIS
Mengubah akun Storage Anda.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### StorageEncryption (Default)
```
Set-AzureRmStorageAccount [-ResourceGroupName] <String> [-Name] <String> [-Force] [[-SkuName] <String>]
 [[-AccessTier] <String>] [[-CustomDomainName] <String>] [[-UseSubDomain] <Boolean>]
 [[-EnableEncryptionService] <EncryptionSupportServiceEnum>]
 [[-DisableEncryptionService] <EncryptionSupportServiceEnum>] [[-Tag] <Hashtable>]
 [-EnableHttpsTrafficOnly <Boolean>] [-StorageEncryption] [-AssignIdentity]
 [-NetworkRuleSet <PSNetworkRuleSet>] [-DefaultProfile <IAzureContextContainer>]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### KeyvaultEncryption
```
Set-AzureRmStorageAccount [-ResourceGroupName] <String> [-Name] <String> [-Force] [[-SkuName] <String>]
 [[-AccessTier] <String>] [[-CustomDomainName] <String>] [[-UseSubDomain] <Boolean>]
 [[-EnableEncryptionService] <EncryptionSupportServiceEnum>]
 [[-DisableEncryptionService] <EncryptionSupportServiceEnum>] [[-Tag] <Hashtable>]
 [-EnableHttpsTrafficOnly <Boolean>] [-KeyvaultEncryption] -KeyName <String> -KeyVersion <String>
 -KeyVaultUri <String> [-AssignIdentity] [-NetworkRuleSet <PSNetworkRuleSet>]
 [-DefaultProfile <IAzureContextContainer>] [-InformationAction <ActionPreference>]
 [-InformationVariable <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzureRmStorageAccount** mengubah akun Azure Storage Anda.
Anda dapat menggunakan cmdlet ini untuk mengubah tipe akun, memperbarui domain pelanggan, atau mengatur tag di akun Storage Anda.

## EXAMPLES

### Contoh 1: Atur tipe akun Storage Anda
```
PS C:\>Set-AzureRmStorageAccount -ResourceGroupName "MyResourceGroup" -AccountName "MyStorageAccount" -Type "Standard_RAGRS"
```

Perintah ini mengatur tipe Storage ini ke Standard_RAGRS.

### Contoh 2: Mengatur domain kustom untuk akun Storage Anda
```
PS C:\>Set-AzureRmStorageAccount -ResourceGroupName "MyResourceGroup" -AccountName "MyStorageAccount" -CustomDomainName "www.contoso.com" -UseSubDomain $True
```

Perintah ini mengatur domain kustom untuk suatu Storage kustom.

### Contoh 3: Aktifkan enkripsi pada Blob dan Layanan File
```
PS C:\>Set-AzureRmStorageAccount -ResourceGroupName "MyResourceGroup" -AccountName "MyStorageAccount" -EnableEncryptionService "Blob,File"
```

Perintah ini memungkinkan Storage Enkripsi Layanan pada Blob dan File untuk Storage pengguna.

### Contoh 4: Mengatur nilai tingkat akses
```
PS C:\>Set-AzureRmStorageAccount -ResourceGroupName "MyResourceGroup" -AccountName "MyStorageAccount" -AccessTier Cool
```

Perintah mengatur nilai Tingkat Akses menjadi keren.

### Contoh 4: Setel domain dan tag kustom
```
PS C:\>Set-AzureRmStorageAccount -ResourceGroupName "MyResourceGroup" -AccountName "MyStorageAccount" -CustomDomainName "www.domainname.com" -UseSubDomain $true -Tag @{tag0="value0";tag1="value1";tag2="value2"}
```

Perintah mengatur nilai Tingkat Akses menjadi keren.

### Contoh 5: Mengaktifkan enkripsi pada Layanan Blob dengan Keyvault
```
PS C:\>Set-AzureRmStorageAccount -ResourceGroupName "MyResourceGroup" -AccountName "MyStorageAccount" -AssignIdentity
PS C:\>$account = Get-AzureRmStorageAccount -ResourceGroupName "MyResourceGroup" -AccountName "MyStorageAccount"

PS C:\>$keyVault = New-AzureRmKeyVault -VaultName "MyKeyVault" -ResourceGroupName "MyResourceGroup" -Location "EastUS2"
PS C:\>$key = Add-AzureKeyVaultKey -VaultName "MyKeyVault" -Name "MyKey" -Destination 'Software'
PS C:\>Set-AzureRmKeyVaultAccessPolicy -VaultName "MyKeyVault" -ObjectId $account.Identity.PrincipalId -PermissionsToKeys wrapkey,unwrapkey

PS C:\>Set-AzureRmStorageAccount -ResourceGroupName "MyResourceGroup" -AccountName "MyStorageAccount" -EnableEncryptionService "Blob" -KeyvaultEncryption -KeyName $key.Name -KeyVersion $key.Version -KeyVaultUri $keyVault.VaultUri
```

Perintah ini memungkinkan Storage Enkripsi Layanan di Blob dengan Keyvault yang dibuat baru.

### Contoh 6: Nonaktifkan enkripsi pada Layanan File dengan KeySource diatur ke "Microsoft. Storage"
```
PS C:\>Set-AzureRmStorageAccount -ResourceGroupName "MyResourceGroup" -AccountName "MyStorageAccount" -DisableEncryptionService File  -StorageEncryption
```

Perintah ini menonaktifkan enkripsi pada Layanan File dengan KeySource yang diatur ke "Microsoft. Storage"

## PARAMETERS

### -AccessTier
Menentukan tingkatan akses dari akun Storage yang ditentukan cmdlet ini.
Nilai yang dapat diterima untuk parameter ini adalah: Hot dan Cool.

Jika Anda mengubah tingkat akses, hal itu mungkin akan mengakibatkan biaya tambahan.
Untuk informasi selengkapnya, lihat Azure Blob Storage: Hot dan cool storage tiers https://go.microsoft.com/fwlink/?LinkId=786482 ( https://go.microsoft.com/fwlink/?LinkId=786482) .
Jika jenis akun Storage tidak Storage, jangan tentukan parameter ini.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AssignIdentity
Buat dan tetapkan Identitas Akun Storage baru untuk akun penyimpanan ini untuk digunakan dengan layanan manajemen kunci seperti Azure KeyVault.

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

### -CustomDomainName
Menentukan nama domain kustom.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisableEncryptionService
Menunjukkan apakah cmdlet ini menonaktifkan Storage Enkripsi layanan pada Storage Layanan.
Layanan File Azure Blob dan Azure didukung.

```yaml
Type: System.Nullable`1[Microsoft.Azure.Commands.Management.Storage.StorageAccountBaseCmdlet+EncryptionSupportServiceEnum]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 7
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableEncryptionService
Menunjukkan apakah cmdlet ini mengaktifkan Storage Enkripsi layanan pada Storage Layanan.
Layanan File Azure Blob dan Azure didukung.

```yaml
Type: System.Nullable`1[Microsoft.Azure.Commands.Management.Storage.StorageAccountBaseCmdlet+EncryptionSupportServiceEnum]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 6
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableHttpsTrafficOnly
Menunjukkan apakah pengaturan Akun Storage mengaktifkan lalu lintas https saja.

```yaml
Type: System.Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Force
Jika Anda mengubah tingkat akses, hal itu mungkin akan mengakibatkan biaya tambahan.
Untuk informasi selengkapnya, lihat Azure Blob Storage: Hot dan cool storage tiers https://go.microsoft.com/fwlink/?LinkId=786482 ( https://go.microsoft.com/fwlink/?LinkId=786482) .
Jika jenis akun Storage tidak Storage, jangan tentukan parameter ini.

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

### -InformationAction
Menentukan bagaimana cmdlet merespons kejadian informasi.

Nilai yang dapat diterima untuk parameter ini adalah:

- Lanjutkan
- Abaikan
- Pemeriksaan
- SilentlyContinue
- Stop
- Tangguhkan

```yaml
Type: System.Management.Automation.ActionPreference
Parameter Sets: (All)
Aliases: infa

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InformationVariable
Menentukan variabel informasi.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: iv

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -KeyName
Storage Kunci enkripsi AkunSource KeyVault KeyName

```yaml
Type: System.String
Parameter Sets: KeyvaultEncryption
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -KeyvaultEncryption
Apakah akan mengatur Storage Enkripsi AkunSource ke Microsoft.Keyvault atau tidak. Jika Anda menentukan KeyName, KeyVersion dan KeyvaultUri, kunci enkripsi akun Storage Juga akan diatur ke Microsoft.Keyvault cuaca parameter ini diatur atau tidak.
```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: KeyvaultEncryption
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -KeyVaultUri
Storage Kunci enkripsi AkunSource KeyVaultVaultUri

```yaml
Type: System.String
Parameter Sets: KeyvaultEncryption
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -KeyVersion
Storage kunci enkripsi AkunSource KeyVault KeyVersion

```yaml
Type: System.String
Parameter Sets: KeyvaultEncryption
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Menentukan nama akun Storage Diubah.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: StorageAccountName, AccountName

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NetworkRuleSet
Storage Akun JaringanRuleSet

```yaml
Type: Microsoft.Azure.Commands.Management.Storage.Models.PSNetworkRuleSet
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Menentukan nama grup sumber daya untuk mengubah Storage tersebut.

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

### -SkuName
Menentukan nama SKU akun penyimpanan.
Nilai yang dapat diterima untuk parameter ini adalah:

- Standard_LRS.
Penyimpanan lokal yang berlebihan. 
- Standard_ZRS.
Penyimpanan tidak berlebihan zona.
- Standard_GRS.
Penyimpanan geo berlebihan. 
- Standard_RAGRS.
Baca mengakses penyimpanan geo berlebihan. 
- Premium_LRS.
Premium yang berlebihan secara lokal.

Anda tidak bisa Standard_ZRS tipe Premium_LRS ke tipe akun lain.
Anda tidak bisa mengubah tipe akun lain Standard_ZRS atau Premium_LRS.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: StorageAccountType, AccountType, Type

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StorageEncryption
Apakah akan mengatur Storage Kunci Enkripsi Akun ke Microsoft.Storage atau tidak.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: StorageEncryption
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Tag
Jika Anda menentukan nilai BlobStorage untuk parameter *Kind* dari cmdlet New-AzureRmStorageAccount, Anda harus menentukan nilai untuk parameter *AccessTier.*

Jika Anda menentukan nilai yang Storage untuk parameter *Kind* ini, jangan tentukan parameter *AccessTier.*

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases: Tags

Required: False
Position: 8
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -UseSubDomain
Menunjukkan apakah akan mengaktifkan validasi CName tidak langsung.

```yaml
Type: System.Nullable`1[System.Boolean]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 5
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
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan.
Cmdlet tidak berjalan.

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

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

## OUTPUTS

## CATATAN

## RELATED LINKS

[Get-AzureRmStorageAccount](./Get-AzureRmStorageAccount.md)

[New-AzureRmStorageAccount](./New-AzureRmStorageAccount.md)

[Remove-AzureRmStorageAccount](./Remove-AzureRmStorageAccount.md)


