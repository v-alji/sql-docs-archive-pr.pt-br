---
title: MSSQLSERVER_1204 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 1204 (Database Engine error)
ms.assetid: de6ece78-79de-484d-9224-ca0f7645815f
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 7ca03c19552b88e391d2de053193a70531571ece
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573084"
---
# <a name="mssqlserver_1204"></a><span data-ttu-id="61c9c-102">MSSQLSERVER_1204</span><span class="sxs-lookup"><span data-stu-id="61c9c-102">MSSQLSERVER_1204</span></span>
    
## <a name="details"></a><span data-ttu-id="61c9c-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="61c9c-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="61c9c-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="61c9c-104">Product Name</span></span>|<span data-ttu-id="61c9c-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="61c9c-105">SQL Server</span></span>|  
|<span data-ttu-id="61c9c-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="61c9c-106">Event ID</span></span>|<span data-ttu-id="61c9c-107">1204</span><span class="sxs-lookup"><span data-stu-id="61c9c-107">1204</span></span>|  
|<span data-ttu-id="61c9c-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="61c9c-108">Event Source</span></span>|<span data-ttu-id="61c9c-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="61c9c-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="61c9c-110">Componente</span><span class="sxs-lookup"><span data-stu-id="61c9c-110">Component</span></span>|<span data-ttu-id="61c9c-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="61c9c-111">SQLEngine</span></span>|  
|<span data-ttu-id="61c9c-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="61c9c-112">Symbolic Name</span></span>|<span data-ttu-id="61c9c-113">LK_OUTOF</span><span class="sxs-lookup"><span data-stu-id="61c9c-113">LK_OUTOF</span></span>|  
|<span data-ttu-id="61c9c-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="61c9c-114">Message Text</span></span>|<span data-ttu-id="61c9c-115">A instância do Mecanismo de Banco de Dados do SQL Server não pode obter um recurso LOCK neste momento.</span><span class="sxs-lookup"><span data-stu-id="61c9c-115">The instance of the SQL Server Database Engine cannot obtain a LOCK resource at this time.</span></span> <span data-ttu-id="61c9c-116">Execute a instrução novamente quando houver menos usuários ativos.</span><span class="sxs-lookup"><span data-stu-id="61c9c-116">Rerun your statement when there are fewer active users.</span></span> <span data-ttu-id="61c9c-117">Peça ao administrador de banco de dados que verifique a configuração do bloqueio e da memória dessa instância ou as transações de longa execução.</span><span class="sxs-lookup"><span data-stu-id="61c9c-117">Ask the database administrator to check the lock and memory configuration for this instance, or to check for long-running transactions.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="61c9c-118">Explicação</span><span class="sxs-lookup"><span data-stu-id="61c9c-118">Explanation</span></span>  
 <span data-ttu-id="61c9c-119">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] não pôde obter um recurso de bloqueio.</span><span class="sxs-lookup"><span data-stu-id="61c9c-119">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cannot obtain a lock resource.</span></span> <span data-ttu-id="61c9c-120">Isso pode ter sido causado por qualquer uma das seguintes razões:</span><span class="sxs-lookup"><span data-stu-id="61c9c-120">This can be caused by either of the following reasons:</span></span>  
  
-   <span data-ttu-id="61c9c-121">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] não pode alocar mais memória do sistema operacional porque está sendo usado por outros processos ou porque o servidor está operando com a opção **memória máxima do servidor** configurada.</span><span class="sxs-lookup"><span data-stu-id="61c9c-121">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cannot allocate more memory from the operating system, either because other processes are using it, or because the server is operating with the **max server memory** option configured.</span></span>  
  
-   <span data-ttu-id="61c9c-122">O gerenciador de bloqueio não usará mais que 60 por cento da memória disponível para o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="61c9c-122">The lock manager will not use more than 60 percent of the memory available to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="61c9c-123">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="61c9c-123">User Action</span></span>  
 <span data-ttu-id="61c9c-124">Se você suspeitar que o SQL Server não pode alocar memória suficiente, tente o seguinte:</span><span class="sxs-lookup"><span data-stu-id="61c9c-124">If you suspect that SQL Server cannot allocate sufficient memory, try the following:</span></span>  
  
-   <span data-ttu-id="61c9c-125">Se outros aplicativos além do SQL Server estiverem consumindo recursos, tente interromper esses aplicativos ou considere executá-los em um servidor separado.</span><span class="sxs-lookup"><span data-stu-id="61c9c-125">If applications besides SQL Server are consuming resources, try stopping these applications or consider running them on a separate server.</span></span> <span data-ttu-id="61c9c-126">Isso irá liberar memória de outros processos para o SQL Server.</span><span class="sxs-lookup"><span data-stu-id="61c9c-126">This will remove release memory from other processes for SQL Server.</span></span>  
  
-   <span data-ttu-id="61c9c-127">Se você tiver configurado a memória máxima do servidor, aumente a definição da memória máxima do servidor.</span><span class="sxs-lookup"><span data-stu-id="61c9c-127">If you have configured max server memory, increase max server memory setting.</span></span>  
  
 <span data-ttu-id="61c9c-128">Se você suspeitar que o gerenciador de bloqueio usou o máximo de memória disponível, identifique a transação que está mantendo a maioria dos bloqueios e a conclua.</span><span class="sxs-lookup"><span data-stu-id="61c9c-128">If you suspect that the lock manager has used the maximum amount of available memory identify the transaction that is holding the most locks and terminate it.</span></span> <span data-ttu-id="61c9c-129">O script seguinte identificará a transação com a maioria de bloqueios:</span><span class="sxs-lookup"><span data-stu-id="61c9c-129">The following script will identify the transaction with the most locks:</span></span>  
  
```  
SELECT request_session_id, COUNT (*) num_locks  
FROM sys.dm_tran_locks  
GROUP BY request_session_id   
ORDER BY count (*) DESC  
```  
  
 <span data-ttu-id="61c9c-130">Identifique a ID da sessão mais elevada e encerre-a usando o comando KILL.</span><span class="sxs-lookup"><span data-stu-id="61c9c-130">Take the highest session id, and terminate it using the KILL command.</span></span>  
  
  
