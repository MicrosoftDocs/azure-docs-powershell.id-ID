---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Automation.dll-Help.xml
Module Name: Az.Automation
ms.assetid: 2D5B16F0-0662-4D9F-A13F-808CE5EEBBA3
online version: https://docs.microsoft.com/powershell/module/az.automation/new-azautomationaccount
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Automation/Automation/help/New-AzAutomationAccount.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Automation/Automation/help/New-AzAutomationAccount.md
ms.openlocfilehash: 12b551c9ab1c39e9179f29c2b170c3721e5d3a55
ms.sourcegitcommit: 82b4008b76d035e4aee733727371765b0d853bed
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145683832"
---
# New-AzAutomationAccount

## SYNOPSIS
Membuat akun Automation.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.automation/new-azautomationaccount) untuk informasi terbaru.

## SYNTAX

```
New-AzAutomationAccount [-ResourceGroupName] <String> [-Name] <String> [-Location] <String> [-Plan <String>]
 [-Tags <IDictionary>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzAutomationAccount** membuat akun Azure Automation dalam grup sumber daya.
Akun Automation adalah kontainer untuk sumber daya Automation yang terisolasi dari sumber daya akun Automation lainnya. Sumber daya Automation mencakup runbook, konfigurasi Desired State Configuration (DSC), pekerjaan, dan aset.

## EXAMPLES

### Contoh 1: Membuat akun otomatisasi
```powershell
PS C:\> New-AzAutomationAccount -Name "ContosoAutomationAccount" -Location "East US" -ResourceGroupName "ResourceGroup01"
```

Perintah ini membuat akun otomatisasi baru bernama ContosoAutomationAccount di wilayah US Timur.

### Contoh 2

Membuat akun Automation. (dibuat otomatis)

<!-- Aladdin Generated Example -->
```powershell
New-AzAutomationAccount -Location 'East US' -Name 'ContosoAutomationAccount' -ResourceGroupName 'ResourceGroup01' -Tags <IDictionary>
```

## PARAMETERS

### -AssignSystemIdentity
Buat dan tetapkan Identitas Sistem baru untuk Akun Automation ini untuk digunakan dengan layanan lain seperti Azure KeyVault.

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
Menentukan daftar identitas yang ditetapkan pengguna yang terkait dengan akun otomatisasi. Referensi identitas yang ditetapkan pengguna akan menjadi id sumber daya ARM dalam formulir: '/subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.ManagedIdentity/identities/{identityName}'

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
Apakah akan mengatur Automation Account Encryption KeySource ke Microsoft.AutomationServices atau tidak.

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
Apakah akan menonaktifkan lalu lintas pada titik akhir non-ARM (Webhook/Agent) dari internet publik dan hanya mengizinkan akses melalui jaringan privat.

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
Enkripsi Akun Automation KeyVault KeyName

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
Apakah akan mengatur kunci enkripsi Akun AutomationSource ke Microsoft.KeyVault atau tidak. Jika Anda menentukan KeyName, KeyVersion, dan KeyVaultUri, Automation Account Encryption KeySource juga akan diatur ke Microsoft.KeyVault apakah parameter ini diatur atau tidak.

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
Enkripsi Akun Automation KeyVault KeyVaultUri

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
Enkripsi Akun Automation KeyVault KeyVersion

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
Menentukan lokasi di mana cmdlet ini membuat akun Automation.
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

### -Name
Menentukan nama untuk akun Automation.

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
Menentukan paket untuk akun Automation.
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
Menentukan nama grup sumber daya tempat cmdlet ini menambahkan akun Automation.

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
Identitas yang Ditetapkan Pengguna yang terkait dengan akun yang akan digunakan untuk enkripsi. Referensi identitas yang ditetapkan pengguna akan menjadi id sumber daya ARM dalam formulir: '/subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.ManagedIdentity/identities/{identityName}'

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
Pasangan kunci-nilai dalam bentuk tabel hash. Misalnya: @{key0="value0";key1=$null;key2="value2"}

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### System.Collections.IDictionary

## OUTPUTS

### Microsoft.Azure.Commands.Automation.Model.AutomationAccount

## NOTES

## RELATED LINKS

[Get-AzAutomationAccount](./Get-AzAutomationAccount.md)

[Remove-AzAutomationAccount](./Remove-AzAutomationAccount.md)

[Set-AzAutomationAccount](./Set-AzAutomationAccount.md)
