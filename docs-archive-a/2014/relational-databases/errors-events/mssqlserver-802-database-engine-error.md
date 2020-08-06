---
title: MSSQLSERVER_802 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 802 (Database Engine error)
ms.assetid: 5892ed24-4dcb-4bf9-a8a4-a7ca898832d5
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 9edcdda1410d7651f7c7531ef98c64c85741f15a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87584159"
---
# <a name="mssqlserver_802"></a><span data-ttu-id="76451-102">MSSQLSERVER_802</span><span class="sxs-lookup"><span data-stu-id="76451-102">MSSQLSERVER_802</span></span>
    
## <a name="details"></a><span data-ttu-id="76451-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="76451-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="76451-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="76451-104">Product Name</span></span>|<span data-ttu-id="76451-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="76451-105">SQL Server</span></span>|  
|<span data-ttu-id="76451-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="76451-106">Event ID</span></span>|<span data-ttu-id="76451-107">802</span><span class="sxs-lookup"><span data-stu-id="76451-107">802</span></span>|  
|<span data-ttu-id="76451-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="76451-108">Event Source</span></span>|<span data-ttu-id="76451-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="76451-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="76451-110">Componente</span><span class="sxs-lookup"><span data-stu-id="76451-110">Component</span></span>|<span data-ttu-id="76451-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="76451-111">SQLEngine</span></span>|  
|<span data-ttu-id="76451-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="76451-112">Symbolic Name</span></span>|<span data-ttu-id="76451-113">NO_BUFS</span><span class="sxs-lookup"><span data-stu-id="76451-113">NO_BUFS</span></span>|  
|<span data-ttu-id="76451-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="76451-114">Message Text</span></span>|<span data-ttu-id="76451-115">Não há memória suficiente disponível no pool de buffers.</span><span class="sxs-lookup"><span data-stu-id="76451-115">There is insufficient memory available in the buffer pool.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="76451-116">Explicação</span><span class="sxs-lookup"><span data-stu-id="76451-116">Explanation</span></span>  
 <span data-ttu-id="76451-117">Isso ocorre quando o pool de buffers está cheio e não pode ficar maior.</span><span class="sxs-lookup"><span data-stu-id="76451-117">This is caused when the buffer pool is full and the buffer pool can not grow any larger.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="76451-118">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="76451-118">User Action</span></span>  
 <span data-ttu-id="76451-119">Esta lista descreve etapas gerais que ajudarão a corrigir erros de memória:</span><span class="sxs-lookup"><span data-stu-id="76451-119">The following list outlines general steps that will help in troubleshooting memory errors:</span></span>  
  
1.  <span data-ttu-id="76451-120">Verifique se outros aplicativos ou serviços estão consumindo memória neste servidor.</span><span class="sxs-lookup"><span data-stu-id="76451-120">Verify whether other applications or services are consuming memory on this server.</span></span> <span data-ttu-id="76451-121">Reconfigure os aplicativos ou serviços menos críticos de maneira que eles consumam menos memória.</span><span class="sxs-lookup"><span data-stu-id="76451-121">Reconfigure less critical applications or services to consume less memory.</span></span>  
  
2.  <span data-ttu-id="76451-122">Comece a coletar contadores do monitor de desempenho para [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **: Gerenciador de Buffer**, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **: Gerenciador de Memória**.</span><span class="sxs-lookup"><span data-stu-id="76451-122">Start collecting performance monitor counters for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]**: Buffer Manager**, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]**: Memory Manager**.</span></span>  
  
3.  <span data-ttu-id="76451-123">Verifique os seguintes parâmetros de configuração da memória do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="76451-123">Check the following [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] memory configuration parameters:</span></span>  
  
    -   <span data-ttu-id="76451-124">**memória máxima do servidor**</span><span class="sxs-lookup"><span data-stu-id="76451-124">**max server memory**</span></span>  
  
    -   <span data-ttu-id="76451-125">**memória mínima do servidor**</span><span class="sxs-lookup"><span data-stu-id="76451-125">**min server memory**</span></span>  
  
    -   <span data-ttu-id="76451-126">**memória mínima por consulta**</span><span class="sxs-lookup"><span data-stu-id="76451-126">**min memory per query**</span></span>  
  
     <span data-ttu-id="76451-127">Observe todas as configurações incomuns e corrija-as conforme suas necessidades.</span><span class="sxs-lookup"><span data-stu-id="76451-127">Notice any unusual settings and correct them as necessary.</span></span> <span data-ttu-id="76451-128">Considere os requisitos de memória aumentados para [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="76451-128">Account for increased memory requirements for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="76451-129">As configurações padrão estão listadas em "Definindo opções de configuração do servidor" nos Manuais Online do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="76451-129">Default settings are listed in "Setting Server Configuration Options" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
4.  <span data-ttu-id="76451-130">Observe o resultado do DBCC MEMORYSTATUS e a forma como ele se altera quando você vê essas mensagens de erro.</span><span class="sxs-lookup"><span data-stu-id="76451-130">Observe DBCC MEMORYSTATUS output and the way it changes when you see these error messages.</span></span>  
  
5.  <span data-ttu-id="76451-131">Verifique a carga de trabalho (o número de sessões simultâneas, consultas em execução atualmente).</span><span class="sxs-lookup"><span data-stu-id="76451-131">Check the workload (number of concurrent sessions, currently executing queries).</span></span>  
  
 <span data-ttu-id="76451-132">As seguintes ações podem disponibilizar mais memória para o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="76451-132">The following actions may make more memory available to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="76451-133">Se outros aplicativos além do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] estiverem consumindo recursos, tente parar esses aplicativos ou executá-los em um servidor separado.</span><span class="sxs-lookup"><span data-stu-id="76451-133">If applications besides [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] are consuming resources, try stopping these applications or running them on a separate server.</span></span>  
  
-   <span data-ttu-id="76451-134">Se você tiver configurado a **memória máxima do servidor**, aumente a configuração.</span><span class="sxs-lookup"><span data-stu-id="76451-134">If you have configured **max server memory,** increase the setting.</span></span>  
  
 <span data-ttu-id="76451-135">Execute os comandos DBCC a seguir para liberar diversos caches de memória do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="76451-135">Run the following DBCC commands to free several [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] memory caches.</span></span>  
  
-   <span data-ttu-id="76451-136">DBCC FREESYSTEMCACHE</span><span class="sxs-lookup"><span data-stu-id="76451-136">DBCC FREESYSTEMCACHE</span></span>  
  
-   <span data-ttu-id="76451-137">DBCC FREESESSIONCACHE</span><span class="sxs-lookup"><span data-stu-id="76451-137">DBCC FREESESSIONCACHE</span></span>  
  
-   <span data-ttu-id="76451-138">DBCC FREEPROCCACHE</span><span class="sxs-lookup"><span data-stu-id="76451-138">DBCC FREEPROCCACHE</span></span>  
  
 <span data-ttu-id="76451-139">Se o problema persistir, será necessário aprofundar as investigações e possivelmente reduzir a carga de trabalho.</span><span class="sxs-lookup"><span data-stu-id="76451-139">If the problem continues, you will need to investigate further and possibly reduce workload.</span></span>  
  
  
