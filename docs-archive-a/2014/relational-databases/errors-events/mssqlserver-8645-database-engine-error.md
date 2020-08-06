---
title: MSSQLSERVER_8645 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 8645 (Database Engine error)
ms.assetid: 63d6d6d7-3850-4061-8e96-b1fa665e3180
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 7be9774452e2008c34ecb52d228a0123992c5368
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575858"
---
# <a name="mssqlserver_8645"></a><span data-ttu-id="605b6-102">MSSQLSERVER_8645</span><span class="sxs-lookup"><span data-stu-id="605b6-102">MSSQLSERVER_8645</span></span>
    
## <a name="details"></a><span data-ttu-id="605b6-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="605b6-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="605b6-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="605b6-104">Product Name</span></span>|<span data-ttu-id="605b6-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="605b6-105">SQL Server</span></span>|  
|<span data-ttu-id="605b6-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="605b6-106">Event ID</span></span>|<span data-ttu-id="605b6-107">8645</span><span class="sxs-lookup"><span data-stu-id="605b6-107">8645</span></span>|  
|<span data-ttu-id="605b6-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="605b6-108">Event Source</span></span>|<span data-ttu-id="605b6-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="605b6-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="605b6-110">Componente</span><span class="sxs-lookup"><span data-stu-id="605b6-110">Component</span></span>|<span data-ttu-id="605b6-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="605b6-111">SQLEngine</span></span>|  
|<span data-ttu-id="605b6-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="605b6-112">Symbolic Name</span></span>|<span data-ttu-id="605b6-113">MEMTIMEDOUT_ERR</span><span class="sxs-lookup"><span data-stu-id="605b6-113">MEMTIMEDOUT_ERR</span></span>|  
|<span data-ttu-id="605b6-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="605b6-114">Message Text</span></span>|<span data-ttu-id="605b6-115">O tempo limite expirou enquanto aguardava por recursos de memória para executar a consulta.</span><span class="sxs-lookup"><span data-stu-id="605b6-115">A time out occurred while waiting for memory resources to execute the query.</span></span> <span data-ttu-id="605b6-116">Execute a consulta novamente.</span><span class="sxs-lookup"><span data-stu-id="605b6-116">Rerun the query.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="605b6-117">Explicação</span><span class="sxs-lookup"><span data-stu-id="605b6-117">Explanation</span></span>  
 <span data-ttu-id="605b6-118">Tempo limite excedido ao aguardar recursos de memória para executar a consulta no pool de recursos 'default'.</span><span class="sxs-lookup"><span data-stu-id="605b6-118">A timeout occurred while waiting for memory resources to execute the query in the resource pool 'default'.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="605b6-119">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="605b6-119">User Action</span></span>  
 <span data-ttu-id="605b6-120">Se você não estiver usando o Administrador de Recursos, nós recomendamos que você verifique o estado de servidor geral e a carga ou verifique o pool de recursos ou as configurações do grupo de cargas de trabalho.</span><span class="sxs-lookup"><span data-stu-id="605b6-120">If you are not using Resource Governor, we recommend that you verify the overall server state and load, or check the resource pool or workload group settings.</span></span>  
  
 <span data-ttu-id="605b6-121">Esta lista descreve etapas gerais que ajudarão a corrigir erros de memória:</span><span class="sxs-lookup"><span data-stu-id="605b6-121">The following list outlines general steps that will help in troubleshooting memory errors:</span></span>  
  
1.  <span data-ttu-id="605b6-122">Verifique se outros aplicativos ou serviços estão consumindo memória neste servidor.</span><span class="sxs-lookup"><span data-stu-id="605b6-122">Verify whether other applications or services are consuming memory on this server.</span></span> <span data-ttu-id="605b6-123">Reconfigure os aplicativos ou serviços menos críticos de maneira que eles consumam menos memória.</span><span class="sxs-lookup"><span data-stu-id="605b6-123">Reconfigure less critical applications or services to consume less memory.</span></span>  
  
2.  <span data-ttu-id="605b6-124">Comece a coletar contadores do monitor de desempenho para o **SQL Server: Gerenciador de Buffer**, **SQL Server: Gerenciador de Memória**.</span><span class="sxs-lookup"><span data-stu-id="605b6-124">Start collecting performance monitor counters for **SQL Server: Buffer Manager**, **SQL Server: Memory Manager**.</span></span>  
  
3.  <span data-ttu-id="605b6-125">Verifique os seguintes parâmetros de configuração da memória do SQL Server:</span><span class="sxs-lookup"><span data-stu-id="605b6-125">Check the following SQL Server memory configuration parameters:</span></span>  
  
    -   <span data-ttu-id="605b6-126">**memória máxima do servidor**</span><span class="sxs-lookup"><span data-stu-id="605b6-126">**max server memory**</span></span>  
  
    -   <span data-ttu-id="605b6-127">**memória mínima do servidor**</span><span class="sxs-lookup"><span data-stu-id="605b6-127">**min server memory**</span></span>  
  
    -   <span data-ttu-id="605b6-128">**memória mínima por consulta**</span><span class="sxs-lookup"><span data-stu-id="605b6-128">**min memory per query**</span></span>  
  
     <span data-ttu-id="605b6-129">Observe se há configurações incomuns.</span><span class="sxs-lookup"><span data-stu-id="605b6-129">Notice unusual settings.</span></span> <span data-ttu-id="605b6-130">Corrija-as conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="605b6-130">Correct them as necessary.</span></span> <span data-ttu-id="605b6-131">Considere os requisitos de memória aumentados para [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="605b6-131">Account for increased memory requirements for [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="605b6-132">As configurações padrão estão listadas em "Definindo opções de configuração do servidor" nos Manuais Online do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="605b6-132">Default settings are listed in "Setting Server Configuration Options" in SQL Server Books Online.</span></span>  
  
4.  <span data-ttu-id="605b6-133">Observe o resultado do DBCC MEMORYSTATUS e a forma como ele se altera quando você vê essas mensagens de erro.</span><span class="sxs-lookup"><span data-stu-id="605b6-133">Observe DBCC MEMORYSTATUS output and the way it changes when you see these error messages.</span></span>  
  
5.  <span data-ttu-id="605b6-134">Verifique a carga de trabalho (por exemplo, o número de sessões simultâneas e de consultas em execução).</span><span class="sxs-lookup"><span data-stu-id="605b6-134">Check the workload (for example, number of concurrent sessions, currently executing queries).</span></span>  
  
 <span data-ttu-id="605b6-135">As seguintes ações podem disponibilizar mais memória para o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="605b6-135">The following actions may make more memory available to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="605b6-136">Se outros aplicativos além do SQL Server estiverem consumindo recursos, tente parar a execução desses aplicativos ou considere a possibilidade de executá-los em outro servidor.</span><span class="sxs-lookup"><span data-stu-id="605b6-136">If applications besides SQL Server are consuming resources, try stopping running these applications or consider running them on a separate server.</span></span> <span data-ttu-id="605b6-137">Isso eliminará a pressão de memória externa.</span><span class="sxs-lookup"><span data-stu-id="605b6-137">This will remove external memory pressure.</span></span>  
  
-   <span data-ttu-id="605b6-138">Se você tiver configurado a opção **memória máxima do servidor**, aumente sua configuração.</span><span class="sxs-lookup"><span data-stu-id="605b6-138">If you have configured **max server memory,** increase its setting.</span></span>  
  
 <span data-ttu-id="605b6-139">Execute os comandos DBCC a seguir para liberar diversos caches de memória do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="605b6-139">Run the following DBCC commands to free several SQL Server memory caches.</span></span>  
  
-   <span data-ttu-id="605b6-140">DBCC FREESYSTEMCACHE</span><span class="sxs-lookup"><span data-stu-id="605b6-140">DBCC FREESYSTEMCACHE</span></span>  
  
-   <span data-ttu-id="605b6-141">DBCC FREESESSIONCACHE</span><span class="sxs-lookup"><span data-stu-id="605b6-141">DBCC FREESESSIONCACHE</span></span>  
  
-   <span data-ttu-id="605b6-142">DBCC FREEPROCCACHE</span><span class="sxs-lookup"><span data-stu-id="605b6-142">DBCC FREEPROCCACHE</span></span>  
  
 <span data-ttu-id="605b6-143">Se o problema persistir, será necessário aprofundar as investigações e possivelmente reduzir a carga de trabalho.</span><span class="sxs-lookup"><span data-stu-id="605b6-143">If the problem continues, you will need to investigate further and possibly reduce workload.</span></span>  
  
  
