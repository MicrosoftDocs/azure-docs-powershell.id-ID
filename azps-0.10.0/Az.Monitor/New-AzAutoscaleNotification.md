---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Monitor.dll-Help.xml
Module Name: Az.Monitor
ms.assetid: B5B5F494-D912-40D0-99E2-A62FAACA3EC9
online version: https://docs.microsoft.com/en-us/powershell/module/az.monitor/new-azautoscalenotification
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/Azs-tzl/src/Monitor/Monitor/help/New-AzAutoscaleNotification.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/Azs-tzl/src/Monitor/Monitor/help/New-AzAutoscaleNotification.md
ms.openlocfilehash: 6b14ce05ba618f624012002d459a76b1103b65c4f4bf4df97f562727102f9c87
ms.sourcegitcommit: 49f8ffe5d8e08ba3d22e3b2e76db0e54dd55d4f0
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/11/2021
ms.locfileid: "132413847"
---
# New-AzAutoscaleNotification

## SYNOPSIS
Membuat pemberitahuan email Skala Otomatis.

## SYNTAX

```
New-AzAutoscaleNotification [[-Webhook] <WebhookNotification[]>] [[-CustomEmail] <String[]>]
 [-SendEmailToSubscriptionAdministrator] [-SendEmailToSubscriptionCoAdministrator]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzAutoscaleNotification** membuat pemberitahuan email untuk Skala Otomatis.

## EXAMPLES

### Contoh 1: Membuat pemberitahuan email Skala Otomatis
```
PS C:\>New-AzAutoscaleNotification -CustomEmail "pattif@contoso.com, davidchew@contoso.net"
```

Perintah ini akan membuat pemberitahuan email Skala Otomatis untuk dua alamat yang ditentukan.

### Contoh 2: Buat pemberitahuan email Skala Otomatis untuk administrator langganan
```
PS C:\>New-AzAutoscaleNotification -SendEmailToSubscriptionAdministrator
```

Perintah ini akan membuat pemberitahuan email Skala Otomatis untuk administrator langganan.

## PARAMETERS

### -CustomEmail
Menentukan daftar alamat email yang dipisahkan tanda koma.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

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

### -SendEmailToSubscriptionAdministrator
Menunjukkan bahwa operasi ini mengirimkan pemberitahuan email ke administrator langganan.

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

### -SendEmailToSubscriptionCoAdministrator
Menunjukkan bahwa operasi ini mengirimkan pemberitahuan email ke administrator bersama langganan.

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

### -Webhook
Menentukan daftar web skala otomatis yang dipisahkan koma.

```yaml
Type: Microsoft.Azure.Management.Monitor.Management.Models.WebhookNotification[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Management.Monitor.Management.Models.WebhookNotification[]

### System.String[]

### System.Management.Automation.SwitchParameter

## OUTPUTS

### Microsoft.Azure.Management.Monitor.Management.Models.AutoscaleNotification

## CATATAN

## RELATED LINKS

[New-AzAutoscaleWebhook](./New-AzAutoscaleWebhook.md)


