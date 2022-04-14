---
external help file: ''
Module Name: Az.CustomProviders
online version: https://docs.microsoft.com/powershell/module/az.customproviders/new-azcustomproviderassociation
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CustomProviders/help/New-AzCustomProviderAssociation.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CustomProviders/help/New-AzCustomProviderAssociation.md
ms.openlocfilehash: 742e2827da6b7feb85e091b1eb089340eb0d8c09
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142113731"
---
# New-AzCustomProviderAssociation

## SYNOPSIS
Membuat atau memperbarui asosiasi.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.customproviders/new-azcustomproviderassociation) untuk informasi terbaru.

## SYNTAX

```
New-AzCustomProviderAssociation -Name <String> -Scope <String> [-TargetResourceId <String>]
 [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Membuat atau memperbarui asosiasi.

## EXAMPLES

### Contoh 1: Membuat asosiasi penyedia kustom
```powershell
$provider = Get-AzCustomProvider -ResourceGroupName myRg -Name Namespace.Type
New-AzCustomProviderAssociation -Scope $resourceId -Name MyAssoc -TargetResourceId $provider.Id
```

```output
Location  Name     Type
--------  ----     ----
East US 2 MyAssoc  Microsoft.CustomProviders/associations
```

Buat asosiasi penyedia kustom, provioder target terkait harus dikonfigurasi dengan benar dengan rute untuk "asosiasi"

## PARAMETERS

### -AsJob
Menjalankan perintah sebagai pekerjaan

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
Nama asosiasi.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: AssociationName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoWait
Jalankan perintah secara asinkron

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

### -Lingkup
Lingkup asosiasi.
Lingkup dapat berupa instans sumber daya REST apa pun yang valid.
Misalnya, gunakan '/subscriptions/{subscription-id}/resourceGroups/{resource-group-name}/providers/Microsoft.Compute/virtualMachines/{vm-name}' untuk sumber daya mesin virtual.

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

### -TargetResourceId
Contoh sumber daya REST dari sumber daya target untuk asosiasi ini.

```yaml
Type: System.String
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.CustomProviders.Models.Api20180901Preview.IAssociation

## CATATAN

ALIAS

## RELATED LINKS

