---
external help file: Microsoft.Azure.Commands.AzureBackup.dll-Help.xml
Module Name: AzureRM.Backup
ms.assetid: 95FF3F7A-5CC6-4AA6-A393-5EBB5579D9A2
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.backup/get-azurermbackupvault
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/AzureBackup/Commands.AzureBackup/help/Get-AzureRmBackupVault.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/AzureBackup/Commands.AzureBackup/help/Get-AzureRmBackupVault.md
ms.openlocfilehash: c11170e6bee80b9eaa19135ad604d8bf70e1baab
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143110457"
---
# Get-AzureRmBackupVault

## SYNOPSIS
Mendapatkan kubah Cadangan.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Get-AzureRmBackupVault [[-ResourceGroupName] <String>] [[-Name] <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureRmBackupVault** mendapatkan Azure Backup kubah.
Cmdlet ini mengembalikan objek **AzureRmBackupVault** untuk digunakan dengan cmdlet lainnya.

## EXAMPLES

### Contoh 1: Menampilkan semua kubah Cadangan
```
PS C:\>Get-AzureRmBackupVault
```

Perintah ini mendapatkan semua Azure Backup kubah.

### Contoh 2: Menampilkan semua kubah yang dibuat di AS Barat
```
PS C:\>Get-AzureRmBackupVault | Where-Object { $_.Region -eq "westus" }
```

Perintah ini mendapatkan semua kubah Cadangan.
Perintah mengarahkan mereka ke cmdlet Where-Object menggunakan operator pipeline.
Cmdlet tersebut memfilter hasil berdasarkan properti **Kawasan** .
Untuk informasi selengkapnya, ketik .`Get-Help Where-Object`

### Contoh 3: Dapatkan kubah tertentu
```
PS C:\>Get-AzureRmBackupVault -Name "Vault03"
ResourceId        : /subscriptions/4bfbe168-f42a-4a06-8f5a-331cad1f497e/resourceGroups/ResourceGroup011/providers/Microsoft.Backup
                    /BackupVault/Vault
Name              : Vault03
ResourceGroupName : ResourceGroup01
Region            : westus
Storage           : GeoRedundant
```

Perintah ini mendapatkan kubah bernama Vault03.

### Contoh 4: Menghitung jumlah kubah yang memiliki penyimpanan lokal yang berlebihan
```
PS C:\>Get-AzureRmBackupVault | Where-Object { $_.Storage -match "LocallyRedundant" } | Measure-Object
Count    : 4
Average  : 
Sum      : 
Maximum  : 
Minimum  : 
Property :
```

Perintah ini mendapatkan semua Azure Backup kubah.
Perintah mengarahkan mereka ke **Where-Object**, yang memfilter hasil berdasarkan properti **Storage**.
Perintah melewati yang memiliki nilai LocallyRedundant ke cmdlet Measure-Object, yang menghitung hasil.
Untuk informasi selengkapnya, ketik .`Get-Help Measure-Object`

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure

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

### -Nama
Menentukan nama kubah Cadangan yang didapatkan cmdlet ini.
Jika lebih dari satu kubah Cadangan memiliki nama yang sama, cmdlet ini mengembalikan semuanya.
Tentukan parameter *ResourceGroupName* untuk mendapatkan kubah unik.

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
Menentukan nama grup sumber daya Azure tempat cmdlet ini mendapatkan kubah Cadangan.

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak

## OUTPUTS

### Microsoft.Azure.Commands.AzureBackup.Models.AzureRMBackupVault

## NOTES

## RELATED LINKS

[Get-AzureRmBackupContainer](./Get-AzureRmBackupContainer.md)

[AzureRmBackupVault Baru](./New-AzureRmBackupVault.md)

[Hapus-AzureRmBackupVault](./Remove-AzureRmBackupVault.md)

[Set-AzureRmBackupVault](./Set-AzureRmBackupVault.md)


