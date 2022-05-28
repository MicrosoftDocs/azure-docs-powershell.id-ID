---
external help file: Microsoft.Azure.PowerShell.Cmdlets.ResourceManager.dll-Help.xml
Module Name: Az.Resources
online version: https://docs.microsoft.com/powershell/module/az.resources/get-azpolicyexemption
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Get-AzPolicyExemption.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Get-AzPolicyExemption.md
ms.openlocfilehash: fb68d5a8e3fd829a307d8c58b522ef619b732d65
ms.sourcegitcommit: 82b4008b76d035e4aee733727371765b0d853bed
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145642922"
---
# Get-AzPolicyExemption

## SYNOPSIS
Mendapatkan pengecualian kebijakan.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.resources/get-azpolicyexemption) untuk informasi terbaru.

## SYNTAX

### NameParameterSet (Default)
```
Get-AzPolicyExemption [-Name <String>] [-Scope <String>] [-PolicyAssignmentIdFilter <String>]
 [-ApiVersion <String>] [-Pre] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### SertakanDescendentParameterSet
```
Get-AzPolicyExemption [-Scope <String>] [-IncludeDescendent] [-ApiVersion <String>] [-Pre]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### IdParameterSet
```
Get-AzPolicyExemption -Id <String> [-PolicyAssignmentIdFilter <String>] [-ApiVersion <String>] [-Pre]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzPolicyExemption** mendapatkan semua pengecualian kebijakan atau pengecualian tertentu.
Identifikasi pengecualian kebijakan untuk mendapatkan berdasarkan nama dan cakupan atau berdasarkan ID.

## EXAMPLES

### Contoh 1 Dapatkan semua pengecualian kebijakan
```powershell
Get-AzPolicyExemption
```

Perintah ini mendapatkan semua pengecualian kebijakan.

### Contoh 2: Mendapatkan pengecualian kebijakan tertentu
```powershell
$ResourceGroup = Get-AzResourceGroup -Name 'ResourceGroup11'
Get-AzPolicyExemption -Name 'PolicyExemption07' -Scope $ResourceGroup.ResourceId
```

Perintah pertama mendapatkan grup sumber daya bernama ResourceGroup11 dengan menggunakan cmdlet Get-AzResourceGroup dan menyimpannya dalam variabel $ResourceGroup.
Perintah kedua mendapatkan pengecualian kebijakan bernama PolicyExemption07 untuk cakupan yang diidentifikasi properti **ResourceId** dari $ResourceGroup.

### Contoh 3: Mendapatkan semua pengecualian kebijakan yang terkait dengan penetapan kebijakan
```powershell
$Assignment = Get-AzPolicyAssignment -Name 'PolicyAssignment07'
Get-AzPolicyExemption -PolicyAssignmentIdFilter $Assignment.ResourceId
```

Perintah pertama mendapatkan penetapan kebijakan bernama PolicyAssignment07.
Perintah kedua mendapatkan semua pengecualian kebijakan yang ditetapkan dengan penetapan kebijakan.

## PARAMETERS

### -ApiVersion
Saat diatur, menunjukkan versi API penyedia sumber daya yang akan digunakan.
Jika tidak ditentukan, versi API secara otomatis ditentukan sebagai yang terbaru yang tersedia.

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

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

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

### -Id
ID pengecualian kebijakan yang sepenuhnya memenuhi syarat untuk mendapatkan, termasuk cakupan, misalnya /subscriptions/{subscriptionId}/resourcegroups/{resourceGroupName}/providers/Microsoft.Authorization/policyExemptions/{policyExemptionName}.

```yaml
Type: System.String
Parameter Sets: IdParameterSet
Aliases: ResourceId

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IncludeDescendent
Menyebabkan daftar pengecualian kebijakan yang dikembalikan menyertakan semua pengecualian yang terkait dengan cakupan yang diberikan, termasuk yang berasal dari cakupan leluhur dan yang berasal dari cakupan keturunan.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: IncludeDescendentParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Nama pengecualian kebijakan yang akan didapatkan.

```yaml
Type: System.String
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PolicyAssignmentIdFilter
Membatasi daftar pengecualian kebijakan yang dikembalikan kepada mereka yang menetapkan penetapan kebijakan yang diidentifikasi oleh Id yang sepenuhnya memenuhi syarat ini.

```yaml
Type: System.String
Parameter Sets: NameParameterSet, IdParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Pre
Ketika diatur, menunjukkan bahwa cmdlet harus menggunakan versi API pra-rilis saat secara otomatis menentukan versi mana yang akan digunakan.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Cakupan
Cakupan pengecualian kebijakan untuk mendapatkan, misalnya /providers/managementGroups/{managementGroupName}, default ke langganan saat ini.

```yaml
Type: System.String
Parameter Sets: NameParameterSet, IncludeDescendentParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### System.String

### System.Management.Automation.SwitchParameter

## OUTPUTS

### Microsoft.Azure.Commands.ResourceManager.Cmdlets.Implementation.Policy.PsPolicyExemption

## NOTES

## RELATED LINKS
