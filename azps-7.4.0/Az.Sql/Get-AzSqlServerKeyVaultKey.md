---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Sql.dll-Help.xml
Module Name: Az.Sql
online version: https://docs.microsoft.com/powershell/module/az.sql/get-azsqlserverkeyvaultkey
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Sql/Sql/help/Get-AzSqlServerKeyVaultKey.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Sql/Sql/help/Get-AzSqlServerKeyVaultKey.md
ms.openlocfilehash: 49facc6f62218e9e8067d7a045755a9079829ebc
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143307539"
---
# Get-AzSqlServerKeyVaultKey

## SYNOPSIS
Mendapatkan kunci Key Vault server SQL.

## SYNTAX

```
Get-AzSqlServerKeyVaultKey [[-KeyId] <String>] [-ServerName] <String> [-ResourceGroupName] <String>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet Get-AzSqlServerKeyVaultKey mendapatkan informasi tentang kunci Key Vault di server SQL.
Anda dapat melihat semua kunci di server atau melihat kunci tertentu dengan menyediakan KeyId.

## EXAMPLES

### Contoh 1: Dapatkan semua kunci Key Vault
```powershell
Get-AzSqlServerKeyVaultKey -ServerName 'ContosoServer' -ResourceGroupName 'ContosoResourceGroup'
```

```output
ResourceGroupName : ContosoResourceGroup
ServerName        : ContosoServer
ServerKeyName     : contoso_contosokey_01234567890123456789012345678901
Type              : AzureKeyVault
Uri               : https://contoso.vault.azure.net/keys/contosokey/01234567890123456789012345678901
Thumbprint        : 1122334455667788990011223344556677889900
CreationDate      : 1/1/2017 12:00:00 AM
ResourceGroupName : ContosoResourceGroup
ServerName        : ContosoServer
ServerKeyName     : contoso_contosokey2_01234567890123456789012345678901
Type              : AzureKeyVault
Uri               : https://contoso.vault.azure.net/keys/contosokey2/09876543210987654321098765432109
Thumbprint        : 0099887766554433221100998877665544332211
CreationDate      : 1/1/2017 12:00:00 AM
```
Perintah ini mendapatkan semua kunci Key Vault di server SQL.
### Contoh 2: Dapatkan kunci Key Vault tertentu
```powershell
$MyServerKeyVaultKey = Get-AzSqlServerKeyVaultKey -KeyId 'https://contoso.vault.azure.net/keys/contosokey/01234567890123456789012345678901' -ServerName 'ContosoServer' -ResourceGroupName 'ContosoResourceGroup'
```

Perintah ini mendapatkan kunci Key Vault dengan Id 'https://contoso.vault.azure.net/keys/contosokey/01234567890123456789012345678901', lalu menyimpannya dalam variabel $MyServerKeyVaultKey.
Anda dapat memeriksa properti $MyServerKeyVaultKey untuk mendapatkan detail tentang kubah kunci.

## PARAMETERS

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

### -KeyId
Azure Key Vault KeyId.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
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

### -Konfirmasi
Meminta konfirmasi sebelum menjalankan cmdlet.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Sql.ServerKeyVaultKey.Model.AzureSqlServerKeyVaultKeyModel

## NOTES

## RELATED LINKS

[Dokumentasi SQL Database](https://docs.microsoft.com/azure/sql-database/)
