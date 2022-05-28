---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Monitor.dll-Help.xml
Module Name: Az.Monitor
ms.assetid: B1000C10-265E-4465-B167-F1251470BE3E
online version: https://docs.microsoft.com/powershell/module/az.monitor/new-azalertruleemail
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Monitor/Monitor/help/New-AzAlertRuleEmail.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Monitor/Monitor/help/New-AzAlertRuleEmail.md
ms.openlocfilehash: 58e3b607164842e01df3e9dbb9fe12f9c659ef3d
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145516903"
---
# New-AzAlertRuleEmail

## SYNOPSIS
Membuat tindakan email untuk aturan pemberitahuan.

## SYNTAX

```
New-AzAlertRuleEmail [[-CustomEmail] <String[]>] [-SendToServiceOwner]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzAlertRuleEmail** membuat tindakan email untuk aturan pemberitahuan.

## EXAMPLES

### Contoh 1: Membuat tindakan email aturan pemberitahuan untuk pemilik layanan
```powershell
New-AzAlertRuleEmail -SendToServiceOwner
```

Perintah ini membuat tindakan email aturan pemberitahuan untuk dikirimkan kepada pemilik layanannya saat aturan pemberitahuan diaktifkan.

### Contoh 2: Membuat tindakan email aturan pemberitahuan untuk pemilik non-layanan
```powershell
New-AzAlertRuleEmail -CustomEmail pattif@contoso.com,davidchew@contoso.net
```

Perintah ini membuat tindakan email aturan pemberitahuan untuk alamat email yang ditentukan, tetapi tidak untuk pemilik layanan.

### Contoh 3: Membuat tindakan email aturan pemberitahuan untuk pemilik layanan dan pemilik non-layanan
```powershell
New-AzAlertRuleEmail -CustomEmail pattif@contoso.net -SendToServiceOwner
```

Perintah ini membuat tindakan email aturan pemberitahuan untuk alamat yang ditentukan dan untuk pemilik layanannya.

## PARAMETERS

### -CustomEmail
Menentukan daftar alamat email yang dipisahkan koma.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

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

### -SendToServiceOwner
Menunjukkan bahwa operasi ini mengirim email ke pemilik layanan ketika aturan diaktifkan.

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### System.String[]

### System.Management.Automation.SwitchParameter

## OUTPUTS

### Microsoft.Azure.Management.Monitor.Management.Models.RuleEmailAction

## NOTES

## RELATED LINKS

[Add-AzMetricAlertRule](./Add-AzMetricAlertRule.md)

[Add-AzWebtestAlertRule](./Add-AzWebtestAlertRule.md)

[New-AzAlertRuleWebhook](./New-AzAlertRuleWebhook.md)


