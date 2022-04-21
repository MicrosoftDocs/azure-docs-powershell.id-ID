---
external help file: Microsoft.Azure.PowerShell.Cmdlets.RecoveryServices.dll-Help.xml
Module Name: Az.RecoveryServices
ms.assetid: 368DD95E-EA25-4FC4-8171-CB7348FE480C
online version: https://docs.microsoft.com/powershell/module/az.recoveryservices/set-azrecoveryservicesvaultcontext
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RecoveryServices/RecoveryServices/help/Set-AzRecoveryServicesVaultContext.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RecoveryServices/RecoveryServices/help/Set-AzRecoveryServicesVaultContext.md
ms.openlocfilehash: 076ac91c78f94449092eb9dcb35b735608bff75b
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142802476"
---
# Set-AzRecoveryServicesVaultContext

## SYNOPSIS

Mengatur konteks vault.

## SYNTAX

```
Set-AzRecoveryServicesVaultContext -Vault <ARSVault> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION

Cmdlet **Set-AzRecoveryServicesVaultContext** mengatur konteks vault untuk layanan Azure Site Recovery.

Peringatan: Cmdlet ini tidak digunakan lagi dalam rilis perubahan yang melanggar di masa mendatang. Tidak akan ada penggantinya. Silakan gunakan parameter -VaultId di semua perintah Layanan Pemulihan ke depannya.

## EXAMPLES

### Contoh 1

```powershell
$vault = Get-AzRecoveryServicesVault -ResourceGroupName "resourceGroup" -Name "vaultName"
Set-AzRecoveryServicesVaultContext -Vault $vault
```

Mengatur konteks vault.

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

### -Vault

Menentukan nama vault.
Vault harus berupa objek **AzureRmRecoveryServicesVault** .

```yaml
Type: Microsoft.Azure.Commands.RecoveryServices.ARSVault
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Microsoft.Azure.Commands.RecoveryServices.ARSVault

## OUTPUTS

### System.Void

## NOTES

## RELATED LINKS
