---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Storage.Management.dll-Help.xml
Module Name: Az.Storage
online version: https://docs.microsoft.com/powershell/module/az.storage/invoke-azstorageaccounthierarchicalnamespaceupgrade
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Storage/Storage.Management/help/Invoke-AzStorageAccountHierarchicalNamespaceUpgrade.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Storage/Storage.Management/help/Invoke-AzStorageAccountHierarchicalNamespaceUpgrade.md
ms.openlocfilehash: fda26d2be0b5d98b51018c8136c0828f40409164
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144729968"
---
# Invoke-AzStorageAccountHierarchicalNamespaceUpgrade

## SYNOPSIS
Memvalidasi apakah akun penyimpanan dapat ditingkatkan untuk mengaktifkan HierarchicalNamespace, atau meningkatkan akun Storage ke HierarchicalNamespace yang diaktifkan.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.storage/invoke-azstorageaccounthierarchicalnamespaceupgrade) untuk informasi terbaru.

## SYNTAX

### AccountName (Default)
```
Invoke-AzStorageAccountHierarchicalNamespaceUpgrade [-ResourceGroupName] <String> [-Name] <String>
 -RequestType <String> [-Force] [-AsJob] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### AccountObject
```
Invoke-AzStorageAccountHierarchicalNamespaceUpgrade -InputObject <PSStorageAccount> -RequestType <String>
 [-Force] [-AsJob] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Invoke-AzStorageAccountHierarchicalNamespaceUpgrade** dapat memvalidasi apakah akun penyimpanan dapat ditingkatkan untuk mengaktifkan HierarchicalNamespace, atau meningkatkan akun Storage ke HierarchicalNamespace yang diaktifkan.

## EXAMPLES

### Contoh 1: Memvalidasi akun stroage dapat ditingkatkan untuk mengaktifkan HierarchicalNamespace, lalu meningkatkannya ke HierarchicalNamespace yang diaktifkan
```
PS C:\> Invoke-AzStorageAccountHierarchicalNamespaceUpgrade -ResourceGroupName $rgname -Name $accountName -RequestType Validation
True

PS C:\> $task = Invoke-AzStorageAccountHierarchicalNamespaceUpgrade -ResourceGroupName $rgname -Name $accountName -RequestType Upgrade -Force -AsJob

PS C:\> $task | Wait-Job
```

Perintah pertama memvalidasi apakah akun stroage dapat ditingkatkan untuk mengaktifkan HierarchicalNamespace. Perintah kedua meningkatkan akun penyimpanan untuk mengaktifkan HierarchicalNamespace. Karena peningkatan akan memakan waktu, gunakan '-Asjob' untuk menjalankannya di backend, dan mengembalikan tugas.  Kemudian tunggu tugas selesai.

## PARAMETERS

### -AsJob
Jalankan cmdlet di latar belakang

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

### -Force
Paksa untuk Failover Akun

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

### -InputObject
Storage objek akun

```yaml
Type: Microsoft.Azure.Commands.Management.Storage.Models.PSStorageAccount
Parameter Sets: AccountObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Storage Nama Akun.

```yaml
Type: System.String
Parameter Sets: AccountName
Aliases: StorageAccountName, AccountName

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RequestType
RequestType HierarchicalNamespaceUpgrade untuk dijalankan: 
- Validasi: Validasi apakah akun dapat ditingkatkan untuk mengaktifkan HierarchicalNamespace. 
- Peningkatan: Tingkatkan akun penyimpanan untuk mengaktifkan HierarchicalNamespace.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Validation, Upgrade

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama Grup Sumber Daya.

```yaml
Type: System.String
Parameter Sets: AccountName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm
Meminta Anda mengonfirmasi sebelum menjalankan cmdlet.

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
Menunjukkan yang akan terjadi jika cmdlet dijalankan.
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Microsoft.Azure.Commands.Management. Storage. Models.PSStorageAccount

## OUTPUTS

### Microsoft.Azure.Commands.Management. Storage. Models.PSStorageAccount

## NOTES

## RELATED LINKS
