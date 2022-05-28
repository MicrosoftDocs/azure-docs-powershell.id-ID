---
external help file: Microsoft.Azure.PowerShell.Cmdlets.LogicApp.dll-Help.xml
Module Name: Az.LogicApp
ms.assetid: 4813EE2B-16C4-4716-B6DD-9447A0B46F3D
online version: https://docs.microsoft.com/powershell/module/az.logicapp/get-azintegrationaccountcallbackurl
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/LogicApp/LogicApp/help/Get-AzIntegrationAccountCallbackUrl.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/LogicApp/LogicApp/help/Get-AzIntegrationAccountCallbackUrl.md
ms.openlocfilehash: c90da6d91e80233032cf7c41d6ee2bff15458bd9
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145528642"
---
# Get-AzIntegrationAccountCallbackUrl

## SYNOPSIS
Mendapatkan URL panggilan balik akun integrasi.

## SYNTAX

```
Get-AzIntegrationAccountCallbackUrl -ResourceGroupName <String> -Name <String> [-NotAfter <DateTime>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzIntegrationAccountCallbackUrl** mendapatkan URL panggilan balik akun integrasi dari grup sumber daya.
Cmdlet ini mengembalikan objek **CallbackUrl** yang mewakili URL panggilan balik akun integrasi.
Tentukan nama akun integrasi dan nama grup sumber daya.
Modul ini mendukung parameter dinamis.
Untuk menggunakan parameter dinamis, ketikkan dalam perintah .
Untuk menemukan nama parameter dinamis, ketik tanda hubung (-) setelah nama cmdlet, lalu tekan tombol Tab berulang kali untuk menelusuri parameter yang tersedia.
Jika Anda menghilangkan parameter templat yang diperlukan, cmdlet akan meminta nilainya.

## EXAMPLES

### Contoh 1: Mendapatkan URL panggilan balik akun integrasi
```powershell
Get-AzIntegrationAccountCallbackUrl -ResourceGroupName "ResourceGroup11" -Name "IntegrationAccount31" -NotAfter "03/25/2016 18:23:22"
```

```output
CallBackUrl : https://<baseurl>/integrationAccounts/8811f0155a364b5e9618ba28f7180601?api-version=2015-08-01-preview&se=2016-03
              -25T18%3A23%3A22.0000000Z&sp=%2F%2Fread&sv=1.0&sig=<value>
```

Perintah ini mendapatkan URL panggilan balik akun integrasi.

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

### -Name
Menentukan nama akun integrasi.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: IntegrationAccountName, ResourceName

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NotAfter
Menentukan tanggal kedaluwarsa untuk URL panggilan balik.

```yaml
Type: System.Nullable`1[System.DateTime]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Menentukan nama grup sumber daya.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Management.Logic.Models.CallbackUrl

## NOTES

## RELATED LINKS

[Get-AzLogicAppTriggerCallbackUrl](./Get-AzLogicAppTriggerCallbackUrl.md)


