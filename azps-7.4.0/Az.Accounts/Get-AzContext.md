---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Accounts.dll-Help.xml
Module Name: Az.Accounts
online version: https://docs.microsoft.com/powershell/module/az.accounts/get-azcontext
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Accounts/Accounts/help/Get-AzContext.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Accounts/Accounts/help/Get-AzContext.md
ms.openlocfilehash: 7e5d887e061d2f839f8edc40af713bd812d062d7
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144676402"
---
# Get-AzContext

## SYNOPSIS
Mendapatkan metadata yang digunakan untuk mengautentikasi permintaan Azure Resource Manager.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.accounts/get-azcontext) untuk informasi terbaru.

## SYNTAX

### GetSingleContext (Default)
```
Get-AzContext [-DefaultProfile <IAzureContextContainer>] [[-Name] <String>] [<CommonParameters>]
```

### ListAllContexts
```
Get-AzContext [-ListAvailable] [-RefreshContextFromTokenCache] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet Get-AzContext mendapatkan metadata saat ini yang digunakan untuk mengautentikasi permintaan Azure Resource Manager.
Cmdlet ini mendapatkan akun Direktori Aktif, penyewa Direktori Aktif, langganan Azure, dan lingkungan Azure yang ditargetkan.
Cmdlet Azure Resource Manager menggunakan pengaturan ini secara default saat membuat permintaan Azure Resource Manager. Ketika jumlah langganan yang tersedia melebihi batas default 25, beberapa langganan mungkin tidak muncul dalam hasil `Get-AzContext -ListAvailable`. Silakan jalankan `Connect-AzAccount -MaxContextPopulation <int>` untuk mendapatkan lebih banyak konteks.

## EXAMPLES

### Contoh 1: Mendapatkan konteks saat ini
```powershell
Connect-AzAccount
Get-AzContext
```

```Output
Name                                     Account             SubscriptionName    Environment         TenantId
----                                     -------             ----------------    -----------         --------
Subscription1 (xxxxxxxx-xxxx-xxxx-xxx... test@outlook.com    Subscription1       AzureCloud          xxxxxxxx-x...
```

Dalam contoh ini kita masuk ke akun kita dengan langganan Azure menggunakan Koneksi-AzAccount, dan kemudian kita mendapatkan konteks sesi saat ini dengan memanggil Get-AzContext.

### Contoh 2: Mencantumkan semua konteks yang tersedia
```powershell
Get-AzContext -ListAvailable
```

```Output
Name                                     Account             SubscriptionName    Environment         TenantId
----                                     -------             ----------------    -----------         --------
Subscription1 (xxxxxxxx-xxxx-xxxx-xxx... test@outlook.com    Subscription1       AzureCloud          xxxxxxxx-x...
Subscription2 (xxxxxxxx-xxxx-xxxx-xxx... test@outlook.com    Subscription2       AzureCloud          xxxxxxxx-x...
Subscription3 (xxxxxxxx-xxxx-xxxx-xxx... test@outlook.com    Subscription3       AzureCloud          xxxxxxxx-x...
```

Dalam contoh ini, semua konteks yang tersedia saat ini ditampilkan.  Pengguna dapat memilih salah satu konteks ini menggunakan Select-AzContext.

## PARAMETERS

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

### -ListAvailable
Cantumkan semua konteks yang tersedia dalam sesi saat ini.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ListAllContexts
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Nama konteks

```yaml
Type: System.String
Parameter Sets: GetSingleContext
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RefreshContextFromTokenCache
Refresh konteks dari cache token

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ListAllContexts
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Tidak ada

## OUTPUTS

### Microsoft.Azure.Commands.Profile.Models.Core.PSAzureContext

## NOTES

## RELATED LINKS

[Set-AzContext](./Set-AzContext.md)

[Connect-AzAccount](./Connect-AzAccount.md)
