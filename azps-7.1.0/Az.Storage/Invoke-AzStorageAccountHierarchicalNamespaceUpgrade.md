---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Storage.Management.dll-Help.xml
Module Name: Az.Storage
online version: https://docs.microsoft.com/powershell/module/az.storage/invoke-azstorageaccounthierarchicalnamespaceupgrade
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Storage/Storage.Management/help/Invoke-AzStorageAccountHierarchicalNamespaceUpgrade.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Storage/Storage.Management/help/Invoke-AzStorageAccountHierarchicalNamespaceUpgrade.md
ms.openlocfilehash: 09b729a1a30d1a7c927ad761b2b6b98623b315f0
ms.sourcegitcommit: e109cc5320478db6aa8a52d49996b133007a65b9
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 01/12/2022
ms.locfileid: "136750740"
---
# Invoke-AzStorageAccountHierarchicalNamespaceUpgrade

## SYNOPSIS
Memvalidasi jika akun penyimpanan dapat dimutakhirkan untuk mengaktifkan HierarchicalNamespace, atau memutakhirkan akun Storage ke mengaktifkan HierarchicalNamespace.

## SYNTAX

### Nama Akun (Default)
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
Cmdlet **Invoke-AzStorageAccountHierarchicalNamespaceUpgrade** dapat memvalidasi apakah akun penyimpanan dapat dimutakhirkan untuk mengaktifkan HierarchicalNamespace, atau memutakhirkan akun Storage ke mengaktifkan HierarchicalNamespace.

## EXAMPLES

### Contoh 1: Memvalidasi akunage dapat diupgrade untuk mengaktifkan HierarchicalNamespace, lalu memutakhirkan ke HierarchicalNamespace yang diaktifkan
```
PS C:\> Invoke-AzStorageAccountHierarchicalNamespaceUpgrade -ResourceGroupName $rgname -Name $accountName -RequestType Validation
True

PS C:\> $task = Invoke-AzStorageAccountHierarchicalNamespaceUpgrade -ResourceGroupName $rgname -Name $accountName -RequestType Upgrade -Force -AsJob

PS C:\> $task | Wait-Job
```

Perintah pertama memvalidasi jika akun space dapat dimutakhirkan untuk mengaktifkan HierarchicalNamespace. Perintah kedua, mutakhirkan akun penyimpanan untuk mengaktifkan HierarchicalNamespace. Karena pemutakhiran akan memakan waktu, gunakan '-Asjob' untuk menjalankannya dalam backend, dan mengembalikan tugas.  Kemudian, tunggu hingga tugas selesai.

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
Paksa ke Failover Akun

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

### -Nama
Storage Akun.

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
The HierarchicalNamespaceUpgrade requestType to run: 
- Validasi: Validasi jika akun dapat di mutakhirkan untuk mengaktifkan HierarchicalNamespace. 
- Pemutakhiran: Mutakhirkan akun penyimpanan untuk mengaktifkan HierarchicalNamespace.

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

### -Konfirmasi
Meminta konfirmasi Anda sebelum menjalankan cmdlet.

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
Cmdlet tidak berjalan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Management. Storage. Models.PSStorageAccount

## OUTPUTS

### Microsoft.Azure.Commands.Management. Storage. Models.PSStorageAccount

## CATATAN

## RELATED LINKS
