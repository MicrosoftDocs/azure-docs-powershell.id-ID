---
external help file: ''
Module Name: Az.DataBox
online version: https://docs.microsoft.com/powershell/module/az.DataBox/new-AzDataBoxTransferConfigurationObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataBox/help/New-AzDataBoxTransferConfigurationObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataBox/help/New-AzDataBoxTransferConfigurationObject.md
ms.openlocfilehash: a7e7441c0f230f93c4411a94ad491c511e7a8c06
ms.sourcegitcommit: 5df8b100721844736630242c724da453a2168434
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/26/2022
ms.locfileid: "146607089"
---
# New-AzDataBoxTransferConfigurationObject

## SYNOPSIS
Buat objek dalam memori untuk TransferConfiguration.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.databox/new-azdataboxtransferconfigurationobject) untuk informasi terbaru.

## SYNTAX

```
New-AzDataBoxTransferConfigurationObject -Type <TransferConfigurationType>
 [-TransferAllDetail <ITransferConfigurationTransferAllDetails>]
 [-TransferFilterDetail <ITransferConfigurationTransferFilterDetails>] [<CommonParameters>]
```

## DESCRIPTION
Buat objek dalam memori untuk TransferConfiguration.

## EXAMPLES

### Contoh 1: Objek dalam memori untuk konfigurasi transfer pekerjaan ekspor 
```powershell
$transferConfigurationType = New-AzDataBoxTransferConfigurationObject -Type "TransferAll" -TransferAllDetail @{"IncludeDataAccountType"="StorageAccount";"IncludeTransferAllBlob"= "True"; "IncludeTransferAllFile"="True"}
```

Membuat objek dalam memori untuk pekerjaan ekspor TransferConfiguration

## PARAMETERS

### -TransferAllDetail
Peta jenis filter dan detail untuk mentransfer semua data.
Bidang ini diperlukan hanya jika TransferConfigurationType diberikan sebagai TransferAll.
Untuk membuat, lihat bagian CATATAN untuk properti TRANSFERALLDETAIL dan buat tabel hash.

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
Peta jenis filter dan detail untuk difilter.
Bidang ini diperlukan hanya jika TransferConfigurationType diberikan sebagai TransferUsingFilter.
Untuk membuat, lihat bagian CATATAN untuk properti TRANSFERFILTERDETAIL dan buat tabel hash.

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

### -Type
Jenis konfigurasi untuk transfer.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.DataBox.Models.Api20210301.TransferConfiguration

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


TRANSFERALLDETAIL `<ITransferConfigurationTransferAllDetails>`: Peta jenis filter dan detail untuk mentransfer semua data. Bidang ini diperlukan hanya jika TransferConfigurationType diberikan sebagai TransferAll.
  - `[IncludeDataAccountType <DataAccountType?>]`: Jenis akun data
  - `[IncludeTransferAllBlob <Boolean?>]`: Untuk menunjukkan apakah semua blob Azure harus ditransfer
  - `[IncludeTransferAllFile <Boolean?>]`: Untuk menunjukkan apakah semua Azure Files harus ditransfer

TRANSFERFILTERDETAIL `<ITransferConfigurationTransferFilterDetails>`: Peta jenis filter dan detail untuk difilter. Bidang ini diperlukan hanya jika TransferConfigurationType diberikan sebagai TransferUsingFilter.
  - `[AzureFileFilterDetailFilePathList <String[]>]`: Daftar jalur lengkap file yang akan ditransfer.
  - `[AzureFileFilterDetailFilePrefixList <String[]>]`: Daftar awalan file Azure yang akan ditransfer.
  - `[AzureFileFilterDetailFileShareList <String[]>]`: Daftar berbagi file yang akan ditransfer.
  - `[BlobFilterDetailBlobPathList <String[]>]`: Daftar jalur lengkap blob yang akan ditransfer.
  - `[BlobFilterDetailBlobPrefixList <String[]>]`: Daftar awalan blob Azure yang akan ditransfer.
  - `[BlobFilterDetailContainerList <String[]>]`: Daftar kontainer blob yang akan ditransfer.
  - `[IncludeDataAccountType <DataAccountType?>]`: Jenis akun data.
  - `[IncludeFilterFileDetail <IFilterFileDetails[]>]`: Detail file filter yang akan digunakan untuk transfer data.
    - `FilterFilePath <String>`: Jalur file yang berisi detail semua item yang akan ditransfer.
    - `FilterFileType <FilterFileType>`: Jenis file filter.

## RELATED LINKS

