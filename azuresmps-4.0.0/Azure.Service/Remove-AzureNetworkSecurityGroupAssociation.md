---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.Network.dll-Help.xml
ms.assetid: 3E3E0237-8E2D-4B3A-AD0C-2121DDE1AAB6
online version: ''
schema: 2.0.0
ms.openlocfilehash: 32ed03788f14eac65fdee9f3284f10dc4e9daab6
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142334990"
---
# Remove-AzureNetworkSecurityGroupAssociation

## SYNOPSIS
Menghapus grup keamanan jaringan.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

### RemoveNetworkSecurityGroupAssociationFromSubnet
```
Remove-AzureNetworkSecurityGroupAssociation -Name <String> -VirtualNetworkName <String> -SubnetName <String>
 [-Force] [-PassThru] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### RemoveNetworkSecurityGroupAssociationFromIaaSRole
```
Remove-AzureNetworkSecurityGroupAssociation -Name <String> -VM <PersistentVMRoleContext> -ServiceName <String>
 [-NetworkInterfaceName <String>] [-Force] [-PassThru] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### RemoveNetworkSecurityGroupAssociationFromPaaSRole
```
Remove-AzureNetworkSecurityGroupAssociation -Name <String> [-Slot <String>] -RoleName <String>
 -ServiceName <String> [-NetworkInterfaceName <String>] [-Force] [-PassThru] [-Profile <AzureSMProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Remove-AzureNetworkSecurityGroupAssociation** menghapus grup keamanan jaringan dari mesin virtual.

## EXAMPLES

### Contoh 1: Menghapus mesin virtual ke grup keamanan jaringan
```
PS C:\> Get-AzureVM -ServiceName "ContosoService" -Name "ContosoVM06" | Remove-AzureNetworkSecurityGroupAssociation -Name "ContosoNetworkSecurityGroup"
```

Perintah ini mendapatkan mesin virtual bernama ContosoVM06 untuk layanan bernama ContosoService, dan meneruskan objek mesin virtual tersebut ke cmdlet saat ini.
Cmdlet saat ini menghapus grup keamanan jaringan bernama ContosoNetworkSecurityGroup dari mesin virtual tersebut.

## PARAMETERS

### -Paksa
Memaksa perintah untuk berjalan tanpa meminta konfirmasi pengguna.

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

### -Nama
Menentukan nama grup keamanan jaringan yang dihapus cmdlet ini.

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

### -NetworkInterfaceName
Menentukan nama adapter jaringan tempat cmdlet ini menghapus grup keamanan jaringan.

```yaml
Type: String
Parameter Sets: RemoveNetworkSecurityGroupAssociationFromIaaSRole, RemoveNetworkSecurityGroupAssociationFromPaaSRole
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru
Mengembalikan objek yang mewakili item tempat Anda bekerja.
Secara default, cmdlet ini tidak menghasilkan output apa pun.

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

### -Profil
Menentukan profil Azure tempat cmdlet ini dibaca.
Jika Anda tidak menentukan profil, cmdlet ini akan dibaca dari profil default lokal.

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
Menentukan nama peran PaaS tempat cmdlet ini menghapus grup keamanan jaringan.

```yaml
Type: String
Parameter Sets: RemoveNetworkSecurityGroupAssociationFromPaaSRole
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ServiceName
Menentukan nama layanan awan.
Peran PaaS tempat cmdlet ini menghapus grup keamanan jaringan milik layanan yang ditentukan parameter ini.

```yaml
Type: String
Parameter Sets: RemoveNetworkSecurityGroupAssociationFromIaaSRole, RemoveNetworkSecurityGroupAssociationFromPaaSRole
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Slot
Menentukan slot PaaS.
Peran PaaS tempat cmdlet ini menghapus grup keamanan jaringan memiliki slot yang ditentukan parameter ini.
Nilai yang valid adalah:

- Produksi
- Pementasan

Nilai defaultnya adalah Produksi.

```yaml
Type: String
Parameter Sets: RemoveNetworkSecurityGroupAssociationFromPaaSRole
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubnetName
Menentukan nama subnet tempat cmdlet ini menghapus grup keamanan jaringan.

```yaml
Type: String
Parameter Sets: RemoveNetworkSecurityGroupAssociationFromSubnet
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualNetworkName
Menentukan nama jaringan virtual yang berisi subnet tempat cmdlet ini menghapus grup keamanan jaringan.

```yaml
Type: String
Parameter Sets: RemoveNetworkSecurityGroupAssociationFromSubnet
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
Parameter Sets: RemoveNetworkSecurityGroupAssociationFromIaaSRole
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### System.Boolean

## CATATAN

## RELATED LINKS

[Get-AzureNetworkSecurityGroupAssociation](./Get-AzureNetworkSecurityGroupAssociation.md)

[Set-AzureNetworkSecurityGroupAssociation](./Set-AzureNetworkSecurityGroupAssociation.md)
