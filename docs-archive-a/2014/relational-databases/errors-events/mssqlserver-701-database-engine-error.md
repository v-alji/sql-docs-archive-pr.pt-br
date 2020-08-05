---
title: MSSQLSERVER_701 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 701 (Database Engine error)
ms.assetid: 3b975000-63a1-43c2-a40f-89d0a8a36bef
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 542535223d3e394c72079092411add143de61545
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572086"
---
# <a name="mssqlserver_701"></a><span data-ttu-id="3dcf6-102">MSSQLSERVER_701</span><span class="sxs-lookup"><span data-stu-id="3dcf6-102">MSSQLSERVER_701</span></span>
    
## <a name="details"></a><span data-ttu-id="3dcf6-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="3dcf6-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3dcf6-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="3dcf6-104">Product Name</span></span>|<span data-ttu-id="3dcf6-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="3dcf6-105">SQL Server</span></span>|  
|<span data-ttu-id="3dcf6-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="3dcf6-106">Event ID</span></span>|<span data-ttu-id="3dcf6-107">701</span><span class="sxs-lookup"><span data-stu-id="3dcf6-107">701</span></span>|  
|<span data-ttu-id="3dcf6-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="3dcf6-108">Event Source</span></span>|<span data-ttu-id="3dcf6-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="3dcf6-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="3dcf6-110">Componente</span><span class="sxs-lookup"><span data-stu-id="3dcf6-110">Component</span></span>|<span data-ttu-id="3dcf6-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="3dcf6-111">SQLEngine</span></span>|  
|<span data-ttu-id="3dcf6-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="3dcf6-112">Symbolic Name</span></span>|<span data-ttu-id="3dcf6-113">NOSYSMEM</span><span class="sxs-lookup"><span data-stu-id="3dcf6-113">NOSYSMEM</span></span>|  
|<span data-ttu-id="3dcf6-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="3dcf6-114">Message Text</span></span>|<span data-ttu-id="3dcf6-115">Não há memória de sistema suficiente para executar essa consulta.</span><span class="sxs-lookup"><span data-stu-id="3dcf6-115">There is insufficient system memory to run this query.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="3dcf6-116">Explicação</span><span class="sxs-lookup"><span data-stu-id="3dcf6-116">Explanation</span></span>  
 <span data-ttu-id="3dcf6-117">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] falhou ao alocar memória suficiente para executar a consulta.</span><span class="sxs-lookup"><span data-stu-id="3dcf6-117">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has failed to allocate sufficient memory to run the query.</span></span> <span data-ttu-id="3dcf6-118">A falha pode ser causada por vários motivos, incluindo configurações do sistema operacional, disponibilidade de memória física ou limites de memória impostos à carga de trabalho atual.</span><span class="sxs-lookup"><span data-stu-id="3dcf6-118">This can be caused by a variety of reasons including operating system settings, physical memory availability, or memory limits on the current workload.</span></span> <span data-ttu-id="3dcf6-119">Na maioria dos casos, a transação com falha não é a causa do erro.</span><span class="sxs-lookup"><span data-stu-id="3dcf6-119">In most cases, the transaction that failed is not the cause of this error.</span></span>  
  
 <span data-ttu-id="3dcf6-120">As consultas de diagnósticos, como instruções DBCC, podem falhar porque o servidor não tem memória suficiente.</span><span class="sxs-lookup"><span data-stu-id="3dcf6-120">Diagnostic queries, such as DBCC statements, may fail because server the does not have sufficient memory.</span></span>  
  
 <span data-ttu-id="3dcf6-121">Tempo limite excedido ao aguardar recursos de memória para executar a consulta no pool de recursos 'default'.</span><span class="sxs-lookup"><span data-stu-id="3dcf6-121">A timeout occurred while waiting for memory resources to execute the query in the resource pool 'default'.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="3dcf6-122">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="3dcf6-122">User Action</span></span>  
 <span data-ttu-id="3dcf6-123">Se você não estiver usando o Administrador de Recursos, nós recomendamos que você verifique o estado de servidor geral e a carga ou verifique o pool de recursos ou as configurações do grupo de cargas de trabalho.</span><span class="sxs-lookup"><span data-stu-id="3dcf6-123">If you are not using Resource Governor, we recommend that you verify the overall server state and load, or check the resource pool or workload group settings.</span></span>  
  
 <span data-ttu-id="3dcf6-124">Esta lista descreve etapas gerais que ajudarão a corrigir erros de memória:</span><span class="sxs-lookup"><span data-stu-id="3dcf6-124">The following list outlines general steps that will help in troubleshooting memory errors:</span></span>  
  
1.  <span data-ttu-id="3dcf6-125">Verifique se outros aplicativos ou serviços estão consumindo memória neste servidor.</span><span class="sxs-lookup"><span data-stu-id="3dcf6-125">Verify whether other applications or services are consuming memory on this server.</span></span> <span data-ttu-id="3dcf6-126">Reconfigure os aplicativos ou serviços menos críticos de maneira que eles consumam menos memória.</span><span class="sxs-lookup"><span data-stu-id="3dcf6-126">Reconfigure less critical applications or services to consume less memory.</span></span>  
  
2.  <span data-ttu-id="3dcf6-127">Comece a coletar contadores do monitor de desempenho para [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **: Gerenciador de Buffer**, **SQL Server: Gerenciador de Memória**.</span><span class="sxs-lookup"><span data-stu-id="3dcf6-127">Start collecting performance monitor counters for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]**: Buffer Manager**, **SQL Server: Memory Manager**.</span></span>  
  
3.  <span data-ttu-id="3dcf6-128">Verifique os seguintes parâmetros de configuração da memória do SQL Server:</span><span class="sxs-lookup"><span data-stu-id="3dcf6-128">Check the following SQL Server memory configuration parameters:</span></span>  
  
    -   <span data-ttu-id="3dcf6-129">**memória máxima do servidor**</span><span class="sxs-lookup"><span data-stu-id="3dcf6-129">**max server memory**</span></span>  
  
    -   <span data-ttu-id="3dcf6-130">**memória mínima do servidor**</span><span class="sxs-lookup"><span data-stu-id="3dcf6-130">**min server memory**</span></span>  
  
    -   <span data-ttu-id="3dcf6-131">**memória mínima por consulta**</span><span class="sxs-lookup"><span data-stu-id="3dcf6-131">**min memory per query**</span></span>  
  
     <span data-ttu-id="3dcf6-132">Observe se há configurações incomuns.</span><span class="sxs-lookup"><span data-stu-id="3dcf6-132">Notice unusual settings.</span></span> <span data-ttu-id="3dcf6-133">Corrija-as conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="3dcf6-133">Correct them as necessary.</span></span> <span data-ttu-id="3dcf6-134">Considere mais requisitos de memória.</span><span class="sxs-lookup"><span data-stu-id="3dcf6-134">Account for increased memory requirements.</span></span> <span data-ttu-id="3dcf6-135">As configurações padrão estão listadas em "Definindo opções de configuração do servidor" nos Manuais Online do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="3dcf6-135">Default settings are listed in "Setting Server Configuration Options" in SQL Server Books Online.</span></span>  
  
4.  <span data-ttu-id="3dcf6-136">Observe o resultado do DBCC MEMORYSTATUS e a forma como ele se altera quando você vê essas mensagens de erro.</span><span class="sxs-lookup"><span data-stu-id="3dcf6-136">Observe DBCC MEMORYSTATUS output and the way it changes when you see these error messages.</span></span>  
  
5.  <span data-ttu-id="3dcf6-137">Verifique a carga de trabalho (por exemplo, o número de sessões simultâneas e de consultas em execução).</span><span class="sxs-lookup"><span data-stu-id="3dcf6-137">Check the workload (for example, number of concurrent sessions, currently executing queries).</span></span>  
  
 <span data-ttu-id="3dcf6-138">As seguintes ações podem disponibilizar mais memória para o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="3dcf6-138">The following actions may make more memory available to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="3dcf6-139">Se outros aplicativos além do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] estiverem consumindo recursos, experimente interrompê-los ou considere a possibilidade de executá-los em um servidor à parte.</span><span class="sxs-lookup"><span data-stu-id="3dcf6-139">If applications besides [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] are consuming resources, try stopping running these applications or consider running them on a separate server.</span></span> <span data-ttu-id="3dcf6-140">Isso eliminará a pressão de memória externa.</span><span class="sxs-lookup"><span data-stu-id="3dcf6-140">This will remove external memory pressure.</span></span>  
  
-   <span data-ttu-id="3dcf6-141">Se você tiver configurado a opção **memória máxima do servidor**, aumente sua configuração.</span><span class="sxs-lookup"><span data-stu-id="3dcf6-141">If you have configured **max server memory,** increase its setting.</span></span>  
  
 <span data-ttu-id="3dcf6-142">Execute os comandos DBCC a seguir para liberar diversos caches de memória do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3dcf6-142">Run the following DBCC commands to free several [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] memory caches.</span></span>  
  
-   <span data-ttu-id="3dcf6-143">DBCC FREESYSTEMCACHE</span><span class="sxs-lookup"><span data-stu-id="3dcf6-143">DBCC FREESYSTEMCACHE</span></span>  
  
-   <span data-ttu-id="3dcf6-144">DBCC FREESESSIONCACHE</span><span class="sxs-lookup"><span data-stu-id="3dcf6-144">DBCC FREESESSIONCACHE</span></span>  
  
-   <span data-ttu-id="3dcf6-145">DBCC FREEPROCCACHE</span><span class="sxs-lookup"><span data-stu-id="3dcf6-145">DBCC FREEPROCCACHE</span></span>  
  
 <span data-ttu-id="3dcf6-146">Se o problema persistir, será necessário aprofundar as investigações e possivelmente reduzir a carga de trabalho.</span><span class="sxs-lookup"><span data-stu-id="3dcf6-146">If the problem continues, you will need to investigate further and possibly reduce workload.</span></span>  
  
  
