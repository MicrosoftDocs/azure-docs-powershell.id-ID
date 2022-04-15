---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
online version: https://docs.microsoft.com/en-us/powershell/module/az.network/get-AzApplicationGatewayBackendHttpSetting
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/Azs-tzl/src/Network/Network/help/Get-AzApplicationGatewayBackendHttpSetting.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/Azs-tzl/src/Network/Network/help/Get-AzApplicationGatewayBackendHttpSetting.md
ms.openlocfilehash: 96872aa399c3241710e12e3b96a14e8678f21d83
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142328183"
---
# Get-AzApplicationGatewayBackendHttpSetting

## SYNOPSIS
Mendapatkan pengaturan HTTP ujung-belakang gateway aplikasi.

## SYNTAX

```
Get-AzApplicationGatewayBackendHttpSetting [-Name <String>] -ApplicationGateway <PSApplicationGateway>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet Get-AzApplicationGatewayBackendHttpSetting mendapatkan pengaturan HTTP ujung-belakang gateway aplikasi.

## EXAMPLES

### Contoh 1: Dapatkan pengaturan HTTP ujung-belakang berdasarkan nama
```
PS C:\>$AppGw = Get-AzApplicationGateway -Name "ApplicationGateway01" -ResourceGroupName "ResourceGroup01"
PS C:\> $Settings  = Get-AzApplicationGatewayBackendHttpSetting -Name "Settings01" -ApplicationGateway $AppGw
```

Perintah pertama mendapatkan gateway aplikasi bernama ApplicationGateway01 dalam grup sumber daya bernama ResourceGroup01, dan menyimpannya dalam variabel $AppGw. Perintah kedua mendapatkan pengaturan HTTP bernama Pengaturan01 untuk $AppGw dan menyimpan pengaturan dalam variabel $Pengaturan.

### Contoh 2: Dapatkan kumpulan pengaturan HTTP ujung-belakang
```
PS C:\>$AppGw = Get-AzApplicationGateway -Name "ApplicationGateway01" -ResourceGroupName "ResourceGroup01"
PS C:\> $SettingsList  = Get-AzApplicationGatewayBackendHttpSetting -ApplicationGateway $AppGw
```

Perintah pertama mendapatkan gateway aplikasi bernama ApplicationGateway01 dalam grup sumber daya bernama ResourceGroup01, dan menyimpannya dalam variabel $AppGw. Perintah kedua mendapatkan kumpulan pengaturan HTTP untuk $AppGw dan menyimpan pengaturan dalam variabel $SettingsList.

## PARAMETERS

### -ApplicationGateway
Menentukan objek gateway aplikasi yang berisi pengaturan HTTP ujung-belakang.

```yaml
Type: PSApplicationGateway
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure.

```yaml
Type: IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Menentukan nama pengaturan http backend yang didapatkan cmdlet ini.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

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

### Microsoft.Azure.Commands.Network.Models.AzureApplicationGatewayBackendHttpSettings

## CATATAN

## RELATED LINKS

[Add-AzApplicationGatewayBackendHttpSetting]()

[New-AzApplicationGatewayBackendHttpSetting]()

[Remove-AzApplicationGatewayBackendHttpSetting]()

[Set-AzApplicationGatewayBackendHttpSetting]()

