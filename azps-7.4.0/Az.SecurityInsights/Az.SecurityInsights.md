---
Module Name: Az.SecurityInsights
Module Guid: 453d4fb9-65ec-4cf1-8358-6a0fbd995d19
Download Help Link: https://docs.microsoft.com/powershell/module/az.securityinsights
Help Version: 1.1.0
Locale: en-US
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/SecurityInsights/SecurityInsights/help/Az.SecurityInsights.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/SecurityInsights/SecurityInsights/help/Az.SecurityInsights.md
ms.openlocfilehash: 136c6911a8fb713e2de09562fe70ad75721ca19c
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142174737"
---
# Modul Az.SecurityInsights
## Deskripsi
Microsoft Azure Sentinel adalah solusi manajemen kejadian informasi keamanan (SIEM, Automated Response) yang dapat diskalakan, cloud-native, dan security orchestration automated response (SOAR). Azure Sentinel memberikan analitik keamanan cerdas dan kecerdasan ancaman di seluruh perusahaan, menyediakan solusi tunggal untuk deteksi peringatan, visibilitas ancaman, perburuan proaktif, dan respons ancaman.<br/> Modul Azure Sentinel PowerShell (Az.SecurityInsights) memungkinkan Anda berinteraksi dengan komponen berikut: * Insiden * Aturan Analitik (Aturan Peringatan)
* Templat Aturan Analitik
* Tindakan Aturan Analitik (seperti melampirkan Azure Logic Apps Playbook ke aturan Anda)
* Bookmark
* Konektor Data
* Komentar

Semua cmdlet dapat bekerja dengan objek koneksi untuk menyediakan resourceGroupName dan workspaceName seperti dalam contoh berikut:

## Cmdlet Az.SecurityInsights
### [Get-AzSentinelAlertRule](Get-AzSentinelAlertRule.md)
Mendapatkan aturan analitik tertentu atau semua (Aturan Peringatan).

### [Get-AzSentinelAlertRuleAction](Get-AzSentinelAlertRuleAction.md)
Mendapatkan Respons Otomatis (Tindakan Aturan Peringatan) untuk Aturan Analitik, seperti Playbook Azure Logic Apps.<br/>
Aturan Otomatisasi Azure Sentinel akan didukung di masa mendatang.

*Catatan: Ini memerlukan nilai parameter "AlertRuleId"*

### [Get-AzSentinelAlertRuleTemplate](Get-AzSentinelAlertRuleTemplate.md)
Mendapatkan Templat Aturan Analitik.

### [Get-AzSentinelBookmark](Get-AzSentinelBookmark.md)
Mendapatkan Bookmark. <br/>
Bookmark digunakan untuk mempertahankan kueri, komentar, dan tag untuk insiden tertentu.<br/>
Anda membuat Bookmark terlebih dahulu lalu menambahkannya ke insiden.

### [Get-AzSentinelDataConnector](Get-AzSentinelDataConnector.md)
Mendapatkan Konektor Data. <br/><br/>
Harap diperhatikan bahwa dukungan otomatisasi hanya tersedia untuk konektor data berikut:
* AADDataConnector
* AATPDataConnector
* ASCDataConnector
* AwsCloudTrailDataConnector
* MCASDataConnector
* MDATPDataConnector
* OfficeDataConnector
* TIDataConnector

### [Get-AzSentinelIncident](Get-AzSentinelIncident.md)
Dapatkan satu atau beberapa Insiden Azure Sentinel.

### [Get-AzSentinelIncidentComment](Get-AzSentinelIncidentComment.md)
Mendapatkan Komentar Insiden.

### [New-AzSentinelAlertRule](New-AzSentinelAlertRule.md)
Membuat Aturan Analitik (Aturan Peringatan).

### [New-AzSentinelAlertRuleAction](New-AzSentinelAlertRuleAction.md)
Menambahkan Respons Otomatis ke Aturan Analitik.

### [AzSentinelBookmark Baru](New-AzSentinelBookmark.md)
Membuat Bookmark untuk insiden tertentu.<br/>

### [New-AzSentinelDataConnector](New-AzSentinelDataConnector.md)
Membuat Konektor Data.

### [New-AzSentinelIncident](New-AzSentinelIncident.md)
Membuat Insiden.

### [New-AzSentinelIncidentComment](New-AzSentinelIncidentComment.md)
Menambahkan Komentar ke Insiden.

### [New-AzSentinelIncidentOwner](New-AzSentinelIncidentOwner.md)
Buat objek Pemilik Insiden untuk memperbarui pemilik insiden.

### [Hapus-AzSentinelAlertRule](Remove-AzSentinelAlertRule.md)
Menghapus Aturan Analitik (AlertRule)

### [Remove-AzSentinelAlertRuleAction](Remove-AzSentinelAlertRuleAction.md)
Menghapus Respons Otomatis dari Aturan Analitik.

### [Hapus-AzSentinelBookmark](Remove-AzSentinelBookmark.md)
Menghapus Bookmark.

### [Remove-AzSentinelDataConnector](Remove-AzSentinelDataConnector.md)
Menghapus Konektor Data.

### [Hapus-AzSentinelIncident](Remove-AzSentinelIncident.md)
Menghapus Insiden.

### [Update-AzSentinelAlertRule](Update-AzSentinelAlertRule.md)
Memperbarui Aturan Analitik (Aturan Peringatan).

### [Update-AzSentinelAlertRuleAction](Update-AzSentinelAlertRuleAction.md)
Memperbarui Respons Otomatis (Tindakan Aturan Peringatan).

### [Update-AzSentinelBookmark](Update-AzSentinelBookmark.md)
Memperbarui Bookmark.

### [Update-AzSentinelDataConnector](Update-AzSentinelDataConnector.md)
Memperbarui Konektor Data.

### [Update-AzSentinelIncident](Update-AzSentinelIncident.md)
Memperbarui Insiden

