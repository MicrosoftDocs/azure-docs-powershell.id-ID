---
external help file: Microsoft.Azure.Commands.Compute.dll-Help.xml
Module Name: AzureRM.Compute
ms.assetid: FC6BC096-DBC4-48DA-A366-B87EB18A0496
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.compute/get-azurermvmss
schema: 2.0.0
ms.openlocfilehash: ec66d20e0d9a63b8101b1a9a46410c9e64ac2079
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143054477"
---
# Get-AzureRmVmss

## SYNOPSIS
Mendapatkan properti VMSS.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### DefaultParameter (Default)
```
Get-AzureRmVmss [[-ResourceGroupName] <String>] [[-VMScaleSetName] <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### FriendMethod
```
Get-AzureRmVmss [[-ResourceGroupName] <String>] [[-VMScaleSetName] <String>] [-InstanceView]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureRmVmss** mendapatkan model dan tampilan instans Kumpulan Skala Mesin Virtual (VMSS).
Tampilan model adalah properti mesin virtual yang ditentukan pengguna.
Tampilan instans adalah status tingkat instans mesin virtual.
Tentukan parameter *Status* untuk mendapatkan hanya tampilan instans mesin virtual.

## EXAMPLES

### Contoh 1: Dapatkan properti VMSS
```
PS C:\> Get-AzureRmVmss -ResourceGroupName "Group001" -VMScaleSetName "VMSS001"
```

Perintah ini mendapatkan properti VMSS bernama VMSS001 yang termasuk dalam grup sumber daya bernama Group001.
Karena perintah tidak menentukan parameter switch *InstanceView* , cmdlet mendapatkan tampilan model mesin virtual.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure.

```yaml
Type: IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InstanceView
Menunjukkan bahwa cmdlet ini hanya mendapatkan tampilan instans mesin virtual.

```yaml
Type: SwitchParameter
Parameter Sets: FriendMethod
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Menentukan nama Grup Sumber Daya dari VMSS.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VMScaleSetName
Spesies nama VMSS.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Name

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak
Cmdlet ini tidak menerima input apa pun.

## OUTPUTS

### Cmdlet ini tidak menghasilkan output apa pun.

## NOTES

## RELATED LINKS

[AzureRmVms baru](./New-AzureRmVmss.md)

[Hapus-AzureRmVms](./Remove-AzureRmVmss.md)

[Mulai ulang-AzureRmVms](./Restart-AzureRmVmss.md)

[Set-AzureRmVms](./Set-AzureRmVmss.md)

[Mulai AzureRmVms](./Start-AzureRmVmss.md)

[Stop-AzureRmVms](./Stop-AzureRmVmss.md)

[Pembaruan-AzureRmVms](./Update-AzureRmVmss.md)


