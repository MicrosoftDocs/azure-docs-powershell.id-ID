---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Storage.dll-Help.xml
Module Name: Az.Storage
online version: https://docs.microsoft.com/powershell/module/az.storage/new-azdatalakegen2sastoken
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Storage/Storage.Management/help/New-AzDataLakeGen2SasToken.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Storage/Storage.Management/help/New-AzDataLakeGen2SasToken.md
ms.openlocfilehash: 03341c134bc2cebfbbfc53c193fad579c94fa520
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145620703"
---
# New-AzDataLakeGen2SasToken

## SYNOPSIS
Menghasilkan token SAS untuk item Azure DatalakeGen2.

## SYNTAX

### ReceiveManual (Default)
```
New-AzDataLakeGen2SasToken [-FileSystem] <String> [-Path <String>] [-Permission <String>]
 [-Protocol <SasProtocol>] [-IPAddressOrRange <String>] [-StartTime <DateTimeOffset>]
 [-ExpiryTime <DateTimeOffset>] [-FullUri] [-Context <IStorageContext>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ItemPipeline
```
New-AzDataLakeGen2SasToken -InputObject <AzureDataLakeGen2Item> [-Permission <String>]
 [-Protocol <SasProtocol>] [-IPAddressOrRange <String>] [-StartTime <DateTimeOffset>]
 [-ExpiryTime <DateTimeOffset>] [-FullUri] [-Context <IStorageContext>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzDataLakeGen2SasToken** menghasilkan token Tanda Tangan Akses Bersama (SAS) untuk item Azure DatalakeGen2.

## EXAMPLES

### Contoh 1: Membuat token SAS dengan izin penuh
```
New-AzDataLakeGen2SasToken -FileSystem "filesystem1" -Path "dir1/dir2" -Permission racwdlmeop
```

Contoh ini menghasilkan token SAS DatalakeGen2 dengan izin penuh.

### Contoh 2: Menghasilkan token SAS dengan StartTime tertentu, ExpireTime, Protocal, IPAddressOrRange, dengan alur item datalakegen2
```
Get-AzDataLakeGen2Item -FileSystem test -Path "testdir/dir2" | New-AzDataLakeGen2SasToken -Permission rw -Protocol Https -IPAddressOrRange 10.0.0.0-12.10.0.0 -StartTime (Get-Date) -ExpiryTime (Get-Date).AddDays(6)
```

Contoh ini menghasilkan token SAS DatalakeGen2 dengan alur item datalake gen2, dan dengan StartTime tertentu, ExpireTime, Protocal, IPAddressOrRange.

## PARAMETERS

### -Context
Objek Konteks Azure Storage

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.IStorageContext
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExpiryTime
Waktu Kedaluwarsa

```yaml
Type: System.Nullable`1[System.DateTimeOffset]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FileSystem
Nama FileSystem

```yaml
Type: System.String
Parameter Sets: ReceiveManual
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -FullUri
Menampilkan uri penuh dengan token sas

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

### -InputObject
Objek Item Azure Datalake Gen2 untuk dihapus.

```yaml
Type: Microsoft.WindowsAzure.Commands.Common.Storage.ResourceModel.AzureDataLakeGen2Item
Parameter Sets: ItemPipeline
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -IPAddressOrRange
IP, atau rentang IP ACL (daftar kontrol akses) bahwa permintaan akan diterima oleh Azure Storage.

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

### -Jalur
Jalur dalam FileSystem yang ditentukan yang harus diambil.
Dapat berupa file atau direktori Dalam format 'directory/file.txt' atau 'directory1/directory2/'.
Lewati atur parameter ini untuk mendapatkan direktori akar Filesystem.

```yaml
Type: System.String
Parameter Sets: ReceiveManual
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Izin
Izin untuk blob.
Izin dapat berupa subset "racwdlmeop" yang tidak kosong.

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

### -Protokol
Protokol dapat digunakan dalam permintaan dengan token SAS ini.

```yaml
Type: System.Nullable`1[Azure.Storage.Sas.SasProtocol]
Parameter Sets: (All)
Aliases:
Accepted values: None, HttpsAndHttp, Https

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StartTime
Waktu Mulai

```yaml
Type: System.Nullable`1[System.DateTimeOffset]
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

### System.String

### Microsoft.WindowsAzure.Commands.Common. Storage. ResourceModel.AzureDataLakeGen2Item

### Microsoft.Azure.Commands.Common.Authentication.Abstractions.IStorageContext

## OUTPUTS

### System.String

## NOTES

## RELATED LINKS
