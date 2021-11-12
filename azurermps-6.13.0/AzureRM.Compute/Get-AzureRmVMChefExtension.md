---
external help file: Microsoft.Azure.Commands.Compute.dll-Help.xml
Module Name: AzureRM.Compute
ms.assetid: F41953F1-9515-4081-8624-6A1494DA4BB2
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.compute/get-azurermvmchefextension
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Compute/Commands.Compute/help/Get-AzureRmVMChefExtension.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Compute/Commands.Compute/help/Get-AzureRmVMChefExtension.md
ms.openlocfilehash: 29d30bc039f826f4c2d56fde15286695187aabb5
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132426325"
---
# Get-AzureRmVMChefExtension

## SYNOPSIS
Mendapatkan informasi tentang ekstensi Chef.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### Linux
```
Get-AzureRmVMChefExtension [-ResourceGroupName] <String> [-VMName] <String> [[-Name] <String>] [-Status]
 [-Linux] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### Windows
```
Get-AzureRmVMChefExtension [-ResourceGroupName] <String> [-VMName] <String> [[-Name] <String>] [-Status]
 [-Windows] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureVMChefExtension** mendapatkan informasi tentang ekstensi Chef yang diinstal di komputer virtual.

## EXAMPLES

### Contoh 1: Dapatkan detail ekstensi Chef untuk Windows virtual gratis
```
PS C:\> Get-AzureRmVMChefExtension -ResourceGroupName "ResourceGroup001" -VMName "WindowsVM001" -Windows
```

Perintah ini mendapatkan ekstensi Chef dari komputer virtual Windows bernama WindowsVM001 yang dimiliki grup sumber daya bernama ResourceGroup001.

### Contoh 2: Dapatkan detail ekstensi Chef untuk mesin virtual Linux
```
PS C:\> Get-AzureRmVMChefExtension -ResourceGroupName "ResourceGroup002" -VMName "LinuxVM001" -Linux
```

Perintah ini mendapatkan ekstensi Chef dari mesin virtual Linux bernama LinuxVM001 yang dimiliki oleh grup sumber daya yang bernama ResourceGroup002.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

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

### -Linux
Menunjukkan bahwa cmdlet ini bekerja di komputer virtual Linux.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Linux
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Menentukan nama ekstensi Chef.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: ExtensionName

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Menentukan nama grup sumber daya yang berisi komputer virtual.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Status
Menunjukkan bahwa cmdlet ini hanya mendapatkan tampilan contoh ekstensi Chef.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VMName
Menentukan nama mesin virtual.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: ResourceName

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Windows
Menunjukkan bahwa cmdlet ini adalah untuk komputer virtual Windows komputer virtual.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Windows
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### System.String

### System.Management.Automation.SwitchParameter

## OUTPUTS

### Microsoft.Azure.Commands.Compute.Models.PSVirtualMachineExtension

## CATATAN

## RELATED LINKS

[Set-AzureRmVMChefExtension](./Set-AzureRmVMChefExtension.md)

[Remove-AzureRmVMChefExtension](./Remove-AzureRmVMChefExtension.md)


