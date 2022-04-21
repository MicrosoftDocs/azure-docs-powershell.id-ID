---
external help file: Microsoft.Azure.PowerShell.Cmdlets.LogicApp.dll-Help.xml
Module Name: Az.LogicApp
online version: https://docs.microsoft.com/powershell/module/az.logicapp/set-azintegrationaccountreceivedicn
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/LogicApp/LogicApp/help/Set-AzIntegrationAccountReceivedIcn.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/LogicApp/LogicApp/help/Set-AzIntegrationAccountReceivedIcn.md
ms.openlocfilehash: 6cf8821079b1c0660c606c08c3548bf1a5784821
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142701586"
---
# Set-AzIntegrationAccountReceivedIcn

## SYNOPSIS
Memperbarui akun integrasi yang diterima nomor kontrol pertukaran (ICN, Interchange Control Number) di grup sumber daya Azure.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.logicapp/set-azintegrationaccountreceivedicn) untuk informasi terbaru.

## SYNTAX

```
Set-AzIntegrationAccountReceivedIcn -ResourceGroupName <String> -Name <String> -AgreementName <String>
 -ControlNumberValue <String> -IsMessageProcessingFailed <Boolean> [-AgreementType <String>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet Set-AzIntegrationAccountGeneratedIcn memperbarui akun integrasi yang sudah ada yang diterima nomor kontrol pertukaran (ICN) dan mengembalikan objek yang mewakili akun integrasi yang diterima nomor kontrol pertukaran.
Gunakan cmdlet ini untuk memperbarui akun integrasi yang diterima status pemrosesan pesan nomor kontrol pertukaran.
Anda dapat memperbarui nomor kontrol pertukaran akun integrasi yang diterima dengan menentukan nama akun integrasi, nama grup sumber daya, nama perjanjian, nilai nomor kontrol, dan status pemrosesan pesan.
Anda tidak dapat membuat akun integrasi baru yang diterima bertukar nomor kontrol dengan perintah ini.
Untuk menggunakan parameter dinamis, cukup ketikkan parameter dalam perintah, atau ketik tanda hubung(-) untuk menunjukkan nama parameter lalu tekan tombol TAB berulang kali untuk menelusuri parameter yang tersedia.
Jika Anda melewatkan parameter templat yang diperlukan, cmdlet akan meminta nilainya.
Nilai file parameter templat yang Anda tentukan di baris perintah lebih diutamakan daripada nilai parameter templat dalam objek parameter templat.
Harap sediakan parameter "-AgreementType" untuk menentukan apakah nomor kontrol X12 atau Edifact akan dikembalikan

## EXAMPLES

### Contoh 1
```
PS C:\> Set-AzIntegrationAccountGeneratedIcn -AgreementType "X12" -ResourceGroupName "ResourceGroup1" -Name "IntegrationAccount1" -AgreementName "X12IntegrationAccountAgreement" -ControlNumber "123" -IsMessageProcessingFailed $true
ControlNumber             : 1100
ControlNumberChangedTime  : 2/15/2017 12:36:00 AM
IsMessageProcessingFailed : True
```

Perintah ini memperbarui akun integrasi yang diterima X12 nomor kontrol pertukaran untuk perjanjian akun integrasi tertentu dan nilai dengan status pemrosesan pesan gagal.

### Contoh 2
```
PS C:\> Set-AzIntegrationAccountGeneratedIcn -AgreementType "Edifact" -ResourceGroupName "ResourceGroup1" -Name "IntegrationAccount1" -AgreementName "EdifactIntegrationAccountAgreement" -ControlNumber "123" -IsMessageProcessingFailed $true
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
Meminta konfirmasi sebelum menjalankan cmdlet.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.LogicApp.Utilities.IntegrationAccountControlNumber

## NOTES

## RELATED LINKS

[Get-AzIntegrationAccountReceivedIcn](./Get-AzIntegrationAccountReceivedIcn.md)
 [Remove-AzIntegrationAccountReceivedIcn](./Remove-AzIntegrationAccountReceivedIcn.md)
