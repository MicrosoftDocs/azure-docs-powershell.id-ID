---
external help file: Microsoft.Azure.PowerShell.Cmdlets.ApiManagement.ServiceManagement.dll-Help.xml
Module Name: Az.ApiManagement
ms.assetid: 6CD1C2B8-0416-4FF3-81B0-0C9E59AE6CF9
online version: https://docs.microsoft.com/powershell/module/az.apimanagement/set-azapimanagementpolicy
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ApiManagement/ApiManagement/help/Set-AzApiManagementPolicy.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ApiManagement/ApiManagement/help/Set-AzApiManagementPolicy.md
ms.openlocfilehash: 09ca63c0c6aacd243c75e9e89d86528034e80c93
ms.sourcegitcommit: 82b4008b76d035e4aee733727371765b0d853bed
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145686190"
---
# Set-AzApiManagementPolicy

## SYNOPSIS
Mengatur kebijakan cakupan yang ditentukan untuk API Management.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.apimanagement/set-azapimanagementpolicy) untuk informasi terbaru.

## SYNTAX

### SetTenantLevel (Default)
```
Set-AzApiManagementPolicy -Context <PsApiManagementContext> [-Format <String>] [-Policy <String>]
 [-PolicyFilePath <String>] [-PolicyUrl <String>] [-PassThru] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### SetProductLevel
```
Set-AzApiManagementPolicy -Context <PsApiManagementContext> [-Format <String>] -ProductId <String>
 [-Policy <String>] [-PolicyFilePath <String>] [-PolicyUrl <String>] [-PassThru]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### SetApiLevel
```
Set-AzApiManagementPolicy -Context <PsApiManagementContext> [-Format <String>] -ApiId <String>
 [-ApiRevision <String>] [-Policy <String>] [-PolicyFilePath <String>] [-PolicyUrl <String>] [-PassThru]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### SetOperationLevel
```
Set-AzApiManagementPolicy -Context <PsApiManagementContext> [-Format <String>] -ApiId <String>
 [-ApiRevision <String>] -OperationId <String> [-Policy <String>] [-PolicyFilePath <String>]
 [-PolicyUrl <String>] [-PassThru] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzApiManagementPolicy** menetapkan kebijakan cakupan yang ditentukan untuk API Management.

## EXAMPLES

### Contoh 1: Mengatur kebijakan tingkat penyewa
```powershell
$apimContext = New-AzApiManagementContext -ResourceGroupName "Api-Default-WestUS" -ServiceName "contoso"
Set-AzApiManagementPolicy -Context $apimContext -PolicyFilePath "C:\contoso\policies\tenantpolicy.xml"
```

Perintah ini menetapkan kebijakan tingkat penyewa dari file bernama tenantpolicy.xml.

### Contoh 2: Menetapkan kebijakan cakupan produk
```powershell
$apimContext = New-AzApiManagementContext -ResourceGroupName "Api-Default-WestUS" -ServiceName "contoso"
Set-AzApiManagementPolicy -Context $apimContext -ProductId "0123456789" -Policy $PolicyString
```

Perintah ini menetapkan kebijakan cakupan produk untuk API Management.

### Contoh 3: Mengatur kebijakan cakupan API
```powershell
$apimContext = New-AzApiManagementContext -ResourceGroupName "Api-Default-WestUS" -ServiceName "contoso"
Set-AzApiManagementPolicy -Context $apimContext -ApiId "9876543210" -Policy $PolicyString
```

Perintah ini menetapkan kebijakan cakupan API untuk API Management.

### Contoh 4: Mengatur kebijakan cakupan operasi
```powershell
$apimContext = New-AzApiManagementContext -ResourceGroupName "Api-Default-WestUS" -ServiceName "contoso"
Set-AzApiManagementPolicy -Context $apimContext -ApiId "9876543210" -OperationId "777" -Policy $PolicyString
```

Perintah ini menetapkan kebijakan cakupan operasi untuk API Management.

## PARAMETERS

### -ApiId
Menentukan pengidentifikasi API yang ada.
Jika Anda menentukan parameter ini, cmdlet menetapkan kebijakan cakupan API.

```yaml
Type: System.String
Parameter Sets: SetApiLevel, SetOperationLevel
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ApiRevision
Pengidentifikasi Revisi API. Parameter ini bersifat opsional. Jika tidak ditentukan, kebijakan akan diperbarui dalam revisi api yang saat ini aktif.

```yaml
Type: System.String
Parameter Sets: SetApiLevel, SetOperationLevel
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

### -Format
Menentukan format kebijakan. Saat menggunakan `application/vnd.ms-azure-apim.policy+xml`, ekspresi yang terkandung dalam kebijakan harus dilewati XML. Saat menggunakannya `application/vnd.ms-azure-apim.policy.raw+xml` **, kebijakan tidak** perlu diloloskan XML.
Nilai defaultnya adalah `application/vnd.ms-azure-apim.policy+xml`.
Parameter ini bersifat opsional.

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

### -OperationId
Menentukan pengidentifikasi operasi yang ada.
Jika ditentukan dengan ApiId akan mengatur kebijakan cakupan operasi.
Parameter ini diperlukan.

```yaml
Type: System.String
Parameter Sets: SetOperationLevel
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

### -Kebijakan
Menentukan dokumen kebijakan sebagai string.
Parameter ini diperlukan jika -*PolicyFilePath* tidak ditentukan.

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

### -PolicyFilePath
Menentukan jalur file dokumen kebijakan.
Parameter ini diperlukan jika parameter *Policy* tidak ditentukan.

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

### -PolicyUrl
Url tempat dokumen Kebijakan dihosting. Parameter ini diperlukan jika -Policy atau -PolicyFilePath tidak ditentukan.

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

### -ProductId
Menentukan pengidentifikasi produk yang ada.
Jika parameter ini ditentukan, cmdlet menetapkan kebijakan cakupan produk.

```yaml
Type: System.String
Parameter Sets: SetProductLevel
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Microsoft.Azure.Commands.ApiManagement.ServiceManagement.Models.PsApiManagementContext

### System.String

### System.Management.Automation.SwitchParameter

## OUTPUTS

### System.Boolean

## NOTES

## RELATED LINKS

[Get-AzApiManagementPolicy](./Get-AzApiManagementPolicy.md)

[Remove-AzApiManagementPolicy](./Remove-AzApiManagementPolicy.md)


