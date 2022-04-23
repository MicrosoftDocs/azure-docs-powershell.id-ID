---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Compute.dll-Help.xml
Module Name: Az.Compute
online version: https://docs.microsoft.com/powershell/module/az.compute/set-azdisksecurityprofile.md
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Set-AzDiskSecurityProfile.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Set-AzDiskSecurityProfile.md
ms.openlocfilehash: d26ecccf18cb8d43cd0efc307921064d4c260b7d
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143171873"
---
# Set-AzDiskSecurityProfile

## SYNOPSIS
Mengatur SecurityProfile pada disk yang dikelola

## SYNTAX

```
Set-AzDiskSecurityProfile [-Disk] <PSDisk> [-SecurityType <String>] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Mengatur SecurityProfile pada disk yang dikelola

## EXAMPLES

### Contoh 1
```powershell
$diskconfig = New-AzDiskConfig -DiskSizeGB 10 -AccountType PremiumLRS -OsType Windows -CreateOption FromImage;
$image = '/subscriptions/0000000-0000-0000-0000-000000000000/resourceGroups/ResourceGroup01/providers/Microsoft.Compute/images/TestImage123';        
$diskconfig = Set-AzDiskImageReference -Disk $diskconfig -Id $image -Lun 0;
$diskconfig = Set-AzDiskSecurityProfile -Disk $diskconfig -SecurityType "TrustedLaunch";
New-AzDisk -ResourceGroupName 'ResourceGroup01' -DiskName 'Disk01' -Disk $diskconfig;
#$disk.Properties.SecurityProfile.SecurityType == "TrustedLaunch";
```

Pelanggan dapat mengatur SecurityType disk terkelola.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Disk
Profil Keamanan Disk

```yaml
Type: PSDisk
Parameter Sets: (All)
Aliases: DiskSecurityProfile

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -SecurityType
Tipe Diska Keamanan

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Compute.Automation.Models.PSDisk

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Compute.Automation.Models.PSDisk

## NOTES

## RELATED LINKS
