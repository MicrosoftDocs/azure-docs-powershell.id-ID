---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Peering.dll-Help.xml
Module Name: Az.Peering
online version: https://docs.microsoft.com/powershell/module/az.peering/new-azpeerasncontactdetail
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Peering/Peering/help/New-AzPeerAsnContactDetail.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Peering/Peering/help/New-AzPeerAsnContactDetail.md
ms.openlocfilehash: 932b9f1879394d1dfdcfc766477d12bf6235e4de
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144183002"
---
# New-AzPeerAsnContactDetail

## SYNOPSIS
Membuat detail kontak dalam memori untuk PeerAsn. 

## SYNTAX

```
New-AzPeerAsnContactDetail -Role <String> -Email <String> [-Phone <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Buat detail kontak PeerAsn dalam memori.

## EXAMPLES

### Membuat detail kontak dan menambahkan ke PeerAsn
```powershell
$nocContact = New-AzPeerAsnContactDetail -Role Noc -Email "noc@contoso.com" -Phone "+1 (887) 888-8088"
$customerContact = New-AzPeerAsnContactDetail -Role Noc -Email "noc@contoso.com" -Phone "+1 (887) 888-8088"
New-AzPeerAsn -Name $name -PeerName "Contoso Networks Limited" -PeerAsn 65000 -ContactDetail $nocContact,$customerContact
```

Peran dan email diperlukan. Telepon bersifat opsional. Telepon mendukung +-() atau spasi. PeerAsn harus menyertakan setidaknya satu detail kontak jenis "Noc"

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

### -Email
Alamat Email yang digunakan untuk menghubungi jika masalah muncul biasanya Pusat Operasi Jaringan

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

### -Telepon
Telepon digunakan untuk menghubungi jika masalah muncul biasanya Pusat Operasi Jaringan

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

### -Peran
Pilih peran yang paling sesuai dengan informasi kontak.
Kontak NOC diperlukan.

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Tidak ada

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Peering.Models.PSContactDetail

## NOTES

## RELATED LINKS
