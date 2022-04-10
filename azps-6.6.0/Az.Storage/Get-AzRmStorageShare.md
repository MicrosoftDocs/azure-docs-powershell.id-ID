---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Storage.Management.dll-Help.xml
Module Name: Az.Storage
online version: https://docs.microsoft.com/powershell/module/az.storage/get-azrmstorageshare
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Storage/Storage.Management/help/Get-AzRmStorageShare.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Storage/Storage.Management/help/Get-AzRmStorageShare.md
ms.openlocfilehash: 04b2769339f428f8c565bdd9fbe2455fa5787905
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140500179"
---
# Get-AzRmStorageShare

## SYNOPSIS
Gets or lists Storage file shares.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan [lihat versi terbaru](/powershell/module/az.storage/get-azrmstorageshare) untuk informasi terkini.

## SYNTAX

### AccountNameSingle (Default)
```
Get-AzRmStorageShare [-ResourceGroupName] <String> [-StorageAccountName] <String> [-Name <String>]
 [-SnapshotTime <DateTime>] [-GetShareUsage] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### Nama Akun
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
Get-AzRmStorageShare [-ResourceId] <String> [-Name <String>] [-GetShareUsage]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzRmStorageShare** mendapatkan atau Storage file bersama.

## EXAMPLES

### Contoh 1: Dapatkan Storage berbagi file dengan Storage nama akun dan nama berbagi
```
PS C:\>Get-AzRmStorageShare -ResourceGroupName "myresourcegroup" -StorageAccountName "mystorageaccount" -Name "myshare"

   ResourceGroupName: myresourcegroup, StorageAccountName: mystorageaccount

Name     QuotaGiB EnabledProtocols AccessTier Deleted Version ShareUsageBytes
----     -------- ---------------- ---------- ------- ------- ---------------
myshare  5120
```

Perintah ini berisi informasi Storage file dengan Storage dan nama berbagi.

### Contoh 2: Daftar semua Storage berbagi file dari Storage tersebut
```
PS C:\>Get-AzRmStorageShare -ResourceGroupName "myresourcegroup" -StorageAccountName "mystorageaccount"

   ResourceGroupName: myresourcegroup, StorageAccountName: mystorageaccount

Name     QuotaGiB EnabledProtocols AccessTier           Deleted Version ShareUsageBytes
----     -------- ---------------- ----------           ------- ------- ---------------
share1   5120                     TransactionOptimized
share2   5120                     TransactionOptimized
```

Perintah ini mencantumkan semua Storage berbagi file dari Storage ini dengan Storage akun.

### Contoh 3: Get a Storage blob container with Storage account object and container name.
```
Get-AzStorageAccount -ResourceGroupName "myresourcegroup" -StorageAccountName "mystorageaccount" | Get-AzRmStorageShare -Name "myshare"

   ResourceGroupName: myresourcegroup, StorageAccountName: mystorageaccount

Name     QuotaGiB EnabledProtocols AccessTier Deleted Version ShareUsageBytes
----     -------- ---------------- ---------- ------- ------- ---------------
myshare  5120
```

Perintah ini akan mendapatkan Storage blob dengan Storage objek akun dan nama wadah.

### Contoh 4: Dapatkan Storage berbagi file dengan penggunaan berbagi dalam byte
```
PS C:\>Get-AzRmStorageShare -ResourceGroupName "myresourcegroup" -StorageAccountName "mystorageaccount" -Name "myshare" -GetShareUsage

   ResourceGroupName: myresourcegroup, StorageAccountName: mystorageaccount

Name     QuotaGiB EnabledProtocols AccessTier Deleted Version ShareUsageBytes
----     -------- ---------------- ---------- ------- ------- ---------------
myshare  5120                                                2097152
```

Perintah ini berisi Storage file yang dibagikan Storage nama akun dan nama berbagi, serta menyertakan penggunaan berbagi dalam byte.

### Contoh 5: Mencantumkan Storage berbagi file dari akun Storage, termasuk berbagi yang dihapus, termasuk snapshot berbagi
```
PS C:\> Get-AzRmStorageShare -ResourceGroupName "myresourcegroup" -StorageAccountName "mystorageaccount" -IncludeDeleted -IncludeSnapshot 

   ResourceGroupName: myresourcegroup, StorageAccountName: mystorageaccount

Name       QuotaGiB EnabledProtocols AccessTier           Deleted Version          ShareUsageBytes snapshotTime       
----       -------- ---------------- ----------           ------- -------          --------------- ------------       
testshare1 5120                     TransactionOptimized                                          2021-05-10T08:04:08Z
testshare1 5120                     TransactionOptimized                                                      
share1     100                      TransactionOptimized True    01D61FD1FC5498B6
```

Perintah ini mencantumkan semua Storage file bersama termasuk berbagi file yang dihapus dan berbagi jepretan layar.

### Contoh 6: Mendapatkan satu snapshot berbagi
```
PS C:\> Get-AzRmStorageShare -ResourceGroupName "myresourcegroup" -StorageAccountName "mystorageaccount" -Name "testshare1" -SnapshotTime "2021-05-10T08:04:08Z"

   ResourceGroupName: myresourcegroup, StorageAccountName: mystorageaccount

Name       QuotaGiB EnabledProtocols AccessTier           Deleted Version ShareUsageBytes snapshotTime       
----       -------- ---------------- ----------           ------- ------- --------------- ------------       
testshare1 5120                     TransactionOptimized                                 2021-05-10T08:04:08Z
```

Perintah ini mengambil satu file rekam jepret berbagi dengan nama dan waktu jepretan layar.

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
Tentukan parameter ini untuk mendapatkan Berbagi Penggunaan dalam Byte.

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
Sertakan jumlah yang dihapus, menurut berbagi daftar default tidak akan menyertakan berbagi yang dihapus

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
Sertakan bagikan snapshot, berbagi daftar secara default tidak akan menyertakan berbagi snapshot.

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

### -Nama
Bagikan Nama

```yaml
Type: System.String
Parameter Sets: AccountNameSingle, ShareResourceId
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
Memasukkan Id Sumber Daya Berbagi File.

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
Berbagi SnapshotTime

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
Storage Akun.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### Microsoft.Azure.Commands.Management. Storage. Models.PSStorageAccount

## OUTPUTS

### Microsoft.Azure.Commands.Management. Storage. Models.PSShare

## CATATAN

## RELATED LINKS
