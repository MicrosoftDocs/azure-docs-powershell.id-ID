---
external help file: Microsoft.Azure.PowerShell.Cmdlets.ResourceManager.dll-Help.xml
Module Name: Az.Resources
ms.assetid: BA40BD11-8167-48D7-AC71-72B2FD9924F2
online version: https://docs.microsoft.com/powershell/module/az.resources/new-azpolicyassignment
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/New-AzPolicyAssignment.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/New-AzPolicyAssignment.md
ms.openlocfilehash: 550331ea4c08fbb44afc5779b73ed7e9cddee494
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140228293"
---
# New-AzPolicyAssignment

## SYNOPSIS
Membuat penetapan kebijakan.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan [lihat versi terbaru](/powershell/module/az.resources/new-azpolicyassignment) untuk informasi terkini.

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
Menentukan kebijakan dan lingkup.

## EXAMPLES

### Contoh 1: Penetapan kebijakan di tingkat langganan
```
PS C:\> $Subscription = Get-AzSubscription -SubscriptionName 'Subscription01'
PS C:\> $Policy = Get-AzPolicyDefinition -Name 'VirtualMachinePolicy'
PS C:\> New-AzPolicyAssignment -Name 'VirtualMachinePolicyAssignment' -PolicyDefinition $Policy -Scope "/subscriptions/$($Subscription.Id)"
```

Perintah pertama mendapatkan langganan bernama Subscription01 menggunakan cmdlet Get-AzSubscription dan menyimpannya di $Subscription variabel.
Perintah kedua mendapatkan definisi kebijakan bernama VirtualMachinePolicy menggunakan cmdlet Get-AzPolicyDefinition dan menyimpannya dalam $Policy variabel.
Perintah terakhir menetapkan kebijakan di $Policy di tingkat langganan yang diidentifikasi oleh string lingkup langganan.

### Contoh 2: Penetapan kebijakan di tingkat grup sumber daya
```
PS C:\> $ResourceGroup = Get-AzResourceGroup -Name 'ResourceGroup11'
PS C:\> $Policy = Get-AzPolicyDefinition -Name 'VirtualMachinePolicy'
PS C:\> New-AzPolicyAssignment -Name 'VirtualMachinePolicyAssignment' -PolicyDefinition $Policy -Scope $ResourceGroup.ResourceId
```

Perintah pertama mendapatkan grup sumber daya bernama ResourceGroup11 dengan menggunakan cmdlet Get-AzResourceGroup dan menyimpannya di $ResourceGroup sumber daya.
Perintah kedua mendapatkan definisi kebijakan bernama VirtualMachinePolicy menggunakan cmdlet Get-AzPolicyDefinition dan menyimpannya dalam $Policy variabel.
Perintah terakhir menetapkan kebijakan dalam $Policy tingkat grup sumber daya yang diidentifikasi oleh properti **ResourceId** dari $ResourceGroup.

### Contoh 3: Penetapan kebijakan di tingkat grup sumber daya dengan objek parameter kebijakan
```
PS C:\> $ResourceGroup = Get-AzResourceGroup -Name 'ResourceGroup11'
PS C:\> $Policy = Get-AzPolicyDefinition -BuiltIn | Where-Object {$_.Properties.DisplayName -eq 'Allowed locations'}
PS C:\> $Locations = Get-AzLocation | where displayname -like '*east*'
PS C:\> $AllowedLocations = @{'listOfAllowedLocations'=($Locations.location)}
PS C:\> New-AzPolicyAssignment -Name 'RestrictLocationPolicyAssignment' -PolicyDefinition $Policy -Scope $ResourceGroup.ResourceId -PolicyParameterObject $AllowedLocations
```

Perintah pertama mendapatkan grup sumber daya bernama ResourceGroup11 dengan menggunakan cmdlet Get-AzResourceGroup cmdlet.
Perintah menyimpan objek tersebut dalam $ResourceGroup variabel.
Perintah kedua mendapatkan definisi kebijakan bawaan untuk lokasi yang diperbolehkan menggunakan cmdlet Get-AzPolicyDefinition cmdlet.
Perintah menyimpan objek tersebut dalam $Policy variabel.
Perintah ketiga dan keempat membuat objek yang berisi semua kawasan Azure dengan "timur" dalam namanya.
Perintah menyimpan objek tersebut dalam $AllowedLocations variabel.
Perintah terakhir menetapkan kebijakan dalam $Policy tingkat grup sumber daya menggunakan objek parameter kebijakan dalam $AllowedLocations.
Properti **ResourceId** dari $ResourceGroup mengidentifikasi grup sumber daya.

### Contoh 4: Penetapan kebijakan di tingkat grup sumber daya dengan file parameter kebijakan
Buat file yang disebut _AllowedLocations.json_ di direktori kerja lokal dengan konten berikut.

```
{
    "listOfAllowedLocations":  {
      "value": [
        "westus",
        "westeurope",
        "japanwest"
      ]
    }
}
```

```
PS C:\> $ResourceGroup = Get-AzResourceGroup -Name 'ResourceGroup11'
PS C:\> $Policy = Get-AzPolicyDefinition -BuiltIn | Where-Object {$_.Properties.DisplayName -eq 'Allowed locations'}
PS C:\> New-AzPolicyAssignment -Name 'RestrictLocationPolicyAssignment' -PolicyDefinition $Policy -Scope $ResourceGroup.ResourceId -PolicyParameter .\AllowedLocations.json
```

Perintah pertama mendapatkan grup sumber daya bernama ResourceGroup11 dengan menggunakan cmdlet Get-AzResourceGroup dan menyimpannya di $ResourceGroup sumber daya.
Perintah kedua mendapatkan definisi kebijakan bawaan untuk lokasi yang diperbolehkan menggunakan cmdlet Get-AzPolicyDefinition dan menyimpannya dalam $Policy baru.
Perintah terakhir menetapkan kebijakan dalam $Policy di grup sumber daya yang diidentifikasi dengan properti **ResourceId** $ResourceGroup menggunakan file parameter kebijakan AllowedLocations.json dari direktori kerja lokal.

### Contoh 5: Penetapan kebijakan dengan sistem yang ditetapkan identitas terkelola
```
PS C:\> $ResourceGroup = Get-AzResourceGroup -Name 'ResourceGroup11'
PS C:\> $Policy = Get-AzPolicyDefinition -Name 'VirtualMachinePolicy'
PS C:\> New-AzPolicyAssignment -Name 'VirtualMachinePolicyAssignment' -PolicyDefinition $Policy -Scope $ResourceGroup.ResourceId -Location 'eastus' -IdentityType 'SystemAssigned'
```

Perintah pertama mendapatkan grup sumber daya bernama ResourceGroup11 dengan menggunakan cmdlet Get-AzResourceGroup dan menyimpannya di $ResourceGroup sumber daya.
Perintah kedua mendapatkan definisi kebijakan bernama VirtualMachinePolicy menggunakan cmdlet Get-AzPolicyDefinition dan menyimpannya dalam $Policy variabel.
Perintah terakhir menetapkan kebijakan dalam $Policy ke grup sumber daya. Identitas terkelola yang ditetapkan secara otomatis dibuat dan ditetapkan untuk penetapan kebijakan.

### Contoh 6: Penetapan kebijakan dengan pengguna identitas terkelola ditetapkan
```
PS C:\> $ResourceGroup = Get-AzResourceGroup -Name 'ResourceGroup11'
PS C:\> $Policy = Get-AzPolicyDefinition -Name 'VirtualMachinePolicy'
PS C:\> $UserAssignedIdentity = Get-AzUserAssignedIdentity -ResourceGroupName 'ResourceGroup1' -Name 'UserAssignedIdentity1'
PS C:\> New-AzPolicyAssignment -Name 'VirtualMachinePolicyAssignment' -PolicyDefinition $Policy -Scope $ResourceGroup.ResourceId -Location 'eastus' -IdentityType 'UserAssigned' -IdentityId $UserAssignedIdentity.Id
```

Perintah pertama mendapatkan grup sumber daya bernama ResourceGroup11 dengan menggunakan cmdlet Get-AzResourceGroup dan menyimpannya di $ResourceGroup sumber daya.
Perintah kedua mendapatkan definisi kebijakan bernama VirtualMachinePolicy menggunakan cmdlet Get-AzPolicyDefinition dan menyimpannya dalam $Policy variabel.
Perintah ketiga mendapatkan identitas terkelola yang ditetapkan pengguna bernama UserAssignedIdentity1 dengan menggunakan cmdlet Get-AzUserAssignedIdentity dan menyimpannya dalam variabel $UserAssignedIdentity baru.
Perintah terakhir menetapkan kebijakan dalam $Policy ke grup sumber daya. Pengguna yang ditetapkan identitas terkelola yang diidentifikasi oleh properti **Id** $UserAssignedIdentity ditetapkan ke penetapan kebijakan dengan memberikan **properti Id*** ke parameter IdentityId.

### Contoh 7: Penetapan kebijakan dengan properti mode penerapan
```
PS C:\> $Subscription = Get-AzSubscription -SubscriptionName 'Subscription01'
PS C:\> $Policy = Get-AzPolicyDefinition -Name 'VirtualMachinePolicy'
PS C:\> New-AzPolicyAssignment -Name 'VirtualMachinePolicyAssignment' -PolicyDefinition $Policy -Scope "/subscriptions/$($Subscription.Id)" -EnforcementMode DoNotEnforce
```

Perintah pertama mendapatkan langganan bernama Subscription01 menggunakan cmdlet Get-AzSubscription dan menyimpannya di $Subscription variabel.
Perintah kedua mendapatkan definisi kebijakan bernama VirtualMachinePolicy menggunakan cmdlet Get-AzPolicyDefinition dan menyimpannya dalam $Policy variabel.
Perintah terakhir menetapkan kebijakan di $Policy di tingkat langganan yang diidentifikasi oleh string lingkup langganan. Penetapan ditetapkan dengan nilai EnforcementMode dari _DoNotEnforce_ i.e. efek kebijakan tidak diberlakukan selama pembuatan atau pembaruan sumber daya.

### Contoh 8: Penetapan kebijakan dengan pesan tidak sesuai
```
PS C:\> $PolicySet = Get-AzPolicySetDefinition -Name 'VirtualMachinePolicySet'
PS C:\> $NonComplianceMessages = @(@{Message="Only DsV2 SKUs are allowed."; PolicyDefinitionReferenceId="DefRef1"}, @{Message="Virtual machines must follow cost management best practices."})
PS C:\> New-AzPolicyAssignment -Name 'VirtualMachinePolicyAssignment' -PolicySetDefinition $PolicySet -NonComplianceMessage $NonComplianceMessages
```

Perintah pertama mendapatkan definisi kumpulan kebijakan bernama VirtualMachinePolicySet menggunakan cmdlet Get-AzPolicySetDefinition dan menyimpannya dalam $PolicySet kolom.
Perintah kedua membuat array pesan tidak memenuhi persyaratan. Satu pesan tujuan umum untuk seluruh penetapan dan satu pesan khusus untuk kebijakan pembatasan SKU di dalam definisi kumpulan kebijakan yang ditetapkan.
Perintah terakhir menetapkan definisi kumpulan kebijakan $PolicySet langganan dengan dua pesan tidak memenuhi syarat yang akan diperlihatkan jika sumber daya ditolak oleh kebijakan.

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
Buat dan tetapkan identitas terkelola sistem untuk penetapan kebijakan ini. Identitas akan digunakan saat menjalankan penyebaran untuk kebijakan 'deployIfNotExists' dan 'modifikasi'. Lokasi diperlukan saat menetapkan identitas.

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
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure

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
Menentukan tipe identitas terkelola untuk ditetapkan ke penetapan kebijakan ini. Jika nilai 'SystemAssigned' disediakan, identitas terkelola yang ditetapkan untuk sistem akan dihasilkan dan ditetapkan untuk penetapan kebijakan ini. Jika nilai 'UserAssigned' disediakan, identitas yang ditetapkan pengguna yang diberikan melalui Id-nya ke parameter -IdentityId ditetapkan untuk penetapan kebijakan ini. Identitas akan digunakan saat menjalankan penyebaran untuk kebijakan 'deployIfNotExists' dan 'modifikasi'. Lokasi diperlukan saat menetapkan identitas. Izin harus diberikan pada identitas menggunakan identitas New-AzRoleAssignment setelah identitas yang ditetapkan sistem dibuat. Parameter IdentityType akan didahulukan jika kedua parameter AssignIdentity dan IdentityType digunakan.

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
Lokasi identitas sumber daya penetapan kebijakan. Hal ini diperlukan saat nilai -IdentityType disediakan.

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
Pesan non-kepatuhan yang menjelaskan mengapa sumber daya tidak patuh dengan kebijakan tersebut.

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
The not scopes for policy assignment.

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
Cmdlet ini mempertimbangkan versi API prari release ketika cmdlet menentukan versi mana yang akan digunakan secara otomatis.

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
Menentukan lingkup penetapan kebijakan.
Misalnya, untuk menetapkan kebijakan ke grup sumber daya, tentukan hal berikut ini: `/subscriptions/`nama grup IDresource`/resourcegroups/` langganan

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

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


