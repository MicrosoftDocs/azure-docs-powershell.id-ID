---
external help file: Microsoft.Azure.PowerShell.Cmdlets.MachineLearning.dll-Help.xml
Module Name: Az.MachineLearning
online version: https://docs.microsoft.com/powershell/module/az.machinelearning/get-azmlcommitmentplan
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/MachineLearning/MachineLearning/help/Get-AzMlCommitmentPlan.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/MachineLearning/MachineLearning/help/Get-AzMlCommitmentPlan.md
ms.openlocfilehash: 0625615618658f8acab6fa8c5c0ca3336b0af4ee
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142067755"
---
# Get-AzMlCommitmentPlan

## SYNOPSIS
Mengambil informasi ringkasan untuk satu atau beberapa rencana komitmen.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.machinelearning/get-azmlcommitmentplan) untuk informasi terbaru.

## SYNTAX

```
Get-AzMlCommitmentPlan [-ResourceGroupName <String>] [-Name <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Mengambil informasi rencana komitmen.
Tergantung pada parameter yang dilewati, cmdlet mengembalikan rencana komitmen tertentu, kumpulan rencana komitmen untuk grup sumber daya tertentu dalam langganan saat ini, atau kumpulan rencana komitmen dalam langganan saat ini.

## EXAMPLES

### Contoh 1: Dapatkan rencana komitmen tertentu
```
Get-AzMlCommitmentPlan -ResourceGroupName "MyResourceGroup" -Name "MyCommitmentPlanName"
```

### Contoh 2: Dapatkan semua sumber daya rencana komitmen dalam langganan saat ini
```
Get-AzMlCommitmentPlan
```

### Contoh 3: Dapatkan semua rencana komitmen dalam langganan saat ini dan grup sumber daya yang diberikan
```
Get-AzMlCommitmentPlan -ResourceGroupName "MyResourceGroup"
```

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

### -Nama
Nama rencana komitmen.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya untuk rencana komitmen Azure ML.

```yaml
Type: System.String
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

### Tidak

## OUTPUTS

### Microsoft.Azure.Management.MachineLearning.CommitmentPlans.Models.CommitmentPlan

## CATATAN
Kata kunci: azure, azurerm, lengan, sumber daya, manajemen, manajer, mesin, pembelajaran mesin, azureml

## RELATED LINKS
