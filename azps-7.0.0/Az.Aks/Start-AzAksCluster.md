---
external help file: ''
Module Name: Az.Aks
online version: https://docs.microsoft.com/powershell/module/az.aks/start-azakscluster
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Aks/Aks/help/Start-AzAksCluster.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Aks/Aks/help/Start-AzAksCluster.md
ms.openlocfilehash: 131d9256917a761c27e39e8a9fa5e9320e341116
ms.sourcegitcommit: 579224f3f35e223624deb694bceb0033c84a5856
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 12/07/2021
ms.locfileid: "136572110"
---
# Start-AzAksCluster

## SYNOPSIS
Memulai Kluster yang Dihentikan Dikelola

## SYNTAX

### Mulai (Default)
```
Start-AzAksCluster -Name <String> -ResourceGroupName <String> [-SubscriptionId <String>]
 [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```

### StartViaIdentity
```
Start-AzAksCluster -InputObject <IAksIdentity> [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-PassThru]
 [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Memulai Kluster yang Dihentikan Dikelola

## EXAMPLES

### Contoh 1: Mulai kluster Aks dengan nama grup sumber daya dan nama kluster
```powershell
PS C:\> Start-AzAksCluster -ResourceGroupName group -Name myCluster
```

Mulai kluster Aks dengan nama grup sumber daya dan nama kluster.

### Contoh 2: Mulai kluster Aks dengan pipeline
```powershell
PS C:\> Get-AzAksCluster -ResourceGroupName group -Name myCluster | Start-AzAksCluster
```

Mulai kluster Aks dengan pipeline.

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

### -InputObject
Parameter Identitas Untuk membuat, lihat bagian CATATAN untuk properti INPUTOBJECT dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Aks.Models.IAksIdentity
Parameter Sets: StartViaIdentity
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Nama
Nama sumber daya kluster yang dikelola.

```yaml
Type: System.String
Parameter Sets: Start
Aliases: ClusterName

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

```yaml
Type: System.String
Parameter Sets: Start
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubscriptionId
Kredensial langganan yang secara unik mengidentifikasi Microsoft Azure langganan tersebut.
ID langganan membentuk bagian dari URI untuk setiap panggilan layanan.

```yaml
Type: System.String
Parameter Sets: Start
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Aks.Models.IAksIdentity

## OUTPUTS

### System.Boolean

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT <IAksIdentity> : Parameter Identitas
  - `[AgentPoolName <String>]`: Nama agen kolam renang.
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[Location <String>]`: Nama kawasan Azure yang didukung.
  - `[PrivateEndpointConnectionName <String>]`: Nama koneksi titik akhir privat.
  - `[ResourceGroupName <String>]`: Nama grup sumber daya.
  - `[ResourceName <String>]`: Nama sumber daya kluster terkelola.
  - `[RoleName <String>]`: Nama peran untuk sumber daya accessProfile kluster terkelola.
  - `[SubscriptionId <String>]`: Kredensial langganan yang mengidentifikasi langganan Microsoft Azure secara unik. ID langganan membentuk bagian dari URI untuk setiap panggilan layanan.

## RELATED LINKS

