---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Batch.dll-Help.xml
Module Name: Az.Batch
ms.assetid: 07811B64-6A77-452C-B148-DE8C13E73DEF
online version: https://docs.microsoft.com/powershell/module/az.batch/get-azbatchremoteloginsetting
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Batch/Batch/help/Get-AzBatchRemoteLoginSetting.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Batch/Batch/help/Get-AzBatchRemoteLoginSetting.md
ms.openlocfilehash: bdb949a66ad268f69069af357679ac9c1d69d728
ms.sourcegitcommit: e109cc5320478db6aa8a52d49996b133007a65b9
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 01/12/2022
ms.locfileid: "136741389"
---
# Get-AzBatchRemoteLoginSetting

## SYNOPSIS
Dapatkan pengaturan masuk jarak jauh untuk simpul perhitungan.

## SYNTAX

### Id (Default)
```
Get-AzBatchRemoteLoginSetting [-PoolId] <String> [-ComputeNodeId] <String> -BatchContext <BatchAccountContext>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### InputObject
```
Get-AzBatchRemoteLoginSetting [[-ComputeNode] <PSComputeNode>] -BatchContext <BatchAccountContext>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzBatchRemoteLoginSetting** mendapatkan pengaturan masuk jarak jauh untuk simpul perhitungan dalam mesin virtual berbasis pool.

## EXAMPLES

### Contoh 1: Dapatkan pengaturan masuk jarak jauh untuk semua node dalam satu kolam
```
PS C:\>$Context = Get-AzBatchAccountKey -AccountName "ContosoBatchAccount"
PS C:\> Get-AzBatchComputeNode -PoolId "ContosoPool" -BatchContext $Context | Get-AzBatchRemoteLoginSetting -BatchContext $Context
IPAddress       Port
---------       ----
10.214.75.221   50002
10.214.75.221   50001
10.214.75.221   50000
```

Perintah pertama mendapatkan konteks akun kumpulan yang berisi kunci akses untuk langganan Anda dengan menggunakan **Get-AzBatchAccountKey**.
Perintah menyimpan konteks dalam variabel $Context digunakan di perintah berikutnya.
Perintah kedua mendapatkan setiap node perhitungan di pool yang memiliki ID ContosoPool dengan menggunakan **Get-AzBatchComputeNode**.
Perintah tersebut melewati setiap node komputer ke cmdlet saat ini menggunakan operator pipeline.
Perintah tersebut akan mendapatkan pengaturan masuk jarak jauh untuk setiap node perhitungan.

### Contoh 2: Dapatkan pengaturan masuk jarak jauh untuk simpul
```
PS C:\>$Context = Get-AzBatchAccountKey -AccountName "ContosoBatchAccount"
PS C:\> Get-AzBatchRemoteLoginSetting -PoolId "ContosoPool" -ComputeNodeId "tvm-1900272697_1-20150330t205553z" -BatchContext $Context
IPAddress       Port
---------       ----
10.214.75.221   50000
```

Perintah pertama mendapatkan konteks akun kumpulan yang berisi kunci akses untuk langganan Anda, lalu menyimpannya dalam variabel $Context tertentu.
Perintah kedua mendapatkan pengaturan masuk jarak jauh untuk node perhitungan yang memiliki ID tertentu di pool yang memiliki ID ContosoPool.

## PARAMETERS

### -BatchContext
Menentukan contoh **BatchAccountContext** yang digunakan cmdlet untuk berinteraksi dengan layanan Batch.
Untuk mendapatkan **BatchAccountContext** yang berisi tombol akses untuk langganan Anda, gunakan cmdlet Get-AzBatchAccountKey cmdlet.

```yaml
Type: Microsoft.Azure.Commands.Batch.BatchAccountContext
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ComputeNode
Menentukan node perhitungan, sebagai objek **PSComputeNode,** di mana cmdlet ini mendapatkan pengaturan masuk jarak jauh.
Untuk mendapatkan objek node perhitungan, gunakan Get-AzBatchComputeNode cmdlet.

```yaml
Type: Microsoft.Azure.Commands.Batch.Models.PSComputeNode
Parameter Sets: InputObject
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ComputeNodeId
Menentukan ID node perhitungan yang akan mendapatkan pengaturan masuk jarak jauh.
cmdlet ini mendapatkan pengaturan masuk jarak jauh.

```yaml
Type: System.String
Parameter Sets: Id
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PoolId
Menentukan ID pool yang berisi mesin virtual.

```yaml
Type: System.String
Parameter Sets: Id
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Batch.Models.PSComputeNode

### Microsoft.Azure.Commands.Batch.BatchAccountContext

## OUTPUTS

### Microsoft.Azure.Commands.Batch.Models.PSRemoteLoginSettings

## CATATAN

## RELATED LINKS

[Get-AzBatchAccountKey](./Get-AzBatchAccountKey.md)

[Get-AzBatchComputeNode](./Get-AzBatchComputeNode.md)

[Get-AzBatchRemoteDesktopProtocolFile](./Get-AzBatchRemoteDesktopProtocolFile.md)

[Cmdlet Kumpulan Azure](/powershell/module/Az.Batch/)
