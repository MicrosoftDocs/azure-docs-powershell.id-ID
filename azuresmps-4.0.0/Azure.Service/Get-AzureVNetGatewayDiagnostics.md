---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.Network.dll-Help.xml
ms.assetid: 22E8CB18-8CDD-4992-AB81-E1BB400E6BC7
online version: ''
schema: 2.0.0
ms.openlocfilehash: e8aabca6760c02b5f9ae2aae6a155fe812f88e32
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142656244"
---
# Get-AzureVNetGatewayDiagnostics

## SYNOPSIS
Mendapatkan status diagnostik saat ini untuk gateway jaringan virtual.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Get-AzureVNetGatewayDiagnostics -VNetName <String> [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureVNetGatewayDiagnostics** mendapatkan status diagnostik saat ini untuk gateway jaringan virtual.
Jika objek besar biner (blob) ada di tempat **Start-AzureVNetGatewayDiagnostics menyimpan sesi diagnostik** sebelumnya, cmdlet ini juga mengembalikan URL blob tempat cmdlet tersebut menyimpan sesi diagnostik tersebut.

## EXAMPLES

## PARAMETERS

### -Profil
Menentukan profil Azure tempat cmdlet ini dibaca. Jika Anda tidak menentukan profil, cmdlet ini akan dibaca dari profil default lokal.

```yaml
Type: AzureSMProfile
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VNetName
Menentukan jaringan virtual yang berisi gateway jaringan virtual di mana cmdlet ini mendapatkan diagnostik.

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Start-AzureVNetGatewayDiagnostics](./Start-AzureVNetGatewayDiagnostics.md)

[Stop-AzureVNetGatewayDiagnostics](./Stop-AzureVNetGatewayDiagnostics.md)


