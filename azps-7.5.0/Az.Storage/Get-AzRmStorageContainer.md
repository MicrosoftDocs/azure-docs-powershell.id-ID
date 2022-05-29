---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Storage.Management.dll-Help.xml
Module Name: Az.Storage
online version: https://docs.microsoft.com/powershell/module/az.storage/get-azrmstoragecontainer
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Storage/Storage.Management/help/Get-AzRmStorageContainer.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Storage/Storage.Management/help/Get-AzRmStorageContainer.md
ms.openlocfilehash: 6625511ad1ed64b709ffba6239de61fe5402e832
ms.sourcegitcommit: 82b4008b76d035e4aee733727371765b0d853bed
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145718056"
---
# Get-AzRmStorageContainer

## SYNOPSIS
Mendapatkan atau mencantumkan Storage kontainer blob

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.storage/get-azrmstoragecontainer) untuk informasi terbaru.

## SYNTAX

### AccountName (Default)
```
Get-AzRmStorageContainer [-ResourceGroupName] <String> [-StorageAccountName] <String> [-Name <String>]
 [-IncludeDeleted] [-AsJob] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### AccountObject
```
Get-AzRmStorageContainer -StorageAccount <PSStorageAccount> [-Name <String>] [-IncludeDeleted] [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzRmStorageContainer** mendapatkan atau mencantumkan Storage kontainer blob

## EXAMPLES

### Contoh 1: Dapatkan kontainer blob Storage dengan nama akun dan nama kontainer Storage
```
PS C:\>Get-AzRmStorageContainer -ResourceGroupName "myResourceGroup" -AccountName "myStorageAccount" -ContainerName "myContainer"
```

Perintah ini mendapatkan kontainer blob Storage dengan nama akun Storage dan nama kontainer.

### Contoh 2: Mencantumkan semua kontainer blob Storage dari akun Storage
```
PS C:\>Get-AzRmStorageContainer -ResourceGroupName "myResourceGroup" -AccountName "myStorageAccount"
```

Perintah ini mencantumkan semua kontainer blob Storage dari akun Storage dengan nama akun Storage.

### Contoh 3: Dapatkan kontainer blob Storage dengan objek akun Storage dan nama kontainer.
```
PS C:\>$accountObject = Get-AzStorageAccount -ResourceGroupName "myResourceGroup" -AccountName "myStorageAccount"
PS C:\>Get-AzRmStorageContainer -StorageAccount $accountObject -ContainerName "myContainer"
```

Perintah ini mendapatkan kontainer blob Storage dengan objek akun Storage dan nama kontainer.

### Contoh 4: Cantumkan Storage kontainer blob akun Storage, sertakan kontainer yang dihapus.
```
PS C:\>Get-AzRmStorageContainer -ResourceGroupName "myResourceGroup" -AccountName "myStorageAccount" -IncludeDeleted

   ResourceGroupName: myResourceGroup, StorageAccountName: myStorageAccount

Name         PublicAccess LastModified         HasLegalHold HasImmutabilityPolicy Deleted VersionId  
----         ------------ ------------         ------------ --------------------- ------- ---------  
testcon      None         2020-08-28 10:18:13Z False        False                 False   01D685BC91A88F22
testcon2     None         2020-09-04 12:52:37Z False        False                 True    01D67D248986B6DA
```

Contoh ini mencantumkan semua kontainer akun penyimpanan, termasuk kontainer yang dihapus.
Kontainer yang dihapus hanya akan ada setelah softdelete Kontainer yang diaktifkan dengan Enable-AzStorageBlobDeleteRetentionPolicy.

## PARAMETERS

### -AsJob
Jalankan cmdlet di latar belakang

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

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure.

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

### -IncludeDeleted
Menyertakan kontainer yang dihapus, secara default, kontainer daftar tidak akan menyertakan kontainer yang dihapus

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

### -Name
Nama Kontainer

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: N, ContainerName

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
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
Accept pipeline input: True (ByPropertyName)
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
Accept pipeline input: True (ByPropertyName, ByValue)
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
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### Microsoft.Azure.Commands.Management. Storage. Models.PSStorageAccount

## OUTPUTS

### Microsoft.Azure.Commands.Management. Storage. Models.PSContainer

## NOTES

## RELATED LINKS
