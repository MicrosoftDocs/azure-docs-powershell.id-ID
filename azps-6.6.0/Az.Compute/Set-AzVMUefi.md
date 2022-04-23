---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Compute.dll-Help.xml
Module Name: Az.Compute
online version: https://docs.microsoft.com/powershell/module/az.compute/set-azvmuefi
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Set-AzVMUefi.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Set-AzVMUefi.md
ms.openlocfilehash: f6027d761cfb1bd6bb7dfa1f9af106553b13146b
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143260703"
---
# Set-AzVMUefi

## SYNOPSIS
Memodifikasi properti UEFI dari mesin virtual gen 2

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.compute/set-azvmuefi) untuk informasi terbaru.

## SYNTAX

```
Set-AzVMUefi [-VM] <PSVirtualMachine> [-EnableVtpm <Boolean>] [-EnableSecureBoot <Boolean>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzVMUefi** memodifikasi properti UEFI dari mesin virtual.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> $VM = Get-AzVM -ResourceGroupName "ResourceGroup11" -VMName "ContosoVM07"
PS C:\> Set-AzVMUefi -VM $VM -EnableVtpm $true -EnableSecureBoot $true
```

Perintah pertama mendapatkan mesin virtual bernama ContosoVM07 dengan menggunakan **Get-AzVM**.
Perintah menyimpannya dalam variabel $VM.
Perintah kedua mengubah pengaturan UEFI untuk mengaktifkan SecureBoot dan vTPM pada mesin virtual di $VM.
Perintah melewati hasil ke cmdlet Update-AzVM, yang mengimplementasikan perubahan Anda.
Perubahan pada mode kas menyebabkan mesin virtual dimulai ulang.

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
Parameter untuk mengaktifkan boot aman pada VM

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
Parameter untuk mengalihkan vTPM pada VM

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Compute.Models.PSVirtualMachine

### System.Boolean

## OUTPUTS

### Microsoft.Azure.Commands.Compute.Models.PSVirtualMachine

## NOTES

## RELATED LINKS
