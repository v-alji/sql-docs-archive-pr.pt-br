---
title: Propriedade RSWindowsExtendedProtectionLevel (WMI MSReportServer_ConfigurationSetting) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 162ffe86-69c3-49d2-b9ed-49d097c05551
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 02ff3bad42ae25adf6cfa563944d89bac2c600e0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572897"
---
# <a name="rswindowsextendedprotectionlevel-property-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="1b1f7-102">Propriedade RSWindowsExtendedProtectionLevel (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="1b1f7-102">RSWindowsExtendedProtectionLevel Property (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="1b1f7-103">Retorna um valor de cadeia de caracteres que indica o nível de proteção para o qual o servidor de relatório está configurado para oferecer suporte.</span><span class="sxs-lookup"><span data-stu-id="1b1f7-103">Returns a string value that indicates the level of protection the report server is configured to support.</span></span> <span data-ttu-id="1b1f7-104">Essa propriedade é somente leitura.</span><span class="sxs-lookup"><span data-stu-id="1b1f7-104">This property is read-only.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b1f7-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="1b1f7-105">Syntax</span></span>  
  
```vb  
Public Dim RSWindowsExtendedProtectionLevel As String  
```  
  
```csharp  
public string RSWindowsExtendedProtectionLevel;  
```  
  
## <a name="remarks"></a><span data-ttu-id="1b1f7-106">Comentários</span><span class="sxs-lookup"><span data-stu-id="1b1f7-106">Remarks</span></span>  
 <span data-ttu-id="1b1f7-107">Retorna um valor de cadeia de caracteres que indica o nível de proteção para o qual o servidor de relatório está configurado para oferecer suporte.</span><span class="sxs-lookup"><span data-stu-id="1b1f7-107">Returns a string value that indicates the level of protection the report server is configured to support.</span></span> <span data-ttu-id="1b1f7-108">Se o servidor de relatório ao qual o provedor WMI está conectado não der suporte à proteção estendida, "" (cadeia de caracteres vazia) será retornado.</span><span class="sxs-lookup"><span data-stu-id="1b1f7-108">If the report server that the WMI provider is connected to does not support extended protection, "" (empty string) is returned.</span></span> <span data-ttu-id="1b1f7-109">A lista a seguir mostra os valores válidos:</span><span class="sxs-lookup"><span data-stu-id="1b1f7-109">The following list shows valid values:</span></span>  
  
 `"Off" | "Allow" | "Require"`  
  
## <a name="example-code"></a><span data-ttu-id="1b1f7-110">Código de exemplo</span><span class="sxs-lookup"><span data-stu-id="1b1f7-110">Example Code</span></span>  
 [<span data-ttu-id="1b1f7-111">Classe MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="1b1f7-111">MSReportServer_ConfigurationSetting Class</span></span>](msreportserver-configurationsetting-class.md)  
  
## <a name="see-also"></a><span data-ttu-id="1b1f7-112">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="1b1f7-112">See Also</span></span>  
 <span data-ttu-id="1b1f7-113">[Propriedade RSWindowsExtendedProtectionScenario &#40;WMI MSReportServer_ConfigurationSetting&#41;](rswindowsextendedprotectionscenario-property.md) </span><span class="sxs-lookup"><span data-stu-id="1b1f7-113">[RSWindowsExtendedProtectionScenario Property &#40;WMI MSReportServer_ConfigurationSetting&#41;](rswindowsextendedprotectionscenario-property.md) </span></span>  
 <span data-ttu-id="1b1f7-114">[Método SetExtendedProtectionSettings &#40;WMI MSReportServer_ConfigurationSetting&#41;](configurationsetting-method-setextendedprotectionsettings.md) </span><span class="sxs-lookup"><span data-stu-id="1b1f7-114">[SetExtendedProtectionSettings Method &#40;WMI MSReportServer_ConfigurationSetting&#41;](configurationsetting-method-setextendedprotectionsettings.md) </span></span>  
 <span data-ttu-id="1b1f7-115">[Proteção Estendida para Autenticação com o Reporting Services](../security/extended-protection-for-authentication-with-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="1b1f7-115">[Extended Protection for Authentication with Reporting Services](../security/extended-protection-for-authentication-with-reporting-services.md) </span></span>  
 [<span data-ttu-id="1b1f7-116">Arquivo de configuração RSReportServer</span><span class="sxs-lookup"><span data-stu-id="1b1f7-116">RSReportServer Configuration File</span></span>](../report-server/rsreportserver-config-configuration-file.md)  
  
  
