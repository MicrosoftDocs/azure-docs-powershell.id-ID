---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Storage.Management.dll-Help.xml
Module Name: Az.Storage
online version: https://docs.microsoft.com/powershell/module/az.storage/remove-azrmstorageshare
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Storage/Storage.Management/help/Remove-AzRmStorageShare.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Storage/Storage.Management/help/Remove-AzRmStorageShare.md
ms.openlocfilehash: 602ed6ce4092ed0c9c7e94ebc04ed683775b95b6
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144191248"
---
# Remove-AzRmStorageShare

## SYNOPSIS
Menghapus berbagi file Storage.

## SYNTAX

### AccountName (Default)
```
Remove-AzRmStorageShare [-ResourceGroupName] <String> [-StorageAccountName] <String> -Name <String> [-Force]
 [-Include <String>] [-PassThru] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### AccountNameSnapshot
```
Remove-AzRmStorageShare [-ResourceGroupName] <String> [-StorageAccountName] <String> -Name <String>
 -SnapshotTime <DateTime> [-Force] [-PassThru] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### AccountObject
```
Remove-AzRmStorageShare -Name <String> -StorageAccount <PSStorageAccount> [-Force] [-Include <String>]
 [-PassThru] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### AccountObjectSnapshot
```
Remove-AzRmStorageShare -Name <String> -StorageAccount <PSStorageAccount> -SnapshotTime <DateTime> [-Force]
 [-PassThru] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ShareResourceId
```
Remove-AzRmStorageShare [-ResourceId] <String> [-Force] [-Include <String>] [-PassThru]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ShareObject
```
Remove-AzRmStorageShare -InputObject <PSShare> [-Force] [-Include <String>] [-PassThru]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzRmStorageShare** menghapus berbagi file Storage.

## EXAMPLES

### Contoh 1: Menghapus berbagi file Storage dengan nama akun Storage dan nama berbagi
```
PS C:\>Remove-AzRmStorageShare -ResourceGroupName "myResourceGroup" -StorageAccountName "myStorageAccount" -Name "myshare"
```

Perintah ini menghapus berbagi file Storage dengan nama akun Storage dan nama berbagi.

### Contoh 2: Menghapus berbagi file Storage dengan objek akun Storage dan nama berbagi
```
PS C:\>$accountObject = Get-AzStorageAccount -ResourceGroupName "myResourceGroup" -StorageAccountName "myStorageAccount"
PS C:\>Remove-AzRmStorageShare -StorageAccount $accountObject -Name "myshare"
```

Perintah ini menghapus berbagi file Storage dengan objek akun Storage dan nama berbagi.

### Contoh 3: Menghapus semua berbagi file Storage di akun Storage dengan alur
```
PS C:\>Get-AzStorageShare -ResourceGroupName "myResourceGroup" -StorageAccountName "myStorageAccount" | Remove-AzRmStorageShare -Force
```

Perintah ini menghapus semua berbagi file Storage di akun Storage dengan alur.

### Contoh 4: Menghapus salinan bayangan berbagi file Storage tunggal
```
PS C:\>Remove-AzRmStorageShare -ResourceGroupName "myResourceGroup" -StorageAccountName "myStorageAccount" -Name "myshare" -SnapshotTime "2021-05-10T08:04:08Z"
```

Perintah ini menghapus salinan bayangan berbagi file Storage tunggal dengan nama berbagi dan waktu rekam jepret tertentu

### Contoh 5: Menghapus berbagi file Storage dan salinan bayangannya
```
PS C:\>Remove-AzRmStorageShare -ResourceGroupName "myResourceGroup" -StorageAccountName "myStorageAccount" -Name "myshare" -Include Snapshots
```

Perintah ini menghapus berbagi file Storage dan rekam jepret secara default, cmdlet akan gagal jika berbagi file memiliki rekam jepret tanpa parameter "-include".

### Contoh 6: Menghapus berbagi file Storage dan semua rekam jepretnya (termasuk rekam jepret yang disewakan)
```
PS C:\>Remove-AzRmStorageShare -ResourceGroupName "myResourceGroup" -StorageAccountName "myStorageAccount" -Name "myshare" -Include Leased-Snapshots
```

Perintah ini menghapus berbagi file Storage dan semua rekam jepretnya, termasuk rekam jepret yang disewakan dan tidak disewakan.
Secara default, cmdlet akan gagal jika berbagi file memiliki rekam jepret tanpa parameter "-include".

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

### -Force
Paksa untuk menghapus Berbagi dan semua konten di dalamnya

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

### -Meliputi
Nilai yang valid adalah: rekam jepret, rekam jepret sewaan, tidak ada. Nilai defaultnya tidak ada. Untuk 'none', berbagi file akan dihapus jika tidak memiliki salinan bayangan berbagi. Jika berbagi file berisi rekam jepret apa pun (disewakan atau tidak dilepas), penghapusan gagal.
Untuk 'rekam jepret', berbagi file dihapus termasuk semua salinan bayangan berbagi filenya. Jika berbagi file berisi rekam jepret sewaan, penghapusan gagal.
Untuk 'leased-snapshots', berbagi file dihapus menyertakan semua rekam jepret berbagi filenya (disewakan/tidak dilepas). 

```yaml
Type: System.String
Parameter Sets: AccountName, AccountObject, ShareResourceId, ShareObject
Aliases:
Accepted values: None, Snapshots, Leased-Snapshots

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
objek berbagi Storage

```yaml
Type: Microsoft.Azure.Commands.Management.Storage.Models.PSShare
Parameter Sets: ShareObject
Aliases: Share

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Nama Berbagi

```yaml
Type: System.String
Parameter Sets: AccountName, AccountNameSnapshot, AccountObject, AccountObjectSnapshot
Aliases: N, ShareName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Menunjukkan bahwa cmdlet ini mengembalikan **Boolean** yang mencerminkan keberhasilan operasi.
Secara default, cmdlet ini tidak mengembalikan nilai.

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

### -ResourceGroupName
Nama Grup Sumber Daya.

```yaml
Type: System.String
Parameter Sets: AccountName, AccountNameSnapshot
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
Bagikan SnapshotTime

```yaml
Type: System.Nullable`1[System.DateTime]
Parameter Sets: AccountNameSnapshot, AccountObjectSnapshot
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageAccount
Storage objek akun

```yaml
Type: Microsoft.Azure.Commands.Management.Storage.Models.PSStorageAccount
Parameter Sets: AccountObject, AccountObjectSnapshot
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
Parameter Sets: AccountName, AccountNameSnapshot
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

### Microsoft.Azure.Commands.Management. Storage. Models.PSShare

## OUTPUTS

### System.Boolean

## NOTES

## RELATED LINKS
