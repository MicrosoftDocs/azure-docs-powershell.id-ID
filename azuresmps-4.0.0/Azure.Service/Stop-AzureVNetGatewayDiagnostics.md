---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.Network.dll-Help.xml
ms.assetid: 706CBF65-C796-4525-BAEB-AAFAD44C0464
online version: ''
schema: 2.0.0
ms.openlocfilehash: a932bd5c8cc61b21518873fe6f3fa4c376a0d67f0611f9d18af8676af5d15683
ms.sourcegitcommit: 49f8ffe5d8e08ba3d22e3b2e76db0e54dd55d4f0
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/11/2021
ms.locfileid: "132417674"
---
# Stop-AzureVNetGatewayDiagnostics

## SYNOPSIS
Menghentikan sesi diagnostik gateway VPN yang berjalan.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Stop-AzureVNetGatewayDiagnostics -VNetName <String> [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Stop-AzureVNetGatewayDiagnostics** menghentikan sesi diagnostik gateway jaringan privat virtual (VPN, Virtual Private Network) yang sedang berjalan.
Perintah ini menyimpan hasil sesi diagnostik ke akun penyimpanan yang ditentukan cmdlet **Start-AzureVNetGatewayDiagnostics.**

## EXAMPLES

## PARAMETERS

### -Profil
Menentukan profil Azure yang akan dibaca cmdlet ini. Jika Anda tidak menentukan profil, cmdlet ini akan membaca dari profil default lokal.

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
Menentukan jaringan virtual yang berisi gateway jaringan virtual di mana cmdlet ini menghentikan diagnostik.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

## OUTPUTS

## CATATAN

## RELATED LINKS

[Get-AzureVNetGatewayDiagnostics](./Get-AzureVNetGatewayDiagnostics.md)

[Start-AzureVNetGatewayDiagnostics](./Start-AzureVNetGatewayDiagnostics.md)


