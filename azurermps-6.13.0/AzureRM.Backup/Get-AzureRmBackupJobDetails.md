---
external help file: Microsoft.Azure.Commands.AzureBackup.dll-Help.xml
Module Name: AzureRM.Backup
ms.assetid: 6187F603-5298-4854-94F3-0C38FCF3125F
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.backup/get-azurermbackupjobdetails
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/AzureBackup/Commands.AzureBackup/help/Get-AzureRmBackupJobDetails.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/AzureBackup/Commands.AzureBackup/help/Get-AzureRmBackupJobDetails.md
ms.openlocfilehash: bf4ba77a7162faaf593e11b68a82fe5a6e55df1d
ms.sourcegitcommit: d28d7d5f6278862d833182868a9dcde2c31e657b
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/24/2022
ms.locfileid: "132414828"
---
# Get-AzureRmBackupJobDetails

## SYNOPSIS
Mendapatkan detail pekerjaan Pencadangan.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### JobsFiltersSet (Default)
```
Get-AzureRmBackupJobDetails -Job <AzureRMBackupJob> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### IdFiltersSet
```
Get-AzureRmBackupJobDetails -Vault <AzureRMBackupVault> -JobId <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureRmBackupJobDetails** mendapatkan detail pekerjaan Azure Backup.
Anda dapat menggunakan cmdlet ini untuk mengumpulkan informasi tentang pekerjaan yang gagal.

## EXAMPLES

### Contoh 1: Menampilkan detail pekerjaan yang gagal
```
PS C:\>$Vault = Get-AzureRmBackupVault -Name "Vault03" 
PS C:\> $Jobs = Get-AzureRmBackupJob -Vault $Vault -Status Failed
PS C:\> $JobDetails = Get-AzureRmBackupJobDetails -Job $Jobs[0]
PS C:\> $JobDetails.ErrorDetails
ErrorCode ErrorMessage                            Recommendations
--------- ------------                            ---------------
   400001 Command execution failed.               {Another operation is currently in p...
```

Perintah pertama mengambil vault bernama Vault03 menggunakan cmdlet **Get-AzureRmBackupVault** .
Perintah menyimpan objek tersebut dalam $Vault variabel.
Perintah kedua gagal melakukan pekerjaan dari vault di $Vault, lalu menyimpannya dalam $Jobs array tertentu.
Pekerjaan ketiga mendapatkan detail untuk pekerjaan pertama di $Jobs baru, lalu menyimpan detail tersebut di $JobDetails baru.
Perintah terakhir menampilkan properti **ErrorDetails** dari rumus $JobDetails menggunakan sintaks titik standar.

### Contoh 2: Menampilkan tindakan yang direkomendasikan untuk pekerjaan yang gagal
```
PS C:\>$JobDetails.ErrorDetails.Recommendations
Another operation is currently in progress on this item. Please wait until the previous operation is completed, and then retry.
```

Perintah ini menampilkan tindakan yang direkomendasikan $JobDetails variabel yang dibuat dalam contoh pertama.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure

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

### -Job
Menentukan pekerjaan yang mendapatkan detail cmdlet ini.
Untuk mendapatkan objek **AzureRmBackupJob** , gunakan Get-AzureRmBackupJob cmdlet.

```yaml
Type: Microsoft.Azure.Commands.AzureBackup.Models.AzureRMBackupJob
Parameter Sets: JobsFiltersSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -JobId
Menentukan ID pekerjaan yang mendapatkan detail cmdlet ini.
ID adalah properti **InstanceId** dari objek **AzureRmBackupJob** .
Untuk mendapatkan objek **AzureRmBackupJob** , gunakan Get-AzureRmBackupJob.

```yaml
Type: System.String
Parameter Sets: IdFiltersSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Vault
Menentukan vault Cadangan di mana cmdlet ini mendapatkan detail pekerjaan.
Untuk mendapatkan objek **AzureRmBackupVault** , gunakan cmdlet Get-AzureRmBackupVault.

```yaml
Type: Microsoft.Azure.Commands.AzureBackup.Models.AzureRMBackupVault
Parameter Sets: IdFiltersSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.AzureBackup.Models.AzureRMBackupJob
Parameter: Pekerjaan (ByValue)

## OUTPUTS

### Microsoft.Azure.Commands.AzureBackup.Models.AzureRMBackupJobDetails

## CATATAN

## RELATED LINKS

[Get-AzureRmBackupJob](./Get-AzureRmBackupJob.md)

[Get-AzureRmBackupVault](./Get-AzureRmBackupVault.md)


