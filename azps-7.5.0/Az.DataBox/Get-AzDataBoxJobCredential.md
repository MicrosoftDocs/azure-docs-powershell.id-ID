---
external help file: ''
Module Name: Az.DataBox
online version: https://docs.microsoft.com/powershell/module/az.databox/get-azdataboxjobcredential
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataBox/help/Get-AzDataBoxJobCredential.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataBox/help/Get-AzDataBoxJobCredential.md
ms.openlocfilehash: d8217f8989e59ff1334ffbe29c2c697bf8c6bd27
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144205163"
---
# Get-AzDataBoxJobCredential

## SYNOPSIS
Metode ini mendapatkan rahasia yang tidak terenkripsi yang terkait dengan pekerjaan.

## SYNTAX

```
Get-AzDataBoxJobCredential -Name <String> -ResourceGroupName <String> [-SubscriptionId <String[]>]
 [-DefaultProfile <PSObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Metode ini mendapatkan rahasia yang tidak terenkripsi yang terkait dengan pekerjaan.

## EXAMPLES

### Contoh 1: Mendapatkan kredensial pekerjaan databoxHeavy
```powershell
Get-AzDataBoxJobCredential -Name "DtbxPowershell" -ResourceGroupName "resourceGroupName"

$obj = Get-AzDataBoxJobCredential -Name TJy-637522091284252285 -ResourceGroupName bvttoolrg12-Wednesday
$obj | Format-List

AdditionalInfo                          :
Code                                    :
DcAccessSecurityCodeForwardDcAccessCode :
DcAccessSecurityCodeReverseDcAccessCode :
Detail                                  :
JobName                                 : DtbxPowershell
JobSecret                               : Microsoft.Azure.PowerShell.Cmdlets.DataBox.Models.Api20210301.DataBoxHeavyJobSecrets
JobSecretJobSecretsType                 : DataBoxHeavy
Message                                 :
Target                                  :


$obj.JobSecret | Format-List

AdditionalInfo                          :
CabinetPodSecret                        : {, }
Code                                    :
DcAccessSecurityCode                    : Microsoft.Azure.PowerShell.Cmdlets.DataBox.Models.Api20210301.DcAccessSecurityCode
DcAccessSecurityCodeForwardDcAccessCode :
DcAccessSecurityCodeReverseDcAccessCode :
Detail                                  :
Error                                   : Microsoft.Azure.PowerShell.Cmdlets.DataBox.Models.Api20210301.CloudError
Message                                 :
Target                                  :
Type                                    : DataBoxHeavy

$cabinetJobSecret = $obj.JobSecret.CabinetPodSecret | Format-List
```

Mendapatkan kredensial pekerjaan databoxHeavy

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

### -Name
Nama sumber daya pekerjaan dalam grup sumber daya yang ditentukan.
panjang nama pekerjaan harus antara 3 dan 24 karakter dan hanya menggunakan alfanumerik dan garis bawah

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
Nama Grup Sumber Daya

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
Id Langganan

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

### Microsoft.Azure.PowerShell.Cmdlets.DataBox.Models.Api20210301.IUnencryptedCredentials

## NOTES

ALIAS

## RELATED LINKS

