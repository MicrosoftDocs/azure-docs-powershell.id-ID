---
external help file: Microsoft.Azure.PowerShell.Cmdlets.ApiManagement.dll-Help.xml
Module Name: Az.ApiManagement
online version: https://docs.microsoft.com/powershell/module/az.apimanagement/set-azapimanagement
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ApiManagement/ApiManagement/help/Set-AzApiManagement.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ApiManagement/ApiManagement/help/Set-AzApiManagement.md
ms.openlocfilehash: 5a7006da18379243a6ce788677ceb0e11b9796f1
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145513027"
---
# Set-AzApiManagement

## SYNOPSIS

Memperbarui layanan Azure Api Management

## SYNTAX

```
Set-AzApiManagement -InputObject <PsApiManagement> [-SystemAssignedIdentity] [-UserAssignedIdentity <String[]>]
 [-AsJob] [-PassThru] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

Cmdlet **Set-AzApiManagement** memperbarui layanan Azure API Management.

## EXAMPLES

### Contoh 1: Dapatkan layanan API Management dan skalakan ke Premium dan Tambahkan wilayah

```powershell
$apim = Get-AzApiManagement -ResourceGroupName "ContosoGroup" -Name "ContosoApi"
$apim.Sku = "Premium"
$apim.Capacity = 5
$apim.AddRegion("Central US", "Premium", 3)
Set-AzApiManagement -InputObject $apim
```

Contoh ini mendapatkan instans Api Management, menskalakannya ke lima unit premium dan kemudian menambahkan tiga unit tambahan ke wilayah premium.

### Contoh 2: Memperbarui penyebaran (VNET eksternal)

```powershell
$virtualNetwork = New-AzApiManagementVirtualNetwork -SubnetResourceId "/subscriptions/a8ff56dc-3bc7-4174-a1e8-3726ab15d0e2/resourceGroups/Api-Default-WestUS/providers/Microsoft.Network/virtualNetworks/dfVirtualNetwork/subnets/backendSubnet"
$apim = Get-AzApiManagement -ResourceGroupName "ContosoGroup" -Name "ContosoApi"
$apim.VpnType = "External"
$apim.VirtualNetwork = $virtualNetwork
Set-AzApiManagement -InputObject $apim
```

Perintah ini memperbarui penyebaran API Management yang ada dan bergabung ke *VpnType* eksternal.

### Contoh 3: Membuat dan menginisialisasi instans PsApiManagementCustomHostNameConfiguration menggunakan Rahasia dari Sumber Daya KeyVault

```powershell
$portal = New-AzApiManagementCustomHostnameConfiguration -Hostname "portal.contoso.com" -HostnameType Portal -KeyVaultId "https://apim-test-keyvault.vault.azure.net/secrets/api-portal-custom-ssl.pfx"
$proxy1 = New-AzApiManagementCustomHostnameConfiguration -Hostname "gatewayl.contoso.com" -HostnameType Proxy -KeyVaultId "https://apim-test-keyvault.vault.azure.net/secrets/contoso-proxy-custom-ssl.pfx"
$proxy2 = New-AzApiManagementCustomHostnameConfiguration -Hostname "gatewayl.foobar.com" -HostnameType Proxy -KeyVaultId "https://apim-test-keyvault.vault.azure.net/secrets/foobar-proxy-custom-ssl.pfx"
$proxyCustomConfig = @($proxy1,$proxy2)
$apim = Get-AzApiManagement -ResourceGroupName "ContosoGroup" -Name "ContosoApi"
$apim.PortalCustomHostnameConfiguration = $portal
$apim.ProxyCustomHostnameConfiguration = $proxyCustomConfig 
Set-AzApiManagement -InputObject $apim -SystemAssignedIdentity
```

### Contoh 4: Memperbarui Email Publisher, Email NotificationSender, dan Nama Organisasi

```powershell
$apim = Get-AzApiManagement -ResourceGroupName "api-Default-West-US" -Name "Contoso"
$apim.PublisherEmail = "foobar@contoso.com"
$apim.NotificationSenderEmail = "notification@contoso.com"
$apim.OrganizationName = "Contoso"
Set-AzApiManagement -InputObject $apim -PassThru
```

### Contoh 5: Menambahkan Sertifikat Terkelola ke Layanan APIM

```powershell
PS D:> $gateway=New-AzApiManagementCustomHostnameConfiguration -Hostname freecertCanary.contoso.api -HostnameType Proxy -ManagedCertificate
PS D:> $customConfig= @($gateway)
PS D:> $apim=Get-AzApiManagement -ResourceGroupName contosogroup -Name contosoapim
PS D:> $apim.ProxyCustomHostnameConfiguration = $customConfig
PS D:> Set-AzApiManagement -InputObject $apim -PassThru


PublicIPAddresses                     : {20.45.236.81}
PrivateIPAddresses                    :
Id                                    : /subscriptions/a200340d-6b82-494d-9dbf-687ba6e33f9e/resourceGroups/Api-Default-
                                        Central-US-EUAP/providers/Microsoft.ApiManagement/service/contosoapim
Name                                  : contosoapim
Location                              : Central US EUAP
Sku                                   : Developer
Capacity                              : 1
CreatedTimeUtc                        : 8/24/2021 10:40:21 PM
ProvisioningState                     : Succeeded
RuntimeUrl                            : https://contosoapim.azure-api.net
RuntimeRegionalUrl                    : https://contosoapim-centraluseuap-01.regional.azure-api.net
PortalUrl                             : https://contosoapim.portal.azure-api.net
DeveloperPortalUrl                    : https://contosoapim.developer.azure-api.net
ManagementApiUrl                      : https://contosoapim.management.azure-api.net
ScmUrl                                : https://contosoapim.scm.azure-api.net
PublisherEmail                        : zhonren@microsoft.com
OrganizationName                      : Microsoft
NotificationSenderEmail               : apimgmt-noreply@mail.windowsazure.com
VirtualNetwork                        :
VpnType                               : None
PortalCustomHostnameConfiguration     :
ProxyCustomHostnameConfiguration      : {contosoapim.azure-api.net, freecertCanary..contoso.api}
ManagementCustomHostnameConfiguration :
ScmCustomHostnameConfiguration        :
DeveloperPortalHostnameConfiguration  :
SystemCertificates                    :
Tags                                  : {}
AdditionalRegions                     : {}
SslSetting                            : Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagementSslSetting
Identity                              : Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagementServiceIdentity
EnableClientCertificate               :
Zone                                  :
DisableGateway                        : False
MinimalControlPlaneApiVersion         :
PublicIpAddressId                     :
PlatformVersion                       : stv2
PublicNetworkAccess                   : Enabled
PrivateEndpointConnections            :
ResourceGroupName                     : contosogroup

PS D:> $apim.ProxyCustomHostnameConfiguration

CertificateInformation     :
EncodedCertificate         :
HostnameType               : Proxy
CertificatePassword        :
Hostname                   : contosoapim.azure-api.net
KeyVaultId                 :
DefaultSslBinding          : False
NegotiateClientCertificate : False
IdentityClientId           :
CertificateStatus          :
CertificateSource          : BuiltIn

CertificateInformation     : Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagementCertificateInformation
EncodedCertificate         :
HostnameType               : Proxy
CertificatePassword        :
Hostname                   : freecertCanary.contoso.api
KeyVaultId                 :
DefaultSslBinding          : True
NegotiateClientCertificate : False
IdentityClientId           :
CertificateStatus          :
CertificateSource          : Managed

```

Sampel ini menambahkan Sertifikat Terkelola ke layanan API Management.

## PARAMETERS

### -AsJob

Jalankan cmdlet di latar belakang

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

### -InputObject

Instans ApiManagement.

```yaml
Type: Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagement
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -PassThru

Mengirim PsApiManagement yang diperbarui ke alur jika operasi berhasil.

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

### -SystemAssignedIdentity

Buat dan tetapkan identitas Azure Active Directory untuk server ini untuk digunakan dengan layanan manajemen utama seperti Azure KeyVault.

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

### -UserAssignedIdentity

Tetapkan Identitas Pengguna ke server ini untuk digunakan dengan layanan manajemen kunci seperti Azure KeyVault.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
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

### Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagement

## OUTPUTS

### Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagement

## NOTES

## RELATED LINKS

[Get-AzApiManagement](./Get-AzApiManagement.md)

[New-AzApiManagement](./New-AzApiManagement.md)

[Remove-AzApiManagement](./Remove-AzApiManagement.md)
