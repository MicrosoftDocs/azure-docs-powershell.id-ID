---
external help file: ''
Module Name: Az.DataBox
online version: https://docs.microsoft.com/powershell/module/az.DataBox/new-AzDataBoxTransferConfigurationObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataBox/help/New-AzDataBoxTransferConfigurationObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataBox/help/New-AzDataBoxTransferConfigurationObject.md
ms.openlocfilehash: 7e2dcb011e4ea0fbc91ba5fddf282351c913154f
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142216189"
---
# New-AzDataBoxTransferConfigurationObject

## SYNOPSIS
Membuat objek dalam memori untuk TransferConfiguration.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.databox/new-azdataboxtransferconfigurationobject) untuk informasi terbaru.

## SYNTAX

```
New-AzDataBoxTransferConfigurationObject -Type <TransferConfigurationType>
 [-TransferAllDetail <ITransferConfigurationTransferAllDetails>]
 [-TransferFilterDetail <ITransferConfigurationTransferFilterDetails>] [<CommonParameters>]
```

## DESCRIPTION
Membuat objek dalam memori untuk TransferConfiguration.

## EXAMPLES

### Contoh 1: Objek dalam memori untuk konfigurasi transfer pekerjaan ekspor 
```powershell
$transferConfigurationType = New-AzDataBoxTransferConfigurationObject -Type "TransferAll" -TransferAllDetail @{"IncludeDataAccountType"="StorageAccount";"IncludeTransferAllBlob"= "True"; "IncludeTransferAllFile"="True"}
```

Membuat objek dalam memori untuk pekerjaan ekspor TransferConfiguration

## PARAMETERS

### -TransferAllDetail
Peta tipe filter dan detail untuk mentransfer semua data.
Bidang ini diperlukan hanya jika TransferConfigurationType diberikan sebagai TransferAll.
Untuk membangun, lihat bagian CATATAN untuk properti TRANSFERALLDETAIL dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.DataBox.Models.Api20210301.ITransferConfigurationTransferAllDetails
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TransferFilterDetail
Peta tipe filter dan detail yang akan difilter.
Bidang ini diperlukan hanya jika TransferConfigurationType diberikan sebagai TransferUsingFilter.
Untuk membangun, lihat bagian CATATAN untuk properti TRANSFERFILTERDETAIL dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.DataBox.Models.Api20210301.ITransferConfigurationTransferFilterDetails
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Tipe
Tipe konfigurasi untuk transfer.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.DataBox.Support.TransferConfigurationType
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.DataBox.Models.Api20210301.TransferConfiguration

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


TRANSFERALLDETAIL <ITransferConfigurationTransferAllDetails>: Peta tipe filter dan detail untuk mentransfer semua data. Bidang ini diperlukan hanya jika TransferConfigurationType diberikan sebagai TransferAll.
  - `[IncludeDataAccountType <DataAccountType?>]`: Tipe akun data
  - `[IncludeTransferAllBlob <Boolean?>]`: Untuk menunjukkan apakah semua blob Azure harus ditransfer
  - `[IncludeTransferAllFile <Boolean?>]`: Untuk menunjukkan apakah semua Azure Files harus ditransfer

TRANSFERFILTERDETAIL <ITransferConfigurationTransferFilterDetails>: Peta tipe filter dan detail untuk difilter. Bidang ini diperlukan hanya jika TransferConfigurationType diberikan sebagai TransferUsingFilter.
  - `[AzureFileFilterDetailFilePathList <String[]>]`: Daftar jalur lengkap file yang akan ditransfer.
  - `[AzureFileFilterDetailFilePrefixList <String[]>]`: Daftar prefiks file Azure yang akan ditransfer.
  - `[AzureFileFilterDetailFileShareList <String[]>]`: Daftar pembagian file yang akan ditransfer.
  - `[BlobFilterDetailBlobPathList <String[]>]`: Daftar jalur lengkap dari blob yang akan ditransfer.
  - `[BlobFilterDetailBlobPrefixList <String[]>]`: Daftar prefiks blob Azure yang akan ditransfer.
  - `[BlobFilterDetailContainerList <String[]>]`: Daftar wadah blob yang akan ditransfer.
  - `[IncludeDataAccountType <DataAccountType?>]`: Tipe akun data.
  - `[IncludeFilterFileDetail <IFilterFileDetails[]>]`: Detail file filter yang akan digunakan untuk transfer data.
    - `FilterFilePath <String>`: Jalur file yang berisi detail semua item untuk ditransfer.
    - `FilterFileType <FilterFileType>`: Tipe file filter.

## RELATED LINKS

