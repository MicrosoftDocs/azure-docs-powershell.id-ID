---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Sql.dll-Help.xml
Module Name: Az.Sql
online version: https://docs.microsoft.com/powershell/module/az.sql/set-azsqlservertransparentdataencryptionprotector
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Sql/Sql/help/Set-AzSqlServerTransparentDataEncryptionProtector.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Sql/Sql/help/Set-AzSqlServerTransparentDataEncryptionProtector.md
ms.openlocfilehash: b3bb4537bc8c25d2a84fd599a2983b0d86188002
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145512343"
---
# Set-AzSqlServerTransparentDataEncryptionProtector

## SYNOPSIS
Mengatur pelindung Enkripsi Data Transparan (TDE) untuk server SQL.

## SYNTAX

```
Set-AzSqlServerTransparentDataEncryptionProtector [-Type] <EncryptionProtectorType> [[-KeyId] <String>]
 [-AutoRotationEnabled <Boolean>] [-Force] [-AsJob] [-ServerName] <String> [-ResourceGroupName] <String>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet Set-AzSqlServerTransparentDataEncryptionProtector mengatur pelindung TDE untuk server SQL.
Mengubah jenis pelindung TDE akan memutar pelindung.

## EXAMPLES

### Contoh 1: Atur jenis pelindung Enkripsi Data Transparan (TDE) ke ServiceManaged
```powershell
Set-AzSqlServerTransparentDataEncryptionProtector -Type ServiceManaged -ServerName 'ContosoServer' -ResourceGroupName 'ContosoResourceGroup'
```

```output
ResourceGroupName    ServerName                   Type ServerKeyVaultKeyName
-----------------    ----------                   ---- ---------------------
ContosoResourceGroup ContosoServer      ServiceManaged ServiceManaged
```

Perintah ini memperbarui jenis pelindung TDE server ke Dikelola Layanan.

### Contoh 2: Atur jenis pelindung Enkripsi Data Transparan ke Azure Key Vault
```powershell
Set-AzSqlServerTransparentDataEncryptionProtector -Type AzureKeyVault -KeyId 'https://contoso.vault.azure.net/keys/contosokey/01234567890123456789012345678901' -ServerName 'ContosoServer' -ResourceGroupName 'ContosoResourceGroup'
```

```output
ResourceGroupName    ServerName                   Type ServerKeyVaultKeyName
-----------------    ----------                   ---- ---------------------
ContosoResourceGroup ContosoServer       AzureKeyVault contoso_contosokey_01234567890123456789012345678901
```

Perintah ini memperbarui server untuk menggunakan Kunci Key Vault Server dengan Id 'https://contoso.vault.azure.net/keys/contosokey/01234567890123456789012345678901' sebagai pelindung TDE.

### Contoh: 3

Mengatur pelindung Enkripsi Data Transparan (TDE) untuk server SQL. (dibuat otomatis)

<!-- Aladdin Generated Example -->

```powershell
Set-AzSqlServerTransparentDataEncryptionProtector -AutoRotationEnabled $false -KeyId 'https://contoso.vault.azure.net/keys/contosokey/0000000000000000000000000000000000000' -ResourceGroupName 'ContosoResourceGroup' -ServerName 'ContosoServer' -Type AzureKeyVault
```

## PARAMETERS

### -AsJob
Jalankan cmdlet di latar belakang

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

### -AutoRotationEnabled
Status keikutsertaan rotasi otomatis kunci.

```yaml
Type: System.Nullable`1[System.Boolean]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### -Force
Lewati pesan konfirmasi untuk melakukan tindakan

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

### -KeyId
Azure Key Vault KeyId.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya

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

### -ServerName
Nama Azure Sql Server.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Type
Jenis pelindung TDE Azure Sql Database.

```yaml
Type: Microsoft.Azure.Commands.Sql.TransparentDataEncryption.Model.EncryptionProtectorType
Parameter Sets: (All)
Aliases:
Accepted values: AzureKeyVault, ServiceManaged

Required: True
Position: 2
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

### Microsoft.Azure.Commands.Sql.TransparentDataEncryption.Model.EncryptionProtectorType

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Sql.TransparentDataEncryption.Model.AzureSqlServerTransparentDataEncryptionProtectorModel

## NOTES

## RELATED LINKS

[Dokumentasi SQL Database](https://docs.microsoft.com/azure/sql-database/)
