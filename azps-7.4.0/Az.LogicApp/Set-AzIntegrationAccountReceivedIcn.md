---
external help file: Microsoft.Azure.PowerShell.Cmdlets.LogicApp.dll-Help.xml
Module Name: Az.LogicApp
online version: https://docs.microsoft.com/powershell/module/az.logicapp/set-azintegrationaccountreceivedicn
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/LogicApp/LogicApp/help/Set-AzIntegrationAccountReceivedIcn.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/LogicApp/LogicApp/help/Set-AzIntegrationAccountReceivedIcn.md
ms.openlocfilehash: e79b22fe53830e1ca014293ccca7e9f1099ced7d
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144690902"
---
# Set-AzIntegrationAccountReceivedIcn

## SYNOPSIS
Memperbarui akun integrasi yang menerima nomor kontrol pertukaran (ICN) di grup sumber daya Azure.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.logicapp/set-azintegrationaccountreceivedicn) untuk informasi terbaru.

## SYNTAX

```
Set-AzIntegrationAccountReceivedIcn -ResourceGroupName <String> -Name <String> -AgreementName <String>
 -ControlNumberValue <String> -IsMessageProcessingFailed <Boolean> [-AgreementType <String>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet Set-AzIntegrationAccountGeneratedIcn memperbarui akun integrasi yang ada yang menerima nomor kontrol pertukaran (ICN) dan mengembalikan objek yang mewakili akun integrasi yang menerima nomor kontrol pertukaran.
Gunakan cmdlet ini untuk memperbarui akun integrasi yang menerima status pemrosesan pesan nomor kontrol pertukaran.
Anda dapat memperbarui akun integrasi yang menerima nomor kontrol pertukaran dengan menentukan nama akun integrasi, nama grup sumber daya, nama perjanjian, nilai nomor kontrol, dan status pemrosesan pesan.
Anda tidak dapat membuat akun integrasi baru yang menerima nomor kontrol pertukaran dengan perintah ini.
Untuk menggunakan parameter dinamis, cukup ketikkan dalam perintah, atau ketik tanda hubung (-) untuk menunjukkan nama parameter lalu tekan tombol TAB berulang kali untuk menelusuri parameter yang tersedia.
Jika Anda melewatkan parameter templat yang diperlukan, cmdlet akan meminta nilainya.
Nilai file parameter templat yang Anda tentukan di baris perintah lebih diutamakan daripada nilai parameter templat dalam objek parameter templat.
Harap berikan parameter "-AgreementType" untuk menentukan apakah nomor kontrol X12 atau Edifact akan dikembalikan

## EXAMPLES

### Contoh 1
```powershell
Set-AzIntegrationAccountGeneratedIcn -AgreementType "X12" -ResourceGroupName "ResourceGroup1" -Name "IntegrationAccount1" -AgreementName "X12IntegrationAccountAgreement" -ControlNumber "123" -IsMessageProcessingFailed $true
```

```output
ControlNumber             : 1100
ControlNumberChangedTime  : 2/15/2017 12:36:00 AM
IsMessageProcessingFailed : True
```

Perintah ini memperbarui akun integrasi yang menerima nomor kontrol pertukaran X12 untuk perjanjian dan nilai akun integrasi tertentu dengan status pemrosesan pesan gagal.

### Contoh 2
```powershell
Set-AzIntegrationAccountGeneratedIcn -AgreementType "Edifact" -ResourceGroupName "ResourceGroup1" -Name "IntegrationAccount1" -AgreementName "EdifactIntegrationAccountAgreement" -ControlNumber "123" -IsMessageProcessingFailed $true
```

```output
ControlNumber             : 1100
ControlNumberChangedTime  : 2/15/2017 12:36:00 AM
IsMessageProcessingFailed : True
```

Perintah ini memperbarui akun integrasi yang menerima nomor kontrol pertukaran Edifact untuk perjanjian dan nilai akun integrasi tertentu dengan status pemrosesan pesan gagal.

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
Jenis perjanjian akun integrasi (X12 atau Edifact).

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

### -Name
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

### -Confirm
Meminta Anda mengonfirmasi sebelum menjalankan cmdlet.

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
Menunjukkan yang akan terjadi jika cmdlet dijalankan.
Cmdlet tidak dijalankan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.LogicApp.Utilities.IntegrationAccountControlNumber

## NOTES

## RELATED LINKS

[Get-AzIntegrationAccountReceivedIcn](./Get-AzIntegrationAccountReceivedIcn.md)
 [Remove-AzIntegrationAccountReceivedIcn](./Remove-AzIntegrationAccountReceivedIcn.md)
