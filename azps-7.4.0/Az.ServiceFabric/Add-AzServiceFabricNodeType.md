---
external help file: Microsoft.Azure.PowerShell.Cmdlets.ServiceFabric.dll-Help.xml
Module Name: Az.ServiceFabric
online version: https://docs.microsoft.com/powershell/module/az.servicefabric/add-azservicefabricnodetype
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ServiceFabric/ServiceFabric/help/Add-AzServiceFabricNodeType.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ServiceFabric/ServiceFabric/help/Add-AzServiceFabricNodeType.md
ms.openlocfilehash: ef9827210952d88ea9c5ff83bf9fcbfb4176b0ee
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142429487"
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
$pwd = ConvertTo-SecureString -String 'Password$123456' -AsPlainText -Force
Add-AzServiceFabricNodeType -ResourceGroupName 'Group1' -Name 'Contoso01SFCluster' -NodeType 'n2' -Capacity 5 -VmUserName 'adminName' -VmPassword $pwd
```

Perintah ini akan menambahkan NodeType baru 'n2' dengan kapasitas 5, dan nama admin vm adalah 'adminName'.

### Contoh 2
Tipe simpul baru akan menjadi tipe simpul utama dan akan menyalin referensi gambar VM dari Tipe Node VMSS yang ditemukan sebelumnya pertama, mengganti ImageSku dengan 18.04-LTS.
- Referensi gambar tipe simpul yang sudah ada: ImagePublisher: Canonical, ImageOffer: UbuntuServer, ImageSku: 16.04-LTS, ImageVersion: latest
- Referensi gambar tipe simpul baru: ImagePublisher: Canonical, ImageOffer: UbuntuServer, ImageSku: 18.04-LTS, ImageVersion: latest


```powershell
$pwd = ConvertTo-SecureString -String 'Password$123456' -AsPlainText -Force
$resourceGroup = "Group2"
$clusterName = "Contoso01SFCluster"
$nodeTypeName = "n3"
Add-AzServiceFabricNodeType -ResourceGroupName $resourceGroup -Name $clusterName -NodeType $nodeTypeName -Capacity 5 -VmUserName 'adminName' -VmPassword $pwd -DurabilityLevel Silver -Verbose -VMImageSku 18.04-LTS -IsPrimaryNodeType $true
```

Perintah ini akan menambahkan NodeType baru 'n3' dengan kapasitas 5, nama admin vm adalah 'adminName', Tingkat ketahanan Silver (pekerjaan penyewa dan infrastruktur ditengahi dengan aman menggunakan Layanan Infrastruktur), dan VMSS dibuat menggunakan profil VM versi penerbit-penawaran-sku dengan sku berganti ke '18.04-LTS'.

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
Tentukan tingkat ketahanan NodeType.

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
Tentukan apakah tipe simpul adalah tipe simpul utama. Tipe simpul utama mungkin memiliki simpul benih dan layanan sistem.

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
Tentukan nama kluster

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
Nama tipe simpul

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

### -Tingkat
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
Tentukan Publisher referensi gambar VM.

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

### -VmImagesku
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

### -VmSku
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
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan.
Cmdlet tidak dijalankan.

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

### System.String

### System.Int32

### System.Security.SecureString

### Microsoft.Azure.Commands.ServiceFabric.Models.DurabilityLevel

### System.Nullable<System.Boolean>

## OUTPUTS

### Microsoft.Azure.Commands.ServiceFabric.Models.PSCluster

## CATATAN

## RELATED LINKS
