---
external help file: Microsoft.Azure.PowerShell.Cmdlets.CosmosDB.dll-Help.xml
Module Name: Az.CosmosDB
online version: ''
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CosmosDB/CosmosDB/help/Update-AzCosmosDbClientEncryptionKey.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CosmosDB/CosmosDB/help/Update-AzCosmosDbClientEncryptionKey.md
ms.openlocfilehash: 8a4c12dce115f7ab6361d7453c6c2f67a99fdf5d
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145515370"
---
# Update-AzCosmosDbClientEncryptionKey

## SYNOPSIS
Memperbarui Kunci Enkripsi Klien CosmosDB. Melakukan operasi patch sisi klien dengan membaca Kunci Enkripsi Klien yang ada.

## SYNTAX

### ByNameParameterSet (Default)
```
Update-AzCosmosDbClientEncryptionKey -ResourceGroupName <String> -AccountName <String> -DatabaseName <String>
 -Name <String> -KeyWrapMetadata <PSSqlKeyWrapMetadata> [-KeyEncryptionKeyResolver <IKeyEncryptionKeyResolver>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByParentObjectParameterSet
```
Update-AzCosmosDbClientEncryptionKey -Name <String> -KeyWrapMetadata <PSSqlKeyWrapMetadata>
 [-KeyEncryptionKeyResolver <IKeyEncryptionKeyResolver>] -SqlDatabaseObject <PSSqlDatabaseGetResults>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByObjectParameterSet
```
Update-AzCosmosDbClientEncryptionKey -KeyWrapMetadata <PSSqlKeyWrapMetadata>
 [-KeyEncryptionKeyResolver <IKeyEncryptionKeyResolver>] -InputObject <PSSqlClientEncryptionKeyGetResults>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
**Update-AzCosmosDbClientEncryptionKey** memperbarui Kunci Enkripsi Klien CosmosDb. Melakukan operasi patch sisi klien dengan membaca Kunci Enkripsi Klien CosmosDB yang ada.

## EXAMPLES

### Contoh 1
```powershell
$updatedKeyWrapMetadataObject = [Microsoft.Azure.Commands.CosmosDB.Models.PSSqlKeyWrapMetadata]::new([Microsoft.Azure.Management.CosmosDB.Models.KeyWrapMetadata]::new("myKekV2","AZURE_KEY_VAULT", "https://contoso.vault.azure.net/keys/myKekV2/78deebed173b48e48f55abf87ed4cf71", "RSA-OAEP"))
Update-AzCosmosDbClientEncryptionKey -AccountName myAccountName -DatabaseName myDatabaseName -ResourceGroupName myRgName -Name myClientEncryptionKeyName -KeyWrapMetadata $updatedKeyWrapMetadataObject
```

```output
Name     : myContainerName
Id       : /subscriptions/mySubscriptionId/resourceGroups/myRgName/providers/Microsoft.DocumentDB/databaseAccounts/myAccountName/sqlDatabases/myDatabaseName/clientEncryptionKeys/myClientEncryptionKeyName
Resource : Microsoft.Azure.Commands.CosmosDB.Models.PSSqlClientEncryptionKeyGetPropertiesResource
```

Contoh ini menunjukkan bagaimana kunci diperbarui. Jika KeyEncryptionKeyResolver tidak diteruskan Azure Key Vault KeyResolver digunakan secara default.
Perintah pertama membuat objek KeyWrapMetadata dengan nama myKekV2 jenis AZURE_KEY_VAULT dengan nilai diatur ke id https://contoso.vault.azure.net/keys/myKekV2/78deebed173b48e48f55abf87ed4cf71 kunci dan jenis algoritma "RSA-OAEP" yang digunakan untuk mengenkripsi kunci.
Dalam perintah kedua, kunci dengan nama sebagaimana diatur dalam variabel myClientEncryptionKeyName diperbarui dengan KeyWrapMetadata diatur ke nilai yang dikembalikan oleh perintah pertama.

### Contoh 2
```powershell
$updatedKeyWrapMetadataObject = [Microsoft.Azure.Commands.CosmosDB.Models.PSSqlKeyWrapMetadata]::new([Microsoft.Azure.Management.CosmosDB.Models.KeyWrapMetadata]::new("myKekV2","AZURE_KEY_VAULT", "https://contoso.vault.azure.net/keys/myKekV2/78deebed173b48e48f55abf87ed4cf71", "RSA-OAEP"))
$azureKeyVaultKeyResolver = [Azure.Security.KeyVault.Keys.Cryptography.KeyResolver]::new([Azure.Identity.DefaultAzureCredential]::new())
Update-AzCosmosDbClientEncryptionKey -AccountName myAccountName -DatabaseName myDatabaseName -ResourceGroupName myRgName -Name myClientEncryptionKeyName -KeyWrapMetadata $updatedKeyWrapMetadataObject -KeyEncryptionKeyResolver $azureKeyVaultKeyResolver
```

```output
Name     : myContainerName
Id       : /subscriptions/mySubscriptionId/resourceGroups/myRgName/providers/Microsoft.DocumentDB/databaseAccounts/myAccountName/sqlDatabases/myDatabaseName/clientEncryptionKeys/myClientEncryptionKeyName
Resource : Microsoft.Azure.Commands.CosmosDB.Models.PSSqlClientEncryptionKeyGetPropertiesResource
```

Contoh ini menunjukkan bagaimana kunci diperbarui dan bagaimana KeyEncryptionKeyResolver dapat diteruskan sebagai parameter.
Perintah pertama membuat objek KeyWrapMetadata dengan nama myKekV2 jenis AZURE_KEY_VAULT dengan nilai diatur ke id https://contoso.vault.azure.net/keys/myKekV2/78deebed173b48e48f55abf87ed4cf71 kunci dan jenis algoritma "RSA-OAEP" yang digunakan untuk mengenkripsi kunci.
Perintah kedua membuat objek Azure Key Vault KeyResolver menggunakan kredensial Azure Default.
Dalam perintah ketiga kunci dengan nama sebagaimana diatur dalam variabel myClientEncryptionKeyName diperbarui dengan KeyWrapMetadata diatur ke nilai yang dikembalikan oleh perintah pertama dan nilai KeyEncryptionKeyResolver diatur ke objek KeyResolver yang diperoleh melalui perintah kedua.

### Contoh: 3
```powershell
$updatedKeyWrapMetadataObject = [Microsoft.Azure.Commands.CosmosDB.Models.PSSqlKeyWrapMetadata]::new([Microsoft.Azure.Management.CosmosDB.Models.KeyWrapMetadata]::new("myKekV2","AZURE_KEY_VAULT", "https://contoso.vault.azure.net/keys/myKekV2/78deebed173b48e48f55abf87ed4cf71", "RSA-OAEP"))
$keyToUpdate = Get-AzCosmosDbClientEncryptionKey -AccountName myAccountName -DatabaseName myDatabaseName -ResourceGroupName myRgName -ClientEncryptionKeyName myClientEncryptionKeyName
Update-AzCosmosDbClientEncryptionKey -InputObject $keyToUpdate -KeyWrapMetadata $updatedKeyWrapMetadataObject -KeyEncryptionKeyResolver $azureKeyVaultKeyResolver
```

```output
Name     : myContainerName
Id       : /subscriptions/mySubscriptionId/resourceGroups/myRgName/providers/Microsoft.DocumentDB/databaseAccounts/myAccountName/sqlDatabases/myDatabaseName/clientEncryptionKeys/myClientEncryptionKeyName
Resource : Microsoft.Azure.Commands.CosmosDB.Models.PSSqlClientEncryptionKeyGetPropertiesResource
```

Contoh ini menunjukkan bagaimana kunci diperbarui menggunakan InputObject yang diperoleh dengan membaca kunci yang harus diperbarui.
Perintah pertama membuat objek KeyWrapMetadata dengan nama myKekV2 jenis AZURE_KEY_VAULT dengan nilai diatur ke id https://contoso.vault.azure.net/keys/myKekV2/78deebed173b48e48f55abf87ed4cf71 kunci dan jenis algoritma "RSA-OAEP" yang digunakan untuk mengenkripsi kunci.
Pada perintah kedua membaca kunci yang akan diperbarui.
Perintah ketiga memperbarui kunci yang dibaca sebelumnya di perintah kedua. Objek yang dibaca dalam perintah kedua diteruskan sebagai InputObject bersama dengan KeyWrapMetadata yang diperbarui yang diperoleh pada perintah pertama.

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

### -InputObject
Objek Kunci Enkripsi Klien.

```yaml
Type: Microsoft.Azure.Commands.CosmosDB.Models.PSSqlClientEncryptionKeyGetResults
Parameter Sets: ByObjectParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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
Parameter Sets: ByNameParameterSet, ByParentObjectParameterSet
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

### System.Byte[]

### Microsoft.Azure.Commands.CosmosDB.Models.PSSqlKeyWrapMetadata

### Microsoft.Data.Encryption.Cryptography.EncryptionKeyStoreProvider

### Microsoft.Azure.Commands.CosmosDB.Models.PSSqlDatabaseGetResults

### Microsoft.Azure.Commands.CosmosDB.Models.PSSqlClientEncryptionKeyGetResults

## OUTPUTS

### Microsoft.Azure.Commands.CosmosDB.Models.PSSqlClientEncryptionKeyGetResults

### Microsoft.Azure.Commands.CosmosDB.Exceptions.ResourceNotFoundException

## NOTES

## RELATED LINKS

[Get-AzCosmosDbClientEncryptionKey](./Get-AzCosmosDbClientEncryptionKey.md)

[New-AzCosmosDbClientEncryptionKey](./New-AzCosmosDbClientEncryptionKey.md)
