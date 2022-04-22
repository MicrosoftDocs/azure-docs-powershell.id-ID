---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Monitor.dll-Help.xml
Module Name: Az.Monitor
ms.assetid: B1000C10-265E-4465-B167-F1251470BE3E
online version: https://docs.microsoft.com/powershell/module/az.monitor/new-azalertruleemail
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Monitor/Monitor/help/New-AzAlertRuleEmail.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Monitor/Monitor/help/New-AzAlertRuleEmail.md
ms.openlocfilehash: 81de16797413f13f5448e93469506d09c1418b11
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142939943"
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
Cmdlet **New-AzAlertRuleEmail** membuat tindakan email untuk aturan peringatan.

## EXAMPLES

### Contoh 1: Membuat tindakan email aturan peringatan untuk pemilik layanan
```powershell
New-AzAlertRuleEmail -SendToServiceOwners
```

Perintah ini membuat tindakan email aturan pemberitahuan untuk dikirimkan bagi pemilik layanannya saat aturan peringatan ditembakkan.

### Contoh 2: Membuat tindakan email aturan peringatan untuk pemilik non-layanan
```powershell
New-AzAlertRuleEmail -CustomEmail pattif@contoso.com,davidchew@contoso.net
```

Perintah ini membuat tindakan email aturan pemberitahuan untuk alamat email tertentu, tetapi tidak untuk pemilik layanan.

### Contoh 3: Membuat tindakan email aturan peringatan untuk pemilik layanan dan pemilik non-layanan
```powershell
New-AzAlertRuleEmail -CustomEmail pattif@contoso.net -SendToServiceOwners
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
Menunjukkan bahwa operasi ini mengirim email ke pemilik layanan ketika aturan diterapkan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

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


