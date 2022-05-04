---
external help file: Microsoft.Azure.PowerShell.Cmdlets.ResourceManager.dll-Help.xml
Module Name: Az.Resources
ms.assetid: BA40BD11-8167-48D7-AC71-72B2FD9924F2
online version: https://docs.microsoft.com/powershell/module/az.resources/new-azpolicyassignment
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/New-AzPolicyAssignment.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/New-AzPolicyAssignment.md
ms.openlocfilehash: 93417e7b6b5e94afeea55ac31a591ce927410c6f
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144703632"
---
# New-AzPolicyAssignment

## SYNOPSIS
Membuat penetapan kebijakan.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.resources/new-azpolicyassignment) untuk informasi terbaru.

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
Tentukan kebijakan dan cakupan.

## EXAMPLES

### Contoh 1: Penetapan kebijakan di tingkat langganan
```powershell
$Subscription = Get-AzSubscription -SubscriptionName 'Subscription01'
$Policy = Get-AzPolicyDefinition -Name 'VirtualMachinePolicy'
New-AzPolicyAssignment -Name 'VirtualMachinePolicyAssignment' -PolicyDefinition $Policy -Scope "/subscriptions/$($Subscription.Id)"
```

Perintah pertama mendapatkan langganan bernama Subscription01 dengan menggunakan cmdlet Get-AzSubscription dan menyimpannya dalam variabel $Subscription.
Perintah kedua mendapatkan definisi kebijakan bernama VirtualMachinePolicy dengan menggunakan cmdlet Get-AzPolicyDefinition dan menyimpannya dalam variabel $Policy.
Perintah akhir menetapkan kebijakan dalam $Policy pada tingkat langganan yang diidentifikasi oleh string cakupan langganan.

### Contoh 2: Penetapan kebijakan di tingkat grup sumber daya
```powershell
$ResourceGroup = Get-AzResourceGroup -Name 'ResourceGroup11'
$Policy = Get-AzPolicyDefinition -Name 'VirtualMachinePolicy'
New-AzPolicyAssignment -Name 'VirtualMachinePolicyAssignment' -PolicyDefinition $Policy -Scope $ResourceGroup.ResourceId
```

Perintah pertama mendapatkan grup sumber daya bernama ResourceGroup11 dengan menggunakan cmdlet Get-AzResourceGroup dan menyimpannya dalam variabel $ResourceGroup.
Perintah kedua mendapatkan definisi kebijakan bernama VirtualMachinePolicy dengan menggunakan cmdlet Get-AzPolicyDefinition dan menyimpannya dalam variabel $Policy.
Perintah akhir menetapkan kebijakan dalam $Policy pada tingkat grup sumber daya yang diidentifikasi oleh properti **ResourceId** $ResourceGroup.

### Contoh 3: Penetapan kebijakan di tingkat grup sumber daya dengan objek parameter kebijakan
```powershell
$ResourceGroup = Get-AzResourceGroup -Name 'ResourceGroup11'
$Policy = Get-AzPolicyDefinition -BuiltIn | Where-Object {$_.Properties.DisplayName -eq 'Allowed locations'}
$Locations = Get-AzLocation | where displayname -like '*east*'
$AllowedLocations = @{'listOfAllowedLocations'=($Locations.location)}
New-AzPolicyAssignment -Name 'RestrictLocationPolicyAssignment' -PolicyDefinition $Policy -Scope $ResourceGroup.ResourceId -PolicyParameterObject $AllowedLocations
```

Perintah pertama mendapatkan grup sumber daya bernama ResourceGroup11 dengan menggunakan cmdlet Get-AzResourceGroup.
Perintah menyimpan objek tersebut dalam variabel $ResourceGroup.
Perintah kedua mendapatkan definisi kebijakan bawaan untuk lokasi yang diizinkan dengan menggunakan cmdlet Get-AzPolicyDefinition.
Perintah menyimpan objek tersebut dalam variabel $Policy.
Perintah ketiga dan keempat membuat objek yang berisi semua wilayah Azure dengan nama "timur".
Perintah menyimpan objek tersebut dalam variabel $AllowedLocations.
Perintah akhir menetapkan kebijakan dalam $Policy pada tingkat grup sumber daya menggunakan objek parameter kebijakan di $AllowedLocations.
Properti **ResourceId** dari $ResourceGroup mengidentifikasi grup sumber daya.

### Contoh 4: Penetapan kebijakan di tingkat grup sumber daya dengan file parameter kebijakan
Buat file bernama _AllowedLocations.json_ di direktori kerja lokal dengan konten berikut.


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
Perintah kedua mendapatkan definisi kebijakan bawaan untuk lokasi yang diizinkan dengan menggunakan cmdlet Get-AzPolicyDefinition dan menyimpannya dalam variabel $Policy.
Perintah akhir menetapkan kebijakan dalam $Policy di grup sumber daya yang diidentifikasi oleh properti **ResourceId** $ResourceGroup menggunakan file parameter kebijakan AllowedLocations.json dari direktori kerja lokal.

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
Perintah akhir menetapkan kebijakan dalam $Policy ke grup sumber daya. Identitas terkelola yang ditetapkan pengguna yang diidentifikasi oleh properti **Id** $UserAssignedIdentity ditetapkan ke penetapan kebijakan dengan meneruskan properti **Id*** ke parameter IdentityId.

### Contoh 7: Penetapan kebijakan dengan properti mode penegakan
```powershell
$Subscription = Get-AzSubscription -SubscriptionName 'Subscription01'
$Policy = Get-AzPolicyDefinition -Name 'VirtualMachinePolicy'
New-AzPolicyAssignment -Name 'VirtualMachinePolicyAssignment' -PolicyDefinition $Policy -Scope "/subscriptions/$($Subscription.Id)" -EnforcementMode DoNotEnforce
```

Perintah pertama mendapatkan langganan bernama Subscription01 dengan menggunakan cmdlet Get-AzSubscription dan menyimpannya dalam variabel $Subscription.
Perintah kedua mendapatkan definisi kebijakan bernama VirtualMachinePolicy dengan menggunakan cmdlet Get-AzPolicyDefinition dan menyimpannya dalam variabel $Policy.
Perintah akhir menetapkan kebijakan dalam $Policy pada tingkat langganan yang diidentifikasi oleh string cakupan langganan. Penugasan diatur dengan nilai EnforcementMode _doNotEnforce_ yaitu efek kebijakan tidak diberlakukan selama pembuatan atau pembaruan sumber daya.

### Contoh 8: Penetapan kebijakan dengan pesan ketidakpatuhan
```powershell
$PolicySet = Get-AzPolicySetDefinition -Name 'VirtualMachinePolicySet'
$NonComplianceMessages = @(@{Message="Only DsV2 SKUs are allowed."; PolicyDefinitionReferenceId="DefRef1"}, @{Message="Virtual machines must follow cost management best practices."})
New-AzPolicyAssignment -Name 'VirtualMachinePolicyAssignment' -PolicySetDefinition $PolicySet -NonComplianceMessage $NonComplianceMessages
```

Perintah pertama mendapatkan definisi kumpulan kebijakan bernama VirtualMachinePolicySet dengan menggunakan cmdlet Get-AzPolicySetDefinition dan menyimpannya dalam variabel $PolicySet.
Perintah kedua membuat array pesan ketidakpatuhan. Satu pesan tujuan umum untuk seluruh penugasan dan satu pesan khusus untuk kebijakan pembatasan SKU dalam definisi kumpulan kebijakan yang ditetapkan.
Perintah akhir menetapkan definisi kumpulan kebijakan dalam $PolicySet ke langganan dengan dua pesan ketidakpatuhan yang akan ditampilkan jika sumber daya ditolak oleh kebijakan.

## PARAMETERS

### -ApiVersion
Menentukan versi API penyedia sumber daya yang akan digunakan.
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
Buat dan tetapkan identitas terkelola yang ditetapkan sistem untuk penetapan kebijakan ini. Identitas akan digunakan saat menjalankan penyebaran untuk kebijakan 'deployIfNotExists' dan 'modifikasi'. Lokasi diperlukan saat menetapkan identitas.

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
Menentukan Id identitas terkelola yang ditetapkan pengguna untuk ditetapkan ke penetapan kebijakan ini. Nilai ini diperlukan jika nilai 'UserAssigned' diteruskan ke parameter -IdentityType. 

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
Menentukan jenis identitas terkelola yang akan ditetapkan ke penetapan kebijakan ini. Jika nilai 'SystemAssigned' disediakan, identitas terkelola yang ditetapkan sistem dihasilkan dan ditetapkan ke penetapan kebijakan ini. Jika nilai 'UserAssigned' disediakan, identitas yang ditetapkan pengguna diteruskan melalui Id-nya ke parameter -IdentityId ditetapkan ke penetapan kebijakan ini. Identitas akan digunakan saat menjalankan penyebaran untuk kebijakan 'deployIfNotExists' dan 'modifikasi'. Lokasi diperlukan saat menetapkan identitas. Izin harus diberikan kepada identitas menggunakan New-AzRoleAssignment setelah identitas yang ditetapkan sistem dibuat. Parameter IdentityType akan diberikan prioritas jika parameter AssignIdentity dan IdentityType digunakan.

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

### -Name
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
Pesan ketidakpatuh yang menjelaskan mengapa sumber daya tidak mematuhi kebijakan.

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
Tidak ada cakupan untuk penetapan kebijakan.

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
Kebijakan menetapkan objek definisi.

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

### -Pre
Menunjukkan bahwa cmdlet ini mempertimbangkan versi API pra-rilis ketika secara otomatis menentukan versi mana yang akan digunakan.

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

### -Cakupan
Menentukan cakupan untuk menetapkan kebijakan.
Misalnya, untuk menetapkan kebijakan ke grup sumber daya, tentukan yang berikut ini: `/subscriptions/`nama grup IDresource`/resourcegroups/` langganan

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### System.String

### System.String[]

### Microsoft.Azure.Commands.ResourceManager.Cmdlets.Implementation.Policy.PsPolicyDefinition

### Microsoft.Azure.Commands.ResourceManager.Cmdlets.Implementation.Policy.PsPolicySetDefinition

### System.Nullable'1[[Microsoft.Azure.Commands.ResourceManager.Cmdlets.Entities.Policy.PolicyAssignmentEnforcementMode, Microsoft.Azure.PowerShell.Cmdlets.ResourceManager, Version=3.5.0.0, Culture=neutral, PublicKeyToken=null]]

### Microsoft.Azure.Commands.ResourceManager.Cmdlets.Implementation.Policy.PsNonComplianceMessage[]

## OUTPUTS

### Microsoft.Azure.Commands.ResourceManager.Cmdlets.Implementation.Policy.PsPolicyAssignment

## NOTES

## RELATED LINKS

[Get-AzPolicyDefinition](./Get-AzPolicyDefinition.md)

[Get-AzPolicyAssignment](./Get-AzPolicyAssignment.md)

[Remove-AzPolicyAssignment](./Remove-AzPolicyAssignment.md)

[Set-AzPolicyAssignment](./Set-AzPolicyAssignment.md)


