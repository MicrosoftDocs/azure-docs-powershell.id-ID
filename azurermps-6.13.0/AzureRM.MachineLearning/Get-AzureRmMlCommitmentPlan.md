---
external help file: Microsoft.Azure.Commands.MachineLearning.dll-Help.xml
Module Name: AzureRM.MachineLearning
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.machinelearning/get-azurermmlcommitmentplan
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/MachineLearning/Commands.MachineLearning/help/Get-AzureRmMlCommitmentPlan.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/MachineLearning/Commands.MachineLearning/help/Get-AzureRmMlCommitmentPlan.md
ms.openlocfilehash: f0b081911d1bcd2a2b195d3185eb3b36505060c4
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142140040"
---
# Get-AzureRmMlCommitmentPlan

## SYNOPSIS
Mengambil informasi ringkasan untuk satu atau beberapa rencana komitmen.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Get-AzureRmMlCommitmentPlan [-ResourceGroupName <String>] [-Name <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Mengambil informasi rencana komitmen.
Tergantung pada paramenter yang lolos, cmdlet mengembalikan rencana komitmen tertentu, kumpulan rencana komitmen untuk grup sumber daya tertentu dalam langganan saat ini, atau kumpulan rencana komitmen dalam langganan saat ini.

## EXAMPLES

### Contoh 1: Dapatkan rencana komitmen tertentu
```
Get-AzureRmMlCommitmentPlan -ResourceGroupName "MyResourceGroup" -Name "MyCommitmentPlanName"
```

### Contoh 2: Dapatkan semua sumber daya rencana komitmen dalam langganan saat ini
```
Get-AzureRmMlCommitmentPlan
```

### Contoh 3: Dapatkan semua rencana komitmen dalam langganan saat ini dan grup sumber daya yang diberikan
```
Get-AzureRmMlCommitmentPlan -ResourceGroupName "MyResourceGroup"
```

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak

## OUTPUTS

### Microsoft.Azure.Management.MachineLearning.CommitmentPlans.Models.CommitmentPlan

## CATATAN
Kata kunci: azure, azurerm, lengan, sumber daya, manajemen, manajer, mesin, pembelajaran mesin, azureml

## RELATED LINKS
