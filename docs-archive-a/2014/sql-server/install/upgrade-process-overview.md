---
title: Visão geral do processo de atualização | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- upgrading SQL Server
- Upgrade Advisor [SQL Server], process description
- SQL Server Upgrade Advisor, process description
- upgrade process [Upgrade Advisor]
ms.assetid: f77ffbab-a195-4124-acce-9c538f7ca9ce
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 5da6dc3b3e6d6c7058193801100bf2552bfde7cd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87686033"
---
# <a name="upgrade-process-overview"></a><span data-ttu-id="225b1-102">Visão geral do processo de atualização</span><span class="sxs-lookup"><span data-stu-id="225b1-102">Upgrade Process Overview</span></span>
  <span data-ttu-id="225b1-103">Este tópico fornece informações sobre as práticas recomendadas do Supervisor de Atualização do [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] e um resumo dos processos recomendados para a atualização para o [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="225b1-103">This topic provides best practice information for [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Upgrade Advisor and a summary of the recommended process for upgrading to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span>  
  
## <a name="upgrade-process"></a><span data-ttu-id="225b1-104">Processo de atualização</span><span class="sxs-lookup"><span data-stu-id="225b1-104">Upgrade Process</span></span>  
 <span data-ttu-id="225b1-105">Os servidores que executam o [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)] ou [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] podem ser atualizados para o [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="225b1-105">Servers that are running [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], or [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] can be upgraded to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="225b1-106">Enquanto alguns componentes do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] podem ser atualizados no local, outros precisam ser migrados, e ainda há outros que foram substituídos por novos componentes.</span><span class="sxs-lookup"><span data-stu-id="225b1-106">Whereas some [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] components can be upgraded in place, others must be migrated, and still others have been superseded by new components.</span></span> <span data-ttu-id="225b1-107">Por exemplo, a partir do [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], o [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] ([!INCLUDE[ssIS](../../includes/ssis-md.md)]) substitui o DTS (Data Transformation Services), e o DTS não tem mais suporte no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="225b1-107">For example, starting with [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] ([!INCLUDE[ssIS](../../includes/ssis-md.md)]) supersedes Data Transformation Services (DTS), and DTS is no longer supported in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="225b1-108">Quando você formular seu plano de atualização, talvez precise planejar a atualização dos pacotes DTS atuais para pacotes do [!INCLUDE[ssIS](../../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="225b1-108">When you formulate your upgrade plan, you might need to plan for updating your current DTS packages to [!INCLUDE[ssIS](../../includes/ssis-md.md)] packages.</span></span>  
  
 <span data-ttu-id="225b1-109">O Supervisor de Atualização permite que você avalie as instalações, os componentes e os arquivos relacionados atuais do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para identificar problemas conhecidos que causarão problemas durante e após a atualização ou a migração para o [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="225b1-109">Upgrade Advisor enables you to evaluate current [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installations, components, and related files to identify known issues that will cause problems both during and after you upgrade or migrate to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="225b1-110">Alguns desses problemas conhecidos impedem a atualização do [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="225b1-110">A few of these known issues block the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] upgrade.</span></span> <span data-ttu-id="225b1-111">No relatório do Supervisor de Atualização, esses problemas são identificados como Bloqueadores de Atualização.</span><span class="sxs-lookup"><span data-stu-id="225b1-111">In the Upgrade Advisor report, these issues are identified as Upgrade Blockers.</span></span> <span data-ttu-id="225b1-112">Se você não resolveu os Bloqueadores de Atualização antes de executar a Instalação, a Instalação do [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] é encerrada e recomenda que você execute o Supervisor de Atualização para identificar os problemas específicos que estão impedindo a atualização.</span><span class="sxs-lookup"><span data-stu-id="225b1-112">If you have not addressed the Upgrade Blockers before you run Setup, [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Setup exits and recommends that you run Upgrade Advisor to identify the specific issues that are blocking the upgrade.</span></span>  
  
 <span data-ttu-id="225b1-113">Como prática recomendada antes de atualizar para o [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], sugerimos que você faça backup dos dados e das configurações de sistema, e realize etapas estratégicas conforme descrito nas diretrizes operacionais definidas para a sua organização.</span><span class="sxs-lookup"><span data-stu-id="225b1-113">As a best practice before upgrading to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], we recommend that you back up your data and system settings, and take strategic steps as outlined in the operational guidelines defined for your organization.</span></span> <span data-ttu-id="225b1-114">Use as etapas a seguir para concluir a atualização:</span><span class="sxs-lookup"><span data-stu-id="225b1-114">Use the following steps to complete the upgrade:</span></span>  
  
1.  <span data-ttu-id="225b1-115">Analise os [Hardware and Software Requirements for Installing SQL Server 2014](hardware-and-software-requirements-for-installing-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="225b1-115">Review [Hardware and Software Requirements for Installing SQL Server 2014](hardware-and-software-requirements-for-installing-sql-server.md).</span></span>  
  
2.  <span data-ttu-id="225b1-116">Faça backup dos dados e configurações do sistema</span><span class="sxs-lookup"><span data-stu-id="225b1-116">Back up data and system settings.</span></span>  
  
3.  <span data-ttu-id="225b1-117">Execute o Supervisor de Atualização.</span><span class="sxs-lookup"><span data-stu-id="225b1-117">Run Upgrade Advisor.</span></span>  
  
     <span data-ttu-id="225b1-118">Ele não modifica seus dados ou altera as configurações do seu computador.</span><span class="sxs-lookup"><span data-stu-id="225b1-118">Upgrade Advisor does not modify your data or change settings on your computer.</span></span>  
  
4.  <span data-ttu-id="225b1-119">Revise os problemas identificados no relatório do Supervisor de Atualização.</span><span class="sxs-lookup"><span data-stu-id="225b1-119">Review the issues identified in the Upgrade Advisor report.</span></span>  
  
5.  <span data-ttu-id="225b1-120">Solucione qualquer problema que possa impedir a atualização para o [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="225b1-120">Resolve any blocking issues that would prevent you from upgrading to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span>  
  
6.  <span data-ttu-id="225b1-121">Solucione outros problemas de pré-atualização.</span><span class="sxs-lookup"><span data-stu-id="225b1-121">Resolve any other pre-upgrade issues.</span></span>  
  
7.  <span data-ttu-id="225b1-122">Execute o Supervisor de Atualização para verificar se todos os problemas conhecidos foram solucionados.</span><span class="sxs-lookup"><span data-stu-id="225b1-122">Run Upgrade Advisor to verify that all known issues have been addressed.</span></span>  
  
8.  <span data-ttu-id="225b1-123">Execute a Instalação do [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="225b1-123">Run [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Setup.</span></span>  
  
9. <span data-ttu-id="225b1-124">Solucione qualquer problema de pós-atualização e de migração.</span><span class="sxs-lookup"><span data-stu-id="225b1-124">Resolve any post-upgrade and migration issues.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="225b1-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="225b1-125">See Also</span></span>  
 <span data-ttu-id="225b1-126">[Executando o supervisor de atualização &#40;a interface do usuário&#41;](../../../2014/sql-server/install/running-upgrade-advisor-user-interface.md) </span><span class="sxs-lookup"><span data-stu-id="225b1-126">[Running Upgrade Advisor &#40;User Interface&#41;](../../../2014/sql-server/install/running-upgrade-advisor-user-interface.md) </span></span>  
 <span data-ttu-id="225b1-127">[Usando relatórios](../../../2014/sql-server/install/using-reports.md) </span><span class="sxs-lookup"><span data-stu-id="225b1-127">[Using Reports](../../../2014/sql-server/install/using-reports.md) </span></span>  
 [<span data-ttu-id="225b1-128">Trabalhando com o Supervisor de Atualização</span><span class="sxs-lookup"><span data-stu-id="225b1-128">Working with Upgrade Advisor</span></span>](../../../2014/sql-server/install/working-with-upgrade-advisor.md)  
  
  
