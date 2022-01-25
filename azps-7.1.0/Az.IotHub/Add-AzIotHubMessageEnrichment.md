---
external help file: Microsoft.Azure.PowerShell.Cmdlets.IotHub.dll-Help.xml
Module Name: Az.IotHub
online version: https://docs.microsoft.com/powershell/module/az.iothub/add-aziothubmessageenrichment
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/IotHub/IotHub/help/Add-AzIotHubMessageEnrichment.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/IotHub/IotHub/help/Add-AzIotHubMessageEnrichment.md
ms.openlocfilehash: 6c43847a1696125d8ab65d11ad98cec41282f348
ms.sourcegitcommit: e109cc5320478db6aa8a52d49996b133007a65b9
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 01/12/2022
ms.locfileid: "136745168"
---
# Add-AzIotHubMessageEnrichment

## SYNOPSIS
Membuat pengayaan pesan untuk titik akhir yang dipilih di IoT Hub Anda.

## SYNTAX

### ResourceSet (Default)
```
Add-AzIotHubMessageEnrichment [-ResourceGroupName] <String> [-Name] <String> [-Key] <String> -Value <String>
 -Endpoint <String[]> [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObjectSet
```
Add-AzIotHubMessageEnrichment [-InputObject] <PSIotHub> [-Key] <String> -Value <String> -Endpoint <String[]>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ResourceIdSet
```
Add-AzIotHubMessageEnrichment [-ResourceId] <String> [-Key] <String> -Value <String> -Endpoint <String[]>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Tambahkan hingga 10 pengayaan pesan per IoT Hub. Ini ditambahkan sebagai properti aplikasi untuk pesan yang dikirim ke titik akhir yang dipilih.
Untuk mengetahui selengkapnya, lihat https://docs.microsoft.com/azure/iot-hub/iot-hub-message-enrichments-overview

## EXAMPLES

### Contoh 1
```powershell
PS C:\> Add-AzIotHubMessageEnrichment -ResourceGroupName "myresourcegroup" -Name "myiothub" -Key "newKey" -Value "newValue" -Endpoint endpoint1,endpoint2

Key          : newKey
Value        : newValue
Endpoint(s)  : { endpoint1, endpoint2 }
```

Tambahkan pengayaan baru dengan tombol "newKey" dan nilai "newValue". Pengayaan baru ini diterapkan pada titik akhir "endpoint1" dan "endpoint2".

## PARAMETERS

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

### -Titik akhir
Titik akhir untuk menerapkan pengayaan.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Objek IotHub

```yaml
Type: Microsoft.Azure.Commands.Management.IotHub.Models.PSIotHub
Parameter Sets: InputObjectSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Key
Kunci pengayaan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Nama Hub Iot

```yaml
Type: System.String
Parameter Sets: ResourceSet
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama Grup Sumber Daya

```yaml
Type: System.String
Parameter Sets: ResourceSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceId
Id Sumber Daya IotHub

```yaml
Type: System.String
Parameter Sets: ResourceIdSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Value
Nilai pengayaan.

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

### -Konfirmasi
Meminta konfirmasi Anda sebelum menjalankan cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
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
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( http://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### Microsoft.Azure.Commands.Management.IotHub.Models.PSIotHub

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Management.IotHub.Models.PSEnrichmentMetadata

## CATATAN

## RELATED LINKS
