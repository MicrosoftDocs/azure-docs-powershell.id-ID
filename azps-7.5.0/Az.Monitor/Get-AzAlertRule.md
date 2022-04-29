---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Monitor.dll-Help.xml
Module Name: Az.Monitor
ms.assetid: A837077C-0A79-431C-93D2-799B2134EE69
online version: https://docs.microsoft.com/powershell/module/az.monitor/get-azalertrule
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Monitor/Monitor/help/Get-AzAlertRule.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Monitor/Monitor/help/Get-AzAlertRule.md
ms.openlocfilehash: de1e31c4f6dffc731dfcbde808f62dee5426d1b0
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144222218"
---
# Get-AzAlertRule

## SYNOPSIS
Mendapatkan aturan pemberitahuan klasik.

## SYNTAX

### GetByResourceGroup
```
Get-AzAlertRule -ResourceGroupName <String> [-DetailedOutput] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### GetByName
```
Get-AzAlertRule -ResourceGroupName <String> -Name <String> [-DetailedOutput]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### GetByResourceUri
```
Get-AzAlertRule -ResourceGroupName <String> -TargetResourceId <String> [-DetailedOutput]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzAlertRule** mendapatkan aturan pemberitahuan klasik berdasarkan namanya atau URI, atau semua aturan pemberitahuan klasik dari grup sumber daya tertentu.

## EXAMPLES

### Contoh 1: Mendapatkan aturan pemberitahuan untuk grup sumber daya
```powershell
Get-AzAlertRule -ResourceGroup "Default-Web-CentralUS"
```

Perintah ini mendapatkan semua aturan pemberitahuan untuk grup sumber daya bernama Default-Web-CentralUS.
Output tidak berisi detail tentang aturan karena parameter *DetailedOutput* tidak ditentukan.

### Contoh 2: Mendapatkan aturan pemberitahuan berdasarkan nama
```powershell
Get-AzAlertRule -ResourceGroup "Default-Web-CentralUS" -Name "myalert-7da64548-214d-42ca-b12b-b245bb8f0ac8"
```

Perintah ini mendapatkan aturan pemberitahuan bernama myalert-7da64548-214d-42ca-b12b-b245bb8f0ac8.
Karena parameter *DetailedOutput* tidak ditentukan, output hanya berisi informasi dasar tentang aturan pemberitahuan.

### Contoh 3: Dapatkan aturan pemberitahuan berdasarkan nama dengan output terperinci
```powershell
Get-AzAlertRule -ResourceGroup "Default-Web-CentralUS" -Name "myalert-7da64548-214d-42ca-b12b-b245bb8f0ac8" -DetailedOutput
```

Perintah ini mendapatkan aturan pemberitahuan bernama myalert-7da64548-214d-42ca-b12b-b245bb8f0ac8.
Parameter *DetailedOutput* ditentukan, sehingga output dirinci.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure

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

### -DetailedOutput
Menampilkan detail lengkap dalam output.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Menentukan nama aturan pemberitahuan yang akan didapatkan.

```yaml
Type: System.String
Parameter Sets: GetByName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Menentukan nama grup sumber daya.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: ResourceGroup

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TargetResourceId
Menentukan ID sumber daya target.

```yaml
Type: System.String
Parameter Sets: GetByResourceUri
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### System.String

### System.Management.Automation.SwitchParameter

## OUTPUTS

### Microsoft.Azure.Commands. Insights. OutputClasses.PSAlertRule

## NOTES

## RELATED LINKS

[Add-AzMetricAlertRule](./Add-AzMetricAlertRule.md)

[Add-AzWebtestAlertRule](./Add-AzWebtestAlertRule.md)

[Get-AzAlertHistory](./Get-AzAlertHistory.md)

[Remove-AzAlertRule](./Remove-AzAlertRule.md)


