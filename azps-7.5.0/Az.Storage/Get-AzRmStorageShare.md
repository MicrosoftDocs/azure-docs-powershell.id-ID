---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Storage.Management.dll-Help.xml
Module Name: Az.Storage
online version: https://docs.microsoft.com/powershell/module/az.storage/get-azrmstorageshare
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Storage/Storage.Management/help/Get-AzRmStorageShare.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Storage/Storage.Management/help/Get-AzRmStorageShare.md
ms.openlocfilehash: 6fc3560b270d689522a8b709ccb54d9f301eb11d
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144191780"
---
# Get-AzRmStorageShare

## SYNOPSIS
Mendapatkan atau mencantumkan Storage berbagi file.

## SYNTAX

### AccountNameSingle (Default)
```
Get-AzRmStorageShare [-ResourceGroupName] <String> [-StorageAccountName] <String> [-Name <String>]
 [-SnapshotTime <DateTime>] [-GetShareUsage] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### AccountName
```
Get-AzRmStorageShare [-ResourceGroupName] <String> [-StorageAccountName] <String> [-IncludeDeleted]
 [-IncludeSnapshot] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### AccountObjectSingle
```
Get-AzRmStorageShare -StorageAccount <PSStorageAccount> -Name <String> [-SnapshotTime <DateTime>]
 [-GetShareUsage] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### AccountObject
```
Get-AzRmStorageShare -StorageAccount <PSStorageAccount> [-IncludeDeleted] [-IncludeSnapshot]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ShareResourceId
```
Get-AzRmStorageShare [-ResourceId] <String> [-GetShareUsage] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzRmStorageShare** mendapatkan atau mencantumkan Storage berbagi file.

## EXAMPLES

### Contoh 1: Dapatkan berbagi file Storage dengan nama akun Storage dan nama berbagi
```
PS C:\>Get-AzRmStorageShare -ResourceGroupName "myresourcegroup" -StorageAccountName "mystorageaccount" -Name "myshare"

   ResourceGroupName: myresourcegroup, StorageAccountName: mystorageaccount

Name     QuotaGiB EnabledProtocols AccessTier Deleted Version ShareUsageBytes
----     -------- ---------------- ---------- ------- ------- ---------------
myshare  5120
```

Perintah ini mendapatkan berbagi file Storage dengan nama akun Storage dan nama berbagi.

### Contoh 2: Mencantumkan semua berbagi file Storage dari akun Storage
```
PS C:\>Get-AzRmStorageShare -ResourceGroupName "myresourcegroup" -StorageAccountName "mystorageaccount"

   ResourceGroupName: myresourcegroup, StorageAccountName: mystorageaccount

Name     QuotaGiB EnabledProtocols AccessTier           Deleted Version ShareUsageBytes
----     -------- ---------------- ----------           ------- ------- ---------------
share1   5120                     TransactionOptimized
share2   5120                     TransactionOptimized
```

Perintah ini mencantumkan semua berbagi file Storage dari akun Storage dengan nama akun Storage.

### Contoh 3: Dapatkan kontainer blob Storage dengan objek akun Storage dan nama kontainer.
```
Get-AzStorageAccount -ResourceGroupName "myresourcegroup" -StorageAccountName "mystorageaccount" | Get-AzRmStorageShare -Name "myshare"

   ResourceGroupName: myresourcegroup, StorageAccountName: mystorageaccount

Name     QuotaGiB EnabledProtocols AccessTier Deleted Version ShareUsageBytes
----     -------- ---------------- ---------- ------- ------- ---------------
myshare  5120
```

Perintah ini mendapatkan kontainer blob Storage dengan objek akun Storage dan nama kontainer.

### Contoh 4: Mendapatkan berbagi file Storage dengan penggunaan berbagi dalam byte
```
PS C:\>Get-AzRmStorageShare -ResourceGroupName "myresourcegroup" -StorageAccountName "mystorageaccount" -Name "myshare" -GetShareUsage

   ResourceGroupName: myresourcegroup, StorageAccountName: mystorageaccount

Name     QuotaGiB EnabledProtocols AccessTier Deleted Version ShareUsageBytes
----     -------- ---------------- ---------- ------- ------- ---------------
myshare  5120                                                2097152
```

Perintah ini mendapatkan berbagi file Storage dengan nama akun Storage dan nama berbagi, dan menyertakan penggunaan berbagi dalam byte.

### Contoh 5: Cantumkan semua Storage berbagi file dari akun Storage, sertakan berbagi yang dihapus, sertakan salinan bayangan berbagi
```
PS C:\> Get-AzRmStorageShare -ResourceGroupName "myresourcegroup" -StorageAccountName "mystorageaccount" -IncludeDeleted -IncludeSnapshot 

   ResourceGroupName: myresourcegroup, StorageAccountName: mystorageaccount

Name       QuotaGiB EnabledProtocols AccessTier           Deleted Version          ShareUsageBytes snapshotTime       
----       -------- ---------------- ----------           ------- -------          --------------- ------------       
testshare1 5120                     TransactionOptimized                                          2021-05-10T08:04:08Z
testshare1 5120                     TransactionOptimized                                                      
share1     100                      TransactionOptimized True    01D61FD1FC5498B6
```

Perintah ini mencantumkan semua berbagi file Storage menyertakan berbagi yang dihapus dan berbagi rekam jepret.

### Contoh 6: Mendapatkan satu salinan bayangan berbagi
```
PS C:\> Get-AzRmStorageShare -ResourceGroupName "myresourcegroup" -StorageAccountName "mystorageaccount" -Name "testshare1" -SnapshotTime "2021-05-10T08:04:08Z"

   ResourceGroupName: myresourcegroup, StorageAccountName: mystorageaccount

Name       QuotaGiB EnabledProtocols AccessTier           Deleted Version ShareUsageBytes snapshotTime       
----       -------- ---------------- ----------           ------- ------- --------------- ------------       
testshare1 5120                     TransactionOptimized                                 2021-05-10T08:04:08Z
```

Perintah ini mendapatkan satu rekam jepret berbagi file dengan nama berbagi dan waktu rekam jepret.

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

### -GetShareUsage
Tentukan parameter ini untuk mendapatkan Penggunaan Berbagi dalam Byte.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: AccountNameSingle, AccountObjectSingle, ShareResourceId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IncludeDeleted
Menyertakan berbagi yang dihapus, secara default berbagi daftar tidak akan menyertakan berbagi yang dihapus

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: AccountName, AccountObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IncludeSnapshot
Sertakan salinan bayangan berbagi, secara default berbagi daftar tidak akan menyertakan salinan bayangan berbagi.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: AccountName, AccountObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Nama Berbagi

```yaml
Type: System.String
Parameter Sets: AccountNameSingle
Aliases: N, ShareName

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: System.String
Parameter Sets: AccountObjectSingle
Aliases: N, ShareName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama Grup Sumber Daya.

```yaml
Type: System.String
Parameter Sets: AccountNameSingle, AccountName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceId
Masukkan Id Sumber Daya Berbagi File.

```yaml
Type: System.String
Parameter Sets: ShareResourceId
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SnapshotTime
BagiKan SnapshotTime

```yaml
Type: System.Nullable`1[System.DateTime]
Parameter Sets: AccountNameSingle, AccountObjectSingle
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageAccount
Storage objek akun

```yaml
Type: Microsoft.Azure.Commands.Management.Storage.Models.PSStorageAccount
Parameter Sets: AccountObjectSingle, AccountObject
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
Parameter Sets: AccountNameSingle, AccountName
Aliases: AccountName

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### System.String

### Microsoft.Azure.Commands.Management. Storage. Models.PSStorageAccount

## OUTPUTS

### Microsoft.Azure.Commands.Management. Storage. Models.PSShare

## NOTES

## RELATED LINKS
