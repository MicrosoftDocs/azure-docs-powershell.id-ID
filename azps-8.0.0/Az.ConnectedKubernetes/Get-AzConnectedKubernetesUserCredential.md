---
external help file: ''
Module Name: Az.ConnectedKubernetes
online version: https://docs.microsoft.com/powershell/module/az.connectedkubernetes/get-azconnectedkubernetesusercredential
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ConnectedKubernetes/help/Get-AzConnectedKubernetesUserCredential.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ConnectedKubernetes/help/Get-AzConnectedKubernetesUserCredential.md
ms.openlocfilehash: 2fe521f3d9a7c18d86513fda8764d69dd54f262e
ms.sourcegitcommit: 5df8b100721844736630242c724da453a2168434
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/26/2022
ms.locfileid: "146603202"
---
# Get-AzConnectedKubernetesUserCredential

## SYNOPSIS
Mendapatkan kredensial pengguna kluster dari kluster yang terhubung dengan grup dan nama sumber daya tertentu.

## SYNTAX

### ListExpanded (Default)
```
Get-AzConnectedKubernetesUserCredential -ClusterName <String> -ResourceGroupName <String>
 -AuthenticationMethod <AuthenticationMethod> -ClientProxy [-SubscriptionId <String[]>]
 [-DefaultProfile <PSObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```

### Daftar
```
Get-AzConnectedKubernetesUserCredential -ClusterName <String> -ResourceGroupName <String>
 -Property <IListClusterUserCredentialProperties> [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>]
 [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan kredensial pengguna kluster dari kluster yang terhubung dengan grup dan nama sumber daya tertentu.

## EXAMPLES

### Contoh 1: Mendapatkan kredensial pengguna kluster dari kluster yang terhubung dengan grup dan nama sumber daya tertentu.
```powershell
Get-AzConnectedKubernetesUserCredential -ClusterName azps_test_cluster -ResourceGroupName azps_test_group -AuthenticationMethod AAD -ClientProxy
```

```output
HybridConnectionConfigExpirationTime       : 1635508790
HybridConnectionConfigHybridConnectionName : microsoft.kubernetes/connectedclusters/8d3bccced1f3ad1d0e01b03e87d1c8f8a312df7ff028e642512a7999542e46fc/1635497990523092736
HybridConnectionConfigRelay                : azgnrelay-eastus-l1
HybridConnectionConfigToken                : SharedAccessSignature sr=http%3A%2F%2Fazgnrelay-eastus-l1.servicebus.windows.net%2Fmicrosoft.kubernetes%2Fconnectedclusters%2F8d3bccced1f3ad1d0e01b03e87d1c8f8a312df7ff028e642512a7999542e46fc%2F1635497990523092736%2F&sig=wrukC6KAxVFb%2FmsdaTwSv3ChHo0hvTWjf5A80IZs2P4%3D&se=1635509390&skn=sender20211026
Kubeconfig                                 : {{
                                               "name": "KubeConfig",
                                               "value": "YXBpVm***G9wDQo="
                                             }}
```

Mendapatkan kredensial pengguna kluster dari kluster yang terhubung dengan grup dan nama sumber daya tertentu.

### Contoh 2: Mendapatkan kredensial pengguna kluster dari kluster yang terhubung dengan grup sumber daya dan nama tertentu.
```powershell
Get-AzConnectedKubernetesUserCredential -ClusterName azps_test_cluster -ResourceGroupName azps_test_group -AuthenticationMethod Token -ClientProxy:$false
```

```output
HybridConnectionConfigExpirationTime       :
HybridConnectionConfigHybridConnectionName :
HybridConnectionConfigRelay                :
HybridConnectionConfigToken                :
Kubeconfig                                 : {{
                                               "name": "KubeConfig",
                                               "value": "YXBpVm***G9wDQo="
                                             }}
```

Mendapatkan kredensial pengguna kluster dari kluster yang terhubung dengan grup dan nama sumber daya tertentu.

## PARAMETERS

### -AuthenticationMethod
Mode autentikasi klien.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ConnectedKubernetes.Support.AuthenticationMethod
Parameter Sets: ListExpanded
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ClientProxy
Nilai Boolean untuk menunjukkan apakah permintaan tersebut untuk proksi sisi klien atau tidak

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ListExpanded
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ClusterName
Nama kluster Kubernetes tempat get dipanggil.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Name

Required: True
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

### -Properti
.
Untuk membuat, lihat bagian CATATAN untuk properti PROPERTI dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ConnectedKubernetes.Models.Api20211001.IListClusterUserCredentialProperties
Parameter Sets: List
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya.
Nama tidak peka huruf besar/kecil.

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

### -SubscriptionId
ID langganan target.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
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

### Microsoft.Azure.PowerShell.Cmdlets.ConnectedKubernetes.Models.Api20211001.IListClusterUserCredentialProperties

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ConnectedKubernetes.Models.Api20211001.ICredentialResults

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


PROPERTI `<IListClusterUserCredentialProperties>`: .
  - `AuthenticationMethod <AuthenticationMethod>`: Mode autentikasi klien.
  - `ClientProxy <Boolean>`: Nilai Boolean untuk menunjukkan apakah permintaan tersebut untuk proksi sisi klien atau tidak

## RELATED LINKS

