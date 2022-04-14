---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Storage.Management.dll-Help.xml
Module Name: Az.Storage
online version: https://docs.microsoft.com/powershell/module/Az.storage/add-Azstorageaccountmanagementpolicyaction
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Storage/Storage.Management/help/Add-AzStorageAccountManagementPolicyAction.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Storage/Storage.Management/help/Add-AzStorageAccountManagementPolicyAction.md
ms.openlocfilehash: 2e329f8989f52bf1074c0a31a6078eb247badda8
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142040069"
---
# Add-AzStorageAccountManagementPolicyAction

## SYNOPSIS
Menambahkan tindakan ke objek Grup Tindakan ManagementPolicy input, atau membuat objek Grup Tindakan ManagementPolicy dengan tindakan tersebut. Objek dapat digunakan dalam New-AzStorageAccountManagementPolicyRule.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.storage/add-azstorageaccountmanagementpolicyaction) untuk informasi terbaru.

## SYNTAX

### BaseBlob (Default)
```
Add-AzStorageAccountManagementPolicyAction -BaseBlobAction <String> -DaysAfterModificationGreaterThan <Int32>
 [-InputObject <PSManagementPolicyActionGroup>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### BaseBlobLastAccessTime
```
Add-AzStorageAccountManagementPolicyAction -BaseBlobAction <String> -DaysAfterLastAccessTimeGreaterThan <Int32>
 [-EnableAutoTierToHotFromCool] [-InputObject <PSManagementPolicyActionGroup>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### Snapshot
```
Add-AzStorageAccountManagementPolicyAction -SnapshotAction <String> -DaysAfterCreationGreaterThan <Int32>
 [-InputObject <PSManagementPolicyActionGroup>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### BlobVersion
```
Add-AzStorageAccountManagementPolicyAction -BlobVersionAction <String> -DaysAfterCreationGreaterThan <Int32>
 [-InputObject <PSManagementPolicyActionGroup>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Add-AzStorageAccountManagementPolicyAction** menambahkan tindakan ke objek Grup Tindakan ManagementPolicy input, atau membuat objek Grup Tindakan ManagementPolicy dengan tindakan tersebut.

## EXAMPLES

### Contoh 1: Membuat objek Grup Tindakan ManagementPolicy dengan 4 tindakan, lalu menambahkannya ke aturan kebijakan manajemen dan diatur ke akun Storage
```
PS C:\>$action = Add-AzStorageAccountManagementPolicyAction -BaseBlobAction Delete -daysAfterModificationGreaterThan 100
PS C:\>$action = Add-AzStorageAccountManagementPolicyAction -BaseBlobAction TierToArchive -daysAfterModificationGreaterThan 50  -InputObject $action
PS C:\>$action = Add-AzStorageAccountManagementPolicyAction -BaseBlobAction TierToCool -DaysAfterLastAccessTimeGreaterThan 30  -EnableAutoTierToHotFromCool -InputObject $action
PS C:\>$action = Add-AzStorageAccountManagementPolicyAction -SnapshotAction Delete -daysAfterCreationGreaterThan 100 -InputObject $action
PS C:\>$action 

BaseBlob.TierToCool.DaysAfterModificationGreaterThan      : 
BaseBlob.TierToCool.DaysAfterLastAccessTimeGreaterThan    : 30
BaseBlob.EnableAutoTierToHotFromCool                      : True
BaseBlob.TierToArchive.DaysAfterModificationGreaterThan   : 50
BaseBlob.TierToArchive.DaysAfterLastAccessTimeGreaterThan : 
BaseBlob.Delete.DaysAfterModificationGreaterThan          : 100
BaseBlob.Delete.DaysAfterLastAccessTimeGreaterThan        : 
Snapshot.TierToCool.DaysAfterCreationGreaterThan          : 
Snapshot.TierToArchive.DaysAfterCreationGreaterThan       : 
Snapshot.Delete.DaysAfterCreationGreaterThan              : 100
Version.TierToCool.DaysAfterCreationGreaterThan           : 
Version.TierToArchive.DaysAfterCreationGreaterThan        : 
Version.Delete.DaysAfterCreationGreaterThan               : 

PS C:\>$filter = New-AzStorageAccountManagementPolicyFilter
PS C:\>$rule = New-AzStorageAccountManagementPolicyRule -Name Test -Action $action -Filter $filter
PS C:\>$policy = Set-AzStorageAccountManagementPolicy -ResourceGroupName "myresourcegroup" -AccountName "mystorageaccount" -Rule $rule
```

Perintah pertama membuat objek Grup Tindakan ManagementPolicy, 3 perintah berikut ini menambahkan 3 tindakan ke objek. Lalu tambahkan ke aturan kebijakan manajemen dan atur ke akun Storage.

### Contoh 2: Membuat objek Grup Tindakan ManagementPolicy dengan 6 tindakan pada snapshot dan versi blob, lalu menambahkannya ke aturan kebijakan manajemen dan diatur ke akun Storage
```
PS C:\> $action = Add-AzStorageAccountManagementPolicyAction  -SnapshotAction Delete -daysAfterCreationGreaterThan 40
PS C:\> $action = Add-AzStorageAccountManagementPolicyAction -InputObject $action -SnapshotAction TierToArchive -daysAfterCreationGreaterThan 50
PS C:\> $action = Add-AzStorageAccountManagementPolicyAction -InputObject $action -SnapshotAction TierToCool -daysAfterCreationGreaterThan 60
PS C:\> $action = Add-AzStorageAccountManagementPolicyAction -InputObject $action -BlobVersionAction Delete -daysAfterCreationGreaterThan 70
PS C:\> $action = Add-AzStorageAccountManagementPolicyAction -InputObject $action -BlobVersionAction TierToArchive -daysAfterCreationGreaterThan 80
PS C:\> $action = Add-AzStorageAccountManagementPolicyAction -InputObject $action -BlobVersionAction TierToCool -daysAfterCreationGreaterThan 90
PS C:\> $action

BaseBlob.TierToCool.DaysAfterModificationGreaterThan      : 
BaseBlob.TierToCool.DaysAfterLastAccessTimeGreaterThan    : 
BaseBlob.TierToArchive.DaysAfterModificationGreaterThan   : 
BaseBlob.TierToArchive.DaysAfterLastAccessTimeGreaterThan : 
BaseBlob.Delete.DaysAfterModificationGreaterThan          : 
BaseBlob.Delete.DaysAfterLastAccessTimeGreaterThan        : 
Snapshot.TierToCool.DaysAfterCreationGreaterThan          : 60
Snapshot.TierToArchive.DaysAfterCreationGreaterThan       : 50
Snapshot.Delete.DaysAfterCreationGreaterThan              : 40
Version.TierToCool.DaysAfterCreationGreaterThan           : 90
Version.TierToArchive.DaysAfterCreationGreaterThan        : 80
Version.Delete.DaysAfterCreationGreaterThan               : 70

PS C:\>$filter = New-AzStorageAccountManagementPolicyFilter
PS C:\>$rule = New-AzStorageAccountManagementPolicyRule -Name Test -Action $action -Filter $filter
PS C:\>$policy = Set-AzStorageAccountManagementPolicy -ResourceGroupName "myresourcegroup" -AccountName "mystorageaccount" -Rule $rule
```

Perintah pertama membuat objek Grup Tindakan ManagementPolicy, 5 perintah berikut ini menambahkan 5 tindakan pada snapshot dan versi blob ke objek. Lalu tambahkan ke aturan kebijakan manajemen dan atur ke akun Storage.

## PARAMETERS

### -BaseBlobAction
Tindakan kebijakan manajemen untuk baseblob.

```yaml
Type: System.String
Parameter Sets: BaseBlob, BaseBlobLastAccessTime
Aliases:
Accepted values: Delete, TierToArchive, TierToCool

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -BlobVersionAction
Tindakan kebijakan manajemen untuk versi blob.

```yaml
Type: System.String
Parameter Sets: BlobVersion
Aliases:
Accepted values: Delete, TierToArchive, TierToCool

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DaysAfterCreationGreaterThan
Nilai bilangan bulat menunjukkan usia dalam hari setelah pembuatan.

```yaml
Type: System.Int32
Parameter Sets: Snapshot, BlobVersion
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DaysAfterLastAccessTimeGreaterThan
Nilai bilangan bulat menunjukkan usia dalam hari setelah akses blob terakhir. Properti ini hanya dapat digunakan bersama dengan kebijakan pelacakan waktu akses terakhir.

```yaml
Type: System.Int32
Parameter Sets: BaseBlobLastAccessTime
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DaysAfterModificationGreaterThan
Nilai bilangan bulat menunjukkan usia dalam hari setelah modifikasi terakhir.

```yaml
Type: System.Int32
Parameter Sets: BaseBlob
Aliases:

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

### -EnableAutoTierToHotFromCool
Memungkinkan tingkat otomatis blob dari dingin ke panas pada akses blob. Ini hanya berfungsi dengan tindakan TierToCool dan DaysAfterLastAccessTimeGreaterThan.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: BaseBlobLastAccessTime
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Jika memasukkan objek Tindakan ManagementPolicy, akan mengatur tindakan ke objek tindakan input.
Jika tidak diinput, akan membuat objek tindakan baru.

```yaml
Type: Microsoft.Azure.Commands.Management.Storage.Models.PSManagementPolicyActionGroup
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -SnapshotAction
Tindakan kebijakan manajemen untuk snapshot.

```yaml
Type: System.String
Parameter Sets: Snapshot
Aliases:
Accepted values: Delete, TierToArchive, TierToCool

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Management. Storage. Models.PSManagementPolicyActionGroup

## OUTPUTS

### Microsoft.Azure.Commands.Management. Storage. Models.PSManagementPolicyActionGroup

## CATATAN

## RELATED LINKS
