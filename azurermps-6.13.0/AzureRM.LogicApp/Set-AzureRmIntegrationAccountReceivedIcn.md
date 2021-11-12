---
external help file: Microsoft.Azure.Commands.LogicApp.dll-Help.xml
Module Name: AzureRM.LogicApp
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.logicapp/set-azurermintegrationaccountreceivedicn
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/LogicApp/Commands.LogicApp/help/Set-AzureRmIntegrationAccountReceivedIcn.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/LogicApp/Commands.LogicApp/help/Set-AzureRmIntegrationAccountReceivedIcn.md
ms.openlocfilehash: e451e129265aa802b85e9d904137fc2350fb2c315ce5628560a09d3163312e5b
ms.sourcegitcommit: 49f8ffe5d8e08ba3d22e3b2e76db0e54dd55d4f0
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/11/2021
ms.locfileid: "132418555"
---
# Set-AzureRmIntegrationAccountReceivedIcn

## SYNOPSIS
Memperbarui akun integrasi yang diterima nomor kontrol pertukaran (ICN, Interchange Control Number) dalam grup sumber daya Azure.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Set-AzureRmIntegrationAccountReceivedIcn -ResourceGroupName <String> -Name <String> -AgreementName <String>
 -ControlNumberValue <String> -IsMessageProcessingFailed <Boolean> [-AgreementType <String>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet Set-AzureRmIntegrationAccountGeneratedIcn memperbarui akun integrasi yang sudah ada yang diterima nomor kontrol pertukaran (ICN, Interchange Control Number) dan mengembalikan objek yang mewakili akun integrasi yang diterima nomor kontrol pertukaran.
Gunakan cmdlet ini untuk memperbarui akun integrasi yang diterima status pemrosesan pesan nomor kontrol pertukaran.
Anda bisa memperbarui akun integrasi yang diterima nomor kontrol pertukaran dengan menentukan nama akun integrasi, nama grup sumber daya, nama perjanjian, nilai angka kontrol dan status pemrosesan pesan.
Anda tidak bisa membuat akun integrasi baru yang diterima nomor kontrol pertukaran dengan perintah ini.
Untuk menggunakan parameter dinamis, cukup ketikkan parameter dinamis dalam perintah, atau ketikkan tanda hubung(-) untuk menunjukkan nama parameter, lalu tekan tombol TAB berulang kali untuk melihat parameter yang tersedia.
Jika Anda melewatkan parameter templat yang diperlukan, cmdlet akan meminta nilai tersebut.
Nilai file parameter templat yang Anda tentukan di baris perintah diutamakan lebih dari nilai parameter templat dalam objek parameter templat.
Harap sediakan parameter "-AgreementType" untuk menentukan apakah angka kontrol X12 atau Edifact akan dikembalikan

## EXAMPLES

### Contoh 1
```
PS C:\> Set-AzureRmIntegrationAccountGeneratedIcn -AgreementType "X12" -ResourceGroupName "ResourceGroup1" -Name "IntegrationAccount1" -AgreementName "X12IntegrationAccountAgreement" -ControlNumber "123" -IsMessageProcessingFailed $true
ControlNumber             : 1100
ControlNumberChangedTime  : 2/15/2017 12:36:00 AM
IsMessageProcessingFailed : True
```

Perintah ini memperbarui akun integrasi yang diterima nomor kontrol pertukaran X12 untuk perjanjian akun integrasi tertentu dan nilai dengan status pemrosesan pesan gagal.

### Contoh 2
```
PS C:\> Set-AzureRmIntegrationAccountGeneratedIcn -AgreementType "Edifact" -ResourceGroupName "ResourceGroup1" -Name "IntegrationAccount1" -AgreementName "EdifactIntegrationAccountAgreement" -ControlNumber "123" -IsMessageProcessingFailed $true
ControlNumber             : 1100
ControlNumberChangedTime  : 2/15/2017 12:36:00 AM
IsMessageProcessingFailed : True
```

Perintah ini memperbarui akun integrasi yang diterima nomor kontrol pertukaran Edifact untuk perjanjian akun integrasi tertentu dan nilai dengan status pemrosesan pesan gagal.

## PARAMETERS

### -AgreementName
Nama perjanjian akun integrasi.

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

### -AgreementType
Tipe perjanjian akun integrasi (X12 atau Edifact).

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: MessageType
Accepted values: X12, Edifact

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ControlNumberValue
Nilai nomor kontrol akun integrasi.

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

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure

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

### -IsMessageProcessingFailed
Status pemrosesan pesan yang diterima.

```yaml
Type: System.Boolean
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Nama akun integrasi.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: ResourceName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya akun integrasi.

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

### -Konfirmasi
Meminta konfirmasi Anda sebelum menjalankan cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan.
Cmdlet tidak berjalan.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.LogicApp.Utilities.IntegrationAccountControlNumber

## CATATAN

## RELATED LINKS

[Get-AzureRmIntegrationAccountReceivedIcn](./Get-AzureRmIntegrationAccountReceivedIcn.md) 
 [Remove-AzureRmIntegrationAccountReceivedIcn](./Remove-AzureRmIntegrationAccountReceivedIcn.md)
