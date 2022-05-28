---
external help file: Microsoft.Azure.PowerShell.Cmdlets.LogicApp.dll-Help.xml
Module Name: Az.LogicApp
online version: https://docs.microsoft.com/powershell/module/az.logicapp/set-azintegrationaccountgeneratedicn
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/LogicApp/LogicApp/help/Set-AzIntegrationAccountGeneratedIcn.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/LogicApp/LogicApp/help/Set-AzIntegrationAccountGeneratedIcn.md
ms.openlocfilehash: bc8b2ce34e741d461d877063dfbeae4ed8ffc304
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145549187"
---
# Set-AzIntegrationAccountGeneratedIcn

## SYNOPSIS
Memperbarui akun integrasi yang dihasilkan nomor kontrol pertukaran (ICN) di grup sumber daya Azure.

## SYNTAX

```
Set-AzIntegrationAccountGeneratedIcn -ResourceGroupName <String> -Name <String> -AgreementName <String>
 -ControlNumber <String> [-AgreementType <String>] [-DefaultProfile <IAzureContextContainer>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet Set-AzIntegrationAccountGeneratedIcn memperbarui akun integrasi yang ada menghasilkan nomor kontrol pertukaran (ICN) dan mengembalikan objek yang mewakili nomor kontrol pertukaran yang dihasilkan akun integrasi.
Gunakan cmdlet ini untuk memperbarui akun integrasi yang dihasilkan nomor kontrol pertukaran.
Anda dapat memperbarui nomor kontrol pertukaran yang dihasilkan akun integrasi dengan menentukan nama akun integrasi, nama grup sumber daya, dan nama perjanjian.
Anda tidak dapat membuat akun integrasi baru yang dihasilkan nomor kontrol pertukaran dengan perintah ini.
Untuk menggunakan parameter dinamis, cukup ketikkan dalam perintah, atau ketik tanda hubung (-) untuk menunjukkan nama parameter lalu tekan tombol TAB berulang kali untuk menelusuri parameter yang tersedia.
Jika Anda melewatkan parameter templat yang diperlukan, cmdlet akan meminta nilainya.
Nilai file parameter templat yang Anda tentukan di baris perintah lebih diutamakan daripada nilai parameter templat dalam objek parameter templat.
Harap berikan parameter "-AgreementType" untuk menentukan apakah nomor kontrol X12 atau Edifact akan dikembalikan

## EXAMPLES

### Contoh 1
```powershell
$resourceGroup.ResourceGroupName = "ResourceGroup1"
$integrationAccountName = "IntegrationAccount1"
$integrationAccountAgreementName = "X12IntegrationAccountAgreement"
$initialControlNumber = Get-AzIntegrationAccountGeneratedIcn -AgreementType X12 -ResourceGroupName $resourceGroup.ResourceGroupName -Name $integrationAccountName -AgreementName $integrationAccountAgreementName
$incrementedControlNumberValue = [convert]::ToString([convert]::ToInt32($initialControlNumber.ControlNumber, 10) + 100, 10)
Set-AzIntegrationAccountGeneratedIcn -ResourceGroupName $resourceGroup.ResourceGroupName -Name $integrationAccountName -AgreementName $integrationAccountAgreementName -ControlNumber $incrementedControlNumberValue
```

```output
ControlNumber            : 1100
ControlNumberChangedTime : 2/15/2017 12:36:00 AM
IsMessageProcessingFailed:
```

Perintah ini mendapatkan nomor kontrol pertukaran X12 yang dihasilkan akun integrasi yang dihasilkan untuk perjanjian akun integrasi tertentu, meningkatkan nilainya sebesar 100 lalu menulis kembali nilai yang diperbarui.

### Contoh 2
```powershell
$resourceGroup.ResourceGroupName = "ResourceGroup1"
$integrationAccountName = "IntegrationAccount1"
$integrationAccountAgreementName = "EdifactIntegrationAccountAgreement"
$initialControlNumber = Get-AzIntegrationAccountGeneratedIcn -AgreementType EdifactIntegrationAccountAgreement -ResourceGroupName $resourceGroup.ResourceGroupName -Name $integrationAccountName -AgreementName $integrationAccountAgreementName
$incrementedControlNumberValue = [convert]::ToString([convert]::ToInt32($initialControlNumber.ControlNumber, 10) + 100, 10)
Set-AzIntegrationAccountGeneratedIcn -ResourceGroupName $resourceGroup.ResourceGroupName -Name $integrationAccountName -AgreementName $integrationAccountAgreementName -ControlNumber $incrementedControlNumberValue
```

```output
ControlNumber            : 1100
ControlNumberChangedTime : 2/15/2017 12:36:00 AM
IsMessageProcessingFailed:
```

Perintah ini mendapatkan akun integrasi yang dihasilkan EdifactIntegrationAccountAgreement nomor kontrol pertukaran untuk perjanjian akun integrasi tertentu, meningkatkan nilainya sebesar 100 lalu menulis kembali nilai yang diperbarui.

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
Jenis perjanjian akun integrasi.

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

### -ControlNumber
Nomor kontrol yang dihasilkan nilai baru.

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

[Get-AzIntegrationAccountGeneratedIcn](./Get-AzIntegrationAccountGeneratedIcn.md)

