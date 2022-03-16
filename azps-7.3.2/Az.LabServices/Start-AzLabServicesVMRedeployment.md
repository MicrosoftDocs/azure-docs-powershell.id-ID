---
external help file: ''
Module Name: Az.LabServices
online version: https://docs.microsoft.com/powershell/module/az.labservices/start-azlabservicesvmredeployment
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/LabServices/help/Start-AzLabServicesVMRedeployment.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/LabServices/help/Start-AzLabServicesVMRedeployment.md
ms.openlocfilehash: 42224bc1fff185440911a3cf3a0ac56953ac308b
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140000493"
---
# Start-AzLabServicesVMRedeployment

## SYNOPSIS
Tindakan untuk memindahkan kembali mesin virtual lab ke simpul perhitungan berbeda.
Untuk konektivitas pemecahan masalah.

## SYNTAX

### ResourceId (Default)
```
Start-AzLabServicesVMRedeployment -ResourceId <String> [-SubscriptionId <String>] [-DefaultProfile <PSObject>]
 [-AsJob] [-NoWait] [-PassThru] [<CommonParameters>]
```

### Redeploy
```
Start-AzLabServicesVMRedeployment -LabName <String> -ResourceGroupName <String> -VirtualMachineName <String>
 [-SubscriptionId <String>] [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-PassThru] [-Confirm] [-WhatIf]
 [<CommonParameters>]
```

## DESCRIPTION
Tindakan untuk memindahkan kembali mesin virtual lab ke simpul perhitungan berbeda.
Untuk konektivitas pemecahan masalah.

## EXAMPLES

### Contoh 1: Redeploy the specific Virtual machine.
```powershell
PS C:\> Start-AzLabServicesVMRedeployment -LabName "Lab Name" -ResourceGroupName "Group Name" -VirtualMachineName 1

```

The Redeploy removes the machine and creates a new one.

## PARAMETERS

### -AsJob
Menjalankan perintah sebagai pekerjaan

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

### -LabName
Nama lab yang secara unik mengidentifikasinya di dalam berisi akun lab.
Digunakan dalam URI sumber daya.

```yaml
Type: System.String
Parameter Sets: Redeploy
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoWait
Menjalankan perintah secara asinkron

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

### -PassThru
Mengembalikan true saat perintah berhasil

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

### -ResourceGroupName
Nama grup sumber daya.
Namanya peka huruf besar/huruf.

```yaml
Type: System.String
Parameter Sets: Redeploy
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceId


```yaml
Type: System.String
Parameter Sets: ResourceId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubscriptionId
ID langganan target.

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

### -VirtualMachineName
ID mesin virtual yang mengidentifikasinya secara unik di dalam lab berisi.
Digunakan dalam URI sumber daya.

```yaml
Type: System.String
Parameter Sets: Redeploy
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
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
Default value: None
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
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.LabServices.Models.Api20211001Preview.IVirtualMachine

### System.Boolean

## CATATAN

ALIAS

## RELATED LINKS

