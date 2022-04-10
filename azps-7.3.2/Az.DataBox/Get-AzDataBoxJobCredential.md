---
external help file: ''
Module Name: Az.DataBox
online version: https://docs.microsoft.com/powershell/module/az.databox/get-azdataboxjobcredential
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataBox/help/Get-AzDataBoxJobCredential.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataBox/help/Get-AzDataBoxJobCredential.md
ms.openlocfilehash: d8217f8989e59ff1334ffbe29c2c697bf8c6bd27
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140556989"
---
# Get-AzDataBoxJobCredential

## SYNOPSIS
Metode ini rahasia yang belum dienkripsi terkait dengan pekerjaan.

## SYNTAX

```
Get-AzDataBoxJobCredential -Name <String> -ResourceGroupName <String> [-SubscriptionId <String[]>]
 [-DefaultProfile <PSObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Metode ini rahasia yang belum dienkripsi terkait dengan pekerjaan.

## EXAMPLES

### Contoh 1: Dapatkan kotak dataHeavy kredensial pekerjaan
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

Mendapatkan kotak dataHeavy kredensial pekerjaan

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

### -Nama
Nama Sumber Daya pekerjaan di dalam grup sumber daya yang ditentukan.
nama kerja harus panjang antara 3 dan 24 karakter dan gunakan alfanumerik dan garis bawah saja

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

### -Konfirmasi
Meminta konfirmasi Anda sebelum menjalankan cmdlet.

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
Cmdlet tidak berjalan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.DataBox.Models.Api20210301.IUnencryptedCredentials

## CATATAN

ALIAS

## RELATED LINKS

