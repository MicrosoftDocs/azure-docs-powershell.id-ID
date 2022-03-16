---
external help file: Microsoft.Azure.PowerShell.Cmdlets.IotHub.dll-Help.xml
Module Name: Az.IotHub
online version: https://docs.microsoft.com/powershell/module/az.iothub/get-aziothubjob
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/IotHub/IotHub/help/Get-AzIotHubJob.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/IotHub/IotHub/help/Get-AzIotHubJob.md
ms.openlocfilehash: 4ad003464338cac4cd5a4ef91142aa1c4d5f9c8e
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140199639"
---
# Get-AzIotHubJob

## SYNOPSIS
Mendapatkan informasi tentang pekerjaan IotHub.

## SYNTAX

```
Get-AzIotHubJob [-ResourceGroupName] <String> [-Name] <String> [[-JobId] <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan informasi tentang Pekerjaan IotHub.
Pekerjaan IotHub dibuat ketika operasi impor atau ekspor diinisasi menggunakan New-AzIotHubExportDevices atau New-AzIotHubImportDevices impor.
Anda dapat mencantumkan semua pekerjaan atau memfilter pekerjaan menggunakan Pengidentifikasi Pekerjaan.

## EXAMPLES

### Contoh 1 Daftar semua Pekerjaan
```
PS C:\> Get-AzIotHubJob -ResourceGroupName "myresourcegroup" -Name "myiothub"
```

Mendapatkan semua pekerjaan untuk IotHub bernama "myiothub"

### Contoh 2 Mendapatkan Pekerjaan tertentu
```
PS C:\> Get-AzIotHubJob -ResourceGroupName "myresourcegroup" -Name "myiothub" -JobId 3630fc31-4caa-43e8-a232-ea0577221cb2
```

Mendapatkan informasi tentang pekerjaan dengan pengidentifikasi "3630fc31-4caa-43e8-a232-ea0577221cb2" untuk IotHub bernama "myiothub"

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure

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

### -JobId
Pengidentifikasi Pekerjaan. 

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Nama hub IoT. 

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Nama Grup Sumber Daya

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Management.IotHub.Models.PSIotHubJobResponse

## CATATAN

## RELATED LINKS
