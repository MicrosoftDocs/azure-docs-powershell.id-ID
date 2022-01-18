---
external help file: Microsoft.Azure.PowerShell.Cmdlets.MachineLearning.dll-Help.xml
Module Name: Az.MachineLearning
online version: https://docs.microsoft.com/powershell/module/az.machinelearning/export-azmlwebservice
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/MachineLearning/MachineLearning/help/Export-AzMlWebService.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/MachineLearning/MachineLearning/help/Export-AzMlWebService.md
ms.openlocfilehash: 3429cfcac234d492e96686fce5528aa6ed44b96a
ms.sourcegitcommit: 53ef403038f665f1b3a9f616185b31f5de9bd7bb
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/03/2021
ms.locfileid: "136171233"
---
# Export-AzMlWebService

## SYNOPSIS
Mengekspor objek definisi layanan web sebagai string yang diformat JSON.

## SYNTAX

### ExportToFile
```
Export-AzMlWebService -WebService <WebService> -OutputFile <String> [-Force]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ExportToJSON
```
Export-AzMlWebService -WebService <WebService> [-ToJsonString] [-Force]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Mengekspor objek definisi untuk layanan web tertentu sebagai string yang diformat JSON.
Anda dapat segera mengembalikan string atau menyimpannya ke file.

## EXAMPLES

### Contoh 1: Ekspor sebagai string
```
Export-AzMlWebService -WebService $svc -ToJsonString
```

### Contoh 2: Ekspor ke file
```
Export-AzMlWebService -WebService $svc -OutputFile "C:\mlservice.json"
```

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

### -Force
Jangan minta konfirmasi.

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

### -OutputFile
Jalur file untuk definisi yang diekspor.

```yaml
Type: System.String
Parameter Sets: ExportToFile
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ToJsonString
Menentukan bahwa definisi akan diekspor sebagai string JSON.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ExportToJSON
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WebService
Objek definisi layanan web yang akan diekspor.

```yaml
Type: Microsoft.Azure.Management.MachineLearning.WebServices.Models.WebService
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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

### Microsoft.Azure.Management.MachineLearning.WebServices.Models.WebService

## OUTPUTS

### System.String

## CATATAN
Kata kunci: azure, azurerm, arm, resource, management, manager, machine, machine learning, azureml

## RELATED LINKS
