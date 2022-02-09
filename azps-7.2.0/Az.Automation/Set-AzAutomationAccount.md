---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Automation.dll-Help.xml
Module Name: Az.Automation
ms.assetid: B1897EFC-0184-4A8B-B8E4-203CC8E3B179
online version: https://docs.microsoft.com/powershell/module/az.automation/set-azautomationaccount
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Automation/Automation/help/Set-AzAutomationAccount.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Automation/Automation/help/Set-AzAutomationAccount.md
ms.openlocfilehash: e29ac7bb7a2b01f4517c44f720eff08ffff26292
ms.sourcegitcommit: 7e47562b11e670049c3a18af7498414da853a921
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/09/2022
ms.locfileid: "138317355"
---
# Set-AzAutomationAccount

## SYNOPSIS
Memodifikasi akun Otomatisasi.

## SYNTAX

### AutomationServicesEncryption (Default)
```
Set-AzAutomationAccount [-ResourceGroupName] <String> [-Name] <String> [-Plan <String>] [-Tags <IDictionary>]
 [-AssignSystemIdentity] [-AssignUserIdentity <String[]>] [-AutomationServicesEncryption]
 [-DisablePublicNetworkAccess] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### KeyVaultEncryption
```
Set-AzAutomationAccount [-ResourceGroupName] <String> [-Name] <String> [-Plan <String>] [-Tags <IDictionary>]
 [-AssignSystemIdentity] [-AssignUserIdentity <String[]>] [-KeyVaultEncryption] -KeyName <String>
 -KeyVersion <String> -KeyVaultUri <String> [-UserIdentityEncryption <String>] [-DisablePublicNetworkAccess]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzAutomationAccount** mengubah akun Otomatisasi Azure.
Untuk informasi selengkapnya tentang akun Otomatisasi, lihat cmdlet New-AzAutomationAccount waktu.

## EXAMPLES

### Contoh 1: Mengatur tag untuk akun Otomatisasi
```
PS C:\>$Tags = @{"tag01"="value01";"tag02"="value02"}
PS C:\> Set-AzAutomationAccount -Name "AutomationAccount01" -ResourceGroupName "ResourceGroup01" -Tags $Tags
```

Perintah pertama menetapkan dua pasangan kunci/nilai ke $Tags nilai.
Perintah kedua mengatur tag dalam $Tags akun Otomatisasi bernama AutomationAccount01.

### Contoh 2: Mengubah rencana untuk akun Otomatisasi
```
PS C:\>Set-AzAutomationAccount -Name "AutomationAccount01" -ResourceGroupName "ResourceGroup01" -Plan Basic
```

Perintah ini mengubah rencana ke Dasar untuk akun Otomatisasi bernama AutomationAccount01.

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
Menentukan daftar identitas yang ditetapkan pengguna yang terkait dengan akun otomatisasi. Referensi identitas yang ditetapkan pengguna akan menjadi ID sumber daya ARM dalam formulir: '/subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.ManagedIdentity/identities/{identityName}'

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
Tentukan apakah atur Automation Account Encryption KeySource ke Microsoft.AutomationServices atau tidak.

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
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure

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
Apakah akan menonaktifkan lalu lintas di titik akhir non-ARM (Webhook/Agent) dari internet publik dan memperbolehkan akses hanya melalui jaringan privat.

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
Tentukan apakah atur kunci enkripsi Akun OtomatisasiSource ke Microsoft.KeyVault atau tidak. Jika Anda menentukan KeyName, KeyVersion dan KeyVaultUri, Automation Account Encryption KeySource juga akan diatur ke Microsoft.KeyVault apakah parameter ini diatur atau tidak.

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
Otomatisasi Akun enkripsi KeyVaultVaultUri

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

### -Nama
Menentukan nama akun Otomatisasi yang dimodifikasi cmdlet ini.

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
Nilai valid adalah:
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
Menentukan nama grup sumber daya yang berisi akun Otomatisasi yang dimodifikasi cmdlet ini.

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

### -Tag
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

### -UserIdentityEncryption
Identitas yang Ditetapkan Pengguna terkait dengan akun yang akan digunakan untuk enkripsi. Referensi identitas yang ditetapkan pengguna akan menjadi ID sumber daya ARM dalam formulir: '/subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.ManagedIdentity/identities/{identityName}'

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### System.Collections.IDictionary

## OUTPUTS

### Microsoft.Azure.Commands.Automation.Model.AutomationAccount

## CATATAN

## RELATED LINKS

[Get-AzAutomationAccount](./Get-AzAutomationAccount.md)

[New-AzAutomationAccount](./New-AzAutomationAccount.md)

[Remove-AzAutomationAccount](./Remove-AzAutomationAccount.md)
