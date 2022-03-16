---
external help file: ''
Module Name: Az.Quota
online version: https://docs.microsoft.com/powershell/module/az.quota/get-azquotarequeststatus
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Quota/help/Get-AzQuotaRequestStatus.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Quota/help/Get-AzQuotaRequestStatus.md
ms.openlocfilehash: 7f8d99ca34ece7607829564b01116b3955b22952
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "139999173"
---
# Get-AzQuotaRequestStatus

## SYNOPSIS
Dapatkan detail permintaan kuota dan status dengan ID permintaan kuota untuk sumber daya penyedia sumber daya di lokasi tertentu.
Id permintaan **kuota** dikembalikan setelah operasi PUT.

## SYNTAX

### Daftar (Default)
```
Get-AzQuotaRequestStatus -Scope <String> [-Filter <String>] [-Skiptoken <String>] [-Top <Int32>]
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### Dapatkan
```
Get-AzQuotaRequestStatus -Id <String> -Scope <String> [-DefaultProfile <PSObject>] [<CommonParameters>]
```

## DESCRIPTION
Dapatkan detail permintaan kuota dan status dengan ID permintaan kuota untuk sumber daya penyedia sumber daya di lokasi tertentu.
Id permintaan **kuota** dikembalikan setelah operasi PUT.

## EXAMPLES

### Contoh 1: Mencantumkan detail permintaan kuota dan status untuk lingkup
```powershell
PS C:\> Get-AzQuotaRequestStatus -Scope "subscriptions/9e223dbe-3399-4e19-88eb-0975f02ac87f/providers/Microsoft.Network/locations/eastus"

Name                                 ProvisioningState ErrorMessage    Code
----                                 ----------------- ------------    ----
171f4e10-f396-48bc-a93f-245cfd7ebe75 Succeeded
0f5636d8-9377-4aec-9a57-5cdeded08615 Succeeded
3ae1cf1d-c792-448f-b2ff-33334ea1a28b Succeeded
5698cdd1-6b4b-4ec1-9a39-a4b5963094dd Succeeded
fb507eaa-f45f-476d-a1a5-77c74b1224b2 Succeeded
22f8a9f1-a003-42a0-9892-474a0478ceea Succeeded
103e114c-3894-4b33-a673-b3d814eea753 Succeeded
9decdd61-be39-4815-96d7-dfad78674940 Succeeded
3a4c474e-cfb1-4af6-baff-0f0bfea67b61 Succeeded
```

Perintah ini mencantumkan detail dan status permintaan kuota untuk lingkup tersebut.

### Contoh 2: Dapatkan detail permintaan kuota dan status dengan ID permintaan kuota untuk sumber daya penyedia sumber daya di lokasi tertentu
```powershell
PS C:\> Get-AzQuotaRequestStatus -Scope "subscriptions/9e223dbe-3399-4e19-88eb-0975f02ac87f/providers/Microsoft.Network/locations/eastus" -Id "6cf5716a-3df8-421a-8457-719e10381dbc"

Name                                 ProvisioningState ErrorMessage    Code
----                                 ----------------- ------------    ----
6cf5716a-3df8-421a-8457-719e10381dbc Failed            Request failed. QuotaReductionNotSupported
```

Perintah ini mendapatkan detail permintaan kuota dan status dengan ID permintaan kuota untuk sumber daya penyedia sumber daya di lokasi tertentu.
Id permintaan **kuota** dikembalikan setelah operasi PUT.

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

### -Filter
| Bidang | Operator yang didukung 
|---------------------|------------------------

|requestSubmitTime | ge, le, eq, gt, lt |provisioningState eq {QuotaRequestState} |resourceName eq {resourceName}

```yaml
Type: System.String
Parameter Sets: List
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Id
ID permintaan kuota.

```yaml
Type: System.String
Parameter Sets: Get
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Lingkup
URI sumber daya Azure target.
Misalnya, `/subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/qms-test/providers/Microsoft.Batch/batchAccounts/testAccount/`.
Ini adalah URI sumber daya Azure target untuk operasi GET Daftar.
Jika ditambahkan `{resourceName}` setelah `/quotas`, itu adalah URI sumber daya Azure target dalam operasi DAPATKAN untuk sumber daya tertentu.

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

### -Skiptoken
Parameter **Skiptoken** hanya digunakan jika operasi sebelumnya mengembalikan hasil parsial.
Jika respons sebelumnya berisi elemen **nextLink** , nilainya menyertakan parameter **skiptoken** yang menentukan titik awal yang akan digunakan untuk panggilan berikutnya.

```yaml
Type: System.String
Parameter Sets: List
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Top
Jumlah data yang dikembalikan.

```yaml
Type: System.Int32
Parameter Sets: List
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Quota.Models.Api20210315Preview.IQuotaRequestDetails

## CATATAN

ALIAS

## RELATED LINKS

