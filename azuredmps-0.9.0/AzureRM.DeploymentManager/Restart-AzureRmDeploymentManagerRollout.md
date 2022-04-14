---
external help file: Microsoft.Azure.Commands.DeploymentManager.dll-Help.xml
Module Name: AzureRM.DeploymentManager
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.deploymentmanager/restart-azurermdeploymentmanagerrollout
schema: 2.0.0
ms.openlocfilehash: ee1ef6e5b8bcee4af1d3aef67767269042c552df
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141782657"
---
# Restart-AzureRmDeploymentManagerRollout

## SYNOPSIS
Mulai ulang peluncuran yang gagal.

## SYNTAX

### Interaktif (Default)
```
Restart-AzureRmDeploymentManagerRollout [-ResourceGroupName] <String> [-Name] <String> [-SkipSucceeded]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ResourceId
```
Restart-AzureRmDeploymentManagerRollout [-ResourceId] <String> [-SkipSucceeded]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject
```
Restart-AzureRmDeploymentManagerRollout [-Rollout] <PSRollout> [-SkipSucceeded]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Restart-AzureRmDeploymentManagerRollout** memulai ulang peluncuran yang gagal, dan mengembalikan objek yang mewakili peluncuran tersebut dengan semua informasi mendetail tentang kemajuan peluncuran.
Tentukan peluncuran menurut nama dan nama grup sumber dayanya. Alternatifnya, Anda dapat menyediakan objek Rollout atau ResourceId.
Parameter opsional SkipSucceed memungkinkan Anda melewati semua langkah yang berhasil dalam peluncuran sebelumnya.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> Restart-AzureRmDeploymentManagerRollout -ResourceGroupName ContosoResourceGroup -Name ContosoRollout -SkipSucceeded
```

Perintah ini memulai ulang peluncuran bernama ContosoRollout di ContosoResourceGroup. Bendera Dilewati menunjukkan bahwa semua langkah yang sudah berjalan berhasil harus dilewati dan peluncuran harus dilanjutkan eksekusi dari tempat terakhir gagal.

### Contoh 2: Memulai ulang peluncuran menggunakan pengidentifikasi sumber daya
```powershell
PS C:\> Restart-AzureRmDeploymentManagerRollout -ResourceId "/subscriptions/subscriptionId/resourcegroups/ContosoResourceGroup/providers/Microsoft.DeploymentManager/rollouts/ContosoRollout"
```

Perintah ini memulai ulang peluncuran bernama ContosoRollout di ContosoResourceGroup.

### Contoh 3: Mulai ulang peluncuran menggunakan objek peluncuran.
```powershell
PS C:\> Get-AzureRmDeploymentManagerRollout -Rollout $rolloutObject
```

Perintah ini memulai ulang peluncuran yang nama dan ResourceGroupnya masing-masing cocok dengan properti Nama dan ResourceGroupName $rolloutObject.

## PARAMETERS

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

### -Nama
Nama peluncuran.

```yaml
Type: System.String
Parameter Sets: Interactive
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Grup sumber daya.

```yaml
Type: System.String
Parameter Sets: Interactive
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceId
Pengidentifikasi sumber daya.

```yaml
Type: System.String
Parameter Sets: ResourceId
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Peluncuran
Sumber daya yang akan dihapus.

```yaml
Type: Microsoft.Azure.Commands.DeploymentManager.Models.PSRollout
Parameter Sets: InputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -SkipSucceed
Lewati langkah-langkah yang berhasil dalam peluncuran sebelumnya.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Konfirmasi
Meminta konfirmasi sebelum menjalankan cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan.
Cmdlet tidak dijalankan.

```yaml
Type: System.Management.Automation.SwitchParameter
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

### Microsoft.Azure.Commands.DeploymentManager.Models.PSRollout

## OUTPUTS

### Microsoft.Azure.Commands.DeploymentManager.Models.PSRollout

## CATATAN

## RELATED LINKS

[Get-AzureRmDeploymentManagerRollout](./Get-AzureRmDeploymentManagerRollout.md)

[Stop-AzureRmDeploymentManagerRollout](./Stop-AzureRmDeploymentManagerRollout.md)

[Hapus-AzureRmDeploymentManagerRollout](./Remove-AzureRmDeploymentManagerRollout.md)