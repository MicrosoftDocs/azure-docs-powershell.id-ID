---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
online version: https://docs.microsoft.com/powershell/module/az.network/get-azp2svpngatewaydetailedconnectionhealth
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Get-AzP2sVpnGatewayDetailedConnectionHealth.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Get-AzP2sVpnGatewayDetailedConnectionHealth.md
ms.openlocfilehash: 3c2c9d78630812bf1250b88bbeb104827201caee
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141835264"
---
# Get-AzP2sVpnGatewayDetailedConnectionHealth

## SYNOPSIS
Mendapatkan informasi mendetail tentang titik saat ini ke koneksi situs dari P2SVpnGateway.

## SYNTAX

### ByP2SVpnGatewayName (Default)
```
Get-AzP2sVpnGatewayDetailedConnectionHealth [-Name <String>] -ResourceGroupName <String>
 -OutputBlobSasUrl <String> [-VpnUserNamesFilter <String[]>] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### ByP2SVpnGatewayObject
```
Get-AzP2sVpnGatewayDetailedConnectionHealth -InputObject <PSP2SVpnGateway> -OutputBlobSasUrl <String>
 [-VpnUserNamesFilter <String[]>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ByP2SVpnGatewayResourceId
```
Get-AzP2sVpnGatewayDetailedConnectionHealth -ResourceId <String> -OutputBlobSasUrl <String>
 [-VpnUserNamesFilter <String[]>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzP2sVpnGatewayDetailedConnectionHealth** memungkinkan Anda mendapatkan informasi mendetail tentang titik saat ini ke koneksi situs dari P2SVpnGateway. Pelanggan perlu mengirimkan URL SAS di mana kami dapat menempatkan informasi kesehatan mendetail ini.

Harap diperhatikan bahwa URL SAS yang disediakan harus berupa satu untuk **blob** (file) yang telah dibuat di akun penyimpanan dan **bukan** kontainer. Silakan gunakan perintah **New-AzStorageBlobSASToken** Powershell dan bukan **New-AzStorageContainerSASToken**. Anda juga perlu mengizinkan izin membaca dan menulis di SaSURl Anda. 

## EXAMPLES

### Contoh 1
```powershell
$blobSasUrl = New-AzStorageBlobSASToken -Container contp2stesting -Blob emptyfile.txt -Context $context -Permission "rwd" -StartTime $now.AddHours(-1) -ExpiryTime $now.AddDays(1) -FullUri
$blobSasUrl
SignedSasUrl
Get-AzP2sVpnGatewayDetailedConnectionHealth -Name 683482ade8564515aed4b8448c9757ea-westus-gw -ResourceGroupName P2SCortexGATesting -OutputBlobSasUrl $blobSasUrl
SasUrl : SignedSasUrl
```

Cmdlet **Get-AzP2sVpnGatewayDetailedConnectionHealth** memungkinkan Anda mendapatkan informasi mendetail tentang titik saat ini ke koneksi situs dari P2SVpnGateway. Pelanggan dapat mengunduh detail kesehatan dari unduhan url SAS yang lolos. Ini akan memperlihatkan informasi setiap poin ke koneksi situs dengan nama pengguna, byte di, byte keluar, alamat ip yang dialokasikan dll.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Objek gateway vpn p2s yang akan diubah

```yaml
Type: PSP2SVpnGateway
Parameter Sets: ByP2SVpnGatewayObject
Aliases: P2SVpnGateway

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Nama
Nama sumber daya.

```yaml
Type: String
Parameter Sets: ByP2SVpnGatewayName
Aliases: ResourceName

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OutputBlobSasUrl
Url OutputBlob Sas tempat kesehatan koneksi vpn p2s akan ditulis.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya.

```yaml
Type: String
Parameter Sets: ByP2SVpnGatewayName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceId
ID sumber daya Azure dari P2SVpnGateway untuk diubah.

```yaml
Type: String
Parameter Sets: ByP2SVpnGatewayResourceId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VpnUserNamesFilter
Daftar nama pengguna vpn P2S untuk difilter.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String
Microsoft.Azure.Commands.Network.Models.PSP2SVpnGateway

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSP2SVpnConnectionHealth

## CATATAN

## RELATED LINKS
