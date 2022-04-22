---
external help file: Microsoft.Azure.Commands.ResourceManager.Cmdlets.dll-Help.xml
Module Name: AzureRM.Resources
ms.assetid: 2DBAF415-A039-479E-B3CA-E00FD5E476C9
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.resources/get-azurermpolicyassignment
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Resources/Commands.Resources/help/Get-AzureRmPolicyAssignment.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Resources/Commands.Resources/help/Get-AzureRmPolicyAssignment.md
ms.openlocfilehash: 71f3c6ab80fd0ba44d715cb25b4bf690e44359c7
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143046331"
---
# Get-AzureRmPolicyAssignment

## SYNOPSIS
Mendapatkan penetapan kebijakan.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### DefaultParameterSet (Default)
```
Get-AzureRmPolicyAssignment [-ApiVersion <String>] [-Pre] [-DefaultProfile <IAzureContextContainer>]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

### NameParameterSet
```
Get-AzureRmPolicyAssignment [-Name <String>] [-Scope <String>] [-PolicyDefinitionId <String>]
 [-ApiVersion <String>] [-Pre] [-DefaultProfile <IAzureContextContainer>]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

### SertakanDescendentParameterSet
```
Get-AzureRmPolicyAssignment [-Scope <String>] [-IncludeDescendent] [-ApiVersion <String>] [-Pre]
 [-DefaultProfile <IAzureContextContainer>] [-InformationAction <ActionPreference>]
 [-InformationVariable <String>] [<CommonParameters>]
```

### IdParameterSet
```
Get-AzureRmPolicyAssignment -Id <String> [-PolicyDefinitionId <String>] [-ApiVersion <String>] [-Pre]
 [-DefaultProfile <IAzureContextContainer>] [-InformationAction <ActionPreference>]
 [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureRmPolicyAssignment** mendapatkan semua penetapan kebijakan atau penugasan tertentu.
Identifikasi penetapan kebijakan untuk mendapatkan berdasarkan nama dan cakupan atau berdasarkan ID.

## EXAMPLES

### Contoh 1: Mendapatkan semua penetapan kebijakan
```
PS C:\> Get-AzureRmPolicyAssignment
```

Perintah ini mendapatkan semua penetapan kebijakan.

### Contoh 2: Mendapatkan penetapan kebijakan tertentu
```
PS C:\> $ResourceGroup = Get-AzureRmResourceGroup -Name 'ResourceGroup11'
PS C:\> Get-AzureRmPolicyAssignment -Name 'PolicyAssignment07' -Scope $ResourceGroup.ResourceId
```

Perintah pertama mendapatkan grup sumber daya bernama ResourceGroup11 dengan menggunakan cmdlet Get-AzureRMResourceGroup dan menyimpannya dalam variabel $ResourceGroup.
Perintah kedua mendapatkan penetapan kebijakan bernama PolicyAssignment07 untuk cakupan yang diidentifikasi properti **ResourceId** dari $ResourceGroup.

### Contoh 3: Mendapatkan semua penetapan kebijakan yang ditetapkan ke grup manajemen
```
PS C:\> $mgId = 'myManagementGroup'
PS C:\> Get-AzureRmPolicyAssignment -Scope '/providers/Microsoft.Management/managementgroups/$mgId'
```

Perintah pertama menentukan ID grup manajemen yang akan dikueri.
Perintah kedua mendapatkan semua penetapan kebijakan yang ditetapkan ke grup manajemen dengan ID 'myManagementGroup'.

## PARAMETERS

### -ApiVersion
Menentukan versi API penyedia sumber daya yang akan digunakan.
Jika Anda tidak menentukan versi, cmdlet ini menggunakan versi terbaru yang tersedia.

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

### -Id
Menentukan ID sumber daya yang sepenuhnya memenuhi syarat untuk penetapan kebijakan yang didapat cmdlet ini.

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
Menyebabkan daftar penetapan kebijakan yang dikembalikan menyertakan semua tugas yang terkait dengan cakupan yang diberikan, termasuk yang berasal dari cakupan leluhur dan yang berasal dari cakupan keturunan.

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

### -InformationAction
Menentukan bagaimana cmdlet ini merespons peristiwa informasi.
Nilai yang dapat diterima untuk parameter ini adalah:
- Lanjutkan
- Ignore
- Menanyakan
- Lanjutkan Diam-diam
- Hentikan
- Tangguhkan

```yaml
Type: System.Management.Automation.ActionPreference
Parameter Sets: (All)
Aliases: infa

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InformationVariable
Menentukan variabel informasi.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: iv

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Menentukan nama penetapan kebijakan yang didapat cmdlet ini.

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

### -PolicyDefinitionId
Menentukan ID definisi kebijakan dari penetapan kebijakan yang didapat cmdlet ini.

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
Menunjukkan bahwa cmdlet ini mempertimbangkan versi API pra-rilis ketika secara otomatis menentukan versi mana yang akan digunakan.

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
Menentukan cakupan di mana kebijakan diterapkan untuk penugasan yang didapat cmdlet ini.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[New-AzureRmPolicyAssignment](./New-AzureRmPolicyAssignment.md)

[Remove-AzureRmPolicyAssignment](./Remove-AzureRmPolicyAssignment.md)

[Set-AzureRmPolicyAssignment](./Set-AzureRmPolicyAssignment.md)


