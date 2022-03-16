---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Storage.Management.dll-Help.xml
Module Name: Az.Storage
online version: https://docs.microsoft.com/powershell/module/az.storage/remove-azrmstorageshare
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Storage/Storage.Management/help/Remove-AzRmStorageShare.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Storage/Storage.Management/help/Remove-AzRmStorageShare.md
ms.openlocfilehash: 5948aa59c4c2135b12869c27dee875df1a3ceb7c
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "139948265"
---
# Remove-AzRmStorageShare

## SYNOPSIS
Menghapus file Storage bersama.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan [lihat versi terbaru](/powershell/module/az.storage/remove-azrmstorageshare) untuk informasi terkini.

## SYNTAX

### Nama Akun (Default)
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
Cmdlet **New-AzRmStorageShare** menghapus Storage file baru.

## EXAMPLES

### Contoh 1: Hapus Storage berbagi file dengan Storage nama akun dan nama berbagi Anda
```
PS C:\>Remove-AzRmStorageShare -ResourceGroupName "myResourceGroup" -StorageAccountName "myStorageAccount" -Name "myshare"
```

Perintah ini akan menghapus Storage file gratis dengan Storage akun dan nama berbagi.

### Contoh 2: Hapus Storage file bersama dengan Storage objek akun dan nama berbagi
```
PS C:\>$accountObject = Get-AzStorageAccount -ResourceGroupName "myResourceGroup" -StorageAccountName "myStorageAccount"
PS C:\>Remove-AzRmStorageShare -StorageAccount $accountObject -Name "myshare"
```

Perintah ini menghapus file Storage file yang dibagikan dengan Storage objek akun dan nama berbagi Anda.

### Contoh 3: Hapus semua Storage file yang ada dalam Storage dengan pipeline
```
PS C:\>Get-AzStorageShare -ResourceGroupName "myResourceGroup" -StorageAccountName "myStorageAccount" | Remove-AzRmStorageShare -Force
```

Perintah ini menghapus semua Storage file yang ada dalam Storage dengan saluran.

### Contoh 4: Hapus satu Storage berbagi file
```
PS C:\>Remove-AzRmStorageShare -ResourceGroupName "myResourceGroup" -StorageAccountName "myStorageAccount" -Name "myshare" -SnapshotTime "2021-05-10T08:04:08Z"
```

Perintah ini menghapus satu Storage file berbagi jepretan layar dengan nama dan waktu jepretan layar tertentu

### Contoh 5: Hapus Storage berbagi file dan snapshotnya
```
PS C:\>Remove-AzRmStorageShare -ResourceGroupName "myResourceGroup" -StorageAccountName "myStorageAccount" -Name "myshare" -Include Snapshots
```

Perintah ini menghapus file Storage berbagi file dan snapshotnya secara default, cmdlet akan gagal jika berbagi file memiliki snapshot tanpa parameter "-sertakan".

### Contoh 6: Hapus Storage berbagi file dan semua snapshotnya (termasuk snapshot yang disewakan)
```
PS C:\>Remove-AzRmStorageShare -ResourceGroupName "myResourceGroup" -StorageAccountName "myStorageAccount" -Name "myshare" -Include Leased-Snapshots
```

Perintah ini menghapus Storage file yang dibagikan dan semua snapshotnya, termasuk snapshot yang disewakan dan bukan sewa.
Secara default, cmdlet akan gagal jika berbagi file memiliki snapshot tanpa parameter "-sertakan".

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
Paksa untuk menghapus Bagikan dan semua konten di dalamnya

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

### -Sertakan
Nilai valid adalah: snapshot, snapshot yang disewa, tidak ada. Nilai default adalah tidak ada. Untuk 'tidak ada', berbagi file akan dihapus jika tidak memiliki jepretan layar bersama. Jika berbagi file berisi snapshot (menyewa atau tidak leased), penghapusan akan gagal.
Untuk 'jepretan layar', berbagi file akan dihapus, termasuk semua jepretan layar berbagi file. Jika berbagi file berisi snapshot yang disewa, penghapusan akan gagal.
Untuk 'snapshot yang disewa', berbagi file dihapus mencakup semua snapshot berbagi filenya (yang tidak setidaknya / tidak setidaknya). 

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
Storage berbagi objek

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

### -Nama
Bagikan Nama

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
Menunjukkan bahwa cmdlet ini **mengembalikan Boolean** yang mencerminkan keberhasilan operasi.
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
Storage Akun.

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

### -Konfirmasi
Meminta konfirmasi Anda sebelum menjalankan cmdlet.

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
Cmdlet tidak berjalan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### Microsoft.Azure.Commands.Management. Storage. Models.PSStorageAccount

### Microsoft.Azure.Commands.Management. Storage. Models.PSShare

## OUTPUTS

### System.Boolean

## CATATAN

## RELATED LINKS
