---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Monitor.dll-Help.xml
Module Name: Az.Monitor
ms.assetid: B5F2388E-0136-4F8A-8577-67CE2A45671E
online version: https://docs.microsoft.com/powershell/module/az.monitor/set-azdiagnosticsetting
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Monitor/Monitor/help/Set-AzDiagnosticSetting.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Monitor/Monitor/help/Set-AzDiagnosticSetting.md
ms.openlocfilehash: af837a1b6060661d19fa191569d9ce05767ee9d9
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144558868"
---
# Set-AzDiagnosticSetting

## SYNOPSIS
Mengatur pengaturan log dan metrik untuk sumber daya.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.monitor/set-azdiagnosticsetting) untuk informasi terbaru.

## SYNTAX

### OldSetDiagnosticSetting (Default)
```
Set-AzDiagnosticSetting -ResourceId <String> [-Name <String>] [-StorageAccountId <String>]
 [-ServiceBusRuleId <String>] [-EventHubName <String>] [-EventHubAuthorizationRuleId <String>]
 [-Enabled <Boolean>] [-Category <System.Collections.Generic.List`1[System.String]>]
 [-MetricCategory <System.Collections.Generic.List`1[System.String]>]
 [-Timegrain <System.Collections.Generic.List`1[System.String]>] [-RetentionEnabled <Boolean>]
 [-WorkspaceId <String>] [-RetentionInDays <Int32>] [-ExportToResourceSpecific] [-EnableLog <Boolean>]
 [-EnableMetrics <Boolean>] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### NewSetDiagnosticSetting
```
Set-AzDiagnosticSetting -InputObject <PSServiceDiagnosticSettings> [-DefaultProfile <IAzureContextContainer>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzDiagnosticSetting** memungkinkan atau menonaktifkan setiap kali grain dan kategori log untuk sumber daya tertentu.
Log dan metrik disimpan di akun penyimpanan yang ditentukan.
Cmdlet ini mengimplementasikan pola ShouldProcess, yaitu mungkin meminta konfirmasi dari pengguna sebelum benar-benar membuat, memodifikasi, atau menghapus sumber daya.

## EXAMPLES

### Contoh 1: Mengaktifkan semua metrik dan log untuk sumber daya
```powershell
Set-AzDiagnosticSetting -ResourceId "Resource01" -Enabled $True
```

Perintah ini memungkinkan semua metrik dan log yang tersedia untuk Resource01.

### Contoh 2: Menonaktifkan semua metrik dan log
```powershell
Set-AzDiagnosticSetting -ResourceId "Resource01" -Enabled $False
```

Perintah ini menonaktifkan semua metrik dan log yang tersedia untuk sumber daya Resource01.

### Contoh 3: Mengaktifkan/menonaktifkan beberapa kategori metrik
```powershell
Set-AzDiagnosticSetting -ResourceId "Resource01" -Enabled $False -MetricCategory MetricCategory1,MetricCategory2
```

```output
StorageAccountId   : <storageAccountId>
StorageAccountName : <storageAccountName>
Metrics
   Enabled   : False
   Category  : MetricCategory1
   Timegrain : PT1M
   Enabled   : False
   Category  : MetricCategory2
   Timegrain : PT1H
   Enabled   : True
   Category  : MetricCategory3
   Timegrain : PT1H
Logs
   Enabled  : True
   Category : Category1
   Enabled  : True
   Category : Category2
   Enabled  : True
   Category : Category3
   Enabled  : False
   Category : Category4
```

Perintah ini menonaktifkan kategori metrik yang disebut Category1 dan Category2.
Semua kategori lainnya tetap sama.

### Contoh 4: Mengaktifkan/menonaktifkan beberapa kategori log
```powershell
Set-AzDiagnosticSetting -ResourceId "Resource01" -Enabled $True -Category Category1,Category2
```

```output
StorageAccountId   : <storageAccountId>
StorageAccountName : <storageAccountName>
Metrics
   Enabled   : False
   Category  : MetricCategory1
   Timegrain : PT1M
   Enabled   : False
   Category  : MetricCategory2
   Timegrain : PT1H
   Enabled   : True
   Category  : MetricCategory3
   Timegrain : PT1H
Logs
   Enabled  : True
   Category : Category1
   Enabled  : True
   Category : Category2
   Enabled  : True
   Category : Category3
   Enabled  : False
   Category : Category4
```

Perintah ini mengaktifkan Category1 dan Category2.
Semua kategori metrik dan log lainnya tetap sama.

### Contoh 5: Mengaktifkan butir waktu dan beberapa kategori
```powershell
Set-AzDiagnosticSetting -ResourceId "Resource01" -Enabled $True -Category Category1,Category2 -Timegrain PT1M
```

Perintah ini hanya memungkinkan Category1, Category2, dan time grain PT1M.
Semua butir dan kategori waktu lainnya tidak berubah.

### Contoh 6: Menggunakan alur
```powershell
Get-AzDiagnosticSetting -ResourceId "Resource01" | Set-AzDiagnosticSetting -Enabled $True -Category Category1,Category2
```

Perintah ini menggunakan alur PowerShell untuk mengatur (tidak ada perubahan yang dibuat) pengaturan diagnostik.

### Contoh 7: Mengaktifkan semua kategori untuk langganan
```powershell
$list = @()
Get-AzSubscriptionDiagnosticSettingCategory | ForEach-Object {
    $list += (New-AzDiagnosticDetailSetting -Log -Category $_.Name -Enabled)
}
$DiagnosticSettingName = 'please use your setting name here'
$SubscriptionId = 'please use your subscription Id here'
$WorkspaceId = 'please use your workspace Id here'
$setting = New-AzDiagnosticSetting -Name $DiagnosticSettingName -SubscriptionId $SubscriptionId -WorkspaceId $WorkspaceId -Setting $list
Set-AzDiagnosticSetting -InputObject $setting
```

Perintah ini mengaktifkan semua kategori log untuk langganan.

## PARAMETERS

### -Kategori
Menentukan daftar kategori log untuk diaktifkan atau dinonaktifkan, sesuai dengan nilai *Diaktifkan*.
Jika tidak ada kategori yang ditentukan, perintah ini beroperasi pada semua kategori yang didukung. 

```yaml
Type: System.Collections.Generic.List`1[System.String]
Parameter Sets: OldSetDiagnosticSetting
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

### -Diaktifkan
Menunjukkan apakah akan mengaktifkan diagnostik.
Tentukan $True untuk mengaktifkan diagnostik, atau $False untuk menonaktifkan diagnostik.

```yaml
Type: System.Boolean
Parameter Sets: OldSetDiagnosticSetting
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EnableLog
Nilai yang menunjukkan apakah log diagnostik harus diaktifkan atau dinonaktifkan

```yaml
Type: System.Boolean
Parameter Sets: OldSetDiagnosticSetting
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EnableMetrics
Nilai yang menunjukkan apakah metrik diagnostik harus diaktifkan atau dinonaktifkan

```yaml
Type: System.Boolean
Parameter Sets: OldSetDiagnosticSetting
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EventHubAuthorizationRuleId
Id aturan otorisasi pusat aktivitas

```yaml
Type: System.String
Parameter Sets: OldSetDiagnosticSetting
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EventHubName
Nama pusat aktivitas

```yaml
Type: System.String
Parameter Sets: OldSetDiagnosticSetting
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ExportToResourceSpecific
Bendera yang menunjukkan bahwa ekspor ke LA harus dilakukan ke tabel khusus sumber daya, alias. tabel skema khusus atau tetap, dibandingkan dengan tabel skema dinamis **default** yang disebut **AzureDiagnostics**.

Argumen ini hanya efektif ketika argumen **-workspaceId** juga diberikan.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: OldSetDiagnosticSetting
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InputObject
Objek input (dimungkinkan dari alur.) Nama dan resourceId akan diekstrak dari objek ini.

```yaml
Type: Microsoft.Azure.Commands.Insights.OutputClasses.PSServiceDiagnosticSettings
Parameter Sets: NewSetDiagnosticSetting
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -MetricCategory
Daftar kategori metrik. Jika tidak ada kategori yang ditentukan, perintah ini beroperasi pada semua kategori yang didukung. 

```yaml
Type: System.Collections.Generic.List`1[System.String]
Parameter Sets: OldSetDiagnosticSetting
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Nama pengaturan diagnostik. Nilai defaultnya adalah **layanan**.

```yaml
Type: System.String
Parameter Sets: OldSetDiagnosticSetting
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceId
Menentukan ID sumber daya.

```yaml
Type: System.String
Parameter Sets: OldSetDiagnosticSetting
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RetentionEnabled
Menunjukkan apakah retensi informasi diagnostik diaktifkan. Perhatikan bahwa ini hanya berlaku saat menyimpan data ke akun Storage.

```yaml
Type: System.Nullable`1[System.Boolean]
Parameter Sets: OldSetDiagnosticSetting
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RetentionInDays
Menentukan kebijakan penyimpanan, dalam hari. Perhatikan bahwa ini hanya berlaku saat menyimpan data ke akun Storage.

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: OldSetDiagnosticSetting
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ServiceBusRuleId
Id Aturan Bus Layanan.

```yaml
Type: System.String
Parameter Sets: OldSetDiagnosticSetting
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StorageAccountId
Menentukan ID akun Storage untuk menyimpan data.

```yaml
Type: System.String
Parameter Sets: OldSetDiagnosticSetting
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Timegrain
Menentukan butir waktu untuk mengaktifkan atau menonaktifkan metrik, sesuai dengan nilai *Diaktifkan*.
Jika Anda tidak menentukan butir waktu, perintah ini beroperasi pada semua butir waktu yang tersedia.

```yaml
Type: System.Collections.Generic.List`1[System.String]
Parameter Sets: OldSetDiagnosticSetting
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -WorkspaceId
Id sumber daya ruang kerja Log Analytics untuk mengirim log/metrik ke

```yaml
Type: System.String
Parameter Sets: OldSetDiagnosticSetting
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

### Microsoft.Azure.Commands. Insights. OutputClasses.PSServiceDiagnosticSettings

### System.String

### System.Boolean

### System.Collections.Generic.List'1[[System.String, System.Private.CoreLib, Version=4.0.0.0, Culture=netral, PublicKeyToken=7cec85d7bea7798e]]

### System.Nullable'1[[System.Boolean, System.Private.CoreLib, Version=4.0.0.0, Culture=netral, PublicKeyToken=7cec85d7bea7798e]]

### System.Nullable'1[[System.Int32, System.Private.CoreLib, Version=4.0.0.0, Culture=netral, PublicKeyToken=7cec85d7bea7798e]]

## OUTPUTS

### Microsoft.Azure.Commands. Insights. OutputClasses.PSServiceDiagnosticSettings

## NOTES

## RELATED LINKS

[Get-AzDiagnosticSetting](./Get-AzDiagnosticSetting.md)
 [Remove-AzDiagnosticSetting](./Remove-AzDiagnosticSetting.md)
