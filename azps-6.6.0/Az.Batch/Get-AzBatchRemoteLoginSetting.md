---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Batch.dll-Help.xml
Module Name: Az.Batch
ms.assetid: 07811B64-6A77-452C-B148-DE8C13E73DEF
online version: https://docs.microsoft.com/powershell/module/az.batch/get-azbatchremoteloginsetting
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Batch/Batch/help/Get-AzBatchRemoteLoginSetting.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Batch/Batch/help/Get-AzBatchRemoteLoginSetting.md
ms.openlocfilehash: 0315a1fb1e406c39f737eb7f331cc608a0b178d0
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143033687"
---
# Get-AzBatchRemoteLoginSetting

## SYNOPSIS
Mendapatkan pengaturan masuk jarak jauh untuk simpul komputasi.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.batch/get-azbatchremoteloginsetting) untuk informasi terbaru.

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
Cmdlet **Get-AzBatchRemoteLoginSetting** mendapatkan pengaturan masuk jarak jauh untuk simpul komputasi di kumpulan berbasis infrastruktur komputer virtual.

## EXAMPLES

### Contoh 1: Mendapatkan pengaturan masuk jarak jauh untuk semua simpul dalam kumpulan
```
PS C:\>$Context = Get-AzBatchAccountKey -AccountName "ContosoBatchAccount"
PS C:\> Get-AzBatchComputeNode -PoolId "ContosoPool" -BatchContext $Context | Get-AzBatchRemoteLoginSetting -BatchContext $Context
IPAddress       Port
---------       ----
10.214.75.221   50002
10.214.75.221   50001
10.214.75.221   50000
```

Perintah pertama mendapatkan konteks akun batch yang berisi kunci akses untuk langganan Anda dengan menggunakan **Get-AzBatchAccountKey**.
Perintah menyimpan konteks dalam variabel $Context untuk digunakan dalam perintah berikutnya.
Perintah kedua mendapatkan setiap simpul komputasi di kumpulan yang memiliki ID ContosoPool dengan menggunakan **Get-AzBatchComputeNode**.
Perintah meneruskan setiap simpul komputer ke cmdlet saat ini dengan menggunakan operator alur.
Perintah mendapatkan pengaturan masuk jarak jauh untuk setiap simpul komputasi.

### Contoh 2: Mendapatkan pengaturan masuk jarak jauh untuk simpul
```
PS C:\>$Context = Get-AzBatchAccountKey -AccountName "ContosoBatchAccount"
PS C:\> Get-AzBatchRemoteLoginSetting -PoolId "ContosoPool" -ComputeNodeId "tvm-1900272697_1-20150330t205553z" -BatchContext $Context
IPAddress       Port
---------       ----
10.214.75.221   50000
```

Perintah pertama mendapatkan konteks akun batch yang berisi kunci akses untuk langganan Anda, lalu menyimpannya dalam variabel $Context.
Perintah kedua mendapatkan pengaturan masuk jarak jauh untuk simpul komputasi yang memiliki ID yang ditentukan di kumpulan yang memiliki ID ContosoPool.

## PARAMETERS

### -BatchContext
Menentukan instans **BatchAccountContext** yang digunakan cmdlet ini untuk berinteraksi dengan layanan Batch.
Untuk mendapatkan **BatchAccountContext** yang berisi kunci akses untuk langganan Anda, gunakan cmdlet Get-AzBatchAccountKey.

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
Menentukan simpul komputasi, sebagai objek **PSComputeNode** , di mana cmdlet ini mendapatkan pengaturan masuk jarak jauh.
Untuk mendapatkan objek simpul komputasi, gunakan cmdlet Get-AzBatchComputeNode.

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
Menentukan ID simpul komputasi untuk mendapatkan pengaturan masuk jarak jauh.
yang cmdlet ini mendapatkan pengaturan masuk jarak jauh.

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
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure.

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
Menentukan ID kumpulan yang berisi komputer virtual.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Microsoft.Azure.Commands.Batch.Models.PSComputeNode

### Microsoft.Azure.Commands.Batch.BatchAccountContext

## OUTPUTS

### Microsoft.Azure.Commands.Batch.Models.PSRemoteLoginSettings

## NOTES

## RELATED LINKS

[Get-AzBatchAccountKey](./Get-AzBatchAccountKey.md)

[Get-AzBatchComputeNode](./Get-AzBatchComputeNode.md)

[Get-AzBatchRemoteDesktopProtocolFile](./Get-AzBatchRemoteDesktopProtocolFile.md)

[Cmdlet Azure Batch](/powershell/module/Az.Batch/)
