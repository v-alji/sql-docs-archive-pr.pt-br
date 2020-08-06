---
title: MSSQLSERVER_4846 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 4846 (Database Engine error)
ms.assetid: a455e809-1883-4c7d-b3e3-835ee5bfe258
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 923137645aae72476fb4b2ae33f0cbbf3e81c2a3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679967"
---
# <a name="mssqlserver_4846"></a><span data-ttu-id="f06e3-102">MSSQLSERVER_4846</span><span class="sxs-lookup"><span data-stu-id="f06e3-102">MSSQLSERVER_4846</span></span>
    
## <a name="details"></a><span data-ttu-id="f06e3-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="f06e3-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f06e3-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="f06e3-104">Product Name</span></span>|<span data-ttu-id="f06e3-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="f06e3-105">SQL Server</span></span>|  
|<span data-ttu-id="f06e3-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="f06e3-106">Event ID</span></span>|<span data-ttu-id="f06e3-107">4846</span><span class="sxs-lookup"><span data-stu-id="f06e3-107">4846</span></span>|  
|<span data-ttu-id="f06e3-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="f06e3-108">Event Source</span></span>|<span data-ttu-id="f06e3-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="f06e3-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="f06e3-110">Componente</span><span class="sxs-lookup"><span data-stu-id="f06e3-110">Component</span></span>|<span data-ttu-id="f06e3-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="f06e3-111">SQLEngine</span></span>|  
|<span data-ttu-id="f06e3-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="f06e3-112">Symbolic Name</span></span>|<span data-ttu-id="f06e3-113">BULKPROV_MEMORY</span><span class="sxs-lookup"><span data-stu-id="f06e3-113">BULKPROV_MEMORY</span></span>|  
|<span data-ttu-id="f06e3-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="f06e3-114">Message Text</span></span>|<span data-ttu-id="f06e3-115">Falha no provedor de dados em massa ao alocar memória.</span><span class="sxs-lookup"><span data-stu-id="f06e3-115">The bulk data provider failed to allocate memory.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="f06e3-116">Explicação</span><span class="sxs-lookup"><span data-stu-id="f06e3-116">Explanation</span></span>  
 <span data-ttu-id="f06e3-117">Falha na alocação de memória.</span><span class="sxs-lookup"><span data-stu-id="f06e3-117">Memory allocation failed.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f06e3-118">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="f06e3-118">User Action</span></span>  
 <span data-ttu-id="f06e3-119">Siga estas etapas gerais para solucionar os erros de memória:</span><span class="sxs-lookup"><span data-stu-id="f06e3-119">Follow these general steps to troubleshoot memory errors:</span></span>  
  
1.  <span data-ttu-id="f06e3-120">Verifique se outros aplicativos ou serviços estão consumindo memória neste servidor.</span><span class="sxs-lookup"><span data-stu-id="f06e3-120">Verify whether other applications or services are consuming memory on this server.</span></span> <span data-ttu-id="f06e3-121">Reconfigure os aplicativos ou serviços menos críticos de maneira que eles consumam menos memória.</span><span class="sxs-lookup"><span data-stu-id="f06e3-121">Reconfigure less critical applications or services to consume less memory.</span></span>  
  
2.  <span data-ttu-id="f06e3-122">Comece a coletar contadores do monitor de desempenho para o **SQL Server: Gerenciador de Buffer**, **SQL Server: Gerenciador de Memória**.</span><span class="sxs-lookup"><span data-stu-id="f06e3-122">Start collecting performance monitor counters for **SQL Server: Buffer Manager**, **SQL Server: Memory Manager**.</span></span>  
  
3.  <span data-ttu-id="f06e3-123">Verifique os seguintes parâmetros de configuração da memória do SQL Server:</span><span class="sxs-lookup"><span data-stu-id="f06e3-123">Check the following SQL Server memory configuration parameters:</span></span>  
  
    -   <span data-ttu-id="f06e3-124">**memória máxima do servidor**</span><span class="sxs-lookup"><span data-stu-id="f06e3-124">**max server memory**</span></span>  
  
    -   <span data-ttu-id="f06e3-125">**memória mínima do servidor**</span><span class="sxs-lookup"><span data-stu-id="f06e3-125">**min server memory**</span></span>  
  
    -   <span data-ttu-id="f06e3-126">**memória mínima por consulta**</span><span class="sxs-lookup"><span data-stu-id="f06e3-126">**min memory per query**</span></span>  
  
     <span data-ttu-id="f06e3-127">Observe todas as configurações incomuns.</span><span class="sxs-lookup"><span data-stu-id="f06e3-127">Notice any unusual settings.</span></span> <span data-ttu-id="f06e3-128">Corrija-as conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="f06e3-128">Correct them as necessary.</span></span> <span data-ttu-id="f06e3-129">Considere os requisitos de memória para o [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f06e3-129">Account for memory requirements for [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="f06e3-130">As configurações padrão estão listadas em "Definindo opções de configuração do servidor" nos Manuais Online do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f06e3-130">Default settings are listed in "Setting Server Configuration Options" in SQL Server Books Online.</span></span>  
  
4.  <span data-ttu-id="f06e3-131">Observe o resultado do DBCC MEMORYSTATUS e a forma como ele se altera quando você vê essas mensagens de erro.</span><span class="sxs-lookup"><span data-stu-id="f06e3-131">Observe DBCC MEMORYSTATUS output and the way it changes when you see these error messages.</span></span>  
  
5.  <span data-ttu-id="f06e3-132">Verifique a carga de trabalho (por exemplo, o número de sessões simultâneas e de consultas em execução).</span><span class="sxs-lookup"><span data-stu-id="f06e3-132">Check the workload (for example, number of concurrent sessions, currently executing queries).</span></span>  
  
 <span data-ttu-id="f06e3-133">As seguintes ações podem disponibilizar mais memória para o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="f06e3-133">The following actions may make more memory available to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="f06e3-134">Se outros aplicativos além do SQL Server estiverem consumindo recursos, tente parar a execução desses aplicativos ou considere a possibilidade de executá-los em outro servidor.</span><span class="sxs-lookup"><span data-stu-id="f06e3-134">If applications besides SQL Server are consuming resources, try stopping running these applications or consider running them on a separate server.</span></span> <span data-ttu-id="f06e3-135">Isso eliminará a pressão de memória externa.</span><span class="sxs-lookup"><span data-stu-id="f06e3-135">This will remove external memory pressure.</span></span>  
  
-   <span data-ttu-id="f06e3-136">Se você tiver configurado a opção **memória máxima do servidor**, aumente sua configuração.</span><span class="sxs-lookup"><span data-stu-id="f06e3-136">If you have configured **max server memory,** increase its setting.</span></span>  
  
 <span data-ttu-id="f06e3-137">Execute os comandos DBCC a seguir para liberar diversos caches de memória do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f06e3-137">Run the following DBCC commands to free several [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] memory caches.</span></span>  
  
-   <span data-ttu-id="f06e3-138">DBCC FREESYSTEMCACHE</span><span class="sxs-lookup"><span data-stu-id="f06e3-138">DBCC FREESYSTEMCACHE</span></span>  
  
-   <span data-ttu-id="f06e3-139">DBCC FREESESSIONCACHE</span><span class="sxs-lookup"><span data-stu-id="f06e3-139">DBCC FREESESSIONCACHE</span></span>  
  
-   <span data-ttu-id="f06e3-140">DBCC FREEPROCCACHE</span><span class="sxs-lookup"><span data-stu-id="f06e3-140">DBCC FREEPROCCACHE</span></span>  
  
 <span data-ttu-id="f06e3-141">Se o problema persistir, será necessário aprofundar as investigações e possivelmente reduzir a carga de trabalho.</span><span class="sxs-lookup"><span data-stu-id="f06e3-141">If the problem continues, you will need to investigate further and possibly reduce workload.</span></span>  
  
  
