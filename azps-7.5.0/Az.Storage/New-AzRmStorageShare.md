---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Storage.Management.dll-Help.xml
Module Name: Az.Storage
online version: https://docs.microsoft.com/powershell/module/az.storage/new-azrmstorageshare
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Storage/Storage.Management/help/New-AzRmStorageShare.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Storage/Storage.Management/help/New-AzRmStorageShare.md
ms.openlocfilehash: c47bcfff2e435258ca989f91e46a27111fffda68
ms.sourcegitcommit: 82b4008b76d035e4aee733727371765b0d853bed
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145716544"
---
# New-AzRmStorageShare

## SYNOPSIS
Membuat berbagi file Storage.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.storage/new-azrmstorageshare) untuk informasi terbaru.

## SYNTAX

### AccountName (Default)
```
New-AzRmStorageShare [-ResourceGroupName] <String> [-StorageAccountName] <String> -Name <String>
 [-QuotaGiB <Int32>] [-Metadata <Hashtable>] [-AccessTier <String>] [-Snapshot] [-EnabledProtocol <String>]
 [-RootSquash <String>] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### AccountObject
```
New-AzRmStorageShare -StorageAccount <PSStorageAccount> -Name <String> [-QuotaGiB <Int32>]
 [-Metadata <Hashtable>] [-AccessTier <String>] [-Snapshot] [-EnabledProtocol <String>] [-RootSquash <String>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzRmStorageShare** membuat berbagi file Storage.

## EXAMPLES

### Contoh 1: Buat berbagi file Storage dengan nama akun Storage dan nama berbagi, dengan metadata dan bagikan kuota sebagai 100 GiB.
```
PS C:\>New-AzRmStorageShare -ResourceGroupName "myresourcegroup" -StorageAccountName "mystorageaccount" -Name "myshare" -QuotaGiB 100 -Metadata @{"tag1" = "value1"; "tag2" = "value2" } 

   ResourceGroupName: myresourcegroup, StorageAccountName: mystorageaccount

Name     QuotaGiB EnabledProtocol AccessTier Deleted Version ShareUsageBytes
----     -------- --------------- ---------- ------- ------- ---------------
myshare
```

Perintah ini membuat berbagi file Storage dengan metadata dan berbagi kuota sebagai 100 GiB.

### Contoh 2: Membuat berbagi file Storage dengan objek akun Storage
```
Get-AzStorageAccount -ResourceGroupName "myresourcegroup" -StorageAccountName "mystorageaccount" | New-AzRmStorageShare -Name "myshare"

   ResourceGroupName: myresourcegroup, StorageAccountName: mystorageaccount

Name     QuotaGiB EnabledProtocol AccessTier Deleted Version ShareUsageBytes
----     -------- --------------- ---------- ------- ------- ---------------
myshare
```

Perintah ini membuat berbagi file Storage dengan objek akun Storage dan nama berbagi.

### Contoh 3: Membuat berbagi file Storage dengan accesstier sebagai Hot
```
PS C:\>$share = New-AzRmStorageShare -ResourceGroupName "myresourcegroup" -StorageAccountName "mystorageaccount" -Name "myshare" -AccessTier Hot

   ResourceGroupName: myresourcegroup, StorageAccountName: mystorageaccount

Name     QuotaGiB EnabledProtocols AccessTier Deleted Version ShareUsageBytes
----     -------- ---------------- ---------- ------- ------- ---------------
myshare                            Hot
```

Perintah ini membuat berbagi file Storage dengan accesstier sebagai Hot.

### Contoh 4: Membuat rekam jepret berbagi file Storage dari berbagi yang sudah ada
```
PS C:\>$shareSnapshot = New-AzRmStorageShare -ResourceGroupName "myresourcegroup" -StorageAccountName "mystorageaccount" -Name "myshare" -Snapshot

   ResourceGroupName: myresourcegroup, StorageAccountName: mystorageaccount

Name     QuotaGiB EnabledProtocols AccessTier Deleted Version ShareUsageBytes snapshotTime 
----     -------- ---------------- ---------- ------- ------- --------------- ------------   
myshare                                                                       2021-05-10T08:04:08
```

Perintah ini membuat salinan bayangan berbagi file Storage dari berbagi file dasar yang ada.

### Contoh 5: Membuat berbagi file Storage dengan proeprty EnabledProtocol sebagai properti NFS, dan RootSquash sebagai NoRootSquash
```
PS C:\>$share = New-AzRmStorageShare -ResourceGroupName "myresourcegroup" -StorageAccountName "mystorageaccount" -Name "myshare" -EnabledProtocol NFS -RootSquash NoRootSquash 

PS C:\> $share

   ResourceGroupName: myresourcegroup, StorageAccountName: mystorageaccount

Name     QuotaGiB EnabledProtocols AccessTier Deleted Version ShareUsageBytes
----     -------- ---------------- ---------- ------- ------- ---------------
myshare           NFS

PS C:\> $share.RootSquash
NoRootSquash
```

Perintah ini membuat berbagi file Storage dengan EnabledProtocol proeprty sebagai NFS, dan RootSquash proeprty sebagai NoRootSquash.

## PARAMETERS

### -AccessTier
Tingkat akses untuk berbagi tertentu. Akun StorageV2 dapat memilih antara TransactionOptimized (default), Hot, dan Cool. Akun FileStorage dapat memilih Premium.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: TransactionOptimized, Premium, Hot, Cool

Required: False
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

### -EnabledProtocol
Mengatur protokol untuk berbagi file. Ini tidak dapat diubah setelah pembuatan berbagi file. Nilai yang mungkin termasuk: 'SMB', 'NFS'

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: NFS, SMB

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Metadata
Bagi Metadata

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Nama berbagi File Azure

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: N, ShareName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -KuotaGiB
Bagi Kuota di Gibibyte.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: Quota

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama Grup Sumber Daya.

```yaml
Type: System.String
Parameter Sets: AccountName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RootSquash
Mengatur pengurangan hak akses untuk superuser jarak jauh. Nilai yang mungkin termasuk: 'NoRootSquash', 'RootSquash', 'AllSquash'

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: NoRootSquash, RootSquash, AllSquash

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Rekam jepret
Buat rekam jepret berbagi yang ada dengan nama yang sama.

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

### -StorageAccount
Storage objek akun

```yaml
Type: Microsoft.Azure.Commands.Management.Storage.Models.PSStorageAccount
Parameter Sets: AccountObject
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
Parameter Sets: AccountName
Aliases: AccountName

Required: True
Position: 1
Default value: None
Accept pipeline input: False
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

### System.String

### Microsoft.Azure.Commands.Management. Storage. Models.PSStorageAccount

## OUTPUTS

### Microsoft.Azure.Commands.Management. Storage. Models.PSShare

## NOTES

## RELATED LINKS
