---
external help file: Microsoft.Azure.PowerShell.Cmdlets.ApiManagement.dll-Help.xml
Module Name: Az.ApiManagement
online version: https://docs.microsoft.com/powershell/module/az.apimanagement/new-azapimanagementsslsetting
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ApiManagement/ApiManagement/help/New-AzApiManagementSslSetting.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ApiManagement/ApiManagement/help/New-AzApiManagementSslSetting.md
ms.openlocfilehash: ec77689fbab13d4bf3aade2b09307d48ec25d325
ms.sourcegitcommit: 7e47562b11e670049c3a18af7498414da853a921
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/09/2022
ms.locfileid: "138164098"
---
# New-AzApiManagementSslSetting

## SYNOPSIS
Membuat contoh PsApiManagementSslSetting

## SYNTAX

```
New-AzApiManagementSslSetting [-FrontendProtocol <Hashtable>] [-BackendProtocol <Hashtable>]
 [-CipherSuite <Hashtable>] [-ServerProtocol <Hashtable>] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Perintah bantuan untuk membuat contoh PsApiManagementSslSetting.
Perintah ini akan digunakan dengan New-AzApiManagement perintah.

## EXAMPLES

### Contoh 1: Buat Pengaturan SSL untuk mengaktifkan TLS 1.0 pada Backend dan Frontend
```powershell
PS D:\github\azure-powershell\artifacts\Debug\Az.ApiManagement> $enableTls=@{"Tls10" = "True"}
PS D:\github\azure-powershell\artifacts\Debug\Az.ApiManagement> New-AzApiManagementSslSetting -FrontendProtocol $enableTls -BackendProtocol $enableTls

FrontendProtocols BackendProtocols CipherSuites ServerProtocols
----------------- ---------------- ------------ ---------------
{Tls10}           {Tls10}
```

Buat contoh baru PsApiManagementSslSetting untuk Mengaktifkan TLSv 1.0 di Frontend (antara klien dan APIM) dan Backend (antara APIM dan Backend) dari Gateway ApiManagement.

## PARAMETERS

### -BackendProtocol
Pengaturan protokol Keamanan Backend. Parameter ini bersifat opsional.
Protokol yang valid Pengaturan adalah `Tls11` - Tls 1.1 `Tls10` - Tls 1.0 `Ssl30` - SSL 3.0

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CipherSuite
Pengaturan ssl cipher suites dalam urutan yang ditentukan. Parameter ini bersifat opsional.
Syarat Pengaturan adalah `TripleDes168` - Aktifkan / Nonaktifkan Tripe Des 168

```yaml
Type: System.Collections.Hashtable
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
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FrontendProtocol
Pengaturan protokol Keamanan Frontend. Parameter ini bersifat opsional.
Protokol yang valid Pengaturan adalah `Tls11` - Tls 1.1 `Tls10` - Tls 1.0 `Ssl30` - SSL 3.0


```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServerProtocol
Pengaturan protokol server seperti Http2. Parameter ini bersifat opsional.
Opsi yang Pengaturan adalah `Http2` - Aktifkan Http 2.0

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
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

### Tidak ada

## OUTPUTS

### Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagementSsslSettings

## CATATAN

## RELATED LINKS

[New-AzApiManagement](./New-AzApiManagement.md)

