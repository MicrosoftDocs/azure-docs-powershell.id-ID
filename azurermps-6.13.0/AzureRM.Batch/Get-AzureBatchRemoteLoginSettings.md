---
external help file: Microsoft.Azure.Commands.Batch.dll-Help.xml
Module Name: AzureRM.Batch
ms.assetid: 07811B64-6A77-452C-B148-DE8C13E73DEF
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.batch/get-azurebatchremoteloginsettings
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/AzureBatch/Commands.Batch/help/Get-AzureBatchRemoteLoginSettings.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/AzureBatch/Commands.Batch/help/Get-AzureBatchRemoteLoginSettings.md
ms.openlocfilehash: d25e9aeb75c58bcce560043d87f5ce9eef065b97
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141844798"
---
# Get-AzureBatchRemoteLoginSettings

## SYNOPSIS
Mendapatkan pengaturan masuk jarak jauh untuk simpul komputasi.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### Id (Default)
```
Get-AzureBatchRemoteLoginSettings [-PoolId] <String> [-ComputeNodeId] <String>
 -BatchContext <BatchAccountContext> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### InputObject
```
Get-AzureBatchRemoteLoginSettings [[-ComputeNode] <PSComputeNode>] -BatchContext <BatchAccountContext>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureBatchRemoteLoginSettings** mendapatkan pengaturan masuk jarak jauh untuk simpul komputasi di kumpulan berbasis infrastruktur mesin virtual.

## EXAMPLES

### Contoh 1: Dapatkan pengaturan masuk jarak jauh untuk semua node dalam kumpulan
```
PS C:\>$Context = Get-AzureRmBatchAccountKeys -AccountName "ContosoBatchAccount"
PS C:\> Get-AzureBatchComputeNode -PoolId "ContosoPool" -BatchContext $Context | Get-AzureBatchRemoteLoginSettings -BatchContext $Context
IPAddress       Port
---------       ----
10.214.75.221   50002
10.214.75.221   50001
10.214.75.221   50000
```

Perintah pertama mendapatkan konteks akun kumpulan yang berisi kunci akses untuk langganan Anda menggunakan **Get-AzureRmBatchAccountKeys**.
Perintah menyimpan konteks dalam variabel $Context untuk digunakan dalam perintah berikutnya.
Perintah kedua mendapatkan setiap node komputasi dalam kumpulan yang memiliki ID ContosoPool menggunakan **Get-AzureBatchComputeNode**.
Perintah melewati setiap simpul komputer ke cmdlet saat ini menggunakan operator pipeline.
Perintah mendapatkan pengaturan masuk jarak jauh untuk setiap simpul komputasi.

### Contoh 2: Dapatkan pengaturan masuk jarak jauh untuk simpul
```
PS C:\>$Context = Get-AzureRmBatchAccountKeys -AccountName "ContosoBatchAccount"
PS C:\> Get-AzureBatchRemoteLoginSettings -PoolId "ContosoPool" -ComputeNodeId "tvm-1900272697_1-20150330t205553z" -BatchContext $Context
IPAddress       Port
---------       ----
10.214.75.221   50000
```

Perintah pertama mendapatkan konteks akun kumpulan yang berisi kunci akses untuk langganan Anda, lalu menyimpannya dalam variabel $Context.
Perintah kedua mendapatkan pengaturan masuk jarak jauh untuk simpul komputasi yang memiliki ID tertentu dalam kumpulan yang memiliki ID ContosoPool.

## PARAMETERS

### -BatchContext
Menentukan instans **BatchAccountContext** yang digunakan cmdlet ini untuk berinteraksi dengan layanan Batch.
Untuk mendapatkan **BatchAccountContext** yang berisi kunci akses untuk langganan Anda, gunakan cmdlet Get-AzureRmBatchAccountKeys.

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
Untuk mendapatkan objek node komputasi, gunakan cmdlet Get-AzureBatchComputeNode.

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
di mana cmdlet ini mendapatkan pengaturan masuk jarak jauh.

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
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PoolId
Menentukan ID kumpulan yang berisi mesin virtual.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Batch.Models.PSComputeNode
Parameter: ComputeNode (ByValue)

### Microsoft.Azure.Commands.Batch.BatchAccountContext
Parameter: BatchContext (ByValue)

## OUTPUTS

### Microsoft.Azure.Commands.Batch.Models.PSRemoteLoginSettings

## CATATAN

## RELATED LINKS

[Get-AzureRmBatchAccountKeys](./Get-AzureRmBatchAccountKeys.md)

[Get-AzureBatchComputeNode](./Get-AzureBatchComputeNode.md)

[Get-AzureBatchRemoteDesktopProtocolFile](./Get-AzureBatchRemoteDesktopProtocolFile.md)

[Cmdlet Azure Batch](./AzureRM.Batch.md)


