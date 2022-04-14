---
external help file: ''
Module Name: Az.DataProtection
online version: https://docs.microsoft.com/powershell/module/az.dataprotection/initialize-azdataprotectionbackupinstance
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataProtection/help/Initialize-AzDataProtectionBackupInstance.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataProtection/help/Initialize-AzDataProtectionBackupInstance.md
ms.openlocfilehash: fbbac2466a27da3aa93cf16fb7e35aaf1ed39dc6
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142306267"
---
# Initialize-AzDataProtectionBackupInstance

## SYNOPSIS
Menginisialisasi objek Permintaan instans Cadangan untuk mengonfigurasi cadangan

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.dataprotection/initialize-azdataprotectionbackupinstance) untuk informasi terbaru.

## SYNTAX

```
Initialize-AzDataProtectionBackupInstance -DatasourceLocation <String> -DatasourceType <DatasourceTypes>
 [-DatasourceId <String>] [-PolicyId <String>] [-SecretStoreType <SecretStoreTypes>]
 [-SecretStoreURI <String>] [<CommonParameters>]
```

## DESCRIPTION
Menginisialisasi objek Permintaan instans Cadangan untuk mengonfigurasi cadangan

## EXAMPLES

### Contoh 1: Dapatkan objek instans Cadangan untuk Azure Disk
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

Perintah Pertama mendapatkan semua kebijakan dalam kubah tertentu.
Perintah kedua menyimpan id sumber daya disk Azure dalam variabel $AzureDiskId.
Perintah ketiga mengembalikan sumber daya instans cadangan untuk Azure Disk.
Perintah keempat mengatur bidang grup sumber daya snapshot.
Obyek ini kini bisa digunakan untuk mengonfigurasi cadangan untuk diska yang diberikan.

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
Lokasi Datasource yang akan dilindungi.

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
Tipe Sumber Data

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
Id Kebijakan yang akan disebarkan ke Datasource

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
Tipe penyimpanan rahasia untuk autentikasi penyimpanan rahasia sumber data.
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
Rahasia uri untuk penyimpanan rahasia autentikasi sumber data.
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.DataProtection.Models.Api20210701.IBackupInstanceResource

## CATATAN

ALIAS

## RELATED LINKS

