---
external help file: Microsoft.Azure.Commands.AzureBackup.dll-Help.xml
Module Name: AzureRM.Backup
ms.assetid: 95FF3F7A-5CC6-4AA6-A393-5EBB5579D9A2
online version: ''
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/AzureBackup/Commands.AzureBackup/help/Get-AzureRmBackupVault.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/AzureBackup/Commands.AzureBackup/help/Get-AzureRmBackupVault.md
ms.openlocfilehash: ef4d8ca2e1fb21165281375b3d325f5fc8b6ceed
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132427933"
---
# Get-AzureRmBackupVault

## SYNOPSIS
Mendapatkan vault Cadangan.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Get-AzureRmBackupVault [[-ResourceGroupName] <String>] [[-Name] <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureRmBackupVault** mendapatkan vault Azure Backup.
Cmdlet ini mengembalikan **objek AzureRmBackupVault** untuk digunakan dengan cmdlet lainnya.

## EXAMPLES

### Contoh 1: Menampilkan semua vault Cadangan
```
PS C:\>Get-AzureRmBackupVault
```

Perintah ini akan mendapatkan semua vault Azure Backup.

### Contoh 2: Menampilkan semua vault yang dibuat di West US
```
PS C:\>Get-AzureRmBackupVault | Where-Object { $_.Region -eq "westus" }
```

Perintah ini akan mendapatkan semua vault Cadangan.
Perintah itu meneruskannya ke Where-Object cmdlet dengan menggunakan operator pipeline.
Cmdlet tersebut memfilter hasil berdasarkan **properti** Kawasan.
Untuk informasi selengkapnya, ketik `Get-Help Where-Object` .

### Contoh 3: Dapatkan vault tertentu
```
PS C:\>Get-AzureRmBackupVault -Name "Vault03"
ResourceId        : /subscriptions/4bfbe168-f42a-4a06-8f5a-331cad1f497e/resourceGroups/ResourceGroup011/providers/Microsoft.Backup
                    /BackupVault/Vault
Name              : Vault03
ResourceGroupName : ResourceGroup01
Region            : westus
Storage           : GeoRedundant
```

Perintah ini mendapatkan vault bernama Vault03.

### Contoh 4: Hitung jumlah vault yang memiliki penyimpanan lokal yang berlebihan
```
PS C:\>Get-AzureRmBackupVault | Where-Object { $_.Storage -match "LocallyRedundant" } | Measure-Object
Count    : 4
Average  : 
Sum      : 
Maximum  : 
Minimum  : 
Property :
```

Perintah ini akan mendapatkan semua vault Azure Backup.
Perintah melewatinya ke **Where-Object**, yang memfilter hasil berdasarkan **Storage** mereka.
Perintah melewati orang-orang yang memiliki nilai LocallyRedundant ke cmdlet Measure-Object, yang menghitung hasilnya.
Untuk informasi selengkapnya, ketik `Get-Help Measure-Object` .

## PARAMETERS

### -Nama
Menentukan nama vault Cadangan yang akan dapatkan cmdlet ini.
Jika ada lebih dari satu vault Cadangan yang memiliki nama yang sama, cmdlet ini akan mengembalikan semuanya.
Tentukan parameter *ResourceGroupName* untuk mendapatkan vault yang unik.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Menentukan nama grup sumber daya Azure yang mendapatkan vault Cadangan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

## OUTPUTS

### AzureRmBackupVault

## CATATAN
* Tidak ada

## RELATED LINKS

[Get-AzureRmBackupContainer](./Get-AzureRmBackupContainer.md)

[New-AzureRmBackupVault](./New-AzureRmBackupVault.md)

[Remove-AzureRmBackupVault](./Remove-AzureRmBackupVault.md)

[Set-AzureRmBackupVault](./Set-AzureRmBackupVault.md)


