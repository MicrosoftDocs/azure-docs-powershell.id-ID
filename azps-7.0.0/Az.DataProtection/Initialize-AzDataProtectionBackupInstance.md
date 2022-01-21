---
external help file: ''
Module Name: Az.DataProtection
online version: https://docs.microsoft.com/powershell/module/az.dataprotection/initialize-azdataprotectionbackupinstance
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataProtection/help/Initialize-AzDataProtectionBackupInstance.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataProtection/help/Initialize-AzDataProtectionBackupInstance.md
ms.openlocfilehash: 6d9efc75a6ab3ce5cc00f06e39137ce5a3475cea
ms.sourcegitcommit: 579224f3f35e223624deb694bceb0033c84a5856
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 12/07/2021
ms.locfileid: "136560641"
---
# Initialize-AzDataProtectionBackupInstance

## SYNOPSIS
Memulai objek Permintaan instans Cadangan untuk mengonfigurasi cadangan

## SYNTAX

```
Initialize-AzDataProtectionBackupInstance -DatasourceLocation <String> -DatasourceType <DatasourceTypes>
 [-DatasourceId <String>] [-PolicyId <String>] [-SecretStoreType <SecretStoreTypes>]
 [-SecretStoreURI <String>] [<CommonParameters>]
```

## DESCRIPTION
Memulai objek Permintaan instans Cadangan untuk mengonfigurasi cadangan

## EXAMPLES

### Contoh 1: Dapatkan objek instance Cadangan untuk Disk Azure
```powershell
PS C:\> $policy = Get-AzDataProtectionBackupPolicy -SubscriptionId "xxxx-xxx-xxx" -ResourceGroupName sarath-rg -VaultName sarath-vault
PS C:\> $AzureDiskId = "/subscriptions/{subscription}/resourceGroups/{resourceGroup}/providers/Microsoft.Compute/disks/{diskname}"
PS C:\> $instance = Initialize-AzDataProtectionBackupInstance -DatasourceType AzureDisk -DatasourceLocation westus -DatasourceId $AzureDiskId -PolicyId $policy[0].Id
PS C:\> $instance.Property.PolicyInfo.PolicyParameter.DataStoreParametersList[0].ResourceGroupId = "/subscriptions/{subscription}/resourceGroups/{snapshotResourceGroup}"
PS C:\> $instance

Name Type BackupInstanceName
---- ---- ------------------
          sarath-disk3-sarath-disk3-af697a80-e2bc-49f1-af6c-22f6c4d68405
```

Perintah Pertama menerapkan semua kebijakan dalam vault tertentu.
Perintah kedua menyimpan id sumber daya disk Azure dalam $AzureDiskId sumber daya.
Perintah ketiga mengembalikan sumber daya instans cadangan untuk Azure Disk.
Perintah keempat mengatur bidang grup sumber daya snapshot.
Objek ini sekarang bisa digunakan untuk mengonfigurasi cadangan untuk disk tertentu.

## PARAMETERS

### -DatasourceId
ID sumber data yang akan dilindungi

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DatasourceLocation
Lokasi SumberData untuk diproteksi.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DatasourceType
Tipe SumberData

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.DataProtection.Support.DatasourceTypes
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PolicyId
Id Kebijakan yang akan diberikan ke SumberData

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SecretStoreType
Tipe penyimpanan rahasia untuk autentikasi sumber data toko rahasia.
Parameter ini hanya didukung untuk AzureDatabaseForPostgreSQL saat ini.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.DataProtection.Support.SecretStoreTypes
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SecretStoreURI
Rahasia uri untuk autentikasi penyimpanan rahasia sumber data.
Parameter ini hanya didukung untuk AzureDatabaseForPostgreSQL saat ini.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.DataProtection.Models.Api20210701.IBackupInstanceResource

## CATATAN

ALIAS

## RELATED LINKS

