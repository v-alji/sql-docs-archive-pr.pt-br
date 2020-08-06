---
title: Propriedade RSWindowsExtendedProtectionScenario (WMI MSReportServer_ConfigurationSetting) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 5ac7ab80-9adf-4f65-abfa-fedf53b082b5
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 84e14d056cc0352b0d1d85bc12c9c873a1b89ced
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87682073"
---
# <a name="rswindowsextendedprotectionscenario-property-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="ba422-102">Propriedade RSWindowsExtendedProtectionScenario (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="ba422-102">RSWindowsExtendedProtectionScenario Property (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="ba422-103">Retorna um valor de cadeia de caracteres que indica o cenário de proteção estendida que o servidor de relatório está configurado para permitir.</span><span class="sxs-lookup"><span data-stu-id="ba422-103">Returns a string value that indicates the extended protection scenario the report server is configured to allow.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba422-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="ba422-104">Syntax</span></span>  
  
```vb  
Public Dim RSWindowsExtendedProtectionScenario As String  
```  
  
```csharp  
public string RSWindowsExtendedProtectionScenario;  
```  
  
## <a name="remarks"></a><span data-ttu-id="ba422-105">Comentários</span><span class="sxs-lookup"><span data-stu-id="ba422-105">Remarks</span></span>  
 <span data-ttu-id="ba422-106">Retorna um valor de cadeia de caracteres que indica o cenário de proteção estendida que o servidor de relatório está configurado para permitir.</span><span class="sxs-lookup"><span data-stu-id="ba422-106">Returns a string value that indicates the extended protection scenario the report server is configured to allow.</span></span> <span data-ttu-id="ba422-107">Se o servidor de relatório ao qual o provedor WMI está conectado não der suporte à proteção estendida, "" (cadeia de caracteres vazia) será retornado.</span><span class="sxs-lookup"><span data-stu-id="ba422-107">If the report server that the WMI provider is connected to does not support extended protection, "" (empty string) is returned.</span></span>  
  
 <span data-ttu-id="ba422-108">A lista a seguir mostra os valores válidos:</span><span class="sxs-lookup"><span data-stu-id="ba422-108">The following list shows valid values:</span></span>  
  
 `"Any | Proxy | Direct"`  
  
## <a name="example-code"></a><span data-ttu-id="ba422-109">Código de exemplo</span><span class="sxs-lookup"><span data-stu-id="ba422-109">Example Code</span></span>  
 [<span data-ttu-id="ba422-110">Classe MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="ba422-110">MSReportServer_ConfigurationSetting Class</span></span>](msreportserver-configurationsetting-class.md)  
  
## <a name="see-also"></a><span data-ttu-id="ba422-111">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ba422-111">See Also</span></span>  
 <span data-ttu-id="ba422-112">[Propriedade RSWindowsExtendedProtectionLevel &#40;WMI MSReportServer_ConfigurationSetting&#41;](rswindowsextendedprotectionlevel-property.md) </span><span class="sxs-lookup"><span data-stu-id="ba422-112">[RSWindowsExtendedProtectionLevel Property &#40;WMI MSReportServer_ConfigurationSetting&#41;](rswindowsextendedprotectionlevel-property.md) </span></span>  
 <span data-ttu-id="ba422-113">[Método SetExtendedProtectionSettings &#40;WMI MSReportServer_ConfigurationSetting&#41;](configurationsetting-method-setextendedprotectionsettings.md) </span><span class="sxs-lookup"><span data-stu-id="ba422-113">[SetExtendedProtectionSettings Method &#40;WMI MSReportServer_ConfigurationSetting&#41;](configurationsetting-method-setextendedprotectionsettings.md) </span></span>  
 <span data-ttu-id="ba422-114">[Proteção Estendida para Autenticação com o Reporting Services](../security/extended-protection-for-authentication-with-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="ba422-114">[Extended Protection for Authentication with Reporting Services](../security/extended-protection-for-authentication-with-reporting-services.md) </span></span>  
 [<span data-ttu-id="ba422-115">Arquivo de configuração RSReportServer</span><span class="sxs-lookup"><span data-stu-id="ba422-115">RSReportServer Configuration File</span></span>](../report-server/rsreportserver-config-configuration-file.md)  
  
  
