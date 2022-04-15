---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.Network.dll-Help.xml
ms.assetid: 6AF7D392-8C8B-4695-95D0-E927093F654A
online version: ''
schema: 2.0.0
ms.openlocfilehash: a93ffdc2d8a3e524d289b065f6710557f00c66a7
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142313539"
---
# Get-AzureNetworkSecurityGroupAssociation

## SYNOPSIS
Mendapatkan grup keamanan jaringan untuk mesin virtual, adaptor jaringan, atau peran PaaS.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

### GetNetworkSecurityGroupAssociationForSubnet
```
Get-AzureNetworkSecurityGroupAssociation -VirtualNetworkName <String> -SubnetName <String> [-Detailed]
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### GetNetworkSecurityGroupAssociationForIaaSRole
```
Get-AzureNetworkSecurityGroupAssociation -VM <PersistentVMRoleContext> -ServiceName <String>
 [-NetworkInterfaceName <String>] [-Detailed] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### GetNetworkSecurityGroupAssociationForPaaSRole
```
Get-AzureNetworkSecurityGroupAssociation [-Slot <String>] -RoleName <String> -ServiceName <String>
 [-NetworkInterfaceName <String>] [-Detailed] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureNetworkSecurityGroupAssociation** mendapatkan grup keamanan jaringan untuk mesin virtual, adaptor jaringan, atau platform sebagai peran layanan (PaaS).

## EXAMPLES

### Contoh 1: Dapatkan grup keamanan jaringan untuk mesin virtual
```
PS C:\> Get-AzureVM -ServiceName "ContosoService" -Name "ContosoVM06" | Get-AzureNetworkSecurityGroupAssociation
```

Perintah ini mendapatkan mesin virtual bernama ContosoVM06 untuk layanan bernama ContosoService, dan meneruskan objek mesin virtual tersebut ke cmdlet saat ini.
Cmdlet saat ini mendapatkan grup keamanan jaringan yang terkait dengan mesin virtual tersebut.

## PARAMETERS

### -Detail
Menunjukkan bahwa cmdlet ini mengembalikan detail grup keamanan jaringan yang terkait dengan mesin virtual.
Detail ini mencakup lokasi dan aturan.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NetworkInterfaceName
Menentukan nama adapter jaringan di mana cmdlet ini mendapatkan grup keamanan jaringan.

```yaml
Type: String
Parameter Sets: GetNetworkSecurityGroupAssociationForIaaSRole, GetNetworkSecurityGroupAssociationForPaaSRole
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
Menentukan nama peran PaaS tempat cmdlet ini mendapatkan grup keamanan jaringan.

```yaml
Type: String
Parameter Sets: GetNetworkSecurityGroupAssociationForPaaSRole
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
Parameter Sets: GetNetworkSecurityGroupAssociationForIaaSRole, GetNetworkSecurityGroupAssociationForPaaSRole
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Slot
Menentukan slot PaaS.
Peran PaaS di mana cmdlet ini mendapatkan grup keamanan jaringan memiliki slot yang ditentukan parameter ini.
Nilai yang valid adalah: 

- Produksi
- Pementasan 

Nilai defaultnya adalah Produksi.

```yaml
Type: String
Parameter Sets: GetNetworkSecurityGroupAssociationForPaaSRole
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubnetName
Menentukan nama subnet tempat cmdlet ini mendapatkan grup keamanan jaringan.

```yaml
Type: String
Parameter Sets: GetNetworkSecurityGroupAssociationForSubnet
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualNetworkName
Menentukan nama jaringan virtual yang berisi subnet tempat cmdlet ini mendapatkan grup keamanan jaringan.

```yaml
Type: String
Parameter Sets: GetNetworkSecurityGroupAssociationForSubnet
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VM
Menentukan mesin virtual tempat cmdlet ini menerapkan grup keamanan jaringan.

```yaml
Type: PersistentVMRoleContext
Parameter Sets: GetNetworkSecurityGroupAssociationForIaaSRole
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

### Microsoft.WindowsAzure.Commands.ServiceManagement.Network.NetworkSecurityGroup.Model.INetworkSecurityGroup

## CATATAN

## RELATED LINKS

[Remove-AzureNetworkSecurityGroupAssociation](./Remove-AzureNetworkSecurityGroupAssociation.md)

[Set-AzureNetworkSecurityGroupAssociation](./Set-AzureNetworkSecurityGroupAssociation.md)


