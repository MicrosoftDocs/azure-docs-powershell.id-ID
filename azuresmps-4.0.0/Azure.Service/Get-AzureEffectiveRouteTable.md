---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.Network.dll-Help.xml
ms.assetid: 82CF6E71-FFE2-4B2C-8AAD-04C137AD5706
online version: ''
schema: 2.0.0
ms.openlocfilehash: 1366e69f7da032aa243c2946b91788d165408dc86c3858e8b83f437b8695bdd5
ms.sourcegitcommit: 49f8ffe5d8e08ba3d22e3b2e76db0e54dd55d4f0
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/11/2021
ms.locfileid: "132418975"
---
# Get-AzureEffectiveRouteTable

## SYNOPSIS
Rute akan diterapkan di mesin virtual.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

### IaaSGetEffectiveRouteTableParamSet
```
Get-AzureEffectiveRouteTable -VM <PersistentVMRoleContext> -ServiceName <String>
 [-NetworkInterfaceName <String>] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### SlotGetEffectiveRouteTableParamSet
```
Get-AzureEffectiveRouteTable -ServiceName <String> [-Slot <String>] -RoleInstanceName <String>
 [-NetworkInterfaceName <String>] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureEffectiveRouteTable** akan mendapatkan rute yang diterapkan di mesin virtual.
Operasi ini dapat memakan waktu beberapa detik untuk selesai.

## EXAMPLES

### Contoh 1: Dapatkan rute efektif yang diterapkan mesin virtual
```
PS C:\> Get-AzureVM -ServiceName "ContosoService" -Name "ContosoVM06" | Get-AzureEffectiveRouteTable
```

Perintah ini mendapatkan mesin virtual bernama ContosoVM06 untuk layanan bernama ContosoService, dan meneruskan objek mesin virtual tersebut ke cmdlet saat ini.
Cmdlet saat ini akan menerapkan rute ke mesin virtual tersebut.

## PARAMETERS

### -NetworkInterfaceName
Menentukan nama adaptor jaringan tempat cmdlet ini mendapatkan rute efektif.

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

### -RoleInstanceName
Menentukan nama peran PaaS di mana cmdlet ini mendapatkan rute yang efektif.

```yaml
Type: String
Parameter Sets: SlotGetEffectiveRouteTableParamSet
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ServiceName
Menentukan nama layanan awan.
Peran PaaS di mana cmdlet ini mendapatkan rute efektif milik layanan yang ditentukan parameter ini.

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
Peran PaaS yang mendapatkan rute efektif dari cmdlet ini memiliki slot yang ditentukan parameter ini.
Nilai valid adalah: 

- Produksi
- Perekanan 

Nilai defaultnya adalah Produksi.

```yaml
Type: String
Parameter Sets: SlotGetEffectiveRouteTableParamSet
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VM
Menentukan objek mesin virtual tempat cmdlet mendapatkan rute efektif.

```yaml
Type: PersistentVMRoleContext
Parameter Sets: IaaSGetEffectiveRouteTableParamSet
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

## OUTPUTS

### System.Collections.Generic.IEnumerable<Microsoft.WindowsAzure.Management.Network.Models.EffectiveRouteTable, Microsoft.WindowsAzure.Management.Network>

## CATATAN

## RELATED LINKS

[Get-AzureRouteTable](./Get-AzureRouteTable.md)

[New-AzureRouteTable](./New-AzureRouteTable.md)

[Remove-AzureRouteTable](./Remove-AzureRouteTable.md)

[Remove-AzureSubnetRouteTable](./Remove-AzureSubnetRouteTable.md)

[Set-AzureSubnetRouteTable](./Set-AzureSubnetRouteTable.md)


