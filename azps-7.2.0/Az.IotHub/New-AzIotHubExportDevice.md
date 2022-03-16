---
external help file: Microsoft.Azure.PowerShell.Cmdlets.IotHub.dll-Help.xml
Module Name: Az.IotHub
online version: https://docs.microsoft.com/powershell/module/az.iothub/new-aziothubexportdevice
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/IotHub/IotHub/help/New-AzIotHubExportDevice.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/IotHub/IotHub/help/New-AzIotHubExportDevice.md
ms.openlocfilehash: a9952221371dc922222872fab7513a08f650494c
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140122803"
---
# New-AzIotHubExportDevice

## SYNOPSIS
Membuat pekerjaan perangkat ekspor baru.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan [lihat versi terbaru](/powershell/module/az.iothub/new-aziothubexportdevice) untuk informasi terkini.

## SYNTAX

```
New-AzIotHubExportDevice [-ResourceGroupName] <String> [-Name] <String> [-ExportBlobContainerUri] <String>
 [-ExcludeKeys] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Membuat pekerjaan ekspor perangkat baru untuk IotHub.
Langkah ini akan mengekspor semua perangkat ke wadah yang ditentukan. Lihat artikel berikut tentang cara menghasilkan URI SAS.
https://docs.microsoft.com/azure/iot-hub/iot-hub-bulk-identity-mgmt#get-the-container-sas-uri .

## EXAMPLES

### Contoh 1 Masalah permintaan perangkat ekspor.
```
PS C:\> New-AzIotHubExportDevice -ResourceGroupName "myresourcegroup" -Name "myiothub" -ExportBlobContainerUri "https://mystorageaccount.blob.core.windows.net/mystoragecontainer?sv=2015-04-05&ss=bfqt&sr=c&srt=sco&sp=rwdl&se=2016-10-27T04:01:48Z&st=2016-10-26T20:01:48Z&spr=https&sig=QqpIhHsIMF8hNuFO%3D" -ExcludeKeys
```

Membuat permintaan perangkat ekspor baru untuk "myiothub" IotHub tidak termasuk kunci.

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

### -ExcludeKeys
Memungkinkan untuk mengekspor perangkat tanpa kunci.

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

### -ExportBlobContainerUri
Uri untuk mengekspor blob ke. 

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Nama IotHub

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

### -Konfirmasi
Meminta konfirmasi Anda sebelum menjalankan cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan.
Cmdlet tidak berjalan.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
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
