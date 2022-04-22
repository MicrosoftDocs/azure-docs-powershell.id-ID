---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.Network.dll-Help.xml
ms.assetid: BE661AC7-BA39-4D6A-8083-16CE9327DC08
online version: ''
schema: 2.0.0
ms.openlocfilehash: c9a4389c78d909be37e2755953f9a2ba2622dabc
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143044153"
---
# Get-AzureIPForwarding

## SYNOPSIS
Mendapatkan status penerusan IP.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

### IaaSIPForwardingParamSet
```
Get-AzureIPForwarding -VM <PersistentVMRoleContext> -ServiceName <String> [-NetworkInterfaceName <String>]
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### SlotIPForwardingParamSet
```
Get-AzureIPForwarding -ServiceName <String> [-Slot <String>] -RoleName <String>
 [-NetworkInterfaceName <String>] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureIPForwarding** mendapatkan status penerusan IP.

## EXAMPLES

### Contoh 1: Dapatkan status penerusan IP untuk mesin virtual
```
PS C:\> Get-AzureVM -ServiceName "ContosoService" -Name "ContosoVM06" | Get-AzureIPForwarding
Disabled
```

Perintah ini mendapatkan mesin virtual bernama ContosoVM06 untuk layanan bernama ContosoService, dan meneruskan objek mesin virtual tersebut ke cmdlet saat ini.
Cmdlet saat ini mendapatkan status penerusan IP untuk mesin virtual tersebut.

## PARAMETERS

### -NetworkInterfaceName
Menentukan nama adapter jaringan di mana cmdlet ini mendapatkan status penerusan IP.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

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

### -RoleName
Menentukan nama peran PaaS tempat cmdlet ini mendapatkan status penerusan IP.

```yaml
Type: String
Parameter Sets: SlotIPForwardingParamSet
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ServiceName
Menentukan nama layanan awan.
Peran PaaS termasuk dalam layanan yang ditentukan parameter ini.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Slot
Menentukan slot PaaS.
Peran PaaS di mana cmdlet ini mendapatkan status penerusan memiliki slot yang ditentukan parameter ini.
Nilai yang valid adalah: 

- Produksi
- Pementasan 

Nilai defaultnya adalah Produksi.

```yaml
Type: String
Parameter Sets: SlotIPForwardingParamSet
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VM
Menentukan objek mesin virtual di mana cmdlet ini mendapatkan status penerusan IP.

```yaml
Type: PersistentVMRoleContext
Parameter Sets: IaaSIPForwardingParamSet
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### System.String

## NOTES

## RELATED LINKS

[Set-AzureIPForwarding](./Set-AzureIPForwarding.md)


