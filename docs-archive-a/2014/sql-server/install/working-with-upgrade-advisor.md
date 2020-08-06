---
title: Trabalhando com o supervisor de atualização | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Upgrade Advisor [SQL Server], when to use
- SQL Server Upgrade Advisor, when to use
- when to use Upgrade Advisor
ms.assetid: 5f26a7b9-1ac2-442c-8316-87b078db3baf
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 75a16e57734493cdd7ac00e7bad3124eb7a99d84
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573378"
---
# <a name="working-with-upgrade-advisor"></a><span data-ttu-id="c7c81-102">Trabalhando com o Supervisor de Atualização</span><span class="sxs-lookup"><span data-stu-id="c7c81-102">Working with Upgrade Advisor</span></span>
  <span data-ttu-id="c7c81-103">Para ajudar a assegurar que a atualização para o [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] seja bem-sucedida, o Supervisor de Atualização fornece um console central para identificar problemas que devem ser solucionados nas instalações antes da atualização para o [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c7c81-103">To help ensure that your upgrade to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] is successful, Upgrade Advisor provides a central console to identify issues to address in your installations before upgrading to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span>  
  
 <span data-ttu-id="c7c81-104">Você pode utilizar o Supervisor de Atualização para as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="c7c81-104">You can use Upgrade Advisor to perform the following tasks:</span></span>  
  
-   <span data-ttu-id="c7c81-105">Analisar componentes de versões anteriores em servidores locais ou remotos.</span><span class="sxs-lookup"><span data-stu-id="c7c81-105">Analyze previous version's components on local or remote servers.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="c7c81-106">Você não pode analisar instâncias remotas do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c7c81-106">You cannot analyze remote instances of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="c7c81-107">Exiba os resultados da análise.</span><span class="sxs-lookup"><span data-stu-id="c7c81-107">View the results of the analysis.</span></span>  
  
 <span data-ttu-id="c7c81-108">O Supervisor de Atualização inclui um analisador e um visualizador.</span><span class="sxs-lookup"><span data-stu-id="c7c81-108">Upgrade Advisor includes an analyzer and a viewer.</span></span> <span data-ttu-id="c7c81-109">O Assistente para Análise do Supervisor de Atualização analisa os componentes que você selecionar.</span><span class="sxs-lookup"><span data-stu-id="c7c81-109">The Upgrade Advisor Analysis Wizard analyzes the components you select.</span></span> <span data-ttu-id="c7c81-110">Em seguida, o analisador gera relatórios personalizados sobre os problemas que devem ser solucionados antes da atualização para o [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c7c81-110">The analyzer then generates custom reports about issues that you must handle before you can upgrade to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="c7c81-111">Use o Visualizador de Relatórios do Supervisor de Atualização para exibir os relatórios personalizados.</span><span class="sxs-lookup"><span data-stu-id="c7c81-111">You use the Upgrade Advisor Report Viewer to view the custom reports.</span></span> <span data-ttu-id="c7c81-112">Para obter mais informações sobre o que a análise do supervisor de atualização detecta, consulte [resolvendo problemas de atualização](../../../2014/sql-server/install/resolving-upgrade-issues.md).</span><span class="sxs-lookup"><span data-stu-id="c7c81-112">For more information about what Upgrade Advisor analysis detects, see [Resolving Upgrade Issues](../../../2014/sql-server/install/resolving-upgrade-issues.md).</span></span>  
  
 <span data-ttu-id="c7c81-113">Os tópicos desta seção fornecem uma visão geral da funcionalidade do Supervisor de Atualização e informações sobre como usar o Supervisor de Atualização e seus relatórios.</span><span class="sxs-lookup"><span data-stu-id="c7c81-113">The topics in this section provide an overview of Upgrade Advisor functionality and information about how to use Upgrade Advisor and Upgrade Advisor reports.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c7c81-114">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="c7c81-114">In This Section</span></span>  
  
|<span data-ttu-id="c7c81-115">Tópico</span><span class="sxs-lookup"><span data-stu-id="c7c81-115">Topic</span></span>|<span data-ttu-id="c7c81-116">Descrição</span><span class="sxs-lookup"><span data-stu-id="c7c81-116">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="c7c81-117">Visão geral do Assistente de Atualização</span><span class="sxs-lookup"><span data-stu-id="c7c81-117">Overview of Upgrade Advisor</span></span>](../../../2014/sql-server/install/overview-of-upgrade-advisor.md)|<span data-ttu-id="c7c81-118">Fornece uma visão geral do processo de atualização, do Assistente para Análise do Supervisor de Atualização e do Visualizador de Relatórios do Supervisor de Atualização.</span><span class="sxs-lookup"><span data-stu-id="c7c81-118">Provides an overview of the upgrade process, the Upgrade Advisor Analysis Wizard, and the Upgrade Advisor Report Viewer.</span></span>|  
|[<span data-ttu-id="c7c81-119">Tópicos de informações práticas do Supervisor de Atualização</span><span class="sxs-lookup"><span data-stu-id="c7c81-119">Upgrade Advisor How-to Topics</span></span>](../../../2014/sql-server/install/upgrade-advisor-how-to-topics.md)|<span data-ttu-id="c7c81-120">Fornece instruções para executar procedimentos comuns do Supervisor de Atualização.</span><span class="sxs-lookup"><span data-stu-id="c7c81-120">Provides instructions to perform common Upgrade Advisor procedures.</span></span>|  
|[<span data-ttu-id="c7c81-121">Referência da interface de usuário do Supervisor de Atualização</span><span class="sxs-lookup"><span data-stu-id="c7c81-121">Upgrade Advisor User Interface Reference</span></span>](../../../2014/sql-server/install/upgrade-advisor-user-interface-reference.md)|<span data-ttu-id="c7c81-122">Contém os tópicos que aparecem se você pressionar a tecla F1 ou clicar em **ajuda** nas páginas do assistente de análise do supervisor de atualização.</span><span class="sxs-lookup"><span data-stu-id="c7c81-122">Contains topics that appear if you press the F1 key or click **Help** on the Upgrade Advisor Analysis Wizard pages.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c7c81-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c7c81-123">See Also</span></span>  
 <span data-ttu-id="c7c81-124">[Instalando o supervisor de atualização](../../../2014/sql-server/install/installing-upgrade-advisor.md) </span><span class="sxs-lookup"><span data-stu-id="c7c81-124">[Installing Upgrade Advisor](../../../2014/sql-server/install/installing-upgrade-advisor.md) </span></span>  
 [<span data-ttu-id="c7c81-125">Solucionando problemas de atualização</span><span class="sxs-lookup"><span data-stu-id="c7c81-125">Resolving Upgrade Issues</span></span>](../../../2014/sql-server/install/resolving-upgrade-issues.md)  
  
  
