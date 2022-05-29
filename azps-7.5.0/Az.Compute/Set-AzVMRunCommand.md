---
external help file: ''
Module Name: Az.Compute
online version: https://docs.microsoft.com/powershell/module/az.compute/set-azvmruncommand
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Set-AzVMRunCommand.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Set-AzVMRunCommand.md
ms.openlocfilehash: b6e1d8011c346aa5f21bded189015018622997d1
ms.sourcegitcommit: 82b4008b76d035e4aee733727371765b0d853bed
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145732726"
---
# Set-AzVMRunCommand

## SYNOPSIS
Operasi untuk membuat atau memperbarui perintah jalankan.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.compute/set-azvmruncommand) untuk informasi terbaru.

## SYNTAX

```
Set-AzVMRunCommand -ResourceGroupName <String> -RunCommandName <String> -VMName <String> -Location <String>
 [-SubscriptionId <String>] [-AsyncExecution] [-ErrorBlobUri <String>] [-OutputBlobUri <String>]
 [-Parameter <IRunCommandInputParameter[]>] [-ProtectedParameter <IRunCommandInputParameter[]>]
 [-RunAsPassword <String>] [-RunAsUser <String>] [-SourceCommandId <String>] [-SourceScript <String>]
 [-SourceScriptUri <String>] [-Tag <Hashtable>] [-TimeoutInSecond <Int32>] [-DefaultProfile <PSObject>]
 [-AsJob] [-NoWait] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Operasi untuk membuat atau memperbarui perintah jalankan.

## EXAMPLES

### Contoh 1: Contoh Sederhana
```powershell
Set-AzVMRunCommand -ResourceGroupName $rgname -VMName $vmname -RunCommandName 'firstruncommand' 
```

```output
Location Name             Type
-------- ----             ----
eastus   firstruncommand2 Microsoft.Compute/virtualMachines/runCommands
```

Cmdlet Set-AzVMRunCommand memperbarui properti untuk perintah jalankan yang ada atau menambahkan perintah jalankan baru ke komputer virtual.

## PARAMETERS

### -AsJob
Jalankan perintah sebagai pekerjaan

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

### -AsyncExecution
Opsional.
Jika diatur ke true, provisi akan selesai segera setelah skrip dimulai dan tidak akan menunggu skrip selesai.

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

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases: AzureRMContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ErrorBlobUri
Menentukan blob penyimpanan Azure tempat aliran kesalahan skrip akan diunggah.

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

### -Lokasi
Lokasi sumber daya

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

### -NoWait
Jalankan perintah secara asinkron

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

### -OutputBlobUri
Menentukan blob penyimpanan Azure tempat aliran output skrip akan diunggah.

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

### -Parameter
Parameter yang digunakan oleh skrip.
Untuk membuat, lihat bagian CATATAN untuk properti PARAMETER dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Compute.Models.Api20210701.IRunCommandInputParameter[]
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
Untuk membuat, lihat bagian CATATAN untuk properti PROTECTEDPARAMETER dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Compute.Models.Api20210701.IRunCommandInputParameter[]
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
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RunAsPassword
Menentukan kata sandi akun pengguna pada VM saat menjalankan perintah jalankan.

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

### -RunAsUser
Menentukan akun pengguna pada VM saat menjalankan perintah jalankan.

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

### -RunCommandName
Nama perintah eksekusi komputer virtual.

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

### -SourceCommandId
Menentukan commandId dari skrip bawaan yang telah ditentukan sebelumnya.

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

### -SourceScript
Menentukan konten skrip yang akan dijalankan pada VM.

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

### -SourceScriptUri
Menentukan lokasi pengunduhan skrip.

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

### -SubscriptionId
Kredensial langganan yang secara unik mengidentifikasi langganan Microsoft Azure.
ID langganan membentuk bagian dari URI untuk setiap panggilan layanan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### -Tag
Tag sumber daya

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

### -TimeoutInSecond
Batas waktu dalam detik untuk menjalankan perintah jalankan.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMName
Nama komputer virtual tempat perintah jalankan harus dibuat atau diperbarui.

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

### -Confirm
Meminta Anda mengonfirmasi sebelum menjalankan cmdlet.

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
Menunjukkan yang akan terjadi jika cmdlet dijalankan.
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Compute.Models.Api20210701.IVirtualMachineRunCommand

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


PARAMETER <IRunCommandInputParameter[]>: Parameter yang digunakan oleh skrip.
  - `Name <String>`: Nama parameter perintah eksekusi.
  - `Value <String>`: Nilai parameter perintah eksekusi.

PROTECTEDPARAMETER <IRunCommandInputParameter[]>: Parameter yang digunakan oleh skrip.
  - `Name <String>`: Nama parameter perintah eksekusi.
  - `Value <String>`: Nilai parameter perintah eksekusi.

## RELATED LINKS

