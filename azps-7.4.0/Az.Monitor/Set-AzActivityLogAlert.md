---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Monitor.dll-Help.xml
Module Name: Az.Monitor
ms.assetid: 7436F31F-9DCB-4365-BA6D-41BDB5D7FCB6
online version: https://docs.microsoft.com/powershell/module/az.monitor/set-azactivitylogalert
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Monitor/Monitor/help/Set-AzActivityLogAlert.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Monitor/Monitor/help/Set-AzActivityLogAlert.md
ms.openlocfilehash: 199693b23f4eb35c198dd19095f3e722796851a2
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144719300"
---
# Set-AzActivityLogAlert

## SYNOPSIS
Membuat baru atau menetapkan pemberitahuan log aktivitas yang sudah ada.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.monitor/set-azactivitylogalert) untuk informasi terbaru.

## SYNTAX

### SetByNameAndResourceGroup
```
Set-AzActivityLogAlert -Location <String> -Name <String> -ResourceGroupName <String>
 -Scope <System.Collections.Generic.List`1[System.String]>
 -Condition <System.Collections.Generic.List`1[Microsoft.Azure.Management.Monitor.Management.Models.ActivityLogAlertLeafCondition]>
 -Action <System.Collections.Generic.List`1[Microsoft.Azure.Management.Monitor.Management.Models.ActivityLogAlertActionGroup]>
 [-DisableAlert] [-Description <String>]
 [-Tag <System.Collections.Generic.Dictionary`2[System.String,System.String]>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### SetByResourceId
```
Set-AzActivityLogAlert [-Location <String>] [-Scope <System.Collections.Generic.List`1[System.String]>]
 [-Condition <System.Collections.Generic.List`1[Microsoft.Azure.Management.Monitor.Management.Models.ActivityLogAlertLeafCondition]>]
 [-Action <System.Collections.Generic.List`1[Microsoft.Azure.Management.Monitor.Management.Models.ActivityLogAlertActionGroup]>]
 [-DisableAlert] [-Description <String>]
 [-Tag <System.Collections.Generic.Dictionary`2[System.String,System.String]>] -ResourceId <String>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### SetByInputObject
```
Set-AzActivityLogAlert [-Scope <System.Collections.Generic.List`1[System.String]>]
 [-Condition <System.Collections.Generic.List`1[Microsoft.Azure.Management.Monitor.Management.Models.ActivityLogAlertLeafCondition]>]
 [-Action <System.Collections.Generic.List`1[Microsoft.Azure.Management.Monitor.Management.Models.ActivityLogAlertActionGroup]>]
 [-Description <String>] [-Tag <System.Collections.Generic.Dictionary`2[System.String,System.String]>]
 -InputObject <PSActivityLogAlertResource> [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzActivityLogAlert** membuat baru atau mengatur pemberitahuan log aktivitas yang ada.
Untuk tag, kondisi, dan tindakan objek harus dibuat terlebih dahulu dan diteruskan sebagai parameter dalam panggilan ini sebagai dipisahkan koma (lihat contoh di bawah).
Cmdlet ini mengimplementasikan pola ShouldProcess, yaitu mungkin meminta konfirmasi dari pengguna sebelum benar-benar membuat/memodifikasi sumber daya.
**CATATAN**: Cmdlet ini dan yang terkait menggantikan **Add-AzLogAlertRule** yang tidak digunakan lagi (November 2017).

## EXAMPLES

### Contoh 1: Membuat Pemberitahuan Log Aktivitas
```powershell
$location = 'Global'
$alertName = 'myAlert'
$resourceGroupName = 'theResourceGroupName'
$condition1 = New-AzActivityLogAlertCondition -Field 'field1' -Equal 'equals1'
$condition2 = New-AzActivityLogAlertCondition -Field 'field2' -Equal 'equals2'
$dict = New-Object "System.Collections.Generic.Dictionary``2[System.String,System.String]"
$dict.Add('key1', 'value1')
$actionGrp1 = New-AzActionGroup -ActionGroupId 'actiongr1' -WebhookProperty $dict
Set-AzActivityLogAlert -Location $location -Name $alertName -ResourceGroupName $resourceGroupName -Scope 'scope1','scope2' -Action $actionGrp1 -Condition $condition1, $condition2
```

Empat perintah pertama membuat kondisi daun dan grup tindakan.
Perintah akhir membuat Pemberitahuan Log Aktivitas menggunakan kondisi dan grup tindakan.

### Contoh 2: Membuat Pemberitahuan Log Aktivitas dinonaktifkan
```powershell
$location = 'Global'
$alertName = 'myAlert'
$resourceGroupName = 'theResourceGroupName'
$condition1 = New-AzActivityLogAlertCondition -Field 'field1' -Equal 'equals1'
$condition2 = New-AzActivityLogAlertCondition -Field 'field2' -Equal 'equals2'
$dict = New-Object "System.Collections.Generic.Dictionary``2[System.String,System.String]"
$dict.Add('key1', 'value1')
$actionGrp1 = New-AzActionGroup -ActionGroupId 'actiongr1' -WebhookProperty $dict
Set-AzActivityLogAlert -Location $location -Name $alertName -ResourceGroupName $resourceGroupName -Scope 'scope1','scope2' -Action $actionGrp1 -Condition $condition1, $condition2 -DisableAlert
```

Empat perintah pertama membuat kondisi daun dan grup tindakan.
Perintah akhir membuat Pemberitahuan Log Aktivitas menggunakan kondisi dan grup tindakan, tetapi membuat pemberitahuan dinonaktifkan.

### Contoh 3: Mengatur pemberitahuan log aktivitas berdasarkan menggunakan nilai dari pipa atau parameter InputObject
```powershell
Get-AzActivityLogAlert -Name $alertName -ResourceGroupName $resourceGroupName | Set-AzActivityLogAlert
$alert = Get-AzActivityLogAlert -Name $alertName -ResourceGroupName $resourceGroupName
$alert.Description = 'Changing the description'
$alert.Enabled = $false
Set-AzActivityLogAlert -InputObject $alert
```

Perintah pertama mirip dengan nop, perintah ini mengatur pemberitahuan dengan nilai yang sama yang sudah dimuat Perintah lainnya mengambil aturan pemberitahuan, mengubah deskripsi dan menonaktifkannya, lalu menggunakan parameter InputObject untuk mempertahankan perubahan tersebut

### Contoh 4: Mengatur pemberitahuan log aktivitas berdasarkan menggunakan nilai ResourceId dari pipa
```powershell
Get-AzResource -ResourceGroupName "myResourceGroup" -Name "myLogAlert" | Set-AzActivityLogAlert -DisableAlert
```

Jika aturan pemberitahuan log yang diberikan ada, perintah ini akan menonaktifkannya.

## PARAMETERS

### -Tindakan
Daftar grup tindakan untuk pemberitahuan log aktivitas.

```yaml
Type: System.Collections.Generic.List`1[Microsoft.Azure.Management.Monitor.Management.Models.ActivityLogAlertActionGroup]
Parameter Sets: SetByNameAndResourceGroup
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

```yaml
Type: System.Collections.Generic.List`1[Microsoft.Azure.Management.Monitor.Management.Models.ActivityLogAlertActionGroup]
Parameter Sets: SetByResourceId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

```yaml
Type: System.Collections.Generic.List`1[Microsoft.Azure.Management.Monitor.Management.Models.ActivityLogAlertActionGroup]
Parameter Sets: SetByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Kondisi
Daftar kondisi untuk pemberitahuan log aktivitas.
**CATATAN**: Dalam daftar kondisi harus ada setidaknya satu dengan Bidang yang sama dengan "Kategori". Backend merespons dengan 400 (BadRequest) jika kondisi ini tidak ada.

```yaml
Type: System.Collections.Generic.List`1[Microsoft.Azure.Management.Monitor.Management.Models.ActivityLogAlertLeafCondition]
Parameter Sets: SetByNameAndResourceGroup
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

```yaml
Type: System.Collections.Generic.List`1[Microsoft.Azure.Management.Monitor.Management.Models.ActivityLogAlertLeafCondition]
Parameter Sets: SetByResourceId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

```yaml
Type: System.Collections.Generic.List`1[Microsoft.Azure.Management.Monitor.Management.Models.ActivityLogAlertLeafCondition]
Parameter Sets: SetByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure

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

### -Deskripsi
Deskripsi sumber daya pemberitahuan.

```yaml
Type: System.String
Parameter Sets: SetByNameAndResourceGroup, SetByResourceId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

```yaml
Type: System.String
Parameter Sets: SetByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DisableAlert
Memungkinkan pengguna untuk membuat pemberitahuan log aktivitas yang dinonaktifkan. Jika tidak diberikan, pemberitahuan dibuat diaktifkan.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: SetByNameAndResourceGroup, SetByResourceId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Mengatur properti tag InputObject dari panggilan untuk mengekstrak nama yang diperlukan, dan properti nama grup sumber daya.

```yaml
Type: Microsoft.Azure.Commands.Insights.OutputClasses.PSActivityLogAlertResource
Parameter Sets: SetByInputObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Lokasi
Lokasi tempat pemberitahuan log aktivitas akan ada.

```yaml
Type: System.String
Parameter Sets: SetByNameAndResourceGroup
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

```yaml
Type: System.String
Parameter Sets: SetByResourceId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Nama pemberitahuan log aktivitas.

```yaml
Type: System.String
Parameter Sets: SetByNameAndResourceGroup
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya tempat sumber daya pemberitahuan akan ada.

```yaml
Type: System.String
Parameter Sets: SetByNameAndResourceGroup
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceId
Mengatur properti tag ResourceId dari panggilan untuk mengekstrak nama yang diperlukan, properti nama grup sumber daya.

```yaml
Type: System.String
Parameter Sets: SetByResourceId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Cakupan
Daftar cakupan untuk pemberitahuan log aktivitas.

```yaml
Type: System.Collections.Generic.List`1[System.String]
Parameter Sets: SetByNameAndResourceGroup
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

```yaml
Type: System.Collections.Generic.List`1[System.String]
Parameter Sets: SetByResourceId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

```yaml
Type: System.Collections.Generic.List`1[System.String]
Parameter Sets: SetByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Tag
Mengatur properti tag dari sumber daya pemberitahuan log aktivitas.

```yaml
Type: System.Collections.Generic.Dictionary`2[System.String,System.String]
Parameter Sets: SetByNameAndResourceGroup, SetByResourceId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

```yaml
Type: System.Collections.Generic.Dictionary`2[System.String,System.String]
Parameter Sets: SetByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Menunjukkan yang akan terjadi jika cmdlet dijalankan. Cmdlet tidak dijalankan.

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

### System.String

### System.Collections.Generic.List'1[[System.String, System.Private.CoreLib, Version=4.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]

### System.Collections.Generic.List'1[[Microsoft.Azure.Management.Monitor.Management.Models.ActivityLogAlertLeafCondition, Microsoft.Azure.PowerShell.Cmdlets.Monitor, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null]]

### System.Collections.Generic.List'1[[Microsoft.Azure.Management.Monitor.Management.Models.ActivityLogAlertActionGroup, Microsoft.Azure.PowerShell.Cmdlets.Monitor, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null]]

### System.Collections.Generic.Dictionary'2[[System.String, System.Private.CoreLib, Version=4.0.0.0, Culture=netral, PublicKeyToken=7cec85d7bea7798e],[System.String, System.Private.CoreLib, Version=4.0.0.0, Culture=netral, PublicKeyToken=7cec85d7bea7798e]]

### Microsoft.Azure.Commands. Insights. OutputClasses.PSActivityLogAlertResource

## OUTPUTS

### Microsoft.Azure.Commands. Insights. OutputClasses.PSActivityLogAlertResource

## NOTES

## RELATED LINKS

[Enable-AzActivityLogAlert](./Enable-AzActivityLogAlert.md)

[Disable-AzActivityLogAlert](./Disable-AzActivityLogAlert.md)

[Get-AzActivityLogAlert](./Get-AzActivityLogAlert.md)

[Remove-AzActivityLogAlert](./Remove-AzActivityLogAlert.md)

[New-AzActionGroup](./New-AzActionGroup.md)

[New-AzActivityLogAlertCondition](./New-AzActivityLogAlertCondition.md)
