---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Batch.dll-Help.xml
Module Name: Az.Batch
online version: https://docs.microsoft.com/powershell/module/az.batch/get-azbatchsupportedvirtualmachinesku
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Batch/Batch/help/Get-AzBatchSupportedVirtualMachineSku.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Batch/Batch/help/Get-AzBatchSupportedVirtualMachineSku.md
ms.openlocfilehash: b56e757effa2b6a2ad005f415c2ae66f5aea91a3
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144195140"
---
# Get-AzBatchSupportedVirtualMachineSku

## SYNOPSIS
Mendapatkan daftar ukuran VM Komputer Virtual yang didukung Batch yang tersedia di lokasi tertentu.

## SYNTAX

```
Get-AzBatchSupportedVirtualMachineSku [-Location] <String> [[-MaxResultCount] <Int32>] [[-Filter] <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION

## EXAMPLES

### Contoh 1 Dapatkan sku yang didukung untuk suatu wilayah
```powershell
PS C:\> Get-AzBatchSupportedVirtualMachineSku eastus

Name               FamilyName            Capabilities
----               ----------            ------------
Basic_A1           basicAFamily          {MaxResourceVolumeMB, OSVhdSizeMB, vCPUs, MemoryPreservingMaintenanceSupporte...
Basic_A2           basicAFamily          {MaxResourceVolumeMB, OSVhdSizeMB, vCPUs, MemoryPreservingMaintenanceSupporte...
Basic_A3           basicAFamily          {MaxResourceVolumeMB, OSVhdSizeMB, vCPUs, MemoryPreservingMaintenanceSupporte...
...
```

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

### -Filter
Ekspresi filter OData.
Properti yang valid untuk pemfilteran adalah "familyName".

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Lokasi
Wilayah untuk mendapatkan SKU yang didukung dari.

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

### -MaxResultCount
Jumlah maksimum item yang akan dikembalikan dalam respons.

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### System.String

### System.Nullable'1[[System.Int32, System.Private.CoreLib, Version=6.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]

## OUTPUTS

### Microsoft.Azure.Commands.Batch.Models.PSSupportedSku

## NOTES

## RELATED LINKS
