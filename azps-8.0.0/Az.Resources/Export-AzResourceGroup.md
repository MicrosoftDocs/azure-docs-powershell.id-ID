---
external help file: Microsoft.Azure.PowerShell.Cmdlets.ResourceManager.dll-Help.xml
Module Name: Az.Resources
ms.assetid: 63BBDF98-75FC-4A44-9FD0-95AD21ED93A6
online version: https://docs.microsoft.com/powershell/module/az.resources/export-azresourcegroup
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Export-AzResourceGroup.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Export-AzResourceGroup.md
ms.openlocfilehash: 979f17df6c73bc25990a5817bf841119ec8347e5
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145619976"
---
# Export-AzResourceGroup

## SYNOPSIS
Mengambil grup sumber daya sebagai templat dan menyimpannya ke file.

## SYNTAX

```
Export-AzResourceGroup -ResourceGroupName <String> [-Path <String>] [-IncludeParameterDefaultValue]
 [-IncludeComments] [-SkipResourceNameParameterization] [-SkipAllParameterization] [-Resource <String[]>]
 [-Force] [-ApiVersion <String>] [-Pre] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Export-AzResourceGroup** menangkap grup sumber daya yang ditentukan sebagai templat dan menyimpannya ke file JSON. Ini dapat berguna dalam skenario di mana Anda telah membuat beberapa sumber daya di grup sumber daya Anda, lalu ingin memanfaatkan manfaat menggunakan penyebaran yang didukung templat.
Cmdlet ini memberi Anda awal yang mudah dengan membuat templat untuk sumber daya yang ada di grup sumber daya.
Mungkin ada beberapa kasus di mana cmdlet ini gagal menghasilkan beberapa bagian templat.
Pesan peringatan akan memberi tahu Anda tentang sumber daya yang gagal.
Templat masih akan dihasilkan untuk bagian-bagian yang berhasil.

## EXAMPLES

### Contoh 1: Mengekspor grup sumber daya
```powershell
Export-AzResourceGroup -ResourceGroupName "TestGroup"
```

Perintah ini menangkap grup sumber daya bernama TestGroup sebagai templat, dan menyimpannya ke file JSON di direktori saat ini.

### Contoh 2: Mengekspor satu sumber daya dari grup sumber daya
```powershell
Export-AzResourceGroup -ResourceGroupName "TestGroup" -Resource "/subscriptions/5f43547b-1d2d-4a3e-ace4-88d4b600d568/resourceGroups/TestGroup/providers/Microsoft.Compute/virtualMachines/TestVirtualMachine"
```

Perintah ini menangkap sumber daya Komputer Virtual bernama "TestVirtualMachine" dari grup sumber daya "TestGroup" sebagai templat, dan menyimpannya ke file JSON di direktori saat ini.

### Contoh 3: Mengekspor pilihan sumber daya dari grup sumber daya
```powershell
Export-AzResourceGroup -ResourceGroupName "TestGroup" -SkipAllParameterization -Resource @(
  "/subscriptions/5f43547b-1d2d-4a3e-ace4-88d4b600d568/resourceGroups/TestGroup/providers/Microsoft.Compute/virtualMachines/TestVm",
  "/subscriptions/5f43547b-1d2d-4a3e-ace4-88d4b600d568/resourceGroups/TestGroup/providers/Microsoft.Network/networkInterfaces/TestNic"
)
```

Perintah ini menangkap dua sumber daya dari grup sumber daya "TestGroup" sebagai templat, dan menyimpannya ke file JSON di direktori saat ini. Templat yang dihasilkan tidak akan berisi parameter yang dihasilkan.

## PARAMETERS

### -ApiVersion
Menentukan versi API penyedia sumber daya yang akan digunakan.
Jika tidak ditentukan, versi API terbaru digunakan.

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
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
Memaksa perintah untuk berjalan tanpa meminta konfirmasi pengguna.

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

### -IncludeComments
Menunjukkan bahwa operasi ini mengekspor templat dengan komentar.

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

### -IncludeParameterDefaultValue
Menunjukkan bahwa operasi ini mengekspor parameter templat dengan nilai default.

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

### -Jalur
Menentukan jalur output file templat.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Pre
Menunjukkan bahwa cmdlet ini menggunakan versi API pra-rilis saat secara otomatis menentukan versi API mana yang akan digunakan.

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

### -Sumber daya
Daftar resourceIds untuk memfilter hasilnya.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Menentukan nama grup sumber daya yang akan diekspor.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: ResourceGroup

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SkipAllParameterization
Lewati semua parameterisasi.

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

### -SkipResourceNameParameterization
Lewati parameterisasi nama sumber daya.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### System.String

## OUTPUTS

### System.Management.Automation.PSObject

## NOTES

## RELATED LINKS

[Get-AzResourceGroup](./Get-AzResourceGroup.md)


