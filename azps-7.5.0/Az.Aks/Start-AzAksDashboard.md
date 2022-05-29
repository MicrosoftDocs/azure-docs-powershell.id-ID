---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Aks.dll-Help.xml
Module Name: Az.Aks
online version: https://docs.microsoft.com/powershell/module/az.aks/start-azaksdashboard
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Aks/Aks/help/Start-AzAksDashboard.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Aks/Aks/help/Start-AzAksDashboard.md
ms.openlocfilehash: f890115a7efe6be6e9aa1b21c484f0421ba34506
ms.sourcegitcommit: 321c644cf2161807a71e1af318fc5c5311d22e25
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/25/2022
ms.locfileid: "145782730"
---
# Start-AzAksDashboard

## SYNOPSIS
Buat terowongan Kubectl SSH ke dasbor kluster terkelola.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.aks/start-azaksdashboard) untuk informasi terbaru.

## SYNTAX

### GroupNameParameterSet (Default)
```
Start-AzAksDashboard [-ResourceGroupName] <String> [-Name] <String> [-DisableBrowser] [-ListenPort <Int32>]
 [-PassThru] [-DefaultProfile <IAzureContextContainer>] [-SubscriptionId <String>] [<CommonParameters>]
```

### InputObjectParameterSet
```
Start-AzAksDashboard [-InputObject] <PSKubernetesCluster> [-DisableBrowser] [-ListenPort <Int32>] [-PassThru]
 [-DefaultProfile <IAzureContextContainer>] [-SubscriptionId <String>] [<CommonParameters>]
```

### IdParameterSet
```
Start-AzAksDashboard [-Id] <String> [-DisableBrowser] [-ListenPort <Int32>] [-PassThru]
 [-DefaultProfile <IAzureContextContainer>] [-SubscriptionId <String>] [<CommonParameters>]
```

## DESCRIPTION
Buat terowongan Kubectl SSH ke dasbor kluster terkelola. Terowongan SSH disiapkan dalam pekerjaan PowerShell yang disebut Kubectl-Tunnel dan dapat ditemukan dengan menjalankan `Get-Job`. Terowongan harus dapat diakses melalui [http://127.0.0.1:8001](http://127.0.0.1:8001).

## EXAMPLES

### Mulai terowongan SSH dan buka browser ke dasbor Kubernetes
```powershell
Start-AzAksDashboard -ResourceGroupName group -Name myCluster
```

## PARAMETERS

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

### -DisableBrowser
Jangan buka browser setelah membuat port-forward kubectl.

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

### -Id
Id kluster Kubernetes terkelola

```yaml
Type: System.String
Parameter Sets: IdParameterSet
Aliases: ResourceId

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InputObject
Objek PSKubernetesCluster, biasanya melewati alur.

```yaml
Type: Microsoft.Azure.Commands.Aks.Models.PSKubernetesCluster
Parameter Sets: InputObjectParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ListenPort
Port mendengarkan untuk dasbor. Nilai defaultnya adalah 8003.

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

### -Name
Nama kluster Kubernetes terkelola Anda

```yaml
Type: System.String
Parameter Sets: GroupNameParameterSet
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Cmdlet mengembalikan KubeTunnelJob jika diteruskan.

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
Nama grup sumber daya

```yaml
Type: System.String
Parameter Sets: GroupNameParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubscriptionId
ID langganan.
Secara default, cmdlet dijalankan dalam langganan yang diatur dalam konteks saat ini. Jika pengguna menentukan langganan lain, cmdlet saat ini dijalankan dalam langganan yang ditentukan oleh pengguna.
Mengesampingkan langganan hanya berlaku selama siklus hidup cmdlet saat ini. Ini tidak mengubah langganan dalam konteks, dan tidak memengaruhi cmdlet berikutnya.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Microsoft.Azure.Commands.Aks.Models.PSKubernetesCluster

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Aks.KubeTunnelJob

## NOTES

## RELATED LINKS
