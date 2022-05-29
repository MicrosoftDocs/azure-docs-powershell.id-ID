---
description: Panduan migrasi ini berisi daftar perubahan mencolok yang dilakukan pada Azure PowerShell dalam rilis Az versi 8.0.0.
ms.custom: devx-track-azurepowershell
ms.date: 05/24/2022
ms.devlang: powershell
ms.service: azure-powershell
ms.topic: conceptual
title: Panduan migrasi untuk Az 8.0.0
ms.openlocfilehash: c7e257c34cd2d5740393ec24881339462ecd9514
ms.sourcegitcommit: 82b4008b76d035e4aee733727371765b0d853bed
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145757004"
---
# <a name="migration-guide-for-az-800"></a>Panduan Migrasi untuk Az 8.0.0
## <a name="azaks"></a>Az.Aks

### `Get-AzAks`
Alias `Get-AzAks` dihapus. Silakan gunakan `Get-AzAksCluster` sebagai gantinya.

#### <a name="before"></a>Sebelumnya
```powershell
Get-AzAks -ResourceGroupName $resourceGroupName -Name $name
```
#### <a name="after"></a>Sesudahnya
```powershell
Get-AzAksCluster -ResourceGroupName $resourceGroupName -Name $name
```

### `New-AzAks`
Alias `New-AzAks` dihapus. Silakan gunakan `New-AzAksCluster` sebagai gantinya.

#### <a name="before"></a>Sebelumnya
```powershell
New-AzAks -ResourceGroupName $resourceGroupName -Name $name -Location $location
```
#### <a name="after"></a>Sesudahnya
```powershell
New-AzAksCluster -ResourceGroupName $resourceGroupName -Name $name -Location $location
```

### `Set-AzAks`
Alias `Set-AzAks` dihapus. Silakan gunakan `Set-AzAksCluster` sebagai gantinya.

#### <a name="before"></a>Sebelumnya
```powershell
Set-AzAks -ResourceGroupName $resourceGroupName -Name $name
```
#### <a name="after"></a>Sesudahnya
```powershell
Set-AzAksCluster -ResourceGroupName $resourceGroupName -Name $name
```

### `Remove-AzAks`
Alias `Remove-AzAks` dihapus. Silakan gunakan `Remove-AzAksCluster` sebagai gantinya.

#### <a name="before"></a>Sebelumnya
```powershell
Remove-AzAks -ResourceGroupName $resourceGroupName -Name $name
```
#### <a name="after"></a>Sesudahnya
```powershell
Remove-AzAksCluster -ResourceGroupName $resourceGroupName -Name $name
```

## <a name="azcdn"></a>Az.Cdn

### `New-AzCdnProfile`
Mengubah jenis parameter `Sku` menjadi `SkuName` Mengubah jenis parameter `ProfileName` menjadi `Name`

#### <a name="before"></a>Sebelumnya
```powershell
$profileSku = "Standard_Microsoft";
$cdnProfileName = "profileNameXXXX";
$resourceGroupName = "myresourcegroup"
New-AzCdnProfile -Sku $profileSku -ProfileName $cdnProfileName -ResourceGroupName $resourceGroupName -Location Global
```
#### <a name="after"></a>Sesudahnya
```powershell
$profileSku = "Standard_Microsoft";
$cdnProfileName = "profileNameXXXX";
$resourceGroupName = "myresourcegroup"
New-AzCdnProfile -SkuName $profileSku -Name $cdnProfileName -ResourceGroupName $resourceGroupName -Location Global
```

### `New-AzCdnEndpoint`
Mengubah parameter `EndpointName` ke `Name` Parameter `GeoFilters` yang diubah menjadi `GeoFilter` Parameter `DefaultOriginGroup` yang diubah ke `DefaultOriginGroupId` Parameter `OriginHostName`penggabungan ,`OriginId`,,`OriginName`,`PrivateLinkApprovalMessage``PrivateLinkLocation``Priority`,`PrivateLinkResourceId`,`Weight`,`HttpsPort``HttpPort`ke dalam parameter `Origin` Gabungkan parameter `OriginGroupName`,`OriginGroupProbeIntervalInSeconds`,,`OriginGroupProbeProtocol``OriginGroupProbeRequestType``OriginGroupProbePath`ke parameter `OriginGroup` Pisahkan `DeliveryPolicy` `DeliveryPolicyDescription`parameter ke parameter ,`DeliveryPolicyRule` Tambahkan parameter `SubscriptionId`,`UrlSigningKey` ,`WebApplicationFirewallPolicyLinkId` Hapus parameter`CdnProfile `

#### <a name="before"></a>Sebelumnya
```powershell
New-AzCdnEndpoint -ResourceGroupName myresourcegroup -ProfileName mycdnprofile -Location westus -EndpointName myendpoint `
                  -OriginName mystorage -OriginHostName mystorage.blob.core.windows.net `
                  -OriginHostHeader mystorage.blob.core.windows.net -IsHttpAllowed $false
```
#### <a name="after"></a>Sesudahnya
```powershell
$origin = @{
  Name = "origin1"
  HostName = "host1.hello.com"
};
$location = "westus"

$endpoint = New-AzCdnEndpoint -Name $endpointName -ResourceGroupName $ResourceGroupName -ProfileName $cdnProfileName -Location $location -Origin $origin
```

### `New-AzCdnDeliveryPolicy`
Hapus perintah `New-AzCdnDeliveryPolicy`. Gunakan `New-AzCdnDeliveryRuleObject` buat objek aturan dan gunakan secara `New-AzCdnEndpoint` langsung


### `New-AzCdnDeliveryRule`
Mengubah nama perintah menjadi `New-AzCdnDeliveryRuleObject`

#### <a name="before"></a>Sebelumnya
```powershell
New-AzCdnDeliveryRule -Name "rule1" -Order 1 -Condition $cond1 -Action $action1
```
#### <a name="after"></a>Sesudahnya
```powershell
$cond1 = New-AzCdnDeliveryRuleIsDeviceConditionObject -Name "IsDevice" -ParameterMatchValue "Desktop"
$action1 = New-AzCdnUrlRewriteActionObject -Name "UrlRewrite" -ParameterDestination "/def" -ParameterSourcePattern "/abc" -ParameterPreserveUnmatchedPath $true
$rule1 = New-AzCdnDeliveryRuleObject -Name "Rule1" -Action $action1,$action2 -Condition $cond1 -Order 1
```

### `New-AzCdnCustomDomain`
Mengubah jenis parameter `CustomDomainName` untuk `Name` Menambahkan parameter Hapus parameter `SubscriptionId``CdnEndpoint`

#### <a name="before"></a>Sebelumnya
```powershell
New-AzCdnCustomDomain -ResourceGroupName $resourceGroupName -ProfileName $cdnProfileName -EndpointName $endpointName -CustomDomainName $customDomainName -HostName $customDomainHostName
```
#### <a name="after"></a>Sesudahnya
```powershell
New-AzCdnCustomDomain -ResourceGroupName $resourceGroupName -ProfileName $cdnProfileName -EndpointName $endpointName -Name $customDomainName -HostName $customDomainHostName -SubscriptionId $subId
```

### `Set-AzCdnProfile`
Digantikan oleh perintah `Update-AzCdnProfile`

#### <a name="before"></a>Sebelumnya
```powershell
$profileObject = Get-AzCdnProfile -ResourceGroupName myresourcegroup -ProfileName mycdnprofile
$profileObject.Tags = @{"key"="value"}
Set-AzCdnProfile -CdnProfile $profileObject
```

#### <a name="after"></a>Sesudahnya
```powershell
$profileSku = "Standard_Microsoft";
$cdnProfileName = "profileNameXXXX";
$resourceGroupName = "myresourcegroup"
New-AzCdnProfile -SkuName $profileSku -Name $cdnProfileName -ResourceGroupName $resourceGroupName -Location Global

$tags = @{
  Tag1 = 11
  Tag2  = 22
}
Update-AzCdnProfile -Name $cdnProfileName -ResourceGroupName $resourceGroupName -Tag $tags
```

### `Set-AzCdnEndpoint`
Digantikan oleh perintah `Update-AzCdnEndpoint`
`DeliveryPolicyDescription` dan `DeliveryPolicyRule` harus disediakan bersama-sama ketika Anda ingin memperbarui salah satunya.

#### <a name="before"></a>Sebelumnya
```powershell
$endpointObject = Get-AzCdnEndpoint -ResourceGroupName myresourcegroup -ProfileName mycdnprofile -EndpointName myendpoint
$endpointObject.IsHttpAllowed = $false
Set-AzCdnEndpoint -CdnEndpoint $endpointObject
```
#### <a name="after"></a>Sesudahnya
```powershell
$tags = @{
  Tag1 = 11
  Tag2  = 22
}

//Update tags
Update-AzCdnEndpoint -Name $endpointName -ProfileName $cdnProfileName -ResourceGroupName $resourceGroupName -Tag $tags

//Update DeliveryPolicyDescription or DeliveryPolicyRule
Update-AzCdnEndpoint -Name $endpointName -ProfileName $cdnProfileName -ResourceGroupName $resourceGroupName `
   -DeliveryPolicyDescription $descprption -DeliveryPolicyRule $rule
```

### `Set-AzCdnOriginGroup`
Digantikan oleh perintah `Update-AzCdnOriginGroup`

#### <a name="before"></a>Sebelumnya
```powershell
Set-AzCdnOriginGroup -ResourceGroupName $resourceGroupName -ProfileName $profileName -EndpointName $endpointName -OriginGroupName $originGroupName -OriginId $originIds -ProbeIntervalInSeconds $probeInterval
```
#### <a name="after"></a>Sesudahnya
```powershell
Update-AzCdnOriginGroup -EndpointName $endpointName -Name $originGroup.Name -ProfileName $cdnProfileName -ResourceGroupName $ResourceGroupName `
                -HealthProbeSetting $healthProbeParametersObject2 -Origin @(@{ Id = $originId })

```

### `Set-AzCdnOrigin`
Digantikan oleh perintah `Update-AzCdnOrigin`

#### <a name="before"></a>Sebelumnya
```powershell
Set-AzCdnOrigin -ResourceGroupName $resourceGroupName -ProfileName $cdnProfileName -EndpointName $endpointName `
    -OriginName $originName -HostName "mystorage2.blob.core.windows.net"
```
#### <a name="after"></a>Sesudahnya
```powershell
Update-AzCdnOrigin -ResourceGroupName $resourceGroupName -ProfileName $cdnProfileName -EndpointName $endpointName `
    -Name $originName  -HostName "mystorage2.blob.core.windows.net" -HttpPort 456 -HttpsPort 789
```

## <a name="azeventhub"></a>Az.EventHub

### `New-AzEventHubNamespace`
Parameter `Identity` dihapus.
#### <a name="before"></a>Sebelumnya
```powershell
New-AzEventHubNamespace -ResourceGroupName myresourcegroup -Name MyNamespaceName -Location northeurope -SkuName Premium -IdentityType SystemAssigned -Identity
```
#### <a name="after"></a>Sesudahnya
```powershell
New-AzEventHubNamespace -ResourceGroupName myresourcegroup -Name MyNamespaceName -Location northeurope -SkuName Premium -IdentityType SystemAssigned
```

### `Set-AzEventHubNamespace`
Parameter `Identity` dihapus.
#### <a name="before"></a>Sebelumnya
```powershell
Set-AzEventHubNamespace -ResourceGroupName myresourcegroup -Name MyNamespaceName -EncryptionConfig $ec1,$ec2 -Identity
```
#### <a name="after"></a>Sesudahnya
```powershell
Set-AzEventHubNamespace -ResourceGroupName myresourcegroup -Name MyNamespaceName -EncryptionConfig $ec1,$ec2
```


## <a name="azhealthcareapis"></a>Az.HealthcareApis

### `Set-AzHealthcareApisService`
Gabungkan New-AzHealthcareApisService dan Set-AzHealthcareApisService ke dalam New-AzHealthcareApisService

#### <a name="before"></a>Sebelumnya
```powershell
Set-AzHealthcareApisService -Name MyService -ResourceGroupName MyResourceGroup -CosmosOfferThroughput 500
```
#### <a name="after"></a>Sesudahnya
```powershell
New-AzHealthcareApisService -Name MyService -ResourceGroupName MyResourceGroup -Location MyLocation -Kind fhir-R4 -CosmosOfferThroughput 500
```


### `Get-AzHealthcareApisService`
`-ResourceId` dihapus

#### <a name="before"></a>Sebelumnya
```powershell
Get-AzHealthcareApisService -ResourceId $ResourceId
```
#### <a name="after"></a>Sesudahnya
```powershell
Get-AzHealthcareApisService -ResourceGroupName $ResourceGroup -Name $Name
```


### `Remove-AzHealthcareApisService`
`-ResourceId` dihapus

#### <a name="before"></a>Sebelumnya
```powershell
Remove-AzHealthcareApisService -ResourceId $ResourceId
```
#### <a name="after"></a>Sesudahnya
```powershell
Remove-AzHealthcareApisService -ResourceGroupName $ResourceGroup -Name $Name
```


### `New-AzHealthcareApisService`
`-ManagedIdentity`diganti `-IdentityType``-FhirVersion`
namanya menjadi dihapus dan konten yang diinginkan dapat dipilih dengan parameter `-Kind``-DisableCorsCredential`
dan `-AllowCorsCredential`: sekarang dinamai seragam sebagai `-AllowCorsCredential`, contoh: -AllowCorsCredential:$false atau -AllowCorsCredential:$true `-DisableSmartProxy` dan `-EnableSmartProxy`: sekarang dinamai seragam sebagai `-EnableSmartProxy`, contoh: -EnableSmartProxy:$false atau -EnableSmartProxy:$true

#### <a name="before"></a>Sebelumnya
```powershell
New-AzHealthcareApisService -Name MyService -ResourceGroupName MyResourceGroup -Location MyLocation -FhirVersion fhir-R4 -CosmosOfferThroughput 500 -ManagedIdentity $IdentityType -DisableCorsCredential -DisableSmartProxy
```
#### <a name="after"></a>Sesudahnya
```powershell
New-AzHealthcareApisService -Name MyService -ResourceGroupName MyResourceGroup -Location MyLocation -Kind fhir-R4 -CosmosOfferThroughput 500 -IdentityType $IdentityType -AllowCorsCredential:$false -EnableSmartProxy:$false
```


