---
title: Propriedade IsSharePointIntegrated (WMI MSReportServer_Instance) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- IsSharePointIntegrated property
ms.assetid: e21d00ad-5d9a-4290-8d74-7eeeda39e1ed
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d0c92ebe586d37053b47f90ca98c31b3068a7b91
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572898"
---
# <a name="issharepointintegrated-property-wmi-msreportserver_instance"></a><span data-ttu-id="d57a6-102">Propriedade IsSharePointIntegrated (WMI MSReportServer_Instance)</span><span class="sxs-lookup"><span data-stu-id="d57a6-102">IsSharePointIntegrated Property (WMI MSReportServer_Instance)</span></span>
  <span data-ttu-id="d57a6-103">Especifica se o servidor de relatório está no modo integrado do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="d57a6-103">Specifies whether the report server is in SharePoint integrated mode.</span></span> <span data-ttu-id="d57a6-104">A partir do [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], essa propriedade sempre retorna `False` porque, em modo do SharePoint, as instâncias do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] são serviços compartilhados do SharePoint e não são controladas por provedores WMI.</span><span class="sxs-lookup"><span data-stu-id="d57a6-104">Beginning in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], this property always returns `False` because in SharePoint mode, [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] instances are SharePoint shared services and are not controlled by WMI providers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d57a6-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="d57a6-105">Syntax</span></span>  
  
```vb  
Public Dim IsSharePointIntegrated As Boolean  
```  
  
```csharp  
public Boolean IsSharePointIntegrated;  
```  
  
## <a name="property-values"></a><span data-ttu-id="d57a6-106">Valores da propriedade</span><span class="sxs-lookup"><span data-stu-id="d57a6-106">Property Values</span></span>  
 <span data-ttu-id="d57a6-107">Um objeto `Boolean` que indica se o servidor de relatório está no modo integrado do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="d57a6-107">A `Boolean` value that indicates whether the report server is in SharePoint integrated mode.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d57a6-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d57a6-108">Requirements</span></span>  
 <span data-ttu-id="d57a6-109">**Namespace:** [!INCLUDE[ssRSWMInmspc](../../includes/ssrswminmspc-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d57a6-109">**Namespace:** [!INCLUDE[ssRSWMInmspc](../../includes/ssrswminmspc-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d57a6-110">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d57a6-110">See Also</span></span>  
 <span data-ttu-id="d57a6-111">[Membros MSReportServer_Instance](msreportserver-instance-members.md) </span><span class="sxs-lookup"><span data-stu-id="d57a6-111">[MSReportServer_Instance Members](msreportserver-instance-members.md) </span></span>  
 [<span data-ttu-id="d57a6-112">Classe MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="d57a6-112">MSReportServer_ConfigurationSetting Class</span></span>](msreportserver-configurationsetting-class.md)  
  
  
