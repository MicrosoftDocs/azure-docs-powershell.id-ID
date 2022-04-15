---
external help file: Microsoft.Azure.PowerShell.Cmdlets.ResourceManager.dll-Help.xml
Module Name: Az.Resources
ms.assetid: BA40BD11-8167-48D7-AC71-72B2FD9924F2
online version: https://docs.microsoft.com/powershell/module/az.resources/new-azpolicyassignment
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/New-AzPolicyAssignment.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/New-AzPolicyAssignment.md
ms.openlocfilehash: ef8b57d5dea44040a4280ee6ad7fcce8942a0c2a
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142166079"
---
# New-AzPolicyAssignment

## SYNOPSIS
Membuat penetapan kebijakan.

## SYNTAX

### DefaultParameterSet (Default)
```
New-AzPolicyAssignment -Name <String> [-Scope <String>] [-NotScope <String[]>] [-DisplayName <String>]
 [-Description <String>] [-PolicyDefinition <PsPolicyDefinition>]
 [-PolicySetDefinition <PsPolicySetDefinition>] [-Metadata <String>]
 [-EnforcementMode <PolicyAssignmentEnforcementMode>] [-AssignIdentity] [-IdentityType <ManagedIdentityType>]
 [-IdentityId <String>] [-Location <String>] [-NonComplianceMessage <PsNonComplianceMessage[]>]
 [-ApiVersion <String>] [-Pre] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### PolicyParameterObjectParameterSet
```
New-AzPolicyAssignment -Name <String> [-Scope <String>] [-NotScope <String[]>] [-DisplayName <String>]
 [-Description <String>] -PolicyDefinition <PsPolicyDefinition> [-PolicySetDefinition <PsPolicySetDefinition>]
 -PolicyParameterObject <Hashtable> [-Metadata <String>] [-EnforcementMode <PolicyAssignmentEnforcementMode>]
 [-AssignIdentity] [-IdentityType <ManagedIdentityType>] [-IdentityId <String>] [-Location <String>]
 [-NonComplianceMessage <PsNonComplianceMessage[]>] [-ApiVersion <String>] [-Pre]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### PolicyParameterStringParameterSet
```
New-AzPolicyAssignment -Name <String> [-Scope <String>] [-NotScope <String[]>] [-DisplayName <String>]
 [-Description <String>] -PolicyDefinition <PsPolicyDefinition> [-PolicySetDefinition <PsPolicySetDefinition>]
 -PolicyParameter <String> [-Metadata <String>] [-EnforcementMode <PolicyAssignmentEnforcementMode>]
 [-AssignIdentity] [-IdentityType <ManagedIdentityType>] [-IdentityId <String>] [-Location <String>]
 [-NonComplianceMessage <PsNonComplianceMessage[]>] [-ApiVersion <String>] [-Pre]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### PolicySetParameterObjectParameterSet
```
New-AzPolicyAssignment -Name <String> [-Scope <String>] [-NotScope <String[]>] [-DisplayName <String>]
 [-Description <String>] [-PolicyDefinition <PsPolicyDefinition>] -PolicySetDefinition <PsPolicySetDefinition>
 -PolicyParameterObject <Hashtable> [-Metadata <String>] [-EnforcementMode <PolicyAssignmentEnforcementMode>]
 [-AssignIdentity] [-IdentityType <ManagedIdentityType>] [-IdentityId <String>] [-Location <String>]
 [-NonComplianceMessage <PsNonComplianceMessage[]>] [-ApiVersion <String>] [-Pre]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### PolicySetParameterStringParameterSet
```
New-AzPolicyAssignment -Name <String> [-Scope <String>] [-NotScope <String[]>] [-DisplayName <String>]
 [-Description <String>] [-PolicyDefinition <PsPolicyDefinition>] -PolicySetDefinition <PsPolicySetDefinition>
 -PolicyParameter <String> [-Metadata <String>] [-EnforcementMode <PolicyAssignmentEnforcementMode>]
 [-AssignIdentity] [-IdentityType <ManagedIdentityType>] [-IdentityId <String>] [-Location <String>]
 [-NonComplianceMessage <PsNonComplianceMessage[]>] [-ApiVersion <String>] [-Pre]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzPolicyAssignment** membuat penetapan kebijakan.
Tentukan kebijakan dan lingkup.

## EXAMPLES

### Contoh 1: Penetapan kebijakan pada tingkat langganan
```powershell
$Subscription = Get-AzSubscription -SubscriptionName 'Subscription01'
$Policy = Get-AzPolicyDefinition -Name 'VirtualMachinePolicy'
New-AzPolicyAssignment -Name 'VirtualMachinePolicyAssignment' -PolicyDefinition $Policy -Scope "/subscriptions/$($Subscription.Id)"
```

Perintah pertama mendapatkan langganan bernama Subscription01 menggunakan cmdlet Get-AzSubscription dan menyimpannya dalam variabel $Subscription.
Perintah kedua mendapatkan definisi kebijakan bernama VirtualMachinePolicy dengan menggunakan cmdlet Get-AzPolicyDefinition dan menyimpannya dalam variabel $Policy.
Perintah akhir menetapkan kebijakan dalam $Policy pada tingkat langganan yang diidentifikasi oleh string lingkup langganan.

### Contoh 2: Penetapan kebijakan di tingkat grup sumber daya
```powershell
$ResourceGroup = Get-AzResourceGroup -Name 'ResourceGroup11'
$Policy = Get-AzPolicyDefinition -Name 'VirtualMachinePolicy'
New-AzPolicyAssignment -Name 'VirtualMachinePolicyAssignment' -PolicyDefinition $Policy -Scope $ResourceGroup.ResourceId
```

Perintah pertama mendapatkan grup sumber daya bernama ResourceGroup11 dengan menggunakan cmdlet Get-AzResourceGroup dan menyimpannya dalam variabel $ResourceGroup.
Perintah kedua mendapatkan definisi kebijakan bernama VirtualMachinePolicy dengan menggunakan cmdlet Get-AzPolicyDefinition dan menyimpannya dalam variabel $Policy.
Perintah akhir menetapkan kebijakan dalam $Policy pada tingkat grup sumber daya yang diidentifikasi oleh properti **ResourceId** $ResourceGroup.

### Contoh 3: Penetapan kebijakan pada tingkat grup sumber daya dengan objek parameter kebijakan
```powershell
$ResourceGroup = Get-AzResourceGroup -Name 'ResourceGroup11'
$Policy = Get-AzPolicyDefinition -BuiltIn | Where-Object {$_.Properties.DisplayName -eq 'Allowed locations'}
$Locations = Get-AzLocation | where displayname -like '*east*'
$AllowedLocations = @{'listOfAllowedLocations'=($Locations.location)}
New-AzPolicyAssignment -Name 'RestrictLocationPolicyAssignment' -PolicyDefinition $Policy -Scope $ResourceGroup.ResourceId -PolicyParameterObject $AllowedLocations
```

Perintah pertama mendapatkan grup sumber daya bernama ResourceGroup11 menggunakan cmdlet Get-AzResourceGroup.
Perintah menyimpan objek tersebut dalam variabel $ResourceGroup.
Perintah kedua mendapatkan definisi kebijakan bawaan untuk lokasi yang diperbolehkan dengan menggunakan cmdlet Get-AzPolicyDefinition.
Perintah menyimpan objek tersebut dalam variabel $Policy.
Perintah ketiga dan keempat membuat objek yang berisi semua kawasan Azure dengan "timur" dalam nama.
Perintah menyimpan objek tersebut dalam variabel $AllowedLocations.
Perintah akhir menetapkan kebijakan dalam $Policy pada tingkat grup sumber daya menggunakan objek parameter kebijakan di $AllowedLocations.
Properti **ResourceId** $ResourceGroup mengidentifikasi grup sumber daya.

### Contoh 4: Penetapan kebijakan pada tingkat grup sumber daya dengan file parameter kebijakan
Buat file yang disebut _AllowedLocations.json_ di direktori kerja lokal dengan konten berikut ini.


```powershell
<#{
    "listOfAllowedLocations":  {
      "value": [
        "westus",
        "westeurope",
        "japanwest"
      ]
    }
}#>
$ResourceGroup = Get-AzResourceGroup -Name 'ResourceGroup11'
$Policy = Get-AzPolicyDefinition -BuiltIn | Where-Object {$_.Properties.DisplayName -eq 'Allowed locations'}
New-AzPolicyAssignment -Name 'RestrictLocationPolicyAssignment' -PolicyDefinition $Policy -Scope $ResourceGroup.ResourceId -PolicyParameter .\AllowedLocations.json
```

Perintah pertama mendapatkan grup sumber daya bernama ResourceGroup11 dengan menggunakan cmdlet Get-AzResourceGroup dan menyimpannya dalam variabel $ResourceGroup.
Perintah kedua mendapatkan definisi kebijakan bawaan untuk lokasi yang diperbolehkan dengan menggunakan cmdlet Get-AzPolicyDefinition dan menyimpannya dalam variabel $Policy.
Perintah akhir menetapkan kebijakan dalam $Policy di grup sumber daya yang diidentifikasi oleh properti **ResourceId** dari $ResourceGroup menggunakan file parameter kebijakan AllowedLocations.json dari direktori kerja lokal.

### Contoh 5: Penetapan kebijakan dengan identitas terkelola yang ditetapkan sistem
```powershell
$ResourceGroup = Get-AzResourceGroup -Name 'ResourceGroup11'
$Policy = Get-AzPolicyDefinition -Name 'VirtualMachinePolicy'
New-AzPolicyAssignment -Name 'VirtualMachinePolicyAssignment' -PolicyDefinition $Policy -Scope $ResourceGroup.ResourceId -Location 'eastus' -IdentityType 'SystemAssigned'
```

Perintah pertama mendapatkan grup sumber daya bernama ResourceGroup11 dengan menggunakan cmdlet Get-AzResourceGroup dan menyimpannya dalam variabel $ResourceGroup.
Perintah kedua mendapatkan definisi kebijakan bernama VirtualMachinePolicy dengan menggunakan cmdlet Get-AzPolicyDefinition dan menyimpannya dalam variabel $Policy.
Perintah akhir menetapkan kebijakan dalam $Policy ke grup sumber daya. Identitas terkelola yang ditetapkan sistem secara otomatis dibuat dan ditetapkan ke penetapan kebijakan.

### Contoh 6: Penetapan kebijakan dengan identitas terkelola yang ditetapkan pengguna
```powershell
$ResourceGroup = Get-AzResourceGroup -Name 'ResourceGroup11'
$Policy = Get-AzPolicyDefinition -Name 'VirtualMachinePolicy'
$UserAssignedIdentity = Get-AzUserAssignedIdentity -ResourceGroupName 'ResourceGroup1' -Name 'UserAssignedIdentity1'
New-AzPolicyAssignment -Name 'VirtualMachinePolicyAssignment' -PolicyDefinition $Policy -Scope $ResourceGroup.ResourceId -Location 'eastus' -IdentityType 'UserAssigned' -IdentityId $UserAssignedIdentity.Id
```

Perintah pertama mendapatkan grup sumber daya bernama ResourceGroup11 dengan menggunakan cmdlet Get-AzResourceGroup dan menyimpannya dalam variabel $ResourceGroup.
Perintah kedua mendapatkan definisi kebijakan bernama VirtualMachinePolicy dengan menggunakan cmdlet Get-AzPolicyDefinition dan menyimpannya dalam variabel $Policy.
Perintah ketiga mendapatkan identitas terkelola yang ditetapkan pengguna bernama UserAssignedIdentity1 dengan menggunakan cmdlet Get-AzUserAssignedIdentity dan menyimpannya dalam variabel $UserAssignedIdentity.
Perintah akhir menetapkan kebijakan dalam $Policy ke grup sumber daya. Pengguna yang ditetapkan identitas terkelola yang diidentifikasi oleh properti **Id** $UserAssignedIdentity ditetapkan ke penetapan kebijakan dengan mengirimkan properti **Id*** ke parameter IdentityId.

### Contoh 7: Penetapan kebijakan dengan properti mode penerapan
```powershell
$Subscription = Get-AzSubscription -SubscriptionName 'Subscription01'
$Policy = Get-AzPolicyDefinition -Name 'VirtualMachinePolicy'
New-AzPolicyAssignment -Name 'VirtualMachinePolicyAssignment' -PolicyDefinition $Policy -Scope "/subscriptions/$($Subscription.Id)" -EnforcementMode DoNotEnforce
```

Perintah pertama mendapatkan langganan bernama Subscription01 menggunakan cmdlet Get-AzSubscription dan menyimpannya dalam variabel $Subscription.
Perintah kedua mendapatkan definisi kebijakan bernama VirtualMachinePolicy dengan menggunakan cmdlet Get-AzPolicyDefinition dan menyimpannya dalam variabel $Policy.
Perintah akhir menetapkan kebijakan dalam $Policy pada tingkat langganan yang diidentifikasi oleh string lingkup langganan. Penetapan diatur dengan nilai EnforcementMode _doNotEnforce_ yaitu efek kebijakan tidak diberlakukan selama pembuatan atau pembaruan sumber daya.

### Contoh 8: Penetapan kebijakan dengan pesan non-kepatuhan
```powershell
$PolicySet = Get-AzPolicySetDefinition -Name 'VirtualMachinePolicySet'
$NonComplianceMessages = @(@{Message="Only DsV2 SKUs are allowed."; PolicyDefinitionReferenceId="DefRef1"}, @{Message="Virtual machines must follow cost management best practices."})
New-AzPolicyAssignment -Name 'VirtualMachinePolicyAssignment' -PolicySetDefinition $PolicySet -NonComplianceMessage $NonComplianceMessages
```

Perintah pertama mendapatkan definisi kumpulan kebijakan bernama VirtualMachinePolicySet menggunakan cmdlet Get-AzPolicySetDefinition dan menyimpannya dalam variabel $PolicySet.
Perintah kedua membuat array pesan yang tidak sesuai. Satu pesan tujuan umum untuk seluruh tugas dan satu pesan khusus untuk kebijakan pembatasan SKU dalam definisi kumpulan kebijakan yang ditetapkan.
Perintah akhir menetapkan definisi kumpulan kebijakan dalam $PolicySet ke langganan dengan dua pesan ketidakpatuhan yang akan diperlihatkan jika sumber daya ditolak oleh kebijakan.

## PARAMETERS

### -ApiVersion
Menentukan versi API penyedia sumber daya untuk digunakan.
Jika Anda tidak menentukan versi, cmdlet ini menggunakan versi terbaru yang tersedia.

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

### -AssignIdentity
Buat dan tetapkan identitas terkelola sistem yang ditetapkan untuk penetapan kebijakan ini. Identitas akan digunakan saat menjalankan penyebaran untuk kebijakan 'deployIfNotExists' dan 'modifikasi'. Lokasi diperlukan saat menetapkan identitas.

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

### -Deskripsi
Deskripsi untuk penetapan kebijakan

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

### -DisplayName
Menentukan nama tampilan untuk penetapan kebijakan.

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

### -EnforcementMode
Mode penerapan untuk penetapan kebijakan. Saat ini, nilai yang valid adalah Default, DoNotEnforce.

```yaml
Type: System.Nullable`1[Microsoft.Azure.Commands.ResourceManager.Cmdlets.Entities.Policy.PolicyAssignmentEnforcementMode]
Parameter Sets: (All)
Aliases:
Accepted values: Default, DoNotEnforce

Required: False
Position: Named
Default value: Default
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IdentityId
Menentukan ID identitas terkelola yang ditetapkan pengguna untuk ditetapkan ke penetapan kebijakan ini. Nilai ini diperlukan jika nilai 'UserAssigned' dikirimkan ke parameter -IdentityType. 

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

### -IdentityType
Menentukan tipe identitas terkelola untuk ditetapkan ke penetapan kebijakan ini. Jika nilai 'SystemAssigned' disediakan, identitas terkelola yang ditetapkan sistem akan dihasilkan dan ditetapkan untuk penetapan kebijakan ini. Jika nilai 'UserAssigned' disediakan, identitas yang ditetapkan pengguna yang dikirimkan melalui Id ke parameter -IdentityId ditetapkan untuk penetapan kebijakan ini. Identitas akan digunakan saat menjalankan penyebaran untuk kebijakan 'deployIfNotExists' dan 'modifikasi'. Lokasi diperlukan saat menetapkan identitas. Izin harus diberikan ke identitas menggunakan New-AzRoleAssignment setelah identitas yang ditetapkan sistem dibuat. Parameter IdentityType akan diberikan prioritas jika parameter AssignIdentity dan IdentityType digunakan.

```yaml
Type: System.Nullable`1[Microsoft.Azure.Commands.ResourceManager.Cmdlets.Entities.Resources.ManagedIdentityType]
Parameter Sets: (All)
Aliases:
Accepted values: SystemAssigned, UserAssigned, None

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Lokasi
Lokasi identitas sumber daya penetapan kebijakan. Ini diperlukan ketika nilai -IdentityType disediakan.

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

### -Metadata
Metadata untuk penetapan kebijakan baru. Ini bisa berupa jalur ke nama file yang berisi metadata, atau metadata sebagai string.

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

### -Nama
Menentukan nama untuk penetapan kebijakan.

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

### -NonComplianceMessage
Pesan tidak sesuai yang menjelaskan mengapa sumber daya tidak sesuai dengan kebijakan.

```yaml
Type: Microsoft.Azure.Commands.ResourceManager.Cmdlets.Implementation.Policy.PsNonComplianceMessage[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NotScope
Tidak ada lingkup untuk penetapan kebijakan.

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

### -PolicyDefinition
Menentukan kebijakan, sebagai objek **PsPolicyDefinition** yang berisi aturan kebijakan.

```yaml
Type: Microsoft.Azure.Commands.ResourceManager.Cmdlets.Implementation.Policy.PsPolicyDefinition
Parameter Sets: DefaultParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

```yaml
Type: Microsoft.Azure.Commands.ResourceManager.Cmdlets.Implementation.Policy.PsPolicyDefinition
Parameter Sets: PolicyParameterObjectParameterSet, PolicyParameterStringParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

```yaml
Type: Microsoft.Azure.Commands.ResourceManager.Cmdlets.Implementation.Policy.PsPolicyDefinition
Parameter Sets: PolicySetParameterObjectParameterSet, PolicySetParameterStringParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PolicyParameter
Jalur file parameter kebijakan atau string parameter kebijakan.

```yaml
Type: System.String
Parameter Sets: PolicyParameterStringParameterSet, PolicySetParameterStringParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PolicyParameterObject
Objek parameter kebijakan.

```yaml
Type: System.Collections.Hashtable
Parameter Sets: PolicyParameterObjectParameterSet, PolicySetParameterObjectParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PolicySetDefinition
Objek definisi kumpulan kebijakan.

```yaml
Type: Microsoft.Azure.Commands.ResourceManager.Cmdlets.Implementation.Policy.PsPolicySetDefinition
Parameter Sets: DefaultParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

```yaml
Type: Microsoft.Azure.Commands.ResourceManager.Cmdlets.Implementation.Policy.PsPolicySetDefinition
Parameter Sets: PolicyParameterObjectParameterSet, PolicyParameterStringParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

```yaml
Type: Microsoft.Azure.Commands.ResourceManager.Cmdlets.Implementation.Policy.PsPolicySetDefinition
Parameter Sets: PolicySetParameterObjectParameterSet, PolicySetParameterStringParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Pra
Menunjukkan bahwa cmdlet ini mempertimbangkan versi API prarilis ketika secara otomatis menentukan versi mana yang akan digunakan.

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

### -Lingkup
Menentukan lingkup untuk menetapkan kebijakan.
Misalnya, untuk menetapkan kebijakan ke grup sumber daya, tentukan hal berikut: `/subscriptions/`nama grup IDresource`/resourcegroups/` langganan

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### System.String[]

### Microsoft.Azure.Commands.ResourceManager.Cmdlets.Implementation.Policy.PsPolicyDefinition

### Microsoft.Azure.Commands.ResourceManager.Cmdlets.Implementation.Policy.PsPolicySetDefinition

### System.Nullable'1[[Microsoft.Azure.Commands.ResourceManager.Cmdlets.Entities.Policy.PolicyAssignmentEnforcementMode, Microsoft.Azure.PowerShell.Cmdlets.ResourceManager, Version=3.5.0.0, Culture=neutral, PublicKeyToken=null]]

### Microsoft.Azure.Commands.ResourceManager.Cmdlets.Implementation.Policy.PsNonComplianceMessage[]

## OUTPUTS

### Microsoft.Azure.Commands.ResourceManager.Cmdlets.Implementation.Policy.PsPolicyAssignment

## CATATAN

## RELATED LINKS

[Get-AzPolicyDefinition](./Get-AzPolicyDefinition.md)

[Get-AzPolicyAssignment](./Get-AzPolicyAssignment.md)

[Remove-AzPolicyAssignment](./Remove-AzPolicyAssignment.md)

[Set-AzPolicyAssignment](./Set-AzPolicyAssignment.md)


