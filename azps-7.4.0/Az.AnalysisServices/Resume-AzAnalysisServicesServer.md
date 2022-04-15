---
external help file: Microsoft.Azure.PowerShell.Cmdlets.AnalysisServices.dll-Help.xml
Module Name: Az.AnalysisServices
online version: https://docs.microsoft.com/powershell/module/az.analysisservices/resume-azanalysisservicesserver
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/AnalysisServices/AnalysisServices/help/Resume-AzAnalysisServicesServer.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/AnalysisServices/AnalysisServices/help/Resume-AzAnalysisServicesServer.md
ms.openlocfilehash: 21496b60c182db73a87024de8b7954cb728ed161
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142170314"
---
# Resume-AzAnalysisServicesServer

## SYNOPSIS
Melanjutkan contoh server Analysis Services

## SYNTAX

```
Resume-AzAnalysisServicesServer [[-ResourceGroupName] <String>] [-Name] <String> [-PassThru]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet Resume-AzAnalysisServicesServer melanjutkan contoh server Analysis Services

## EXAMPLES

### Contoh 1
```powershell
Resume-AzAnalysisServicesServer -Name "testserver" -ResourceGroupName "testgroup"
```

Perintah ini akan melanjutkan server yang dijeda bernama testserver dalam grup uji grup sumber daya

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure.

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

### -Nama
Nama server Analysis Services

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

### -PassThru
Akan mengembalikan detail server yang dihapus jika operasi berhasil diselesaikan

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

### -ResourceGroupName
Nama grup sumber daya Azure tempat server berada

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Konfirmasi
Meminta pengguna untuk mengonfirmasi apakah akan melakukan operasi

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
Menguraikan tindakan yang akan dilakukan operasi saat ini tanpa benar-benar menjalankannya

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.AnalysisServices.Models.AzureAnalysisServicesServer

## CATATAN
Alias: Resume-AzAs

## RELATED LINKS

[Get-AzAnalysisServicesServer](./Get-AzAnalysisServicesServer.md)

[Suspend-AzAnalysisServicesServer](./Suspend-AzAnalysisServicesServer.md)
