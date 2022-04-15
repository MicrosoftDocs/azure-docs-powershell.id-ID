---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Compute.dll-Help.xml
Module Name: Az.Compute
online version: https://docs.microsoft.com/powershell/module/az.compute/invoke-azvmruncommand
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Invoke-AzVMRunCommand.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Invoke-AzVMRunCommand.md
ms.openlocfilehash: 9f1d6b429d537406322e65461c6fcb7399393ffe
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142434251"
---
# Invoke-AzVMRunCommand

## SYNOPSIS
Jalankan perintah pada VM.

## SYNTAX

### DefaultParameter (Default)
```
Invoke-AzVMRunCommand [-ResourceGroupName] <String> [-VMName] <String> -CommandId <String>
 [-ScriptPath <String>] [-Parameter <Hashtable>] [-AsJob] [-DefaultProfile <IAzureContextContainer>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### ResourceIdParameter
```
Invoke-AzVMRunCommand -CommandId <String> [-ScriptPath <String>] [-Parameter <Hashtable>]
 [-ResourceId] <String> [-AsJob] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### VMParameter
```
Invoke-AzVMRunCommand -CommandId <String> [-ScriptPath <String>] [-Parameter <Hashtable>]
 [-VM] <PSVirtualMachine> [-AsJob] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Memanggil perintah jalankan pada VM.

## EXAMPLES

### Contoh 1: Memanggil perintah di Windows
```powershell
Invoke-AzVMRunCommand -ResourceGroupName 'rgname' -VMName 'vmname' -CommandId 'RunPowerShellScript' -ScriptPath 'sample.ps1' -Parameter @{param1 = "var1"; param2 = "var2"}
```

Gunakan perintah jalankan 'RunPowerShellScript' dengan menimpa skrip 'sample.ps1' pada Windows VM bernama 'vmname' dalam grup sumber daya 'rgname'. Var1 dan var2 didefinisikan sebagai parameter dalam sample.ps1. Nilai parameter hanya dapat berupa tipe string dan skrip bertanggung jawab untuk mengonversinya ke tipe lain jika diperlukan. 

### Contoh 2: Memanggil perintah di Linux
```powershell
export param1=var1 param2=var2
set -- var1 var2 var3

Invoke-AzVMRunCommand -ResourceGroupName 'rgname' -Name 'vmname' -CommandId 'RunShellScript' -ScriptPath 'sample.bash' -Parameter @{"param1" = "var1";"param2" = "var2"}
echo This is a sample bash script
echo Usage 1: Ordered parameters: $0 $1
echo Usage 2: Named exports: $var1 $var2
```

Perintah ini menjalankan perintah 'RunShellScript' dengan menimpa skrip 'sample.bash' pada VM Linux bernama 'vmname'. Var1 dan var2 didefinisikan sebagai parameter dalam sample.bash.

## PARAMETERS

### -AsJob
Jalankan cmdlet di latar belakang dan kembalikan objek pekerjaan untuk melacak kemajuan.

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

### -CommandId
ID perintah jalankan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
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

### -Parameter
Parameter perintah jalankan. Tentukan parameter sebagai pasangan kunci/nilai yang akan dilewati pada eksekusi skrip.

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

### -ResourceGroupName
Nama grup sumber daya.

```yaml
Type: System.String
Parameter Sets: DefaultParameter
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceId
ID sumber daya untuk VM.

```yaml
Type: System.String
Parameter Sets: ResourceIdParameter
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ScriptPath
Jalur skrip yang akan dijalankan. Ketika nilai ini diberikan, skrip yang diberikan akan menimpa skrip default perintah.
Jalur harus menunjuk ke file dari sistem file lokal. Perintah akan memuatnya dan mengirimkannya untuk eksekusi.

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

### -VM
Objek mesin virtual PS.

```yaml
Type: Microsoft.Azure.Commands.Compute.Models.PSVirtualMachine
Parameter Sets: VMParameter
Aliases: VMProfile

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -VMName
Nama mesin virtual.

```yaml
Type: System.String
Parameter Sets: DefaultParameter
Aliases: Name

Required: True
Position: 1
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

### Microsoft.Azure.Commands.Compute.Models.PSVirtualMachine

## OUTPUTS

### Microsoft.Azure.Commands.Compute.Automation.Models.PSRunCommandResult

## CATATAN

## RELATED LINKS
