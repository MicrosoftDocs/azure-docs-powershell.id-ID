---
external help file: ''
Module Name: Az.ConnectedNetwork
online version: https://docs.microsoft.com/powershell/module/az.connectednetwork/get-azconnectednetworkdeviceregistrationkey
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ConnectedNetwork/help/Get-AzConnectedNetworkDeviceRegistrationKey.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ConnectedNetwork/help/Get-AzConnectedNetworkDeviceRegistrationKey.md
ms.openlocfilehash: dfb888907755f36bf07764bf5e28f829c3a2eea8
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145498855"
---
# Get-AzConnectedNetworkDeviceRegistrationKey

## SYNOPSIS
Cantumkan kunci pendaftaran untuk perangkat.

## SYNTAX

```
Get-AzConnectedNetworkDeviceRegistrationKey -DeviceName <String> -ResourceGroupName <String>
 [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Cantumkan kunci pendaftaran untuk perangkat.

## EXAMPLES

### Contoh 1: Get-AzConnectedNetworkDeviceRegistrationKey menggunakan Grup Sumber Daya, Nama sumber daya
```powershell
PS C:\> Get-AzConnectedNetworkDeviceRegistrationKey -DeviceName myMecDevice -ResourceGroupName myResources

eyJNZWNEZXZpY2VUcmFuc2llbnRBdXRoS2V5IjoiMTIzNCIsIk1lY0RldmljZUF1dGhLZXlTdGFydFRpbWUiOiIyMDIxLTExLTIyVDA5OjQ2OjQwLjY0ODExOTFaIiwiU2VydmljZUJ1c1F1ZXVlTmFtZSI6ImFiY2QtMTIzNCIsIkFBREVuZHBvaW50IjpudWxsLCJBQURBdWRpZW5jZSI6bnVsbCwiQXJtUmVzb3VyY2VJZCI6bnVsbCwiTWVjQ29udHJvbGxlckVuZHBvaW50IjoiaHR0cHM6Ly93ZXN0Y2VudHJhbHVzLXByb2QubWVjZGV2aWNlLmF6dXJlLmNvbTo0NDMiLCJEYmVEZXZpY2VJZCI6bnVsbCwiUmVzb3VyY2VVbmlxdWVJZCI6IjEyMy1hYmMtMTIzIiwiU3Vic2NyaXB0aW9uSWQiOiJ4eHh4LTEyMzQteHh4eC0xMjM0IiwiUmVzb3VyY2VHcm91cE5hbWUiOiJzYW1wbGVSR25hbWUiLCJQcm92aWRlck5hbWVzcGFjZSI6Ik1pY3Jvc29mdC5IeWJyaWROZXR3b3JrIiwiUmVzb3VyY2VUeXBlIjoiRGV2aWNlcyIsIlJlc291cmNlVHlwZU5hbWUiOiJJREMtRGV2aWNlNC1XZXN0Q2VudHJhbCJ9
```

Mendapatkan kunci pendaftaran untuk perangkat NFM di grup sumber daya myResources dengan nama sumber daya myMecDevice.
Untuk mendaftarkan perangkat, gunakan commandlet Invoke-MecRegister dengan kunci pendaftaran di sesi minishell.

### Contoh 2: Get-AzConnectedNetworkDeviceRegistrationKey menggunakan Grup Sumber Daya, Nama sumber daya, dan Id Langganan
```powershell
PS C:\> Get-AzConnectedNetworkDeviceRegistrationKey -DeviceName myMecDevice -ResourceGroupName myResources -SubscriptionId xxxxx-00000-xxxxx-00000

eyJNZWNEZXZpY2VUcmFuc2llbnRBdXRoS2V5IjoiMTIzNCIsIk1lY0RldmljZUF1dGhLZXlTdGFydFRpbWUiOiIyMDIxLTExLTIyVDA5OjQ2OjQwLjY0ODExOTFaIiwiU2VydmljZUJ1c1F1ZXVlTmFtZSI6ImFiY2QtMTIzNCIsIkFBREVuZHBvaW50IjpudWxsLCJBQURBdWRpZW5jZSI6bnVsbCwiQXJtUmVzb3VyY2VJZCI6bnVsbCwiTWVjQ29udHJvbGxlckVuZHBvaW50IjoiaHR0cHM6Ly93ZXN0Y2VudHJhbHVzLXByb2QubWVjZGV2aWNlLmF6dXJlLmNvbTo0NDMiLCJEYmVEZXZpY2VJZCI6bnVsbCwiUmVzb3VyY2VVbmlxdWVJZCI6IjEyMy1hYmMtMTIzIiwiU3Vic2NyaXB0aW9uSWQiOiJ4eHh4LTEyMzQteHh4eC0xMjM0IiwiUmVzb3VyY2VHcm91cE5hbWUiOiJzYW1wbGVSR25hbWUiLCJQcm92aWRlck5hbWVzcGFjZSI6Ik1pY3Jvc29mdC5IeWJyaWROZXR3b3JrIiwiUmVzb3VyY2VUeXBlIjoiRGV2aWNlcyIsIlJlc291cmNlVHlwZU5hbWUiOiJJREMtRGV2aWNlNC1XZXN0Q2VudHJhbCJ9
```

Mendapatkan kunci pendaftaran untuk perangkat NFM di grup sumber daya myResources dengan nama sumber daya myMecDevice.
Untuk mendaftarkan perangkat, gunakan commandlet Invoke-MecRegister dengan kunci pendaftaran di sesi minishell.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases: AzureRMContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DeviceName
Nama sumber daya perangkat.

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

### -ResourceGroupName
Nama grup sumber daya.
Nama ini tidak peka huruf besar/kecil.

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

### -SubscriptionId
ID langganan target.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm
Meminta Anda mengonfirmasi sebelum menjalankan cmdlet.

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
Menunjukkan yang akan terjadi jika cmdlet dijalankan.
Cmdlet tidak dijalankan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

## OUTPUTS

### System.String

## NOTES

ALIAS

## RELATED LINKS

