---
external help file: Microsoft.Azure.PowerShell.Cmdlets.ResourceManager.dll-Help.xml
Module Name: Az.Resources
online version: https://docs.microsoft.com/powershell/module/az.resources/remove-azpolicyexemption
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Remove-AzPolicyExemption.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Remove-AzPolicyExemption.md
ms.openlocfilehash: be185869052a7d5285673ad2c84b4d7670fa168f
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143309465"
---
# Remove-AzPolicyExemption

## SYNOPSIS
Menghapus pengecualian kebijakan.

## SYNTAX

### NameParameterSet (Default)
```
Remove-AzPolicyExemption -Name <String> [-Scope <String>] [-Force] [-ApiVersion <String>] [-Pre]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### IdParameterSet
```
Remove-AzPolicyExemption -Id <String> [-Force] [-ApiVersion <String>] [-Pre]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObjectParameterSet
```
Remove-AzPolicyExemption [-Force] -InputObject <PsPolicyExemption> [-ApiVersion <String>] [-Pre]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Remove-AzPolicyExemption** menghapus pengecualian kebijakan yang ditentukan.

## EXAMPLES

### Contoh 1: Hapus pembebasan kebijakan menurut nama dan lingkup
```powershell
$ResourceGroup = Get-AzResourceGroup -Name 'ResourceGroup11'
Remove-AzPolicyExemption -Name 'PolicyExemption07' -Scope $ResourceGroup.ResourceId -Confirm
```

Perintah pertama mendapatkan grup sumber daya bernama ResourceGroup11 menggunakan cmdlet Get-AzResourceGroup.
Perintah menyimpan objek tersebut dalam variabel $ResourceGroup.
Perintah kedua menghapus pengecualian kebijakan bernama PolicyExemption07 yang ditetapkan pada tingkat grup sumber daya.
Properti **ResourceId** $ResourceGroup mengidentifikasi grup sumber daya.

### Contoh 2: Hapus pembebasan kebijakan menurut ID
```powershell
$ResourceGroup = Get-AzResourceGroup -Name 'ResourceGroup11' 
$PolicyExemption = Get-AzPolicyExemption -Name 'PolicyExemption07' -Scope $ResourceGroup.ResourceId
Remove-AzPolicyExemption -Id $PolicyExemption.ResourceId -Confirm
```

Perintah pertama mendapatkan grup sumber daya bernama ResourceGroup11, lalu menyimpan objek tersebut dalam variabel $ResourceGroup.
Perintah kedua mendapatkan pembebasan kebijakan pada tingkat grup sumber daya, lalu menyimpannya dalam variabel $PolicyExemption.
Properti **ResourceId** $ResourceGroup mengidentifikasi grup sumber daya.
Perintah akhir menghapus pengecualian kebijakan yang diidentifikasi properti **ResourceId** $PolicyExemption.

## PARAMETERS

### -ApiVersion
Ketika diatur, menunjukkan versi API penyedia sumber daya yang akan digunakan.
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

### -Paksa
Jangan meminta konfirmasi.

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

### -Id
ID pembebasan kebijakan yang sepenuhnya memenuhi syarat untuk dihapus, termasuk lingkup, misalnya /subscriptions/{subscriptionId}/resourcegroups/{resourceGroupName}/providers/Microsoft.Authorization/policyExemptions/{policyExemptionName}.

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

### -InputObject
Objek pembebasan kebijakan untuk menghapus yang merupakan output dari cmdlet lain.

```yaml
Type: Microsoft.Azure.Commands.ResourceManager.Cmdlets.Implementation.Policy.PsPolicyExemption
Parameter Sets: InputObjectParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Nama
Nama pengecualian kebijakan untuk dihapus.

```yaml
Type: System.String
Parameter Sets: NameParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Pra
Ketika diatur, menunjukkan bahwa cmdlet harus menggunakan versi API prarilis saat menentukan versi mana yang akan digunakan secara otomatis.

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
Lingkup pengecualian kebijakan untuk menghapus, misalnya /providers/managementGroups/{managementGroupName}, default untuk langganan saat ini.

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

### -Konfirmasi
Meminta konfirmasi sebelum menjalankan cmdlet.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### Microsoft.Azure.Commands.ResourceManager.Cmdlets.Implementation.Policy.PsPolicyExemption

## OUTPUTS

### System.Boolean

## NOTES

## RELATED LINKS
