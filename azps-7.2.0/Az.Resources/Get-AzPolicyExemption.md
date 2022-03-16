---
external help file: Microsoft.Azure.PowerShell.Cmdlets.ResourceManager.dll-Help.xml
Module Name: Az.Resources
online version: https://docs.microsoft.com/powershell/module/az.resources/get-azpolicyexemption
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Get-AzPolicyExemption.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Get-AzPolicyExemption.md
ms.openlocfilehash: a565ac42bafd6018565d067ed57341d4f9bf79d9
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140264693"
---
# Get-AzPolicyExemption

## SYNOPSIS
Mendapatkan pengecualian kebijakan.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan [lihat versi terbaru](/powershell/module/az.resources/get-azpolicyexemption) untuk informasi terkini.

## SYNTAX

### NameParameterSet (Default)
```
Get-AzPolicyExemption [-Name <String>] [-Scope <String>] [-PolicyAssignmentIdFilter <String>]
 [-ApiVersion <String>] [-Pre] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### IncludeDescendentParameterSet
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
Identifikasi pengecualian kebijakan untuk mendapatkan menurut nama dan lingkup atau menurut ID.

## EXAMPLES

### Contoh 1 Dapatkan semua pengecualian kebijakan
```powershell
PS C:\> Get-AzPolicyExemption
```

Perintah ini mendapatkan semua pengecualian kebijakan.

### Contoh 2: Mendapatkan pengecualian kebijakan tertentu
```
PS C:\> $ResourceGroup = Get-AzResourceGroup -Name 'ResourceGroup11'
PS C:\> Get-AzPolicyExemption -Name 'PolicyExemption07' -Scope $ResourceGroup.ResourceId
```

Perintah pertama mendapatkan grup sumber daya bernama ResourceGroup11 dengan menggunakan cmdlet Get-AzResourceGroup dan menyimpannya di $ResourceGroup sumber daya.
Perintah kedua mendapatkan pengecualian kebijakan bernama PolicyExemption07 untuk lingkup properti **ResourceId** yang akan $ResourceGroup identifikasi.

### Contoh 3: Mendapatkan semua pengecualian kebijakan yang terkait dengan penetapan kebijakan
```
PS C:\> $Assignment = Get-AzPolicyAssignment -Name 'PolicyAssignment07'
PS C:\> Get-AzPolicyExemption -PolicyAssignmentIdFilter $Assignment.ResourceId
```

Perintah pertama mendapatkan penetapan kebijakan bernama PolicyAssignment07.
Perintah kedua mendapatkan semua pengecualian kebijakan yang ditetapkan dengan penetapan kebijakan.

## PARAMETERS

### -ApiVersion
Saat diatur, menunjukkan versi API penyedia sumber daya yang akan digunakan.
Jika tidak ditentukan, versi API secara otomatis ditentukan sebagai versi terbaru yang tersedia.

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
ID pengecualian kebijakan yang sepenuhnya memenuhi syarat untuk mendapatkan, termasuk lingkup, misalnya /subscriptions/{subscriptionId}/resourcegroups/{resourceGroupName}/providers/Microsoft.Authorization/policyExemptions/{policyExemptionName}.

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
Menyebabkan daftar pengecualian kebijakan yang dikembalikan menyertakan semua pengecualian terkait dengan lingkup tertentu, termasuk yang dari lingkup dan yang dari lingkup turun.

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

### -Nama
Nama pengecualian kebijakan untuk mendapatkannya.

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
Limits the list of returned policy exemptions to those assigning the policy assignment identified by this fully qualified Id.

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

### -Pra
Saat diatur, cmdlet harus menggunakan versi API prari tamu ketika menentukan versi mana yang akan digunakan secara otomatis.

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

### -Lingkup
Cakupan pengecualian kebijakan untuk mendapatkan, misalnya /providers/managementGroups/{managementGroupName}, default untuk langganan saat ini.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### System.Management.Automation.SwitchParameter

## OUTPUTS

### Microsoft.Azure.Commands.ResourceManager.Cmdlets.Implementation.Policy.PsPolicyExemption

## CATATAN

## RELATED LINKS
