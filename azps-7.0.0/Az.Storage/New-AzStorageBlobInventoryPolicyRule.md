---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Storage.Management.dll-Help.xml
Module Name: Az.Storage
online version: https://docs.microsoft.com/powershell/module/az.storage/new-azstorageblobinventorypolicyrule
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Storage/Storage.Management/help/New-AzStorageBlobInventoryPolicyRule.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Storage/Storage.Management/help/New-AzStorageBlobInventoryPolicyRule.md
ms.openlocfilehash: a757b2cd93b551c63c7fe72efc8b4abe9e27e037
ms.sourcegitcommit: 579224f3f35e223624deb694bceb0033c84a5856
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 12/07/2021
ms.locfileid: "136543469"
---
# New-AzStorageBlobInventoryPolicyRule

## SYNOPSIS
Membuat objek aturan kebijakan inventaris blob, yang dapat digunakan di Set-AzStorageBlobInventoryPolicy.

## SYNTAX

### BlobRuleParameterSet (Default)
```
New-AzStorageBlobInventoryPolicyRule [-Name] <String> [-Disabled] -Destination <String> -Format <String>
 -Schedule <String> -BlobSchemaField <String[]> -BlobType <String[]> [-PrefixMatch <String[]>]
 [-IncludeSnapshot] [-IncludeBlobVersion] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ContainerRuleParameterSet
```
New-AzStorageBlobInventoryPolicyRule [-Name] <String> [-Disabled] -Destination <String> -Format <String>
 -Schedule <String> -ContainerSchemaField <String[]> [-PrefixMatch <String[]>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzStorageBlobInventoryPolicyRule** membuat objek aturan kebijakan inventaris blob, yang dapat digunakan di Set-AzStorageBlobInventoryPolicy.

## EXAMPLES

### Contoh 1: Buat objek aturan kebijakan inventaris blob, lalu tetapkan kebijakan inventaris blob dengan objek aturan.
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
Perintah berikut mengatur kebijakan inventaris blob ke akun Storage dengan 2 objek aturan, lalu memperlihatkan kebijakan dan properti aturan yang diperbarui.

## PARAMETERS

### -BlobSchemaField
Menentukan bidang dan properti objek Blob yang akan disertakan dalam inventaris. Nilai yang valid meliputi: Nama, Pembuatan-Waktu, Terakhir Diubah, Panjang Konten, Content-MD5, BlobType, AccessTier, AccessTierChangeTime, Expiry-Time, hdi_isfolder, Owner, Group, Permissions, Acl, Metadata, LastAccessTime, AccessTierInferred, Tags. 'Name' adalah skemafield yang diperlukan. Nilai bidang skema 'Kedaluwarsa-Waktu, hdi_isfolder, Pemilik, Grup, Izin, Acl' hanya valid untuk akun yang diaktifkan HierarchicalNamespace.'Tag' hanya berlaku untuk akun non HierarchicalNamespace.
Jika menentukan '-IncludeSnapshot', akan menyertakan 'Snapshot' di inventaris.  Jika menentukan '-IncludeBlobVersion', akan menyertakan 'VersionId, 'IsCurrentVersion' di inventaris.

```yaml
Type: System.String[]
Parameter Sets: BlobRuleParameterSet
Aliases:
Accepted values: Name, Creation-Time, Last-Modified, Content-Length, Content-MD5, BlobType, AccessTier, AccessTierChangeTime, Expiry-Time, hdi_isfolder, Owner, Group, Permissions, Acl, Metadata, LastAccessTime, AccessTierInferred, Tags

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -BlobType
Mengatur tipe blob untuk aturan kebijakan inventaris blob.
Nilai yang valid menyertakan blockBlob, appendBlob, pageBlob.
AkunHNS tidak mendukung pageBlobs.

```yaml
Type: System.String[]
Parameter Sets: BlobRuleParameterSet
Aliases:
Accepted values: blockBlob, pageBlob, appendBlob

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ContainerSchemaField
Menentukan bidang dan properti objek wadah untuk disertakan dalam inventaris. Nilai yang valid meliputi: Name, Last-Modified, Metadata, LeaseStatus, LeaseState, LeaseDuration, PublicAccess, HasImmutabilityPolicy, HasLegalHold. 'Name' adalah skemafield yang diperlukan.

```yaml
Type: System.String[]
Parameter Sets: ContainerRuleParameterSet
Aliases:
Accepted values: Name, Last-Modified, Metadata, LeaseStatus, LeaseState, LeaseDuration, PublicAccess, HasImmutabilityPolicy, HasLegalHold

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

### -Tujuan
Nama wadah tempat file inventaris blob disimpan. Harus sudah dibuat sebelumnya.

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

### -Dinonaktifkan
Aturan dinonaktifkan jika diatur.

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

### -Format
Menentukan format untuk file inventaris. Kemungkinan nilai termasuk: 'Csv', 'Nilai kolom'

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Csv, Parquet

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IncludeBlobVersion
Aturan dinonaktifkan jika diatur.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: BlobRuleParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IncludeSnapshot
Aturan dinonaktifkan jika diatur.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: BlobRuleParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Nama aturan dapat berisi kombinasi karakter alfa numerik apa pun.
Nama aturan peka huruf besar-kecil.
Kebijakan harus unik di dalam kebijakan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PrefixMatch
Mengatur array string untuk prefiks blob agar sesuai..

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

### -Schedule
Bidang ini digunakan untuk menjadwalkan formasi inventaris. Kemungkinan nilai termasuk: 'Harian', 'Mingguan'

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Daily, Weekly

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( http://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### Tidak ada

## OUTPUTS

### Microsoft.Azure.Commands.Management. Storage. Models.PSBlobInventoryPolicyRule

## CATATAN

## RELATED LINKS
