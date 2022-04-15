---
external help file: Microsoft.Azure.Commands.OperationalInsights.dll-Help.xml
Module Name: AzureRM.OperationalInsights
ms.assetid: 7660F1A2-604D-4488-93F1-CB7C502F135E
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.operationalinsights/new-azurermoperationalinsightsstorageinsight
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/OperationalInsights/Commands.OperationalInsights/help/New-AzureRmOperationalInsightsStorageInsight.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/OperationalInsights/Commands.OperationalInsights/help/New-AzureRmOperationalInsightsStorageInsight.md
ms.openlocfilehash: 1bea5ce9eda22996eb65b6e5d26fb3af19cd1c88
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142136876"
---
# New-AzureRmOperationalInsightsStorageInsight

## SYNOPSIS
Membuat Storage Insight di dalam ruang kerja.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### ByWorkspaceName (Default)
```
New-AzureRmOperationalInsightsStorageInsight [-ResourceGroupName] <String> [-WorkspaceName] <String>
 [-Name] <String> [-StorageAccountResourceId] <String> [-StorageAccountKey] <String> [[-Tables] <String[]>]
 [[-Containers] <String[]>] [-Force] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ByWorkspaceObject
```
New-AzureRmOperationalInsightsStorageInsight [-Workspace] <PSWorkspace> [-Name] <String>
 [-StorageAccountResourceId] <String> [-StorageAccountKey] <String> [[-Tables] <String[]>]
 [[-Containers] <String[]>] [-Force] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzureRmOperationalInsightsStorageInsight** membuat Storage Insight baru di ruang kerja yang sudah ada.

## EXAMPLES

### Contoh 1: Membuat Storage Insight menurut nama
```
PS C:\>$Storage = Get-AzureRmStorageAccount -ResourceGroupName "ContosoResourceGroup" -Name "ContosoStorage"

PS C:\>$StorageKey = ($Storage | Get-AzureRmStorageAccountKey).Key1

PS C:\>New-AzureRmOperationalInsightsStorageInsight -ResourceGroupName "ContosoResourceGroup" -WorkspaceName "MyWorkspace" -Name "MyStorageInsight" -StorageAccountResourceId $Storage.Id -StorageAccountKey $StorageKey -Tables @("WADWindowsEventLogsTable")
```

Perintah pertama menggunakan cmdlet Get-AzureRmStorageAccount untuk mendapatkan akun penyimpanan bernama ContosoStorage, lalu menyimpannya dalam variabel $Storage.
Perintah kedua melewati akun penyimpanan dalam $Storage ke cmdlet Get-AzureRmStorageAccountKey dengan menggunakan operator pipeline untuk mendapatkan kunci akun penyimpanan yang ditentukan, lalu menyimpannya dalam variabel $StorageKey.
Perintah terakhir membuat wawasan penyimpanan bernama MyStorageInsight di ruang kerja bernama MyWorkspace.
Wawasan penyimpanan ini menggunakan data dari tabel WADWindowsEventLogsTable dalam sumber daya akun penyimpanan tertentu.

### Contoh 2: Membuat Storage Insight menggunakan objek ruang kerja
```
PS C:\>$Workspace = Get-AzureRmOperationalInsightsWorkspace -ResourceGroupName "ContosoResourceGroup" -Name "MyWorkspace"

PS C:\>$Storage = Get-AzureRmStorageAccount -ResourceGroupName "ContosoResourceGroup" -Name "ContosoStorage"

PS C:\>$StorageKey = ($Storage | Get-AzureRmStorageAccountKey).Key1

PS C:\>New-AzureRmOperationalInsightsStorageInsight -Workspace $Workspace -Name "MyStorageInsight" -StorageAccountResourceId $Storage.Id -StorageAccountKey $StorageKey -Tables @("WADWindowsEventLogsTable")
```

Perintah pertama menggunakan cmdlet Get-AzureRmOperationalInsightsWorkspace untuk mendapatkan ruang kerja bernama MyWorkspace, lalu menyimpannya dalam variabel $Workspace.
Perintah kedua menggunakan cmdlet Get-AzureRmStorageAccount untuk mendapatkan akun penyimpanan yang ditentukan, lalu menyimpannya dalam variabel $Storage.
Perintah ketiga melewati akun penyimpanan dalam $Storage ke cmdlet Get-AzureRmStorageAccountKey menggunakan operator pipeline untuk mendapatkan kunci yang ditentukan, lalu menyimpannya dalam variabel $StorageKey.
Perintah akhir membuat wawasan penyimpanan bernama MyStorageInsight di ruang kerja yang ditentukan dalam $Workspace.
Storage Insight menggunakan data dari tabel WADWindowsEventLogsTable dalam sumber daya akun penyimpanan tertentu.

## PARAMETERS

### -Kontainer
Menentukan daftar wadah yang berisi data.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 7
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure

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

### -Paksa
Memaksa perintah untuk berjalan tanpa meminta konfirmasi pengguna.

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

### -Nama
Menentukan nama Storage Insight.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Menentukan nama grup sumber daya Azure yang berisi ruang kerja.

```yaml
Type: System.String
Parameter Sets: ByWorkspaceName
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StorageAccountKey
Menentukan kunci akses untuk akun penyimpanan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 5
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StorageAccountResourceId
Menentukan sumber daya Azure dari akun penyimpanan.
Ini dapat diambil dengan menjalankan cmdlet Get-AzureRmStorageAccount dan mengakses parameter *Id* dari hasilnya.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Tabel
Menentukan daftar tabel yang menyediakan data.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 6
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Ruang Kerja
Menentukan ruang kerja untuk Storage Insight yang baru.

```yaml
Type: Microsoft.Azure.Commands.OperationalInsights.Models.PSWorkspace
Parameter Sets: ByWorkspaceObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Nama Ruang Kerja
Menentukan nama ruang kerja yang sudah ada.

```yaml
Type: System.String
Parameter Sets: ByWorkspaceName
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Default value: False
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
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.OperationalInsights.Models.PSWorkspace
Parameter: Ruang Kerja (ByValue)

### System.String

### System.String[]

## OUTPUTS

### Microsoft.Azure.Commands.OperationalInsights.Models.PSStorageInsight

## CATATAN

## RELATED LINKS

[Cmdlet Insights Operasional Azure](./AzureRM.OperationalInsights.md)

[Get-AzureRmOperationalInsightsWorkspace](./Get-AzureRmOperationalInsightsWorkspace.md)


