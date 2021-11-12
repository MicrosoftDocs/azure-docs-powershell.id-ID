---
external help file: Microsoft.Azure.Commands.Profile.dll-Help.xml
online version: ''
schema: 2.0.0
ms.openlocfilehash: 1af07f350229ff4b081b41b4f331bff6be241d265a1a9ec1fd50d557f283e4e8
ms.sourcegitcommit: 49f8ffe5d8e08ba3d22e3b2e76db0e54dd55d4f0
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/11/2021
ms.locfileid: "132417640"
---
# Get-AzureRmSubscription

## SYNOPSIS
Dapatkan langganan yang bisa diakses oleh akun saat ini.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

### ListByIdInTenant (Default)
```
Get-AzureRmSubscription [-SubscriptionId <String>] [-TenantId <String>] [<CommonParameters>]
```

### ListByNameInTenant
```
Get-AzureRmSubscription [-SubscriptionName <String>] [-TenantId <String>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet Get-AzureRmSubscription mendapatkan ID langganan, nama langganan, dan penyewa rumah untuk langganan yang bisa diakses akun saat ini.

## EXAMPLES

### Contoh 1: Dapatkan semua langganan dalam semua penyewa
```
PS C:\>Get-AzureRmSubscription -All

Subscription Name : Contoso Subscription 1
SubscriptionId    : xxxx-xxxx-xxxx-xxxx
TenantId          : yyyy-yyyy-yyyy-yyyy
```

Perintah ini akan mendapatkan semua langganan di semua penyewa yang diizinkan untuk akun saat ini.

### Contoh 2: Mendapatkan semua langganan untuk penyewa tertentu
```
PS C:\>Get-AzureRmSubscription -TenantId "xxxx-xxxx-xxxx-xxxx"

Subscription Name : Contoso Subscription 1
SubscriptionId    : yyyy-yyyy-yyyy-yyyy
TenantId          : xxxx-xxxx-xxxx-xxxx

Subscription Name : Contoso Subscription 2
SubscriptionId    : yyyy-yyyy-yyyy-yyyy
TenantId          : xxxx-xxxx-xxxx-xxxx
```

Daftar semua langganan dalam penyewa tertentu yang diotorisasi untuk akun saat ini.

### Contoh 3: Dapatkan semua langganan dalam penyewa saat ini
```
PS C:\>Get-AzureRmSubscription

Subscription Name : Contoso Subscription 1
SubscriptionId    : yyyy-yyyy-yyyy-yyyy
TenantId          : xxxx-xxxx-xxxx-xxxx

Subscription Name : Contoso Subscription 2
SubscriptionId    : yyyy-yyyy-yyyy-yyyy
TenantId          : xxxx-xxxx-xxxx-xxxx
```

Perintah ini mendapatkan semua langganan di penyewa saat ini yang diotorisasi untuk pengguna saat ini.

### Contoh 4: Mengubah konteks saat ini untuk menggunakan langganan tertentu
```
PS C:\>Get-AzureRmSubscription -SubscriptionId "xxxx-xxxx-xxxx-xxxx" -TenantId "yyyy-yyyy-yyyy-yyyy" | Set-AzureRmContext

Subscription Name : Contoso Subscription 1
SubscriptionId    : xxxx-xxxx-xxxx-xxxx
TenantId          : yyyy-yyyy-yyyy-yyyy
```

Perintah ini akan mendapatkan langganan tertentu, lalu mengatur konteks saat ini untuk menggunakannya.
Semua cmdlet berikutnya dalam sesi ini menggunakan langganan baru (Langganan Contoso 1) secara default.

## PARAMETERS

### -SubscriptionId
Menentukan ID langganan yang akan dapatkan.

```yaml
Type: String
Parameter Sets: ListByIdInTenant
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SubscriptionName
Menentukan nama langganan yang akan dapatkan.

```yaml
Type: String
Parameter Sets: ListByNameInTenant
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TenantId
Menentukan ID penyewa berisi langganan yang akan dapatkan.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

## OUTPUTS

### PSAzureSubscription

## CATATAN

## RELATED LINKS

