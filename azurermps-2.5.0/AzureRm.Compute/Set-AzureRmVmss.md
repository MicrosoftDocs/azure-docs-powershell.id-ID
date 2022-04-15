---
external help file: Microsoft.Azure.Commands.Compute.dll-Help.xml
Module Name: AzureRM.Compute
ms.assetid: 6442E5BB-D59D-483B-8AC5-2586C6C1E925
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.compute/set-azurermvmss
schema: 2.0.0
ms.openlocfilehash: 2d33f111928d0b022c7836d0b5c86fb5ec6f203e
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141929556"
---
# Set-AzureRmVmss

## SYNOPSIS
Mengatur tindakan tertentu pada VMSS tertentu.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### DefaultParameter (Default)
```
Set-AzureRmVmss [-ResourceGroupName] <String> [-VMScaleSetName] <String> [[-InstanceId] <String[]>] [-Reimage]
 [-AsJob] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### FriendMethod
```
Set-AzureRmVmss [-ResourceGroupName] <String> [-VMScaleSetName] <String> [[-InstanceId] <String[]>]
 [-ReimageAll] [-AsJob] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzureRmVmss** mengatur tindakan tertentu pada Kumpulan Skala Mesin Virtual (VMSS).
Satu-satunya tindakan yang didukung cmdlet ini adalah Reimage.

## EXAMPLES

### Contoh 1: Menginisiasi ulang VMSS
```
PS C:\> Set-AzureRmVmss -Reimage -ResourceGroupName "ContosoGroup" -VMScaleSetName "ContosoVMSS"
```

Perintah ini mengoptimalkan VMSS bernama ContosoVMSS yang termasuk dalam grup sumber daya bernama ContosoGroup.

## PARAMETERS

### -AsJob
Jalankan cmdlet di latar belakang dan kembalikan Job untuk melacak kemajuan.

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

### -InstanceId
ID instans mesin virtual.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Reimage
Menunjukkan bahwa cmdlet mereimageS VMSS.

```yaml
Type: SwitchParameter
Parameter Sets: DefaultParameter
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ReimageSemua
Menunjukkan bahwa cmdlet mereimage semua disk dalam VMSS.

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
Menentukan nama grup sumber daya VMSS.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VMScaleSetName
Spesies nama VMSS tempat cmdlet ini mengatur tindakan.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Name

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Konfirmasi
Meminta konfirmasi sebelum menjalankan cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan. Cmdlet tidak dijalankan.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak
Cmdlet ini tidak menerima input apa pun.

## OUTPUTS

### Cmdlet ini tidak menghasilkan output apa pun.

## CATATAN

## RELATED LINKS

[Get-AzureRmVms](./Get-AzureRmVmss.md)

[AzureRmVms baru](./New-AzureRmVmss.md)

[Hapus-AzureRmVms](./Remove-AzureRmVmss.md)

[Mulai ulang-AzureRmVms](./Restart-AzureRmVmss.md)

[Mulai AzureRmVms](./Start-AzureRmVmss.md)

[Stop-AzureRmVms](./Stop-AzureRmVmss.md)

[Pembaruan-AzureRmVms](./Update-AzureRmVmss.md)


