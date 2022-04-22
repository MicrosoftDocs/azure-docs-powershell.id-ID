---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Websites.dll-Help.xml
Module Name: Az.Websites
online version: https://docs.microsoft.com/powershell/module/az.websites/new-AzWebAppCertificate
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Websites/Websites/help/New-AzWebAppCertificate.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Websites/Websites/help/New-AzWebAppCertificate.md
ms.openlocfilehash: 0018ebf774b40e94fb140f14827ee6f26beea574
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142992341"
---
# New-AzWebAppCertificate

## SYNOPSIS
Membuat sertifikat terkelola layanan Aplikasi untuk Azure Web App. 

## SYNTAX

```
New-AzWebAppCertificate [-ResourceGroupName] <String> [-WebAppName] <String> [-Name <String>]
 [[-Slot] <String>] [-HostName] <String> [-AddBinding] [-SslState <SslState>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzWebAppCertificate** membuat Sertifikat yang Dikelola Azure App Service

## EXAMPLES

### Contoh 1
```powershell
New-AzWebAppCertificate -ResourceGroupName Default-Web-WestUS -WebAppName "ContosoSite" -Name "ContosoCert" -HostName "www.ContosoSite.net"
```

Perintah ini membuat Sertifikat terkelola App Service untuk WebApp yang diberikan

### Contoh 2
```powershell
New-AzWebAppCertificate -ResourceGroupName Default-Web-WestUS -WebAppName "ContosoSite" -Name "ContosoCert" -HostName "www.ContosoSite.net" -Slot "test" -AddBinding
```

Perintah ini membuat Sertifikat terkelola App Service dan mengikat ke Slot WebApp tertentu.

### Contoh 3
```powershell
New-AzWebAppCertificate -ResourceGroupName Default-Web-WestUS -WebAppName "ContosoSite" -Name "ContosoCert" -HostName "www.ContosoSite.net" -AddBinding
```

Perintah ini membuat Sertifikat terkelola App Service dan mengikat ke WebApp tertentu.

## PARAMETERS

### -AddBinding
Untuk menambahkan sertifikat yang dibuat ke WebApp/slot.

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
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HostName
Nama host kustom yang terkait dengan aplikasi/slot web.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Nama sertifikat.

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

### -ResourceGroupName
Nama grup sumber daya.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Slot
Nama slot aplikasi web.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SslState
Opsi status ssl.
Gunakan 'SniEnabled' atau 'IpBasedEnabled'.
Opsi default adalah 'SniEnabled'.

```yaml
Type: System.Nullable`1[Microsoft.Azure.Management.WebSites.Models.SslState]
Parameter Sets: (All)
Aliases:
Accepted values: Disabled, SniEnabled, IpBasedEnabled

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WebAppName
Nama aplikasi web.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
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
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan. Cmdlet tidak dijalankan.

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

### Tidak

## OUTPUTS

### Microsoft.Azure.Commands.WebApps.Models.WebApp.PSCertificate

## NOTES

## RELATED LINKS

[Remove-AzWebAppCertificate](./Remove-AzWebAppCertificate.md)
