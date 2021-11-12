---
external help file: Microsoft.Azure.Commands.Compute.dll-Help.xml
ms.assetid: CAA3E6A9-7E1A-4D57-A269-0B2D3D9C3BEC
online version: ''
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Compute/Stack/Commands.Compute/help/Get-AzureRMVMSqlServerExtension.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Compute/Stack/Commands.Compute/help/Get-AzureRMVMSqlServerExtension.md
ms.openlocfilehash: a6f2ed82835cca252f905cb53c5ddd9c8530900a
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132420836"
---
# Get-AzureRmVMSqlServerExtension

## SYNOPSIS
Dapatkan pengaturan untuk ekstensi SQL Server di komputer virtual.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Get-AzureRmVMSqlServerExtension [-ResourceGroupName] <String> [-VMName] <String> [[-Name] <String>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureRmVMSqlServerExtension** mendapatkan pengaturan infrastruktur SQL Server sebagai Agen layanan (IaaS) di komputer virtual.

## EXAMPLES

### Contoh 1: Dapatkan pengaturan ekstensi SQL Server di mesin virtual
```
PS C:\> Get-AzureRmVMSqlServerExtension -ResourceGroupName "ResourceGroup11" -VMName "ContosoVM07"
ExtensionName        : SqlIaaSAgent
Publisher            : Microsoft.SqlServer.Management
Version              : 1.0
State                : Enable
RoleName             : VMName
AutoPatchingSettings : Microsoft.WindowsAzure.Commands.ServiceManagement.IaaS.Extensions.AutoPatchingSettings
AutoBackupSettings   : Microsoft.WindowsAzure.Commands.ServiceManagement.IaaS.Extensions.AutoBackupSettings
```

Perintah ini mendapatkan pengaturan ekstensi SQL Server pada komputer virtual bernama ContosoVM07.

### Contoh 2: Dapatkan pengaturan dengan menggunakan saluran
```
PS C:\> Get-AzureRmVM -ServiceName "Service08" -Name "ContosoVM22" | Get-AzureRmVMSqlServerExtension
ExtensionName        : SqlIaaSAgent
Publisher            : Microsoft.SqlServer.Management
Version              : 1.0
State                : Enable
RoleName             : VMName
AutoPatchingSettings : Microsoft.WindowsAzure.Commands.ServiceManagement.IaaS.Extensions.AutoPatchingSettings
AutoBackupSettings   : Microsoft.WindowsAzure.Commands.ServiceManagement.IaaS.Extensions.AutoBackupSettings
```

Perintah ini mendapatkan mesin virtual bernama ContosoVM22 di layanan Service08 menggunakan cmdlet Get-AzureRmVM cmdlet.
Perintah itu menyampaikan hasilnya ke cmdlet saat ini dengan menggunakan operator pipeline.

Perintah saat ini mendapatkan pengaturan Agen IaaS SQL Server di komputer virtual tersebut.

### Contoh 3: Dapatkan pengaturan versi SQL Server tertentu
```
PS C:\> Get-AzureRmVMSqlServerExtension -ResourceGroupName "ResourceGroup11" -VMName "ContosoVM07" -Version "1.0"
ExtensionName        : SqlIaaSAgent
Publisher            : Microsoft.SqlServer.Management
Version              : 1.0
State                : Enable
RoleName             : VMName
AutoPatchingSettings : Microsoft.WindowsAzure.Commands.ServiceManagement.IaaS.Extensions.AutoPatchingSettings
AutoBackupSettings   : Microsoft.WindowsAzure.Commands.ServiceManagement.IaaS.Extensions.AutoBackupSettings
```

Perintah ini mendapatkan pengaturan ekstensi SQL Server 1.0 versi 1.0 di komputer virtual bernama ContosoVM07.

## PARAMETERS

### -Nama
Menentukan nama SQL Server ekstensi.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Menentukan nama grup sumber daya komputer virtual.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VMName
Menentukan nama mesin virtual.

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### Tidak ada
Cmdlet ini tidak menerima input apa pun.

## OUTPUTS

## CATATAN

## RELATED LINKS

[Get-AzureRmVM](./Get-AzureRmVM.md)

[Remove-AzureRmVMSqlServerExtension](./Remove-AzureRMVMSqlServerExtension.md)

[Set-AzureRmVMSqlServerExtension](./Set-AzureRMVMSqlServerExtension.md)


