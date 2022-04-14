---
external help file: Microsoft.Azure.Commands.Compute.dll-Help.xml
Module Name: AzureRM.Compute
ms.assetid: E6F2EE87-97C4-416A-9AE1-9FBD72062F0F
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.compute/remove-azurermvmss
schema: 2.0.0
ms.openlocfilehash: 0d7e14657d22ac8f8431e82b51cee81d62d5328f
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141889307"
---
# Remove-AzureRmVmss

## SYNOPSIS
Menghapus VMSS atau mesin virtual yang ada dalam VMSS.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Remove-AzureRmVmss [-ResourceGroupName] <String> [-VMScaleSetName] <String> [[-InstanceId] <String[]>] [-Force]
 [-AsJob] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Remove-AzureRmVmss** menghapus Kumpulan Skala Mesin Virtual (VMSS) dari Azure.
Cmdlet ini juga dapat digunakan untuk menghapus mesin virtual tertentu di dalam VMSS.
Anda dapat menggunakan parameter *InstanceId* untuk menghapus mesin virtual tertentu di dalam VMSS.

## EXAMPLES

### Contoh 1: Menghapus VMSS
```
PS C:\> Remove-AzureRmVmss -ResourceGroupName "Group001" -VMScaleSetName "VMScaleSet001"
```

Perintah ini menghapus VMSS bernama VMScaleSet001 yang termasuk dalam grup sumber daya bernama Group001.

### Contoh 2: Menghapus mesin virtual dari dalam VMSS
```
PS C:\> Remove-AzureRmVmss -ResourceGroupName "Group002" -VMScaleSetName "VMScaleSet002" -InstanceId "3";
```

Perintah ini menghapus mesin virtual dengan ID instans 3 dari VMSS bernama VMScaleSet002 yang termasuk dalam grup sumber daya bernama Group002.

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

### -InstanceId
Menentukan, sebagai array string, ID instans yang perlu dimulai.
Misalnya: `-InstanceId "0", "3"`

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

### -ResourceGroupName
Menentukan nama grup sumber daya tempat VMSS berada.

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
Spesies nama VMSS yang cmdlet ini hapus.
Jika Anda menentukan parameter *InstanceId* , cmdlet akan menghapus mesin virtual tertentu dari VMSS yang dinamai oleh parameter ini.

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
Default value: False
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
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak
Cmdlet ini tidak menerima input apa pun.

## OUTPUTS

### Microsoft.Azure.Commands.Compute.Automation.Models.PSOperationStatusResponse

## CATATAN

## RELATED LINKS

[Get-AzureRmVms](./Get-AzureRmVmss.md)

[AzureRmVms baru](./New-AzureRmVmss.md)

[Mulai ulang-AzureRmVms](./Restart-AzureRmVmss.md)

[Set-AzureRmVms](./Set-AzureRmVmss.md)

[Mulai AzureRmVms](./Start-AzureRmVmss.md)

[Stop-AzureRmVms](./Stop-AzureRmVmss.md)

[Pembaruan-AzureRmVms](./Update-AzureRmVmss.md)


