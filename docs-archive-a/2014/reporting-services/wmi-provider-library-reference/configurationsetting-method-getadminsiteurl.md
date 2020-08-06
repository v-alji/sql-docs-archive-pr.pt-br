---
title: Método GetAdminSiteUrl (WMI) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- GetAdminSiteUrl method
ms.assetid: fbc5bf3c-120c-4aec-a4f2-f5391bd415f6
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: cae1a6f7e363ddce8c47c00eb5ef25fc832e59c3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572918"
---
# <a name="getadminsiteurl-method-wmi"></a><span data-ttu-id="108c7-102">Método GetAdminSiteUrl (WMI)</span><span class="sxs-lookup"><span data-stu-id="108c7-102">GetAdminSiteUrl Method (WMI)</span></span>
  <span data-ttu-id="108c7-103">Obtém a URL absoluta para o site da Administração Central do farm do Microsoft [!INCLUDE[winSPServ](../../includes/winspserv-md.md)], [!INCLUDE[offSPServ](../../includes/offspserv-md.md)], [!INCLUDE[SPF2010](../../includes/spf2010-md.md)]ou [!INCLUDE[SPS2010](../../includes/sps2010-md.md)] ao qual o servidor de relatório está integrado.</span><span class="sxs-lookup"><span data-stu-id="108c7-103">Gets the absolute URL for the Central Administration Web site for the Microsoft [!INCLUDE[winSPServ](../../includes/winspserv-md.md)], [!INCLUDE[offSPServ](../../includes/offspserv-md.md)], [!INCLUDE[SPF2010](../../includes/spf2010-md.md)], or [!INCLUDE[SPS2010](../../includes/sps2010-md.md)] farm that the report server is integrated with.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="108c7-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="108c7-104">Syntax</span></span>  
  
```vb  
Public Sub GetAdminSiteUrl(ByRef AdminSiteUrl as String, _  
ByRef HRESULT as Int32)  
```  
  
```csharp  
public void GetAdminSiteUrl(out string AdminSiteUrl, out Int32 HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="108c7-105">parâmetros</span><span class="sxs-lookup"><span data-stu-id="108c7-105">Parameters</span></span>  
 <span data-ttu-id="108c7-106">*AdminSiteUrl*</span><span class="sxs-lookup"><span data-stu-id="108c7-106">*AdminSiteUrl*</span></span>  
 <span data-ttu-id="108c7-107">[out] Uma cadeia de caracteres que contém a URL absoluta para o site da Administração Central do farm do SharePoint ao qual o servidor de relatório está integrado.</span><span class="sxs-lookup"><span data-stu-id="108c7-107">[out] A string that contains the absolute URL for the Central Administration Web site for the SharePoint farm that the report server is integrated with.</span></span>  
  
 <span data-ttu-id="108c7-108">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="108c7-108">*HRESULT*</span></span>  
 <span data-ttu-id="108c7-109">[out] Valor que indica se a chamada obteve êxito ou falhou.</span><span class="sxs-lookup"><span data-stu-id="108c7-109">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="108c7-110">Valor retornado</span><span class="sxs-lookup"><span data-stu-id="108c7-110">Return Value</span></span>  
 <span data-ttu-id="108c7-111">Retorna um *HRESULT* indicando êxito ou falha da chamada do método.</span><span class="sxs-lookup"><span data-stu-id="108c7-111">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="108c7-112">Um valor 0 indica que a chamada do método teve êxito.</span><span class="sxs-lookup"><span data-stu-id="108c7-112">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="108c7-113">Um valor diferente de zero indica que ocorreu um erro.</span><span class="sxs-lookup"><span data-stu-id="108c7-113">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="108c7-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="108c7-114">Requirements</span></span>  
 <span data-ttu-id="108c7-115">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="108c7-115">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="108c7-116">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="108c7-116">See Also</span></span>  
 [<span data-ttu-id="108c7-117">Métodos de MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="108c7-117">MSReportServer_ConfigurationSetting Methods</span></span>](msreportserver-configurationsetting-methods.md)  
  
  
