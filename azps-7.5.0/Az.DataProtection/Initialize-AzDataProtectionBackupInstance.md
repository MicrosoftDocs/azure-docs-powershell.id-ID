---
external help file: ''
Module Name: Az.DataProtection
online version: https://docs.microsoft.com/powershell/module/az.dataprotection/initialize-azdataprotectionbackupinstance
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataProtection/help/Initialize-AzDataProtectionBackupInstance.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataProtection/help/Initialize-AzDataProtectionBackupInstance.md
ms.openlocfilehash: 0ab2bd31874058e862f576c32ace42779d120e30
ms.sourcegitcommit: 82b4008b76d035e4aee733727371765b0d853bed
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145749142"
---
# Initialize-AzDataProtectionBackupInstance

## SYNOPSIS
Menginisialisasi objek Permintaan instans Cadangan untuk mengonfigurasi pencadangan

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.dataprotection/initialize-azdataprotectionbackupinstance) untuk informasi terbaru.

## SYNTAX

```
Initialize-AzDataProtectionBackupInstance -DatasourceLocation <String> -DatasourceType <DatasourceTypes>
 [-DatasourceId <String>] [-PolicyId <String>] [-SecretStoreType <SecretStoreTypes>]
 [-SecretStoreURI <String>] [<CommonParameters>]
```

## DESCRIPTION
Menginisialisasi objek Permintaan instans Cadangan untuk mengonfigurasi pencadangan

## EXAMPLES

### Contoh 1: Dapatkan objek instans Backup untuk Azure Disk
```powershell
$policy = Get-AzDataProtectionBackupPolicy -SubscriptionId "xxxx-xxx-xxx" -ResourceGroupName sarath-rg -VaultName sarath-vault
$AzureDiskId = "/subscriptions/{subscription}/resourceGroups/{resourceGroup}/providers/Microsoft.Compute/disks/{diskname}"
$instance = Initialize-AzDataProtectionBackupInstance -DatasourceType AzureDisk -DatasourceLocation westus -DatasourceId $AzureDiskId -PolicyId $policy[0].Id
$instance.Property.PolicyInfo.PolicyParameter.DataStoreParametersList[0].ResourceGroupId = "/subscriptions/{subscription}/resourceGroups/{snapshotResourceGroup}"
$instance
```

```output
Name Type BackupInstanceName
---- ---- ------------------
          sarath-disk3-sarath-disk3-af697a80-e2bc-49f1-af6c-22f6c4d68405
```

Perintah Pertama mendapatkan semua kebijakan dalam vault tertentu.
Perintah kedua menyimpan id sumber daya disk azure dalam variabel $AzureDiskId.
Perintah ketiga mengembalikan sumber daya instans cadangan untuk Azure Disk.
Perintah keempat mengatur bidang grup sumber daya rekam jepret.
Obyek ini sekarang dapat digunakan untuk mengonfigurasi pencadangan untuk diska yang diberikan.

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
Lokasi Sumber data yang akan dilindungi.

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
Jenis Sumber Data

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
Id Kebijakan yang akan dikaitkan dengan Sumber Data

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
Jenis penyimpanan rahasia untuk autentikasi penyimpanan rahasia sumber data.
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
Uri rahasia untuk autentikasi penyimpanan rahasia sumber data.
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.DataProtection.Models.Api20210701.IBackupInstanceResource

## NOTES

ALIAS

## RELATED LINKS

