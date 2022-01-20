---
external help file: Microsoft.Azure.PowerShell.Cmdlets.ServiceFabric.dll-Help.xml
Module Name: Az.ServiceFabric
online version: https://docs.microsoft.com/powershell/module/az.servicefabric/add-azservicefabricnodetype
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ServiceFabric/ServiceFabric/help/Add-AzServiceFabricNodeType.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ServiceFabric/ServiceFabric/help/Add-AzServiceFabricNodeType.md
ms.openlocfilehash: 5568ef8b44ee82256b03a1fd0dc4cdcbf2ded9d3
ms.sourcegitcommit: 53ef403038f665f1b3a9f616185b31f5de9bd7bb
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/03/2021
ms.locfileid: "136374511"
---
# Add-AzServiceFabricNodeType

## SYNOPSIS
Tambahkan tipe node baru ke kluster yang sudah ada.

## SYNTAX

```
Add-AzServiceFabricNodeType [-ResourceGroupName] <String> [-Name] <String> -Capacity <Int32>
 -VmUserName <String> -VmPassword <SecureString> [-VmSku <String>] [-Tier <String>]
 [-DurabilityLevel <DurabilityLevel>] [-IsPrimaryNodeType <Boolean>] [-VMImagePublisher <String>]
 [-VMImageOffer <String>] [-VMImageSku <String>] [-VMImageVersion <String>] -NodeType <String>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Tambahkan tipe node baru ke kluster yang sudah ada.

## EXAMPLES

### Contoh 1
```powershell
PS c:\> $pwd = ConvertTo-SecureString -String 'Password$123456' -AsPlainText -Force
PS C:\> Add-AzServiceFabricNodeType -ResourceGroupName 'Group1' -Name 'Contoso01SFCluster' -NodeType 'n2' -Capacity 5 -VmUserName 'adminName' -VmPassword $pwd
```

Perintah ini akan menambahkan NodeType 'n2' baru dengan kapasitas 5, dan nama admin vm adalah 'adminName'.

### Contoh 2
Tipe node baru akan menjadi tipe node utama dan akan menyalin referensi gambar VM dari Tipe Node VM yang pertama ditemukan, VMSS mengganti ImageSku dengan 18.04-LTS.
- Referensi gambar tipe node yang sudah ada: ImagePublisher: Kanonis, ImageOffer: UbuntuServer, ImageSku: 16.04-LTS, ImageVersion: terbaru
- Referensi gambar tipe node baru: ImagePublisher: Kanonis, ImageOffer: UbuntuServer, ImageSku: 18.04-LTS, ImageVersion: terbaru


```powershell
PS c:\> $pwd = ConvertTo-SecureString -String 'Password$123456' -AsPlainText -Force
PS c:\> $resourceGroup = "Group2"
PS c:\> $clusterName = "Contoso01SFCluster"
PS c:\> $nodeTypeName = "n3"
PS C:\> Add-AzServiceFabricNodeType -ResourceGroupName $resourceGroup -Name $clusterName -NodeType $nodeTypeName -Capacity 5 -VmUserName 'adminName' -VmPassword $pwd -DurabilityLevel Silver -Verbose -VMImageSku 18.04-LTS -IsPrimaryNodeType $true
```

Perintah ini akan menambahkan NodeType baru 'n3' dengan kapasitas 5, nama admin vm adalah 'adminName', Durability level Silver (pekerjaan penyewa dan infrastruktur yang aman diolah menggunakan Layanan Infrastruktur), dan VMSS dibuat menggunakan VM image profile publisher-offer-sku-version dengan sku yang bergantian menjadi '18.04-LTS'.

## PARAMETERS

### -Kapasitas
Kapasitas

```yaml
Type: System.Int32
Parameter Sets: (All)
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

### -DurabilityLevel
Tentukan tingkat durability dari NodeType.

```yaml
Type: Microsoft.Azure.Commands.ServiceFabric.Models.DurabilityLevel
Parameter Sets: (All)
Aliases:
Accepted values: Bronze, Silver, Gold

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -IsPrimaryNodeType
Tentukan apakah tipe node adalah tipe node utama. Tipe node utama mungkin memiliki node awal dan layanan sistem.

```yaml
Type: System.Nullable`1[System.Boolean]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Nama
Menentukan nama kluster

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: ClusterName

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NodeType
Nama tipe node

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ResourceGroupName
Tentukan nama grup sumber daya.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Tier
Vm Sku Tier

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMImageOffer
Tentukan Penawaran referensi gambar VM.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMImagePublisher
Tentukan referensi gambar VM Publisher.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMImageSku
Tentukan Sku referensi gambar VM.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMImageVersion
Tentukan Versi referensi gambar VM.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VmPassword
Kata sandi untuk masuk ke Vm

```yaml
Type: System.Security.SecureString
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Vmsku
Nama sku

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VmUserName
Nama pengguna untuk pembuatan log ke Vm

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Konfirmasi
Meminta konfirmasi Anda sebelum menjalankan cmdlet.

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
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan.
Cmdlet tidak berjalan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### System.Int32

### System.Security.SecureString

### Microsoft.Azure.Commands.ServiceFabric.Models.DurabilityLevel

### System.Nullable<System.Boolean>

## OUTPUTS

### Microsoft.Azure.Commands.ServiceFabric.Models.PSCluster

## CATATAN

## RELATED LINKS
