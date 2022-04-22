---
external help file: ''
Module Name: Az.ProviderHub
online version: https://docs.microsoft.com/powershell/module/az.providerhub/new-azproviderhubnotificationregistration
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ProviderHub/help/New-AzProviderHubNotificationRegistration.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ProviderHub/help/New-AzProviderHubNotificationRegistration.md
ms.openlocfilehash: fc7f315f04d340e5bf976909711f7cdb905d9838
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142962425"
---
# New-AzProviderHubNotificationRegistration

## SYNOPSIS
Membuat atau memperbarui pendaftaran pemberitahuan.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.providerhub/new-azproviderhubnotificationregistration) untuk informasi terbaru.

## SYNTAX

```
New-AzProviderHubNotificationRegistration -Name <String> -ProviderNamespace <String>
 [-SubscriptionId <String>] [-IncludedEvent <String[]>] [-MessageScope <MessageScope>]
 [-NotificationEndpoint <INotificationEndpoint[]>] [-NotificationMode <NotificationMode>]
 [-ProvisioningState <ProvisioningState>] [-DefaultProfile <PSObject>] [-Confirm] [-WhatIf]
 [<CommonParameters>]
```

## DESCRIPTION
Membuat atau memperbarui pendaftaran pemberitahuan.

## EXAMPLES

### Contoh 1: Membuat/Memperbarui pendaftaran pemberitahuan.
```powershell
PS C:\> New-AzProviderHubNotificationRegistration -ProviderNamespace "Microsoft.Contoso" -Name "notificationRegistrationTest" -NotificationMode "EventHub" -MessageScope "RegisteredSubscriptions" -IncludedEvent "*/write", "Microsoft.Contoso/testResourceType/delete" -NotificationEndpoint @{Location = "", "East US"; NotificationDestination = "/subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/mgmtexp-eastus/providers/Microsoft.EventHub/namespaces/unitedstates-mgmtexpint/eventhubs/armlinkednotifications"}

Name
----
notificationRegistrationTest
```

Membuat/Memperbarui pendaftaran pemberitahuan.

### Contoh 2: Membuat/Memperbarui pendaftaran pemberitahuan.
```powershell
PS C:\> New-AzProviderHubNotificationRegistration -ProviderNamespace "Microsoft.Contoso" -Name "notificationRegistrationTest" -NotificationMode "EventHub" -MessageScope "RegisteredSubscriptions" -IncludedEvent "*/write", "Microsoft.Contoso/testResourceType/delete" -NotificationEndpoint @{Location = "", "East US"; NotificationDestination = "/subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/mgmtexp-eastus/providers/Microsoft.EventHub/namespaces/unitedstates-mgmtexpint/eventhubs/armlinkednotifications"}

Name
----
notificationRegistrationTest
```

Membuat/Memperbarui pendaftaran pemberitahuan.

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

### -IncludedEvent
.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MessageScope
.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ProviderHub.Support.MessageScope
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Pendaftaran pemberitahuan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: NotificationRegistrationName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NotificationEndpoint
.
Untuk membuat, lihat bagian CATATAN untuk properti NOTIFICATIONENDPOINT dan buat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ProviderHub.Models.Api20201120.INotificationEndpoint[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NotificationMode
.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ProviderHub.Support.NotificationMode
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProviderNamespace
Nama penyedia sumber daya yang dihosting dalam ProviderHub.

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

### -ProvisioningState
.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ProviderHub.Support.ProvisioningState
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubscriptionId
ID langganan target.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
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

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ProviderHub.Models.Api20201120.INotificationRegistration

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


NOTIFICATIONENDPOINT <INotificationEndpoint[]>: .
  - `[Location <String[]>]`: 
  - `[NotificationDestination <String>]`: 

## RELATED LINKS

