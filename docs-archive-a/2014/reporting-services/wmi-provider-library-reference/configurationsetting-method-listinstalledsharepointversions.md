---
title: Método ListInstalledSharePointVersions (WMI) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- ListInstalledSharePointVersions method
ms.assetid: 8f0a5e9f-23f1-41e5-9a90-dfec19ef1df7
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f0ceee23876461cf31cbd265ea39ae015ddcbc49
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572916"
---
# <a name="listinstalledsharepointversions-method-wmi"></a><span data-ttu-id="4540a-102">Método ListInstalledSharePointVersions (WMI)</span><span class="sxs-lookup"><span data-stu-id="4540a-102">ListInstalledSharePointVersions Method (WMI)</span></span>
  <span data-ttu-id="4540a-103">Retorna um conjunto de tokens que representam as versões do Microsoft [!INCLUDE[winSPServ](../../includes/winspserv-md.md)][!INCLUDE[offSPServ](../../includes/offspserv-md.md)], [!INCLUDE[SPF2010](../../includes/spf2010-md.md)]ou [!INCLUDE[SPS2010](../../includes/sps2010-md.md)] que estão instaladas no mesmo computador que o servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="4540a-103">Returns a set of tokens that represent the versions of Microsoft [!INCLUDE[winSPServ](../../includes/winspserv-md.md)], [!INCLUDE[offSPServ](../../includes/offspserv-md.md)], [!INCLUDE[SPF2010](../../includes/spf2010-md.md)], or [!INCLUDE[SPS2010](../../includes/sps2010-md.md)] that are installed on the same computer as the report server.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4540a-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="4540a-104">Syntax</span></span>  
  
```vb  
Public Sub ListInstalledSharePointVersions(ByRef VersionTokens() _  
    As String, ByRef Length As Int32, ByRef HRESULT As Int32)  
```  
  
```csharp  
public void ListReportServersInDatabase (out string[] VersionTokens,   
    out Int32 Length, out Int32 HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4540a-105">parâmetros</span><span class="sxs-lookup"><span data-stu-id="4540a-105">Parameters</span></span>  
 <span data-ttu-id="4540a-106">*VersionTokens[]*</span><span class="sxs-lookup"><span data-stu-id="4540a-106">*VersionTokens[]*</span></span>  
 <span data-ttu-id="4540a-107">[fora] Uma matriz que contém os tokens que representam a versão de um produto do SharePoint ou tecnologia que é compatível com o servidor de relatório instalado.</span><span class="sxs-lookup"><span data-stu-id="4540a-107">[out] An array that contains the tokens that represent the version of a SharePoint product or technology that is compatible with the installed report server.</span></span>  
  
 <span data-ttu-id="4540a-108">*Comprimento*</span><span class="sxs-lookup"><span data-stu-id="4540a-108">*Length*</span></span>  
 <span data-ttu-id="4540a-109">[fora] O tamanho da matriz de tokens da versão.</span><span class="sxs-lookup"><span data-stu-id="4540a-109">[out] The length of the version tokens array.</span></span>  
  
 <span data-ttu-id="4540a-110">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="4540a-110">*HRESULT*</span></span>  
 <span data-ttu-id="4540a-111">[out] Valor que indica se a chamada obteve êxito ou falhou.</span><span class="sxs-lookup"><span data-stu-id="4540a-111">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4540a-112">Valor retornado</span><span class="sxs-lookup"><span data-stu-id="4540a-112">Return Value</span></span>  
 <span data-ttu-id="4540a-113">Retorna um *HRESULT* indicando êxito ou falha da chamada do método.</span><span class="sxs-lookup"><span data-stu-id="4540a-113">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="4540a-114">Um valor 0 indica que a chamada do método teve êxito.</span><span class="sxs-lookup"><span data-stu-id="4540a-114">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="4540a-115">Um valor diferente de zero indica que ocorreu um erro.</span><span class="sxs-lookup"><span data-stu-id="4540a-115">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4540a-116">Comentários</span><span class="sxs-lookup"><span data-stu-id="4540a-116">Remarks</span></span>  
 <span data-ttu-id="4540a-117">Cada token retornado representa uma versão do [!INCLUDE[winSPServ](../../includes/winspserv-md.md)] ou [!INCLUDE[SPF2010](../../includes/spf2010-md.md)] que é compatível com o servidor de relatório atualmente instalado.</span><span class="sxs-lookup"><span data-stu-id="4540a-117">Each token that is returned represents a version of [!INCLUDE[winSPServ](../../includes/winspserv-md.md)] or [!INCLUDE[SPF2010](../../includes/spf2010-md.md)] that is compatible with the currently installed report server.</span></span> <span data-ttu-id="4540a-118">Se uma versão específica do SharePoint for compatível com versões anteriores do SharePoint, serão retornados tokens de cada versão compatível do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="4540a-118">If a particular version of SharePoint is compatible with previous SharePoint versions, tokens for each compatible SharePoint version are returned.</span></span>  
  
 <span data-ttu-id="4540a-119">A seguir é apresentada uma tabela dos tokens do SharePoint que são retornados.</span><span class="sxs-lookup"><span data-stu-id="4540a-119">The following is a table of the SharePoint tokens that are returned.</span></span>  
  
|<span data-ttu-id="4540a-120">**Tokens da versão**</span><span class="sxs-lookup"><span data-stu-id="4540a-120">**Version Tokens**</span></span>|<span data-ttu-id="4540a-121">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="4540a-121">**Description**</span></span>|  
|------------------------|---------------------|  
|<span data-ttu-id="4540a-122">WSS_V2_Compatible</span><span class="sxs-lookup"><span data-stu-id="4540a-122">WSS_V2_Compatible</span></span>|<span data-ttu-id="4540a-123">É executada uma instalação do [!INCLUDE[winSPServ](../../includes/winspserv-md.md)], [!INCLUDE[winSPServ](../../includes/winspserv-md.md)], [!INCLUDE[offSPServ](../../includes/offspserv-md.md)], [!INCLUDE[SPF2010](../../includes/spf2010-md.md)]ou [!INCLUDE[SPS2010](../../includes/sps2010-md.md)] , que é compatível com o [!INCLUDE[winSPServ](../../includes/winspserv-md.md)] 2.0.</span><span class="sxs-lookup"><span data-stu-id="4540a-123">A [!INCLUDE[winSPServ](../../includes/winspserv-md.md)], [!INCLUDE[winSPServ](../../includes/winspserv-md.md)], [!INCLUDE[offSPServ](../../includes/offspserv-md.md)], [!INCLUDE[SPF2010](../../includes/spf2010-md.md)], or [!INCLUDE[SPS2010](../../includes/sps2010-md.md)] installation is installed that is compatible with [!INCLUDE[winSPServ](../../includes/winspserv-md.md)] 2.0.</span></span>|  
|<span data-ttu-id="4540a-124">WSS_V3_Compatible</span><span class="sxs-lookup"><span data-stu-id="4540a-124">WSS_V3_Compatible</span></span>|<span data-ttu-id="4540a-125">É executada uma instalação do [!INCLUDE[winSPServ](../../includes/winspserv-md.md)], [!INCLUDE[winSPServ](../../includes/winspserv-md.md)], [!INCLUDE[offSPServ](../../includes/offspserv-md.md)], [!INCLUDE[SPF2010](../../includes/spf2010-md.md)]ou [!INCLUDE[SPS2010](../../includes/sps2010-md.md)] que é compatível com o [!INCLUDE[winSPServ](../../includes/winspserv-md.md)] 3.0.</span><span class="sxs-lookup"><span data-stu-id="4540a-125">A [!INCLUDE[winSPServ](../../includes/winspserv-md.md)], [!INCLUDE[winSPServ](../../includes/winspserv-md.md)], [!INCLUDE[offSPServ](../../includes/offspserv-md.md)], [!INCLUDE[SPF2010](../../includes/spf2010-md.md)], or [!INCLUDE[SPS2010](../../includes/sps2010-md.md)] installation is installed that is compatible with [!INCLUDE[winSPServ](../../includes/winspserv-md.md)] 3.0.</span></span>|  
|<span data-ttu-id="4540a-126">WSS_V4_Compatible</span><span class="sxs-lookup"><span data-stu-id="4540a-126">WSS_V4_Compatible</span></span>|<span data-ttu-id="4540a-127">É executada uma instalação do [!INCLUDE[SPF2010](../../includes/spf2010-md.md)] ou [!INCLUDE[SPS2010](../../includes/sps2010-md.md)] que é compatível com o Office 14.</span><span class="sxs-lookup"><span data-stu-id="4540a-127">A [!INCLUDE[SPF2010](../../includes/spf2010-md.md)] or [!INCLUDE[SPS2010](../../includes/sps2010-md.md)] installation is installed that is compatible with Office 14.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4540a-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4540a-128">Requirements</span></span>  
 <span data-ttu-id="4540a-129">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4540a-129">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4540a-130">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="4540a-130">See Also</span></span>  
 [<span data-ttu-id="4540a-131">Membros de MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="4540a-131">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
