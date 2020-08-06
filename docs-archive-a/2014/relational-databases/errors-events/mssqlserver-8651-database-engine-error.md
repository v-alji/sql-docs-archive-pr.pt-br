---
title: MSSQLSERVER_8651 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 8651 (Database Engine error)
ms.assetid: 4cc3498d-5449-4c4e-b1f9-3271831c725a
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 43a385350a05edee3759ab83d318e365f5b4f3e4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679964"
---
# <a name="mssqlserver_8651"></a><span data-ttu-id="17fe5-102">MSSQLSERVER_8651</span><span class="sxs-lookup"><span data-stu-id="17fe5-102">MSSQLSERVER_8651</span></span>
    
## <a name="details"></a><span data-ttu-id="17fe5-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="17fe5-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="17fe5-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="17fe5-104">Product Name</span></span>|<span data-ttu-id="17fe5-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="17fe5-105">SQL Server</span></span>|  
|<span data-ttu-id="17fe5-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="17fe5-106">Event ID</span></span>|<span data-ttu-id="17fe5-107">8651</span><span class="sxs-lookup"><span data-stu-id="17fe5-107">8651</span></span>|  
|<span data-ttu-id="17fe5-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="17fe5-108">Event Source</span></span>|<span data-ttu-id="17fe5-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="17fe5-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="17fe5-110">Componente</span><span class="sxs-lookup"><span data-stu-id="17fe5-110">Component</span></span>|<span data-ttu-id="17fe5-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="17fe5-111">SQLEngine</span></span>|  
|<span data-ttu-id="17fe5-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="17fe5-112">Symbolic Name</span></span>|<span data-ttu-id="17fe5-113">MEMGRANT_ERR</span><span class="sxs-lookup"><span data-stu-id="17fe5-113">MEMGRANT_ERR</span></span>|  
|<span data-ttu-id="17fe5-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="17fe5-114">Message Text</span></span>|<span data-ttu-id="17fe5-115">Não foi possível executar a operação solicitada porque o mínimo de memória para consulta não está disponível.</span><span class="sxs-lookup"><span data-stu-id="17fe5-115">Could not perform the requested operation because the minimum query memory is not available.</span></span> <span data-ttu-id="17fe5-116">Diminua o valor configurado para a opção de configuração de servidor 'min memory per query'.</span><span class="sxs-lookup"><span data-stu-id="17fe5-116">Decrease the configured value for the 'min memory per query' server configuration option.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="17fe5-117">Explicação</span><span class="sxs-lookup"><span data-stu-id="17fe5-117">Explanation</span></span>  
 <span data-ttu-id="17fe5-118">Outros processos estão usando memória do servidor (exercendo pressão de memória no servidor).</span><span class="sxs-lookup"><span data-stu-id="17fe5-118">Other processes are consuming server memory (exerting memory pressure in the server).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="17fe5-119">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="17fe5-119">User Action</span></span>  
 <span data-ttu-id="17fe5-120">Diminua o valor configurado para a opção de configuração de servidor 'min memory per query' ou reduza a carga de consultas no servidor.</span><span class="sxs-lookup"><span data-stu-id="17fe5-120">Either decrease the configured value for the min memory per query' server configuration option or reduce the query load to the server.</span></span>  
  
 <span data-ttu-id="17fe5-121">Esta lista descreve etapas gerais que ajudarão a corrigir erros de memória:</span><span class="sxs-lookup"><span data-stu-id="17fe5-121">The following list outlines general steps that will help in troubleshooting memory errors:</span></span>  
  
1.  <span data-ttu-id="17fe5-122">Verifique se outros aplicativos ou serviços estão consumindo memória neste servidor.</span><span class="sxs-lookup"><span data-stu-id="17fe5-122">Verify whether other applications or services are consuming memory on this server.</span></span> <span data-ttu-id="17fe5-123">Reconfigure os aplicativos ou serviços menos críticos de maneira que eles consumam menos memória.</span><span class="sxs-lookup"><span data-stu-id="17fe5-123">Reconfigure less critical applications or services to consume less memory.</span></span>  
  
2.  <span data-ttu-id="17fe5-124">Comece a coletar contadores do monitor de desempenho para o **SQL Server: Gerenciador de Buffer**, **SQL Server: Gerenciador de Memória**.</span><span class="sxs-lookup"><span data-stu-id="17fe5-124">Start collecting performance monitor counters for **SQL Server: Buffer Manager**, **SQL Server: Memory Manager**.</span></span>  
  
3.  <span data-ttu-id="17fe5-125">Verifique os seguintes parâmetros de configuração da memória do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="17fe5-125">Check the following [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] memory configuration parameters:</span></span>  
  
    -   <span data-ttu-id="17fe5-126">**memória máxima do servidor**</span><span class="sxs-lookup"><span data-stu-id="17fe5-126">**max server memory**</span></span>  
  
    -   <span data-ttu-id="17fe5-127">**memória mínima do servidor**</span><span class="sxs-lookup"><span data-stu-id="17fe5-127">**min server memory**</span></span>  
  
    -   <span data-ttu-id="17fe5-128">**memória mínima por consulta**</span><span class="sxs-lookup"><span data-stu-id="17fe5-128">**min memory per query**</span></span>  
  
     <span data-ttu-id="17fe5-129">Observe se há configurações incomuns.</span><span class="sxs-lookup"><span data-stu-id="17fe5-129">Notice unusual settings.</span></span> <span data-ttu-id="17fe5-130">Corrija-as conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="17fe5-130">Correct them as necessary.</span></span> <span data-ttu-id="17fe5-131">As configurações padrão estão listadas em "Definindo opções de configuração do servidor" nos Manuais Online do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="17fe5-131">Default settings are listed in "Setting Server Configuration Options" in SQL Server Books Online.</span></span>  
  
4.  <span data-ttu-id="17fe5-132">Verifique a carga de trabalho (por exemplo, o número de sessões simultâneas e de consultas em execução).</span><span class="sxs-lookup"><span data-stu-id="17fe5-132">Check the workload (for example, number of concurrent sessions, currently executing queries).</span></span>  
  
 <span data-ttu-id="17fe5-133">As seguintes ações podem disponibilizar mais memória para o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="17fe5-133">The following actions may make more memory available to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="17fe5-134">Se outros aplicativos além do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] estiverem consumindo recursos, experimente interrompê-los ou considere a possibilidade de executá-los em um servidor à parte.</span><span class="sxs-lookup"><span data-stu-id="17fe5-134">If applications besides [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] are consuming resources, try stopping running these applications or consider running them on a separate server.</span></span> <span data-ttu-id="17fe5-135">Isso eliminará a pressão de memória externa.</span><span class="sxs-lookup"><span data-stu-id="17fe5-135">This will remove external memory pressure.</span></span>  
  
-   <span data-ttu-id="17fe5-136">Se você tiver configurado a opção **memória máxima do servidor**, aumente sua configuração.</span><span class="sxs-lookup"><span data-stu-id="17fe5-136">If you have configured **max server memory,** increase its setting.</span></span>  
  
 <span data-ttu-id="17fe5-137">Execute os comandos DBCC a seguir para liberar diversos caches de memória do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="17fe5-137">Run the following DBCC commands to free several [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] memory caches.</span></span>  
  
-   <span data-ttu-id="17fe5-138">DBCC FREESYSTEMCACHE</span><span class="sxs-lookup"><span data-stu-id="17fe5-138">DBCC FREESYSTEMCACHE</span></span>  
  
-   <span data-ttu-id="17fe5-139">DBCC FREESESSIONCACHE</span><span class="sxs-lookup"><span data-stu-id="17fe5-139">DBCC FREESESSIONCACHE</span></span>  
  
-   <span data-ttu-id="17fe5-140">DBCC FREEPROCCACHE</span><span class="sxs-lookup"><span data-stu-id="17fe5-140">DBCC FREEPROCCACHE</span></span>  
  
 <span data-ttu-id="17fe5-141">Se o problema persistir, será necessário aprofundar as investigações e possivelmente reduzir a carga de trabalho.</span><span class="sxs-lookup"><span data-stu-id="17fe5-141">If the problem continues, you will need to investigate further and possibly reduce workload.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17fe5-142">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="17fe5-142">See Also</span></span>  
 <span data-ttu-id="17fe5-143">[DBCC FREESYSTEMCACHE &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-freesystemcache-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="17fe5-143">[DBCC FREESYSTEMCACHE &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-freesystemcache-transact-sql) </span></span>  
 <span data-ttu-id="17fe5-144">[DBCC FREESESSIONCACHE &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-freesessioncache-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="17fe5-144">[DBCC FREESESSIONCACHE &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-freesessioncache-transact-sql) </span></span>  
 <span data-ttu-id="17fe5-145">[DBCC FREEPROCCACHE &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-freeproccache-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="17fe5-145">[DBCC FREEPROCCACHE &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-freeproccache-transact-sql) </span></span>  
 <span data-ttu-id="17fe5-146">[Opções de configuração do servidor &#40;SQL Server&#41;](../../database-engine/configure-windows/server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="17fe5-146">[Server Configuration Options &#40;SQL Server&#41;](../../database-engine/configure-windows/server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="17fe5-147">[SQL Server, objeto Buffer Manager](../performance-monitor/sql-server-buffer-manager-object.md) </span><span class="sxs-lookup"><span data-stu-id="17fe5-147">[SQL Server, Buffer Manager Object](../performance-monitor/sql-server-buffer-manager-object.md) </span></span>  
 [<span data-ttu-id="17fe5-148">SQL Server, objeto gerenciador de memória</span><span class="sxs-lookup"><span data-stu-id="17fe5-148">SQL Server, Memory Manager Object</span></span>](../performance-monitor/sql-server-memory-manager-object.md)  
  
  
