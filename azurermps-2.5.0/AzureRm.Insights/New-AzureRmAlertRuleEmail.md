---
external help file: Microsoft.Azure.Commands.Insights.dll-Help.xml
Module Name: AzureRM.Insights
ms.assetid: B1000C10-265E-4465-B167-F1251470BE3E
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.insights/new-azurermalertruleemail
schema: 2.0.0
ms.openlocfilehash: 20134cc0f2eef927361439fb431bc4ab9308a9a1
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143053641"
---
# New-AzureRmAlertRuleEmail

## SYNOPSIS
Membuat tindakan email untuk aturan pemberitahuan.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
New-AzureRmAlertRuleEmail [[-CustomEmail] <String[]>] [-SendToServiceOwner]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzureRmAlertRuleEmail** membuat tindakan email untuk aturan peringatan.

## EXAMPLES

### Contoh 1: Membuat tindakan email aturan peringatan untuk pemilik layanan
```
PS C:\>New-AzureRmAlertRuleEmail -SendToServiceOwners
```

Perintah ini membuat tindakan email aturan pemberitahuan untuk dikirimkan bagi pemilik layanannya saat aturan peringatan ditembakkan.

### Contoh 2: Membuat tindakan email aturan peringatan untuk pemilik non-layanan
```
PS C:\>New-AzureRmAlertRuleEmail -CustomEmails pattif@contoso.com,davidchew@contoso.net
```

Perintah ini membuat tindakan email aturan pemberitahuan untuk alamat email tertentu, tetapi tidak untuk pemilik layanan.

### Contoh 3: Membuat tindakan email aturan peringatan untuk pemilik layanan dan pemilik non-layanan
```
PS C:\>New-AzureRmAlertRuleEmail -CustomEmails pattif@contoso.net -SendToServiceOwners
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
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String[]

### System.Management.Automation.SwitchParameter

## OUTPUTS

### Microsoft.Azure.Management.Monitor.Management.Models.RuleEmailAction

## NOTES

## RELATED LINKS



[Add-AzureRmMetricAlertRule](./Add-AzureRmMetricAlertRule.md)

[Add-AzureRmWebtestAlertRule](./Add-AzureRmWebtestAlertRule.md)

[New-AzureRmAlertRuleWebhook](./New-AzureRmAlertRuleWebhook.md)


