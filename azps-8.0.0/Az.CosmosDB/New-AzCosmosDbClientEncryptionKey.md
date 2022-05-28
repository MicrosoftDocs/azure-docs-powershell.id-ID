---
external help file: Microsoft.Azure.PowerShell.Cmdlets.CosmosDB.dll-Help.xml
Module Name: Az.CosmosDB
online version: ''
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CosmosDB/CosmosDB/help/New-AzCosmosDbClientEncryptionKey.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CosmosDB/CosmosDB/help/New-AzCosmosDbClientEncryptionKey.md
ms.openlocfilehash: edb9e0d0a680b471168f6fcd62edb5b07440288a
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145518790"
---
# New-AzCosmosDbClientEncryptionKey

## SYNOPSIS
Membuat Kunci Enkripsi Klien CosmosDB baru.

## SYNTAX

### ByNameParameterSet (Default)
```
New-AzCosmosDbClientEncryptionKey -ResourceGroupName <String> -AccountName <String> -DatabaseName <String>
 -Name <String> -EncryptionAlgorithmName <String> -KeyWrapMetadata <PSSqlKeyWrapMetadata>
 [-KeyEncryptionKeyResolver <IKeyEncryptionKeyResolver>] [-DefaultProfile <IAzureContextContainer>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### ByParentObjectParameterSet
```
New-AzCosmosDbClientEncryptionKey -Name <String> -EncryptionAlgorithmName <String>
 -KeyWrapMetadata <PSSqlKeyWrapMetadata> [-KeyEncryptionKeyResolver <IKeyEncryptionKeyResolver>]
 -SqlDatabaseObject <PSSqlDatabaseGetResults> [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
**New-AzCosmosDbClientEncryptionKey** membuat Kunci Enkripsi Klien CosmosDB baru.

## EXAMPLES

### Contoh 1
```powershell
$myKeyWrapMetadataObject = [Microsoft.Azure.Commands.CosmosDB.Models.PSSqlKeyWrapMetadata]::new([Microsoft.Azure.Management.CosmosDB.Models.KeyWrapMetadata]::new("myKekV1","AZURE_KEY_VAULT", "https://contoso.vault.azure.net/keys/myKekV1/78deebed173b48e48f55abf87ed4cf71", "RSA-OAEP"))
New-AzCosmosDbClientEncryptionKey -AccountName myAccountName -DatabaseName myDatabaseName -ResourceGroupName myRgName -Name myClientEncryptionKeyName -EncryptionAlgorithmName "AEAD_AES_256_CBC_HMAC_SHA256" -KeyWrapMetadata $myKeyWrapMetadataObject
```

```output
Name     : myContainerName
Id       : /subscriptions/mySubscriptionId/resourceGroups/myRgName/providers/Microsoft.DocumentDB/databaseAccounts/myAccountName/sqlDatabases/myDatabaseName/clientEncryptionKeys/myClientEncryptionKeyName
Resource : Microsoft.Azure.Commands.CosmosDB.Models.PSSqlClientEncryptionKeyGetPropertiesResource
```

Contoh ini menunjukkan bagaimana kunci baru dibuat. Jika KeyEncryptionKeyResolver tidak diteruskan Azure Key Vault KeyResolver digunakan secara default.
Perintah pertama membuat objek KeyWrapMetadata dengan nama myKekV1 jenis AZURE_KEY_VAULT dengan nilai diatur ke id https://contoso.vault.azure.net/keys/myKekV1/78deebed173b48e48f55abf87ed4cf71 kunci dan jenis algoritma "RSA-OAEP" yang digunakan untuk mengenkripsi kunci.
Pada perintah kedua, kunci baru dibuat dengan nama sebagaimana diatur dalam variabel myClientEncryptionKeyName dan dengan KeyWrapMetadata diatur ke nilai yang dikembalikan oleh perintah pertama.

### Contoh 2
```powershell
$myKeyWrapMetadataObject = [Microsoft.Azure.Commands.CosmosDB.Models.PSSqlKeyWrapMetadata]::new([Microsoft.Azure.Management.CosmosDB.Models.KeyWrapMetadata]::new("myKekV1","AZURE_KEY_VAULT", "https://contoso.vault.azure.net/keys/myKekV1/78deebed173b48e48f55abf87ed4cf71", "RSA-OAEP"))
$azureKeyVaultKeyResolver = [Azure.Security.KeyVault.Keys.Cryptography.KeyResolver]::new([Azure.Identity.DefaultAzureCredential]::new())
New-AzCosmosDbClientEncryptionKey -AccountName myAccountName -DatabaseName myDatabaseName -ResourceGroupName myRgName -Name myClientEncryptionKeyName -EncryptionAlgorithmName "AEAD_AES_256_CBC_HMAC_SHA256" -KeyWrapMetadata $myKeyWrapMetadataObject -KeyEncryptionKeyResolver $azureKeyVaultKeyResolver
```

```output
Name     : myContainerName
Id       : /subscriptions/mySubscriptionId/resourceGroups/myRgName/providers/Microsoft.DocumentDB/databaseAccounts/myAccountName/sqlDatabases/myDatabaseName/clientEncryptionKeys/myClientEncryptionKeyName
Resource : Microsoft.Azure.Commands.CosmosDB.Models.PSSqlClientEncryptionKeyGetPropertiesResource
```

Contoh ini menunjukkan bagaimana kunci baru dibuat dan bagaimana KeyEncryptionKeyResolver dapat diteruskan sebagai parameter.
Perintah pertama membuat objek KeyWrapMetadata dengan nama myKekV1 jenis AZURE_KEY_VAULT dengan nilai diatur ke id https://contoso.vault.azure.net/keys/myKekV1/78deebed173b48e48f55abf87ed4cf71 kunci dan jenis algoritma "RSA-OAEP" yang digunakan untuk mengenkripsi kunci.
Perintah kedua membuat objek Azure Key Vault KeyResolver menggunakan kredensial Azure Default.
Dalam perintah ketiga, kunci baru dibuat dengan nama sebagaimana diatur dalam variabel myClientEncryptionKeyName, KeyWrapMetadata diatur ke nilai yang dikembalikan oleh perintah pertama dan nilai KeyEncryptionKeyResolver diatur ke objek KeyResolver yang diperoleh melalui perintah kedua.

## PARAMETERS

### -AccountName
Nama akun database Cosmos DB.

```yaml
Type: System.String
Parameter Sets: ByNameParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DatabaseName
Nama database.

```yaml
Type: System.String
Parameter Sets: ByNameParameterSet
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

### -EncryptionAlgorithmName
Nama Algoritma Enkripsi Klien.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -KeyEncryptionKeyResolver
Antarmuka IKeyEncryptionKeyResolver jenis Azure.Core.Cryptography.IKeyEncryptionKeyResolver

```yaml
Type: Azure.Core.Cryptography.IKeyEncryptionKeyResolver
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -KeyWrapMetadata
Objek KeyWrapMetaData jenis Microsoft.Azure.Commands.CosmosDB.PSSqlKeyWrapMetadata.

```yaml
Type: Microsoft.Azure.Commands.CosmosDB.Models.PSSqlKeyWrapMetadata
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Nama Kunci Enkripsi Klien.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: ClientEncryptionKeyName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya.

```yaml
Type: System.String
Parameter Sets: ByNameParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SqlDatabaseObject
Objek Sql Database.

```yaml
Type: Microsoft.Azure.Commands.CosmosDB.Models.PSSqlDatabaseGetResults
Parameter Sets: ByParentObjectParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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
Default value: None
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
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Microsoft.Azure.Commands.CosmosDB.Models.PSSqlKeyWrapMetadata

### System.Byte[]

### Microsoft.Data.Encryption.Cryptography.EncryptionKeyStoreProvider

### Microsoft.Azure.Commands.CosmosDB.Models.PSSqlDatabaseGetResults

## OUTPUTS

### Microsoft.Azure.Commands.CosmosDB.Models.PSSqlClientEncryptionKeyGetResults

### Microsoft.Azure.Commands.CosmosDB.Exceptions.ConflictingResourceException

## NOTES

## RELATED LINKS

[Get-AzCosmosDbClientEncryptionKey](./Get-AzCosmosDbClientEncryptionKey.md)

[Update-AzCosmosDbClientEncryptionKey](./Update-AzCosmosDbClientEncryptionKey.md)
