---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Compute.dll-Help.xml
Module Name: Az.Compute
ms.assetid: 9A6F140C-9F1C-4701-9603-FC6107FCAF92
online version: https://docs.microsoft.com/powershell/module/az.compute/set-azvmbootdiagnostic
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Set-AzVMBootDiagnostic.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Set-AzVMBootDiagnostic.md
ms.openlocfilehash: b93eed9d9331a14d289c08515941462f80124eda
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142433210"
---
# Set-AzVMBootDiagnostic

## SYNOPSIS
Mengubah properti diagnostik boot mesin virtual.

## SYNTAX

### EnableBootDiagnostics
```
Set-AzVMBootDiagnostic [-VM] <PSVirtualMachine> [-Enable] [[-ResourceGroupName] <String>]
 [[-StorageAccountName] <String>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### DisableBootDiagnostics
```
Set-AzVMBootDiagnostic [-VM] <PSVirtualMachine> [-Disable] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzVMBootDiagnostic** memodifikasi properti diagnostik boot mesin virtual.

## EXAMPLES

### Contoh 1: Aktifkan diagnostik boot
```powershell
$VM = Get-AzVM -ResourceGroupName "ResourceGroup11" -Name "ContosoVM07"
Set-AzVMBootDiagnostic -VM $VM -Enable -ResourceGroupName "ResourceGroup11" -StorageAccountName "DiagnosticStorage"
Update-AzVM -VM $VM -ResourceGroupName "ResourceGroup11"
```

Perintah pertama mendapatkan mesin virtual bernama ContosoVM07 dengan menggunakan **Get-AzVM**.
Perintah menyimpannya dalam variabel $VM.
Perintah kedua memungkinkan diagnostik boot untuk mesin virtual di $VM.
Data diagnostik disimpan dalam akun tertentu.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure.

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

### -Non-fungsikan
Menunjukkan bahwa cmdlet ini menonaktifkan diagnostik boot untuk mesin virtual.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: DisableBootDiagnostics
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Aktifkan
Menunjukkan bahwa cmdlet ini mengaktifkan diagnostik boot untuk mesin virtual.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: EnableBootDiagnostics
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Menentukan nama grup sumber daya akun penyimpanan.

```yaml
Type: System.String
Parameter Sets: EnableBootDiagnostics
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StorageAccountName
Menentukan nama akun penyimpanan untuk menyimpan data diagnostik boot. Jika tidak disediakan, ia akan mencari StorageUri di Profil BootDiagnostic di objek PSVirtualMachine yang disediakan dalam parameter '-VM'. Jika StorageUri null, defaultnya akan menggunakan akun penyimpanan terkelola. 

```yaml
Type: System.String
Parameter Sets: EnableBootDiagnostics
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VM
Menentukan mesin virtual di mana cmdlet ini mengubah diagnostik boot.
Untuk mendapatkan objek mesin virtual, gunakan cmdlet Get-AzVM.

```yaml
Type: Microsoft.Azure.Commands.Compute.Models.PSVirtualMachine
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

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Compute.Models.PSVirtualMachine

## CATATAN

## RELATED LINKS

[Get-AzVM](./Get-AzVM.md)

[Get-AzVMBootDiagnosticsData](./Get-AzVMBootDiagnosticsData.md)


