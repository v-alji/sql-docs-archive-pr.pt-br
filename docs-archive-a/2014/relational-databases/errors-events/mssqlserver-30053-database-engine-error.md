---
title: MSSQLSERVER_30053 | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
ms.assetid: 8ad23889-e243-4bd7-bc3e-150403399d89
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 02d6262f93ef3dbbc9834053f864046b4dca30f2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574040"
---
# <a name="mssqlserver_30053"></a><span data-ttu-id="54814-102">MSSQLSERVER_30053</span><span class="sxs-lookup"><span data-stu-id="54814-102">MSSQLSERVER_30053</span></span>
    
## <a name="details"></a><span data-ttu-id="54814-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="54814-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="54814-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="54814-104">Product Name</span></span>|<span data-ttu-id="54814-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="54814-105">SQL Server</span></span>|  
|<span data-ttu-id="54814-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="54814-106">Event ID</span></span>|<span data-ttu-id="54814-107">30053</span><span class="sxs-lookup"><span data-stu-id="54814-107">30053</span></span>|  
|<span data-ttu-id="54814-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="54814-108">Event Source</span></span>|<span data-ttu-id="54814-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="54814-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="54814-110">Componente</span><span class="sxs-lookup"><span data-stu-id="54814-110">Component</span></span>|<span data-ttu-id="54814-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="54814-111">SQLEngine</span></span>|  
|<span data-ttu-id="54814-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="54814-112">Symbolic Name</span></span>|<span data-ttu-id="54814-113">FTXT_QUERY_E_WORDBREAKINGTIMEOUT</span><span class="sxs-lookup"><span data-stu-id="54814-113">FTXT_QUERY_E_WORDBREAKINGTIMEOUT</span></span>|  
|<span data-ttu-id="54814-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="54814-114">Message Text</span></span>|<span data-ttu-id="54814-115">Foi atingido o tempo limite de quebra de palavras para a cadeia de consulta de texto completo.</span><span class="sxs-lookup"><span data-stu-id="54814-115">Word breaking timed out for the full-text query string.</span></span> <span data-ttu-id="54814-116">O separador de palavras pode ter demorado para processar a cadeia de consulta de texto completo ou um grande número de consultas está em execução no servidor.</span><span class="sxs-lookup"><span data-stu-id="54814-116">This can happen if the wordbreaker took a long time to process the full-text query string, or if a large number of queries are running on the server.</span></span> <span data-ttu-id="54814-117">Tente executar a consulta novamente com uma carga mais leve.</span><span class="sxs-lookup"><span data-stu-id="54814-117">Try running the query again under a lighter load.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="54814-118">Explicação</span><span class="sxs-lookup"><span data-stu-id="54814-118">Explanation</span></span>  
 <span data-ttu-id="54814-119">Um erro de tempo limite na separação de palavras pode ocorrer nas seguintes situações:</span><span class="sxs-lookup"><span data-stu-id="54814-119">A word-breaking timeout error can occur in the following situations:</span></span>  
  
-   <span data-ttu-id="54814-120">O separador de palavras para o idioma da consulta está configurado incorretamente. Por exemplo, suas configurações de Registro estão incorretas.</span><span class="sxs-lookup"><span data-stu-id="54814-120">The word breaker for the query language is configured incorrectly; for example, its registry settings are incorrect.</span></span>  
  
-   <span data-ttu-id="54814-121">O separador de palavras funciona incorretamente em uma cadeia de consulta específica.</span><span class="sxs-lookup"><span data-stu-id="54814-121">The word breaker malfunctions for a specific query string.</span></span>  
  
-   <span data-ttu-id="54814-122">O separador de palavras retorna uma quantidade excessiva de dados para uma cadeia de consulta específica.</span><span class="sxs-lookup"><span data-stu-id="54814-122">The word breaker returns too much data for a specific query string.</span></span> <span data-ttu-id="54814-123">O excesso de dados é tratado como um ataque de saturação de buffer em potencial e desliga o processo de daemon de filtro (fdhost.exe) que hospeda os serviços de separação de palavras.</span><span class="sxs-lookup"><span data-stu-id="54814-123">Excess data is treated as a potential buffer overrun attack, and shuts down the filter daemon process (fdhost.exe), which hosts the word-breaking services.</span></span>  
  
-   <span data-ttu-id="54814-124">A configuração do processo de daemon de filtro está incorreta.</span><span class="sxs-lookup"><span data-stu-id="54814-124">The filter daemon process configuration is incorrect.</span></span>  
  
     <span data-ttu-id="54814-125">A maior parte dos problemas comuns de configuração são vencimento de senha ou uma política de domínio que impede que a conta do daemon do filtro faça o logon.</span><span class="sxs-lookup"><span data-stu-id="54814-125">The most common configuration problems are password expiration or a domain policy that prevents the filter daemon account from logging on.</span></span>  
  
-   <span data-ttu-id="54814-126">Uma carga de trabalho de consultas muito pesada está em execução na instância do servidor. Por exemplo, o separador de palavras demorou muito para processar a cadeia de consultas de texto completo ou um grande número de consultas está em execução no servidor.</span><span class="sxs-lookup"><span data-stu-id="54814-126">A very heavy query workload is running on the server instance; for example, the word-breaker took a long time to process the full-text query string, or a large number of queries are running on the server.</span></span> <span data-ttu-id="54814-127">Observe que essa é a causa menos provável.</span><span class="sxs-lookup"><span data-stu-id="54814-127">Note that this is the least likely cause.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="54814-128">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="54814-128">User Action</span></span>  
 <span data-ttu-id="54814-129">Selecione a ação do usuário apropriada à causa provável do tempo limite, da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="54814-129">Select the user action that is appropriate to the probable cause of the timeout, as follows:</span></span>  
  
|<span data-ttu-id="54814-130">Causa provável</span><span class="sxs-lookup"><span data-stu-id="54814-130">Probable cause</span></span>|<span data-ttu-id="54814-131">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="54814-131">User action</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="54814-132">O separador de palavras para o idioma da consulta está configurado incorretamente.</span><span class="sxs-lookup"><span data-stu-id="54814-132">The word breaker for the query language is configured incorrectly.</span></span>|<span data-ttu-id="54814-133">Se você estiver usando um separador de palavras de terceiros, ele poderá estar registrado incorretamente com o sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="54814-133">If you are using a third-party word breaker it might be incorrectly registered with the operating system.</span></span> <span data-ttu-id="54814-134">Nesse caso, registre novamente o separador de palavras.</span><span class="sxs-lookup"><span data-stu-id="54814-134">In this case, re-register the word breaker.</span></span> <span data-ttu-id="54814-135">Para obter mais informações, consulte [Reverter os separadores de palavras usados pela pesquisa para a versão anterior](../search/revert-the-word-breakers-used-by-search-to-the-previous-version.md).</span><span class="sxs-lookup"><span data-stu-id="54814-135">For more information, see [Revert the Word Breakers Used by Search to the Previous Version](../search/revert-the-word-breakers-used-by-search-to-the-previous-version.md).</span></span>|  
|<span data-ttu-id="54814-136">O separador de palavras funciona incorretamente em uma cadeia de consulta específica.</span><span class="sxs-lookup"><span data-stu-id="54814-136">The word breaker malfunctions for a specific query string.</span></span>|<span data-ttu-id="54814-137">Se o separador de palavras for suportado pelo [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], entre em contato com o Suporte e Atendimento ao Cliente Microsoft.</span><span class="sxs-lookup"><span data-stu-id="54814-137">If the word breaker is supported by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], contact Microsoft Customer Service and Support.</span></span>|  
|<span data-ttu-id="54814-138">O separador de palavras retorna uma quantidade excessiva de dados para uma cadeia de consulta específica.</span><span class="sxs-lookup"><span data-stu-id="54814-138">The word breaker returns too much data for a specific query string.</span></span>|<span data-ttu-id="54814-139">Se o separador de palavras for suportado pelo [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], entre em contato com o Suporte e Atendimento ao Cliente Microsoft.</span><span class="sxs-lookup"><span data-stu-id="54814-139">If the word breaker is supported by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], contact Microsoft Customer Service and Support.</span></span>|  
|<span data-ttu-id="54814-140">A configuração do processo de daemon de filtro está incorreta.</span><span class="sxs-lookup"><span data-stu-id="54814-140">The filter daemon process configuration is incorrect.</span></span>|<span data-ttu-id="54814-141">Verifique se você está usando a senha atual e se uma política de domínio não está impedindo a conta do daemon de filtro de fazer logon.</span><span class="sxs-lookup"><span data-stu-id="54814-141">Ensure that you are using the current password and that a domain policy is not preventing the filter daemon account from logging on.</span></span>|  
|<span data-ttu-id="54814-142">Uma carga de trabalho de consulta muito pesada está em execução na instância do servidor.</span><span class="sxs-lookup"><span data-stu-id="54814-142">A very heavy query workload is running on the server instance.</span></span>|<span data-ttu-id="54814-143">Tente executar a consulta novamente com uma carga mais leve.</span><span class="sxs-lookup"><span data-stu-id="54814-143">Try running the query again under a lighter load.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="54814-144">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="54814-144">See Also</span></span>  
 <span data-ttu-id="54814-145">[Definir a conta de serviço para o iniciador do daemon de filtro de texto completo](../search/set-the-service-account-for-the-full-text-filter-daemon-launcher.md) </span><span class="sxs-lookup"><span data-stu-id="54814-145">[Set the Service Account for the Full-text Filter Daemon Launcher](../search/set-the-service-account-for-the-full-text-filter-daemon-launcher.md) </span></span>  
 <span data-ttu-id="54814-146">[Pesquisa de Texto Completo](../search/full-text-search.md) </span><span class="sxs-lookup"><span data-stu-id="54814-146">[Full-Text Search](../search/full-text-search.md) </span></span>  
 <span data-ttu-id="54814-147">[&#41;&#40;Transact-SQL de sp_help_fulltext_system_components](/sql/relational-databases/system-stored-procedures/sp-help-fulltext-system-components-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="54814-147">[sp_help_fulltext_system_components &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-fulltext-system-components-transact-sql) </span></span>  
 <span data-ttu-id="54814-148">[Configurar e gerenciar separadores de palavras e lematizadores para pesquisa](../search/configure-and-manage-word-breakers-and-stemmers-for-search.md) </span><span class="sxs-lookup"><span data-stu-id="54814-148">[Configure and Manage Word Breakers and Stemmers for Search](../search/configure-and-manage-word-breakers-and-stemmers-for-search.md) </span></span>  
 [<span data-ttu-id="54814-149">Configurar e gerenciar filtros de pesquisa</span><span class="sxs-lookup"><span data-stu-id="54814-149">Configure and Manage Filters for Search</span></span>](../search/configure-and-manage-filters-for-search.md)  
  
  
