---
external help file: ''
Module Name: Az.Elastic
online version: https://docs.microsoft.com/powershell/module/az.elastic/update-azelasticvmcollection
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Elastic/help/Update-AzElasticVMCollection.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Elastic/help/Update-AzElasticVMCollection.md
ms.openlocfilehash: 3cfe1d4947abcfc364167a911aebab2b1993ae3f
ms.sourcegitcommit: 7e47562b11e670049c3a18af7498414da853a921
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/09/2022
ms.locfileid: "138166568"
---
# Update-AzElasticVMCollection

## SYNOPSIS
Perbarui detail vm yang akan dipantau oleh sumber daya monitor Elastis.

## SYNTAX

### UpdateExpanded (Default)
```
Update-AzElasticVMCollection -Name <String> -ResourceGroupName <String> [-SubscriptionId <String>]
 [-OperationName <OperationName>] [-VMResourceId <String>] [-DefaultProfile <PSObject>] [-PassThru] [-Confirm]
 [-WhatIf] [<CommonParameters>]
```

### UpdateViaIdentityExpanded
```
Update-AzElasticVMCollection -InputObject <IElasticIdentity> [-OperationName <OperationName>]
 [-VMResourceId <String>] [-DefaultProfile <PSObject>] [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Perbarui detail vm yang akan dipantau oleh sumber daya monitor Elastis.

## EXAMPLES

### Contoh 1: Perbarui detail vm yang akan dipantau oleh sumber daya monitor Elastis
```powershell
PS C:\> Update-AzElasticVMCollection -ResourceGroupName lucas-elastic-test -Name elastic-pwsh02 -OperationName Add -VMResourceId '/subscriptions/xxxxxxxx-xxxxx-xxxx-xxxx-xxxxxxxx/resourceGroups/VIDHI-RG/providers/Microsoft.Compute/virtualMachines/vidhi-linuxOS'

```

Perintah ini memperbarui detail vm yang akan dipantau oleh sumber daya monitor Elastis

### Contoh 2: Perbarui detail vm yang akan dipantau oleh sumber daya monitor Elastis berdasarkan pipeline
```powershell
PS C:\> Get-AzElasticMonitor -ResourceGroupName lucas-elastic-test -Name elastic-pwsh02 | Update-AzElasticVMCollection -OperationName Delete -VMResourceId '/subscriptions/xxxxxxxx-xxxxx-xxxx-xxxx-xxxxxxxx/resourceGroups/VIDHI-RG/providers/Microsoft.Compute/virtualMachines/vidhi-linuxOS'

```

Perintah ini memperbarui detail vm yang akan dipantau oleh sumber daya monitor Elastis melalui pipeline.

## PARAMETERS

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

### -InputObject
Parameter Identitas Untuk membuat, lihat bagian CATATAN untuk properti INPUTOBJECT dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Elastic.Models.IElasticIdentity
Parameter Sets: UpdateViaIdentityExpanded
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Nama
Memantau nama sumber daya

```yaml
Type: System.String
Parameter Sets: UpdateExpanded
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OperationName
Operasi yang akan dilakukan untuk VM tertentu.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Elastic.Support.OperationName
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
Nama grup sumber daya tempat sumber daya Elastis dimiliki.

```yaml
Type: System.String
Parameter Sets: UpdateExpanded
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubscriptionId
ID langganan Azure.
Ini adalah string yang diformat GUID (misalnya 00000000-0000-0000-0000-00000000000)

```yaml
Type: System.String
Parameter Sets: UpdateExpanded
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMResourceId
ARM id dari sumber daya VM.

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

### Microsoft.Azure.PowerShell.Cmdlets.Elastis.Models.IElasticIdentity

## OUTPUTS

### System.Boolean

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT <IElasticIdentity>: Parameter Identitas
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[MonitorName <String>]`: Memantau nama sumber daya
  - `[ResourceGroupName <String>]`: Nama grup sumber daya tempat sumber daya Elastis dimiliki.
  - `[RuleSetName <String>]`: Nama sumber daya Kumpulan Aturan Tag
  - `[SubscriptionId <String>]`: ID langganan Azure. Ini adalah string yang diformat GUID (misalnya 00000000-0000-0000-0000-00000000000)

## RELATED LINKS

