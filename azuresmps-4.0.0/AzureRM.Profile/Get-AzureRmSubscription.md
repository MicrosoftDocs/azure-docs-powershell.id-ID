---
external help file: Microsoft.Azure.Commands.Profile.dll-Help.xml
online version: ''
schema: 2.0.0
ms.openlocfilehash: 757f1024c9f8cf285cfb54a25d12eb570981beea
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142653464"
---
# Get-AzureRmSubscription

## SYNOPSIS
Dapatkan langganan yang dapat diakses akun saat ini.

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
Cmdlet Get-AzureRmSubscription mendapatkan ID langganan, nama langganan, dan penyewa rumah untuk langganan yang dapat diakses akun saat ini.

## EXAMPLES

### Contoh 1: Dapatkan semua langganan di semua penyewa
```
PS C:\>Get-AzureRmSubscription -All

Subscription Name : Contoso Subscription 1
SubscriptionId    : xxxx-xxxx-xxxx-xxxx
TenantId          : yyyy-yyyy-yyyy-yyyy
```

Perintah ini mendapatkan semua langganan di semua penyewa yang diotorisasi untuk akun saat ini.

### Contoh 2: Dapatkan semua langganan untuk penyewa tertentu
```
PS C:\>Get-AzureRmSubscription -TenantId "xxxx-xxxx-xxxx-xxxx"

Subscription Name : Contoso Subscription 1
SubscriptionId    : yyyy-yyyy-yyyy-yyyy
TenantId          : xxxx-xxxx-xxxx-xxxx

Subscription Name : Contoso Subscription 2
SubscriptionId    : yyyy-yyyy-yyyy-yyyy
TenantId          : xxxx-xxxx-xxxx-xxxx
```

Cantumkan semua langganan dalam penyewa tertentu yang diotorisasi untuk akun saat ini.

### Contoh 3: Dapatkan semua langganan di penyewa saat ini
```
PS C:\>Get-AzureRmSubscription

Subscription Name : Contoso Subscription 1
SubscriptionId    : yyyy-yyyy-yyyy-yyyy
TenantId          : xxxx-xxxx-xxxx-xxxx

Subscription Name : Contoso Subscription 2
SubscriptionId    : yyyy-yyyy-yyyy-yyyy
TenantId          : xxxx-xxxx-xxxx-xxxx
```

Perintah ini mendapatkan semua langganan dalam penyewa saat ini yang diotorisasi untuk pengguna saat ini.

### Contoh 4: Mengubah konteks saat ini untuk menggunakan langganan tertentu
```
PS C:\>Get-AzureRmSubscription -SubscriptionId "xxxx-xxxx-xxxx-xxxx" -TenantId "yyyy-yyyy-yyyy-yyyy" | Set-AzureRmContext

Subscription Name : Contoso Subscription 1
SubscriptionId    : xxxx-xxxx-xxxx-xxxx
TenantId          : yyyy-yyyy-yyyy-yyyy
```

Perintah ini mendapatkan langganan yang ditentukan, lalu mengatur konteks saat ini untuk menggunakannya.
Semua cmdlet berikutnya dalam sesi ini menggunakan langganan baru (Langganan Contoso 1) secara default.

## PARAMETERS

### -SubscriptionId
Menentukan ID langganan yang akan didapatkan.

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
Menentukan nama langganan yang akan didapatkan.

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
Menentukan ID penyewa yang berisi langganan yang akan didapatkan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### PSAzureSubscription

## NOTES

## RELATED LINKS

