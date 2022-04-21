---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Compute.dll-Help.xml
Module Name: Az.Compute
online version: https://docs.microsoft.com/powershell/module/az.compute/add-azvmssruncommand
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Add-AzVmssRunCommand.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Add-AzVmssRunCommand.md
ms.openlocfilehash: 020899c19ed375bcf4c41f3fbc74537432528efd
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142830016"
---
# Add-AzVmssRunCommand

## SYNOPSIS
Menambahkan Perintah Jalankan ke instans VMSS

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.compute/add-azvmssruncommand) untuk informasi terbaru.

## SYNTAX

### DefaultParameter (Default)
```
Add-AzVmssRunCommand [-ResourceGroupName] <String> [-VMScaleSetName] <String> [-Location] <String>
 [-CommandId <String>] -Name <String> [-ScriptPath <String>] [-ScriptUri <String>] [-Script <String>]
 [-TimeOutInSeconds <String>] [-ErrorBlobUri <String>] [-OutputBlobUri <String>] [-RunAsUser <String>]
 [-RunAsPassword <SecureString>] [-Parameter <Hashtable>] [-ProtectedParameter <Hashtable>]
 [-AsyncExecution <Boolean>] [-AsJob] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ObjectParameter
```
Add-AzVmssRunCommand [-CommandId <String>] -Name <String> [-ScriptPath <String>] [-ScriptUri <String>]
 [-Script <String>] [-TimeOutInSeconds <String>] [-ErrorBlobUri <String>] [-OutputBlobUri <String>]
 [-RunAsUser <String>] [-RunAsPassword <SecureString>] [-Parameter <Hashtable>]
 [-ProtectedParameter <Hashtable>] [-AsyncExecution <Boolean>]
 [-VirtualMachineScaleSetVM] <PSVirtualMachineScaleSetVM> [-AsJob] [-DefaultProfile <IAzureContextContainer>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Menambahkan Perintah Jalankan ke Semua Instans VMSS

## EXAMPLES

### Contoh 1
```powershell
Add-AzVmssRunCommand -ResourceGroupName $rgname -VMScaleSetName $vmssname -Location eastus -Name myruncommand -Script "Write-Host Hello World" -TimeOutInSeconds 3600 -RunAsUser "admin01" 
```

Menambahkan 'myruncommand' ke VMSS

## PARAMETERS

### -AsJob
Menjalankan cmdlet di latar belakang

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AsyncExecution
Opsional. Jika diatur ke true, penyediaan akan selesai segera setelah skrip dimulai dan tidak akan menunggu skrip selesai.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CommandId
RunCommand Id

```yaml
Type: String
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
Type: IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ErrorBlobUri
Menentukan blob penyimpanan Azure tempat streaming kesalahan skrip akan diunggah.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Lokasi
Lokasi sumber daya

```yaml
Type: String
Parameter Sets: DefaultParameter
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Nama
Nama sumber daya

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OutputBlobUri
Menentukan blob penyimpanan Azure tempat streaming output skrip akan diunggah.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Parameter
Parameter yang digunakan oleh skrip.

```yaml
Type: Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProtectedParameter
Parameter yang digunakan oleh skrip.

```yaml
Type: Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama Grup Sumber Daya

```yaml
Type: String
Parameter Sets: DefaultParameter
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RunAsPassword
Menentukan kata sandi akun pengguna pada VM ketika menjalankan perintah jalankan.

```yaml
Type: SecureString
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RunAsUser
Menentukan akun pengguna pada VM ketika menjalankan perintah jalankan.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Script
Sumber skrip perintah jalankan.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ScriptPath
Jalur sumber skrip perintah jalankan.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ScriptUri
Sumber Uri dari skrip perintah jalankan.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TimeOutInSeconds
Waktu habis dalam detik untuk menjalankan perintah jalankan.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualMachineScaleSetVM
The VirtualMachineScaleSetVM

```yaml
Type: PSVirtualMachineScaleSetVM
Parameter Sets: ObjectParameter
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -VMScaleSetName
The VirtualMachineScaleSet

```yaml
Type: String
Parameter Sets: DefaultParameter
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Konfirmasi
Meminta konfirmasi sebelum menjalankan cmdlet.

```yaml
Type: SwitchParameter
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
Type: SwitchParameter
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

### Microsoft.Azure.Commands.Compute.Automation.Models.PSVirtualMachineScaleSetVM

## OUTPUTS

### Microsoft.Azure.Commands.Compute.Automation.Models.PSRunCommandResult

## NOTES

## RELATED LINKS
