---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Automation.dll-Help.xml
Module Name: Az.Automation
ms.assetid: 2D5B16F0-0662-4D9F-A13F-808CE5EEBBA3
online version: https://docs.microsoft.com/powershell/module/az.automation/new-azautomationaccount
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Automation/Automation/help/New-AzAutomationAccount.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Automation/Automation/help/New-AzAutomationAccount.md
ms.openlocfilehash: 12b551c9ab1c39e9179f29c2b170c3721e5d3a55
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141807656"
---
# New-AzAutomationAccount

## SYNOPSIS
Membuat akun Otomatisasi.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.automation/new-azautomationaccount) untuk informasi terbaru.

## SYNTAX

```
New-AzAutomationAccount [-ResourceGroupName] <String> [-Name] <String> [-Location] <String> [-Plan <String>]
 [-Tags <IDictionary>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzAutomationAccount** membuat akun Azure Automation dalam grup sumber daya.
Akun Otomatisasi adalah wadah untuk sumber daya Otomatisasi yang diisolasi dari sumber daya akun Otomatisasi lainnya. Sumber daya otomatisasi mencakup runbook, konfigurasi, pekerjaan, dan aset Konfigurasi Negara Bagian yang Diinginkan (DSC).

## EXAMPLES

### Contoh 1: Membuat akun otomatisasi
```powershell
PS C:\> New-AzAutomationAccount -Name "ContosoAutomationAccount" -Location "East US" -ResourceGroupName "ResourceGroup01"
```

Perintah ini membuat akun otomatisasi baru bernama ContosoAutomationAccount di kawasan AS Timur.

### Contoh 2

Membuat akun Otomatisasi. (autogenerasi)

<!-- Aladdin Generated Example -->
```powershell
New-AzAutomationAccount -Location 'East US' -Name 'ContosoAutomationAccount' -ResourceGroupName 'ResourceGroup01' -Tags <IDictionary>
```

## PARAMETERS

### -AssignSystemIdentity
Buat dan tetapkan Identitas Sistem baru untuk Akun Otomatisasi ini untuk digunakan dengan layanan lain seperti Azure KeyVault.

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

### -AssignUserIdentity
Menentukan daftar identitas yang ditetapkan pengguna yang terkait dengan akun otomatisasi. Referensi identitas yang ditetapkan pengguna akan berupa id sumber daya ARM dalam formulir: '/subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.ManagedIdentity/identities/{identityName}'

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

### -AutomationServicesEncryption
Apakah mengatur Kunci Enkripsi Akun OtomatisasiSource ke Microsoft.AutomationServices atau tidak.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: AutomationServicesEncryption
Aliases:
Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```


### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure

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

### -DisablePublicNetworkAccess
Apakah akan menonaktifkan lalu lintas di titik akhir non-ARM (Webhook/Agen) dari internet publik dan mengizinkan akses hanya melalui jaringan pribadi.

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

### -KeyName
Enkripsi Akun Otomatisasi KeyVault KeyName

```yaml
Type: System.String
Parameter Sets: KeyVaultEncryption
Aliases:
Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -KeyVaultEncryption
Apakah mengatur kunci enkripsi Akun OtomatisasiSource ke Microsoft.KeyVault atau tidak. Jika Anda menentukan KeyName, KeyVersion dan KeyVaultUri, Automation Account Encryption KeySource juga akan diatur ke Microsoft.KeyVault apakah parameter ini diatur atau tidak.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: KeyVaultEncryption
Aliases:
Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -KeyVaultUri
Enkripsi Akun Otomatisasi KeyVault KeyVaultUri

```yaml
Type: System.String
Parameter Sets: KeyVaultEncryption
Aliases:
Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -KeyVersion
Enkripsi Akun Otomatisasi KeyVault KeyVersion

```yaml
Type: System.String
Parameter Sets: KeyVaultEncryption
Aliases:
Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Lokasi
Menentukan lokasi di mana cmdlet ini membuat akun Otomatisasi.
Untuk mendapatkan lokasi yang valid, gunakan cmdlet Get-AzLocation.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Nama
Menentukan nama untuk akun Otomatisasi.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: AutomationAccountName

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Rencana
Menentukan rencana untuk akun Otomatisasi.
Nilai yang valid adalah:
- Dasar
- Gratis

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Free, Basic

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Menentukan nama grup sumber daya tempat cmdlet ini menambahkan akun Otomatisasi.

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

### -UserIdentityEncryption
Identitas yang Ditetapkan Pengguna yang terkait dengan akun yang akan digunakan untuk enkripsi. Referensi identitas yang ditetapkan pengguna akan berupa ID sumber daya ARM dalam formulir: '/subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.ManagedIdentity/identities/{identityName}'

```yaml
Type: System.String
Parameter Sets: KeyVaultEncryption
Aliases:
Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Tags
Pasangan nilai kunci dalam bentuk tabel hash. Misalnya: @{key0="value0";key1=$null;key2="value2"}

```yaml
Type: System.Collections.IDictionary
Parameter Sets: (All)
Aliases: Tag

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### System.Collections.IDictionary

## OUTPUTS

### Microsoft.Azure.Commands.Automation.Model.AutomationAccount

## CATATAN

## RELATED LINKS

[Get-AzAutomationAccount](./Get-AzAutomationAccount.md)

[Remove-AzAutomationAccount](./Remove-AzAutomationAccount.md)

[Set-AzAutomationAccount](./Set-AzAutomationAccount.md)
