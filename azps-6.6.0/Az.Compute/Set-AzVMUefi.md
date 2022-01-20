---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Compute.dll-Help.xml
Module Name: Az.Compute
online version: https://docs.microsoft.com/powershell/module/az.compute/set-azvmuefi
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Set-AzVMUefi.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Set-AzVMUefi.md
ms.openlocfilehash: 533366c1dc6ced54946b6e6c4049a3c3f08c5b89
ms.sourcegitcommit: 53ef403038f665f1b3a9f616185b31f5de9bd7bb
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/03/2021
ms.locfileid: "136353546"
---
# Set-AzVMUefi

## SYNOPSIS
Mengubah properti UEFI mesin virtual gen 2

## SYNTAX

```
Set-AzVMUefi [-VM] <PSVirtualMachine> [-EnableVtpm <Boolean>] [-EnableSecureBoot <Boolean>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzVMUefi** mengubah properti UEFI mesin virtual.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> $VM = Get-AzVM -ResourceGroupName "ResourceGroup11" -VMName "ContosoVM07"
PS C:\> Set-AzVMUefi -VM $VM -EnableVtpm $true -EnableSecureBoot $true
```

Perintah pertama mendapatkan mesin virtual bernama ContosoVM07 dengan menggunakan **Get-AzVM**.
Perintah menyimpannya di $VM variabel.
Perintah kedua mengubah pengaturan UEFI untuk mengaktifkan SecureBoot dan vTPM pada komputer virtual dalam $VM.
Perintah melewati hasil ke cmdlet Update-AzVM, yang menerapkan perubahan Anda.
Perubahan pada mode kas menyebabkan mesin virtual memulai ulang.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableSecureBoot
Parameter untuk mengaktifkan secure boot pada VM

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EnableVtpm
Parameter untuk mengaktifkan vTPM pada VM

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VM
Profil mesin virtual.

```yaml
Type: PSVirtualMachine
Parameter Sets: (All)
Aliases: VMProfile

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Compute.Models.PSVirtualMachine

### System.Boolean

## OUTPUTS

### Microsoft.Azure.Commands.Compute.Models.PSVirtualMachine

## CATATAN

## RELATED LINKS
