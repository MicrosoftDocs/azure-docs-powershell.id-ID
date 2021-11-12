---
external help file: Microsoft.Azure.Commands.Compute.dll-Help.xml
Module Name: AzureRM.Compute
ms.assetid: 38917534-49C6-47EA-B815-240F794EE655
online version: ''
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Compute/Stack/Commands.Compute/help/Update-AzureRmVM.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Compute/Stack/Commands.Compute/help/Update-AzureRmVM.md
ms.openlocfilehash: ad337c07f22b2805002347758f91bf0ea781adad
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132423065"
---
# Update-AzureRmVM

## SYNOPSIS
Memperbarui status mesin virtual Azure.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### ResourceGroupNameParameterSetName (Default)
```
Update-AzureRmVM -VM <PSVirtualMachine> [-Tags <Hashtable>] [-IdentityType <ResourceIdentityType>]
 [-AssignIdentity] [-ResourceGroupName] <String> [-DefaultProfile <IAzureContextContainer>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### IdParameterSetName
```
Update-AzureRmVM -VM <PSVirtualMachine> [-Tags <Hashtable>] [-IdentityType <ResourceIdentityType>]
 [-AssignIdentity] [-Id] <String> [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Update-AzureRmVM** memperbarui status komputer virtual Azure sesuai dengan status objek mesin virtual.

## EXAMPLES

### Contoh 1: Memperbarui mesin virtual
```
PS C:\> Update-AzureRmVM -ResourceGroupName "ResourceGroup11" -VM $VirtualMachine
```

Perintah ini memperbarui mesin virtual, $VirtualMachine, di ResourceGroup11.
Perintah memperbaruinya menggunakan objek mesin virtual yang disimpan dalam $VirtualMachine variabel.
Untuk mendapatkan objek mesin virtual, gunakan cmdlet **Get-AzureRmVM.**

## PARAMETERS

### -AssignIdentity
Tentukan identitas yang ditetapkan sistem untuk komputer virtual.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

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

### -Id
Menentukan ID Sumber Daya komputer virtual.

```yaml
Type: System.String
Parameter Sets: IdParameterSetName
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IdentityType
Tipe identitas yang digunakan untuk mesin virtual. Saat ini, satu-satunya tipe yang didukung adalah 'SystemAssigned', yang secara implisit membuat identitas.

```yaml
Type: System.Nullable`1[Microsoft.Azure.Management.Compute.Models.ResourceIdentityType]
Parameter Sets: (All)
Aliases: 
Accepted values: SystemAssigned

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Menentukan nama grup sumber daya komputer virtual.

```yaml
Type: System.String
Parameter Sets: ResourceGroupNameParameterSetName
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Tag
Menentukan sumber daya dan grup sumber daya dapat ditandai dengan kumpulan pasangan nama nilai.
Menambahkan tag ke sumber daya memungkinkan Anda mengelompokkan sumber daya bersama-sama di seluruh grup sumber daya dan untuk membuat tampilan Anda sendiri.
Setiap grup sumber daya atau sumber daya dapat memiliki maksimal 15 tag.

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VM
Menentukan objek mesin virtual lokal.
Untuk mendapatkan objek mesin virtual, gunakan cmdlet Get-AzureRmVM.
Objek mesin virtual ini berisi status yang diperbarui untuk mesin virtual.

```yaml
Type: Microsoft.Azure.Commands.Compute.Models.PSVirtualMachine
Parameter Sets: (All)
Aliases: VMProfile

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
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
Default value: False
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
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

## OUTPUTS

## CATATAN

## RELATED LINKS

[Get-AzureRmVM](./Get-AzureRmVM.md)

[New-AzureRmVM](./New-AzureRmVM.md)

[Remove-AzureRmVM](./Remove-AzureRmVM.md)

[Mulai ulang-AzureRmVM](./Restart-AzureRmVM.md)

[Start-AzureRmVM](./Start-AzureRmVM.md)

[Stop-AzureRmVM](./Stop-AzureRmVM.md)

[New-AzureRmVMConfig](./New-AzureRmVMConfig.md)


