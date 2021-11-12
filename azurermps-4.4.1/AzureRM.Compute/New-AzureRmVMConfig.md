---
external help file: Microsoft.Azure.Commands.Compute.dll-Help.xml
Module Name: AzureRM.Compute
ms.assetid: 1BECAC91-BB43-46EB-B2C9-C965C6FBC831
online version: ''
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Compute/Stack/Commands.Compute/help/New-AzureRmVMConfig.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Compute/Stack/Commands.Compute/help/New-AzureRmVMConfig.md
ms.openlocfilehash: 2022a8a830d868f412e505f23e65c4c297bea543
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132422369"
---
# New-AzureRmVMConfig

## SYNOPSIS
Membuat objek mesin virtual yang dapat dikonfigurasi.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
New-AzureRmVMConfig [-VMName] <String> [-VMSize] <String> [[-AvailabilitySetId] <String>]
 [[-LicenseType] <String>] [[-IdentityType] <ResourceIdentityType>] [-AssignIdentity] [-Zone <String[]>]
 [-Tags <Hashtable>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzureRmVMConfig** membuat objek mesin virtual lokal yang dapat dikonfigurasikan untuk Azure.
Cmdlet lain dapat digunakan untuk mengonfigurasi objek mesin virtual, seperti Set-AzureRmVMOperatingSystem, Set-AzureRmVMSourceImage, Add-AzureRmVMNetworkInterface, dan Set-AzureRmVMOSDisk.

## EXAMPLES

### Contoh 1: Membuat objek mesin virtual
```
PS C:\> $AvailabilitySet = Get-AzureRmAvailabilitySet -ResourceGroupName "ResourceGroup11" -Name "AvailabilitySet03"
PS C:\> $VirtualMachine = New-AzureRmVMConfig -VMName "VirtualMachine07" -VMSize "Standard_A1" -AvailabilitySetID $AvailabilitySet.Id
```

Perintah pertama mendapatkan kumpulan ketersediaan bernamaAblity TersediaSet03 dalam grup sumber daya yang bernama ResourceGroup11, lalu menyimpan objek tersebut dalam $AvailabilitySet sumber daya.

Perintah kedua membuat objek mesin virtual, lalu menyimpannya di $VirtualMachine variabel.
Perintah menetapkan nama dan ukuran ke komputer virtual.
Mesin virtual tersebut termasuk dalam kumpulan ketersediaan yang disimpan di $AvailabilitySet.

## PARAMETERS

### -AssignIdentity
Tentukan identitas yang ditetapkan sistem untuk komputer virtual.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -AvailabilitySetId
Menentukan ID kumpulan ketersediaan.
Untuk mendapatkan objek kumpulan ketersediaan, gunakan Get-AzureRmAvailabilitySet cmdlet.
Objek set ketersediaan berisi properti ID.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IdentityType
Identitas mesin virtual, jika dikonfigurasi.

```yaml
Type: System.Nullable`1[Microsoft.Azure.Management.Compute.Models.ResourceIdentityType]
Parameter Sets: (All)
Aliases: 
Accepted values: SystemAssigned

Required: False
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LicenseType
Tipe lisensi, yang akan membawa skenario lisensi Anda sendiri.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Tag
Tag yang dilampirkan ke sumber daya.

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases: Tag

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VMName
Menentukan nama untuk mesin virtual.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: ResourceName, Name

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VMSize
Menentukan ukuran untuk mesin virtual.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Zone
Menentukan daftar zona untuk mesin virtual.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

## OUTPUTS

## CATATAN

## RELATED LINKS

[Update-AzureRmVM](./Update-AzureRmVM.md)

[Set-AzureRmVMOperatingSystem](./Set-AzureRmVMOperatingSystem.md)

[Set-AzureRmVMSourceImage](./Set-AzureRmVMSourceImage.md)

[Get-AzureRmAvailabilitySet](./Get-AzureRmAvailabilitySet.md)


