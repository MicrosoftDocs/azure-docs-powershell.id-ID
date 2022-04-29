---
external help file: Microsoft.Azure.PowerShell.Cmdlets.KeyVault.dll-Help.xml
Module Name: Az.KeyVault
online version: https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvaultrandomnumber
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/KeyVault/KeyVault/help/Get-AzKeyVaultRandomNumber.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/KeyVault/KeyVault/help/Get-AzKeyVaultRandomNumber.md
ms.openlocfilehash: dadf5648458d745ac52ed8d3e78ef47eb0e51cdd
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144237069"
---
# Get-AzKeyVaultRandomNumber

## SYNOPSIS
Dapatkan jumlah byte yang diminta yang berisi nilai acak dari HSM terkelola.

## SYNTAX

### GetByHsmName (Default)
```
Get-AzKeyVaultRandomNumber [-DefaultProfile <IAzureContextContainer>] [-HsmName] <String> -Count <Int32>
 [-AsBase64String] [<CommonParameters>]
```

### GetByHsmResourceId
```
Get-AzKeyVaultRandomNumber [-ResourceId] <String> [-DefaultProfile <IAzureContextContainer>] -Count <Int32>
 [-AsBase64String] [<CommonParameters>]
```

### GetByHsmInputObject
```
Get-AzKeyVaultRandomNumber [-DefaultProfile <IAzureContextContainer>] [-InputObject] <PSManagedHsm>
 -Count <Int32> [-AsBase64String] [<CommonParameters>]
```

## DESCRIPTION
Dapatkan jumlah byte yang diminta yang berisi nilai acak dari HSM terkelola.

## EXAMPLES

### Contoh 1: Dapatkan jumlah byte acak yang diminta berdasarkan nama HSM terkelola
```powershell
Get-AzKeyVaultRandomNumber -HsmName testmhsm -Count 10
```

```output
158
171
96
142
109
28
1
85
178
201
```

Perintah ini mendapatkan 10 byte acak dari "testmhsm" HSM terkelola 

### Contoh 2: Dapatkan angka acak sebagai string base64 dengan pipa
```powershell
Get-AzKeyVaultManagedHsm -HsmName bezmhsm2022 | Get-AzKeyVaultRandomNumber -Count 10 -AsBase64String
```

```output
G1CsEqa9yUp/EA==
```

Perintah ini mendapatkan 10 byte acak sebagai string base-64 dari "testmhsm" HSM terkelola 

### Contoh 3: Dapatkan angka acak menurut id sumber daya
```powershell
Get-AzKeyVaultRandomNumber -ResourceId /subscriptions/0b1fxxxx-xxxx-xxxx-aec3-xxxx72f09590/resourceGroups/test-rg/provders/Microsoft.KeyVault/managedHSMs/testhsm -Count 10
```

```output
158
171
96
142
109
28
1
85
178
201
```

Perintah ini mendapatkan 10 byte acak dari HSM terkelola dengan id sumber daya yang ditentukan

## PARAMETERS

### -AsBase64String
Jika ditentukan, kembalikan angka acak sebagai digit base-64.
Secara default, perintah ini mengulangi angka acak sebagai array byte.

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

### -Count
Jumlah byte acak yang diminta.

```yaml
Type: System.Int32
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

### -HsmName
Nama HSM. Cmdlet membangun FQDN dari HSM terkelola berdasarkan nama dan lingkungan yang saat ini dipilih.

```yaml
Type: System.String
Parameter Sets: GetByHsmName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Objek HSM.

```yaml
Type: Microsoft.Azure.Commands.KeyVault.Models.PSManagedHsm
Parameter Sets: GetByHsmInputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ResourceId
Id sumber daya HSM.

```yaml
Type: System.String
Parameter Sets: GetByHsmResourceId
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### System.String

### Microsoft.Azure.Commands.KeyVault.Models.PSManagedHsm

## OUTPUTS

### System.String

### System.Byte

## NOTES

## RELATED LINKS
