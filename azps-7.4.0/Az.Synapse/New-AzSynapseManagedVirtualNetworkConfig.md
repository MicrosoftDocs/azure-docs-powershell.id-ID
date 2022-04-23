---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Synapse.dll-Help.xml
Module Name: Az.Synapse
online version: https://docs.microsoft.com/powershell/module/az.synapse/new-azsynapsemanagedvirtualnetworkconfig
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/New-AzSynapseManagedVirtualNetworkConfig.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/New-AzSynapseManagedVirtualNetworkConfig.md
ms.openlocfilehash: 1c505a60dc49a8fba9530198745f8cd8cbbf5b4a
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143222813"
---
# New-AzSynapseManagedVirtualNetworkConfig

## SYNOPSIS
Membuat konfigurasi jaringan virtual terkelola.

## SYNTAX

```
New-AzSynapseManagedVirtualNetworkConfig [-PreventDataExfiltration] [-AllowedAadTenantIdsForLinking <String[]>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzSynapseManagedVirtualNetworkConfig** ini membuat konfigurasi jaringan virtual terkelola.

## EXAMPLES

### Contoh 1
```powershell
$config = New-AzSynapseManagedVirtualNetworkConfig -PreventDataExfiltration -AllowedAadTenantIdsForLinking ContosoTenantId
$password = ConvertTo-SecureString "Password123!" -AsPlainText -Force
$creds = New-Object System.Management.Automation.PSCredential ("ContosoUser", $password)
New-AzSynapseWorkspace -ResourceGroupName ContosoResourceGroup -Name ContosoWorkspace -Location northeurope -DefaultDataLakeStorageAccountName ContosoAdlGen2Storage -DefaultDataLakeStorageFilesystem ContosoFileSystem -SqlAdministratorLoginCredential $creds -ManagedVirtualNetwork $config
```

Perintah pertama membuat konfigurasi jaringan virtual terkelola. Kemudian metode lainnya menggunakan konfigurasi untuk membuat ruang kerja Synapse baru.

## PARAMETERS

### -AllowedAadTenantIdsForLinking
ID penyewa AAD yang diperbolehkan untuk penautan.

```yaml
Type: System.String[]
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
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PreventDataExfiltration
Menunjukkan apakah akan mencegah eksfiltrasi data.

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak

## OUTPUTS

### Microsoft.Azure.Commands.Synapse.Models.PSManagedVirtualNetworkSettings

## NOTES

## RELATED LINKS
