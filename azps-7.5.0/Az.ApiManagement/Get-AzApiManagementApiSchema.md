---
external help file: Microsoft.Azure.PowerShell.Cmdlets.ApiManagement.ServiceManagement.dll-Help.xml
Module Name: Az.ApiManagement
online version: https://docs.microsoft.com/powershell/module/az.apimanagement/get-azapimanagementapischema
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ApiManagement/ApiManagement/help/Get-AzApiManagementApiSchema.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ApiManagement/ApiManagement/help/Get-AzApiManagementApiSchema.md
ms.openlocfilehash: 9dbc63161c867ff7f5d2c5af48ca39a5c6619699
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144209531"
---
# Get-AzApiManagementApiSchema

## SYNOPSIS
Mendapatkan detail Skema API

## SYNTAX

### ContextParameterSet (Default)
```
Get-AzApiManagementApiSchema -Context <PsApiManagementContext> -ApiId <String> [-SchemaId <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ResourceIdParameterSet
```
Get-AzApiManagementApiSchema -ResourceId <String> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzApiManagementApiSchema** mendapatkan detail Skema API

## EXAMPLES

### Contoh 1: Dapatkan detail semua Skema Api dari Api
```powershell
$context = New-AzApiManagementContext -ResourceId /subscriptions/subid/resourceGroups/resourceGroupName/providers/Microsoft.ApiManagement/service/sdktestapim4163
Get-AzApiManagementApiSchema -Context $context -ApiId wsdlapitest
```

```output
SchemaId           : 2a03e1b4-1826-4e59-b372-4711f575db28
Api Id             : wsdlapitest
Schema ContentType : xsdschema
Schema Document    : <s:schema elementFormDefault="qualified"....

SchemaId           : b6e5497d-f65a-4851-9f5b-b5684cdae688
Api Id             : wsdlapitest
Schema ContentType : xsdschema
Schema Document    : <?xml version=""1.0"" encoding=""UTF-8""....
```

Perintah ini mendapatkan semua skema API yang terkait dengan Api `swagger-petstore-extensive` untuk Konteks ApiManagement tertentu.

### Contoh 2: Mendapatkan skema tertentu yang terkait dengan Api
```powershell
$context = New-AzApiManagementContext -ResourceId /subscriptions/subid/resourceGroups/resourceGroupName/providers/Microsoft.ApiManagement/service/sdktestapim4163
Get-AzApiManagementApiSchema -Context $context -ApiId swagger-petstore-extensive -SchemaId 5cc9cf67e6ed3b1154e638bd
```

```output
SchemaId           : 5cc9cf67e6ed3b1154e638bd
Api Id             : swagger-petstore-extensive
Schema ContentType : swaggerdefinition
Schema Document    : {
                       "definitions": {
                         "pet": {
                        ....
```

Perintah ini mendapatkan skema `5cc9cf67e6ed3b1154e638bd` API yang terkait dengan Api `swagger-petstore-extensive` untuk Konteks ApiManagement tertentu.

## PARAMETERS

### -ApiId
Pengidentifikasi API untuk dicari.
Jika ditentukan akan mencoba mendapatkan API dengan Id.

```yaml
Type: System.String
Parameter Sets: ContextParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Context
Instans PsApiManagementContext.
Parameter ini diperlukan.

```yaml
Type: Microsoft.Azure.Commands.ApiManagement.ServiceManagement.Models.PsApiManagementContext
Parameter Sets: ContextParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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

### -ResourceId
Pengidentifikasi Sumber Daya Arm dari Skema Api. Jika ditentukan akan mencoba menemukan skema api oleh pengidentifikasi. Parameter ini diperlukan.

```yaml
Type: System.String
Parameter Sets: ResourceIdParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SchemaId
Pengidentifikasi Skema.

```yaml
Type: System.String
Parameter Sets: ContextParameterSet
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

### Microsoft.Azure.Commands.ApiManagement.ServiceManagement.Models.PsApiManagementContext

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.ApiManagement.ServiceManagement.Models.PsApiManagementApiSchema

## NOTES

## RELATED LINKS

[New-AzApiManagementApiSchema](./New-AzApiManagementApiSchema.md)

[Remove-AzApiManagementApiSchema](./Remove-AzApiManagementApiSchema.md)

[Set-AzApiManagementApiSchema](./Set-AzApiManagementApiSchema.md)