---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Storage.Management.dll-Help.xml
Module Name: Az.Storage
online version: https://docs.microsoft.com/powershell/module/az.storage/set-azstorageblobinventorypolicy
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Storage/Storage.Management/help/Set-AzStorageBlobInventoryPolicy.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Storage/Storage.Management/help/Set-AzStorageBlobInventoryPolicy.md
ms.openlocfilehash: 328aa75593382c57bb3694cee20d27fa0e4c5dd6
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142500339"
---
# Set-AzStorageBlobInventoryPolicy

## SYNOPSIS
Membuat atau memperbarui kebijakan persediaan blob dalam akun Storage.

## SYNTAX

### AccountNamePolicyRule (Default)
```
Set-AzStorageBlobInventoryPolicy [-ResourceGroupName] <String> [-StorageAccountName] <String>
 -Rule <PSBlobInventoryPolicyRule[]> [-Disabled] [-DefaultProfile <IAzureContextContainer>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### AccountNamePolicyObject
```
Set-AzStorageBlobInventoryPolicy [-ResourceGroupName] <String> [-StorageAccountName] <String>
 -Policy <PSBlobInventoryPolicy> [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### AccountObjectPolicyRule
```
Set-AzStorageBlobInventoryPolicy -StorageAccount <PSStorageAccount> -Rule <PSBlobInventoryPolicyRule[]>
 [-Disabled] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### AccountObjectPolicyObject
```
Set-AzStorageBlobInventoryPolicy -StorageAccount <PSStorageAccount> -Policy <PSBlobInventoryPolicy>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### AccountResourceIdPolicyRule
```
Set-AzStorageBlobInventoryPolicy [-StorageAccountResourceId] <String> -Rule <PSBlobInventoryPolicyRule[]>
 [-Disabled] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### AccountResourceIdPolicyObject
```
Set-AzStorageBlobInventoryPolicy [-StorageAccountResourceId] <String> -Policy <PSBlobInventoryPolicy>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzStorageBlobInventoryPolicy** membuat atau memperbarui kebijakan inventori blob dalam akun Storage.

## EXAMPLES

### Contoh 1: Membuat atau memperbarui kebijakan inventaris blob dengan objek aturan BlobInventoryPolicy.
```
PS C:\> $rule1 = New-AzStorageBlobInventoryPolicyRule -Name Test1 -Destination $containerName -Disabled -Format Csv -Schedule Daily -ContainerSchemaField Name,Metadata,PublicAccess,Last-mOdified,LeaseStatus,LeaseState,LeaseDuration,HasImmutabilityPolicy,HasLegalHold -PrefixMatch con1,con2

PS C:\> $rule2 = New-AzStorageBlobInventoryPolicyRule -Name Test2 -Destination $containerName -Format Parquet -Schedule Weekly -IncludeBlobVersion -IncludeSnapshot -BlobType blockBlob,appendBlob -PrefixMatch aaa,bbb `
                -BlobSchemaField name,Creation-Time,Last-Modified,Content-Length,Content-MD5,BlobType,AccessTier,AccessTierChangeTime,Expiry-Time,hdi_isfolder,Owner,Group,Permissions,Acl,Metadata

PS C:\> $policy = Set-AzStorageBlobInventoryPolicy -ResourceGroupName myresourcegroup" -AccountName "mystorageaccount" -Disabled -Rule $rule1,$rule2

PS C:\> $policy

StorageAccountName : mystorageaccount
ResourceGroupName  : myresourcegroup
Name               : DefaultInventoryPolicy
Id                 : /subscriptions/{subscription-Id}/resourceGroups/myresourcegroup/providers/Microsoft.Storage/storageAccounts/mystorageaccount/inventoryPolicies/default
Type               : Microsoft.Storage/storageAccounts/inventoryPolicies
LastModifiedTime   : 5/12/2021 8:53:38 AM
Enabled            : False
Rules              : {Test1, Test2}

PS C:\> $policy.Rules

Name  Enabled Destination   ObjectType Format  Schedule IncludeSnapshots IncludeBlobVersions BlobTypes               PrefixMatch  SchemaFields                                           
----  ------- -----------   ---------- ------  -------- ---------------- ------------------- ---------               -----------  ------------                                           
Test1 False   containername Container  Csv     Daily                                                                 {con1, con2} {Name, Metadata, PublicAccess, Last-Modified...}       
Test2 True    containername Blob       Parquet Weekly   True             True                {blockBlob, appendBlob} {aaa, bbb}   {Name, Creation-Time, Last-Modified, Content-Length...}
```

2 perintah pertama ini membuat 2 objek aturan BlobInventoryPolicy: aturan "Test1" untuk inventaris contaienr; aturan "Test2" untuk inventaris blob.
Perintah berikut ini mengatur kebijakan inventaris blob ke akun Storage dengan 2 objek aturan, lalu memperlihatkan properti kebijakan dan aturan yang diperbarui.

### Contoh 2: Membuat atau memperbarui kebijakan inventori blob akun Storage dengan kebijakan format Json.
```
PS C:\> $policy = Set-AzStorageBlobInventoryPolicy -ResourceGroupName $resourceGroupName  -StorageAccountName $accountName -Policy (@{
                Enabled=$true;
                Rules=(@{
                    Enabled=$true;
                    Name="Test1";
                    Destination=$containerName;
                    Definition=(@{
                        ObjectType="Blob";
                        Format="Csv";
                        Schedule="Weekly";
                        SchemaFields=@("name","Content-Length","BlobType","Snapshot","VersionId","IsCurrentVersion");
                        Filters=(@{
                            BlobTypes=@("blockBlob","appendBlob");
                            PrefixMatch=@("prefix1","prefix2");
                            IncludeSnapshots=$true;
                            IncludeBlobVersions=$true;
                        })
                    })
                },
                @{
                    Enabled=$false;
                    Name="Test2";
                    Destination=$containerName;
                    Definition=(@{
                        ObjectType="Container";
                        Format="Parquet";
                        Schedule="Daily";
                        SchemaFields=@("name","Metadata","PublicAccess");
                        Filters=(@{
                            PrefixMatch=@("conpre1","conpre2");
                        })
                    })
                })
            })


PS C:\> $policy

StorageAccountName : weiadlscanary1
ResourceGroupName  : weitry
Name               : DefaultInventoryPolicy
Id                 : /subscriptions/{subscription-Id}/resourceGroups/weitry/providers/Microsoft.Storage/storageAccounts/weiadlscanary1/inventoryPolicies/default
Type               : Microsoft.Storage/storageAccounts/inventoryPolicies
LastModifiedTime   : 5/12/2021 9:02:21 AM
Enabled            : True
Rules              : {Test1, Test2}

PS C:\> $policy.Rules 

Name  Enabled Destination   ObjectType Format  Schedule IncludeSnapshots IncludeBlobVersions BlobTypes               PrefixMatch        SchemaFields                                 
----  ------- -----------   ---------- ------  -------- ---------------- ------------------- ---------               -----------        ------------                                 
Test1 True    containername Blob       Csv     Weekly   True             True                {blockBlob, appendBlob} {prefix1, prefix2} {name, Content-Length, BlobType, Snapshot...}
Test2 False   containername Container  Parquet Daily                                                                 {conpre1, conpre2} {name, Metadata, PublicAccess}                                                                                       {name, Metadata, PublicAccess}
```

Perintah ini membuat atau memperbarui kebijakan persediaan blob akun Storage dengan kebijakan format json.

### Contoh 3: Dapatkan kebijakan inventori blob dari akun Storage, lalu atur ke akun Storage lain.
```
PS C:\>$policy = Get-AzStorageBlobInventoryPolicy -ResourceGroupName "myresourcegroup" -AccountName "mystorageaccount" | Set-AzStorageBlobInventoryPolicy -ResourceGroupName "myresourcegroup2" -AccountName "mystorageaccount2"
```

Perintah ini terlebih dahulu mendapatkan kebijakan persediaan blob dari akun Storage, lalu mengaturnya ke akun Storage lain.
Proeprties: Destination, Enabled, and Rules of the policy akan diatur ke akun tujuan.

### Contoh 4: Dapatkan aturan kebijakan inventori blob dari akun Storage, lalu atur ke akun Storage lain.
```
PS C:\>$policy = ,((Get-AzStorageBlobInventoryPolicy -ResourceGroupName "myresourcegroup" -AccountName "mystorageaccount").Rules) | Set-AzStorageBlobInventoryPolicy -ResourceGroupName "myresourcegroup2" -AccountName "mystorageaccount2" -Disabled
```

Perintah ini terlebih dahulu mendapatkan kebijakan inventori blob dari akun Storage, lalu menetapkan aturan ke akun Storage lain.

## PARAMETERS

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

### -Nonaktif
Kebijakan Inventori Blob diaktifkan secara default, tentukan parameter ini untuk menonaktifkannya.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: AccountNamePolicyRule, AccountObjectPolicyRule, AccountResourceIdPolicyRule
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Kebijakan
Objek Kebijakan Persediaan Blob untuk Diatur

```yaml
Type: Microsoft.Azure.Commands.Management.Storage.Models.PSBlobInventoryPolicy
Parameter Sets: AccountNamePolicyObject, AccountObjectPolicyObject, AccountResourceIdPolicyObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -ResourceGroupName
Nama Grup Sumber Daya.

```yaml
Type: System.String
Parameter Sets: AccountNamePolicyRule, AccountNamePolicyObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Aturan
Aturan Kebijakan Inventori Blob.
Dapatkan objek dengan cmdlet New-AzStorageBlobInventoryPolicyRule.

```yaml
Type: Microsoft.Azure.Commands.Management.Storage.Models.PSBlobInventoryPolicyRule[]
Parameter Sets: AccountNamePolicyRule, AccountObjectPolicyRule, AccountResourceIdPolicyRule
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -StorageAccount
objek akun Storage

```yaml
Type: Microsoft.Azure.Commands.Management.Storage.Models.PSStorageAccount
Parameter Sets: AccountObjectPolicyRule, AccountObjectPolicyObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -StorageAccountName
Storage Nama Akun.

```yaml
Type: System.String
Parameter Sets: AccountNamePolicyRule, AccountNamePolicyObject
Aliases: AccountName

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageAccountResourceId
id sumber daya akun Storage.

```yaml
Type: System.String
Parameter Sets: AccountResourceIdPolicyRule, AccountResourceIdPolicyObject
Aliases:

Required: True
Position: 0
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
Default value: None
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
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Management. Storage. Models.PSStorageAccount

### System.String

### Microsoft.Azure.Commands.Management. Storage. Models.PSBlobInventoryPolicyRule[]

### Microsoft.Azure.Commands.Management. Storage. Models.PSBlobInventoryPolicySchema

## OUTPUTS

### Microsoft.Azure.Commands.Management. Storage. Models.PSManagementPolicy

## CATATAN

## RELATED LINKS
