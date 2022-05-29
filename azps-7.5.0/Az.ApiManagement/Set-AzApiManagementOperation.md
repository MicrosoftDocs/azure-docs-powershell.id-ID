---
external help file: Microsoft.Azure.PowerShell.Cmdlets.ApiManagement.ServiceManagement.dll-Help.xml
Module Name: Az.ApiManagement
ms.assetid: 67EE6EFB-3297-4D21-A6EC-B03F5FE82F84
online version: https://docs.microsoft.com/powershell/module/az.apimanagement/set-azapimanagementoperation
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ApiManagement/ApiManagement/help/Set-AzApiManagementOperation.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ApiManagement/ApiManagement/help/Set-AzApiManagementOperation.md
ms.openlocfilehash: 865c8f00f6204a1c3308a6947ec4fd05fcc3f24c
ms.sourcegitcommit: 82b4008b76d035e4aee733727371765b0d853bed
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145686316"
---
# Set-AzApiManagementOperation

## SYNOPSIS
Mengatur detail operasi API.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.apimanagement/set-azapimanagementoperation) untuk informasi terbaru.

## SYNTAX

```
Set-AzApiManagementOperation -Context <PsApiManagementContext> -ApiId <String> [-ApiRevision <String>]
 -OperationId <String> -Name <String> -Method <String> -UrlTemplate <String> [-Description <String>]
 [-TemplateParameters <PsApiManagementParameter[]>] [-Request <PsApiManagementRequest>]
 [-Responses <PsApiManagementResponse[]>] [-PassThru] [-DefaultProfile <IAzureContextContainer>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzApiManagementOperation** menetapkan detail operasi API.

## EXAMPLES

### Contoh 1: Mengatur detail operasi
```powershell
$apimContext = New-AzApiManagementContext -ResourceGroupName "Api-Default-WestUS" -ServiceName "contoso"
New-AzApiManagementOperation -Context $apimContext -ApiId $APIID -OperationId $OperationId -Name "Get Resource" -Method GET -UrlTemplate "/newresource" -Description "Use this operation to get newresource"
```

Perintah ini menetapkan detail operasi untuk manajemen API.

### Contoh 2

Mengatur detail operasi API. (dibuat otomatis)

```powershell
<!-- Aladdin Generated Example --> 
Set-AzApiManagementOperation -ApiId '0001' -Context <PsApiManagementContext> -Method 'GET' -Name 'ContosoApi' -OperationId 'Operation003' -UrlTemplate '/newresource'
```

## PARAMETERS

### -ApiId
Menentukan pengidentifikasi API.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ApiRevision
Pengidentifikasi Revisi API. Parameter ini bersifat opsional. Jika tidak ditentukan, operasi akan diperbarui dalam revisi api yang saat ini aktif.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Context
Menentukan **instans PsApiManagementContext**.

```yaml
Type: Microsoft.Azure.Commands.ApiManagement.ServiceManagement.Models.PsApiManagementContext
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure.

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
Menentukan deskripsi operasi baru.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Metode
Menentukan metode HTTP operasi baru.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Menentukan nama tampilan operasi baru.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -OperationId
Menentukan pengidentifikasi operasi yang ada.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru
passthru

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Permintaan
Menentukan detail permintaan operasi.

```yaml
Type: Microsoft.Azure.Commands.ApiManagement.ServiceManagement.Models.PsApiManagementRequest
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Respons
Menentukan array kemungkinan respons operasi.

```yaml
Type: Microsoft.Azure.Commands.ApiManagement.ServiceManagement.Models.PsApiManagementResponse[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TemplateParameters
Menentukan array atau parameter yang ditentukan dalam parameter *UrlTemplate*.
Jika Anda tidak menentukan nilai, nilai default akan dihasilkan berdasarkan UrlTemplate.
Gunakan parameter untuk memberikan detail selengkapnya tentang parameter seperti deskripsi, jenis, dan nilai lain yang mungkin.

```yaml
Type: Microsoft.Azure.Commands.ApiManagement.ServiceManagement.Models.PsApiManagementParameter[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -UrlTemplate
Menentukan templat URL.
Misalnya: customers/{cid}/orders/{oid}/?date={date}.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
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

### Microsoft.Azure.Commands.ApiManagement.ServiceManagement.Models.PsApiManagementContext

### System.String

### Microsoft.Azure.Commands.ApiManagement.ServiceManagement.Models.PsApiManagementParameter[]

### Microsoft.Azure.Commands.ApiManagement.ServiceManagement.Models.PsApiManagementRequest

### Microsoft.Azure.Commands.ApiManagement.ServiceManagement.Models.PsApiManagementResponse[]

### System.Management.Automation.SwitchParameter

## OUTPUTS

### Microsoft.Azure.Commands.ApiManagement.ServiceManagement.Models.PsApiManagementOperation

## NOTES

## RELATED LINKS

[Get-AzApiManagementOperation](./Get-AzApiManagementOperation.md)

[New-AzApiManagementOperation](./New-AzApiManagementOperation.md)

[Remove-AzApiManagementOperation](./Remove-AzApiManagementOperation.md)


