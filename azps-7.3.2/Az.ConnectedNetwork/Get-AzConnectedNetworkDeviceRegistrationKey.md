---
external help file: ''
Module Name: Az.ConnectedNetwork
online version: https://docs.microsoft.com/powershell/module/az.connectednetwork/get-azconnectednetworkdeviceregistrationkey
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ConnectedNetwork/help/Get-AzConnectedNetworkDeviceRegistrationKey.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ConnectedNetwork/help/Get-AzConnectedNetworkDeviceRegistrationKey.md
ms.openlocfilehash: fab0e978cb069d1dc622adddd6c88c63edd4ed0b
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142036289"
---
# Get-AzConnectedNetworkDeviceRegistrationKey

## SYNOPSIS
Cantumkan kunci registrasi untuk perangkat.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.connectednetwork/get-azconnectednetworkdeviceregistrationkey) untuk informasi terbaru.

## SYNTAX

```
Get-AzConnectedNetworkDeviceRegistrationKey -DeviceName <String> -ResourceGroupName <String>
 [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Cantumkan kunci registrasi untuk perangkat.

## EXAMPLES

### Contoh 1: Get-AzConnectedNetworkDeviceRegistrationKey menggunakan Grup Sumber Daya, Nama sumber daya
```powershell
PS C:\> Get-AzConnectedNetworkDeviceRegistrationKey -DeviceName myMecDevice -ResourceGroupName myResources

eyJNZWNEZXZpY2VUcmFuc2llbnRBdXRoS2V5IjoiMTIzNCIsIk1lY0RldmljZUF1dGhLZXlTdGFydFRpbWUiOiIyMDIxLTExLTIyVDA5OjQ2OjQwLjY0ODExOTFaIiwiU2VydmljZUJ1c1F1ZXVlTmFtZSI6ImFiY2QtMTIzNCIsIkFBREVuZHBvaW50IjpudWxsLCJBQURBdWRpZW5jZSI6bnVsbCwiQXJtUmVzb3VyY2VJZCI6bnVsbCwiTWVjQ29udHJvbGxlckVuZHBvaW50IjoiaHR0cHM6Ly93ZXN0Y2VudHJhbHVzLXByb2QubWVjZGV2aWNlLmF6dXJlLmNvbTo0NDMiLCJEYmVEZXZpY2VJZCI6bnVsbCwiUmVzb3VyY2VVbmlxdWVJZCI6IjEyMy1hYmMtMTIzIiwiU3Vic2NyaXB0aW9uSWQiOiJ4eHh4LTEyMzQteHh4eC0xMjM0IiwiUmVzb3VyY2VHcm91cE5hbWUiOiJzYW1wbGVSR25hbWUiLCJQcm92aWRlck5hbWVzcGFjZSI6Ik1pY3Jvc29mdC5IeWJyaWROZXR3b3JrIiwiUmVzb3VyY2VUeXBlIjoiRGV2aWNlcyIsIlJlc291cmNlVHlwZU5hbWUiOiJJREMtRGV2aWNlNC1XZXN0Q2VudHJhbCJ9
```

Mendapatkan kunci pendaftaran untuk perangkat NFM dalam grup sumber daya myResources dengan nama sumber daya myMecDevice.
Untuk mendaftarkan perangkat, gunakan commandlet Invoke-MecRegister dengan kunci pendaftaran dalam sesi minishell.

### Contoh 2: Get-AzConnectedNetworkDeviceRegistrationKey menggunakan Grup Sumber Daya, Nama sumber daya dan Id Langganan
```powershell
PS C:\> Get-AzConnectedNetworkDeviceRegistrationKey -DeviceName myMecDevice -ResourceGroupName myResources -SubscriptionId xxxxx-00000-xxxxx-00000

eyJNZWNEZXZpY2VUcmFuc2llbnRBdXRoS2V5IjoiMTIzNCIsIk1lY0RldmljZUF1dGhLZXlTdGFydFRpbWUiOiIyMDIxLTExLTIyVDA5OjQ2OjQwLjY0ODExOTFaIiwiU2VydmljZUJ1c1F1ZXVlTmFtZSI6ImFiY2QtMTIzNCIsIkFBREVuZHBvaW50IjpudWxsLCJBQURBdWRpZW5jZSI6bnVsbCwiQXJtUmVzb3VyY2VJZCI6bnVsbCwiTWVjQ29udHJvbGxlckVuZHBvaW50IjoiaHR0cHM6Ly93ZXN0Y2VudHJhbHVzLXByb2QubWVjZGV2aWNlLmF6dXJlLmNvbTo0NDMiLCJEYmVEZXZpY2VJZCI6bnVsbCwiUmVzb3VyY2VVbmlxdWVJZCI6IjEyMy1hYmMtMTIzIiwiU3Vic2NyaXB0aW9uSWQiOiJ4eHh4LTEyMzQteHh4eC0xMjM0IiwiUmVzb3VyY2VHcm91cE5hbWUiOiJzYW1wbGVSR25hbWUiLCJQcm92aWRlck5hbWVzcGFjZSI6Ik1pY3Jvc29mdC5IeWJyaWROZXR3b3JrIiwiUmVzb3VyY2VUeXBlIjoiRGV2aWNlcyIsIlJlc291cmNlVHlwZU5hbWUiOiJJREMtRGV2aWNlNC1XZXN0Q2VudHJhbCJ9
```

Mendapatkan kunci pendaftaran untuk perangkat NFM dalam grup sumber daya myResources dengan nama sumber daya myMecDevice.
Untuk mendaftarkan perangkat, gunakan commandlet Invoke-MecRegister dengan kunci pendaftaran dalam sesi minishell.

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
Nama ini tidak peka huruf besar kecil.

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

### -Konfirmasi
Meminta konfirmasi sebelum menjalankan cmdlet.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### System.String

## CATATAN

ALIAS

## RELATED LINKS

