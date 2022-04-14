---
external help file: ''
Module Name: Az.Migrate
online version: https://docs.microsoft.com/powershell/module/az.migrate/get-azmigrateproject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Migrate/help/Get-AzMigrateProject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Migrate/help/Get-AzMigrateProject.md
ms.openlocfilehash: 6285d01c6c01cea42b7798662f552e58ea2546dd
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142083487"
---
# Get-AzMigrateProject

## SYNOPSIS
Metode untuk mendapatkan proyek migrasi.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.migrate/get-azmigrateproject) untuk informasi terbaru.

## SYNTAX

```
Get-AzMigrateProject -Name <String> -ResourceGroupName <String> [-SubscriptionId <String[]>]
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

## DESCRIPTION
Metode untuk mendapatkan proyek migrasi.

## EXAMPLES

### Contoh 1: Dapatkan
```powershell
PS C:\> Get-AzMigrateProject -SubscriptionId xxx-xxx-xxx -ResourceGroupName BugBashAVSVMware -Name BugBashAVSVMware

ETag Location      Name             Type
---- --------      ----             ----
     southeastasia BugBashAVSVMware Microsoft.Migrate/MigrateProjects
```

Metode untuk mendapatkan proyek migrasi.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases: AzureRMContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Nama proyek Migrasi Azure.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: MigrateProjectName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama Azure Resource Group yang melakukan migrasi proyek adalah bagian dari.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubscriptionId
Id Langganan Azure tempat proyek migrasi dibuat.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Migrate.Models.Api20180901Preview.IMigrateProject

## CATATAN

ALIAS

## RELATED LINKS

