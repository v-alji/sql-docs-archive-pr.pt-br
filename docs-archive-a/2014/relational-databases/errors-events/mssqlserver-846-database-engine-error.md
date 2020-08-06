---
title: MSSQLSERVER_846 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 846 (Database Engine error)
ms.assetid: ccf367eb-06b0-42b8-b4d6-2b88f4a502d3
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 1b7cb6461d467090b03c246db5074ad203ce0ac3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575872"
---
# <a name="mssqlserver_846"></a><span data-ttu-id="c6706-102">MSSQLSERVER_846</span><span class="sxs-lookup"><span data-stu-id="c6706-102">MSSQLSERVER_846</span></span>
    
## <a name="details"></a><span data-ttu-id="c6706-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="c6706-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c6706-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="c6706-104">Product Name</span></span>|<span data-ttu-id="c6706-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="c6706-105">SQL Server</span></span>|  
|<span data-ttu-id="c6706-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="c6706-106">Event ID</span></span>|<span data-ttu-id="c6706-107">846</span><span class="sxs-lookup"><span data-stu-id="c6706-107">846</span></span>|  
|<span data-ttu-id="c6706-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="c6706-108">Event Source</span></span>|<span data-ttu-id="c6706-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="c6706-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="c6706-110">Componente</span><span class="sxs-lookup"><span data-stu-id="c6706-110">Component</span></span>|<span data-ttu-id="c6706-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="c6706-111">SQLEngine</span></span>|  
|<span data-ttu-id="c6706-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="c6706-112">Symbolic Name</span></span>|<span data-ttu-id="c6706-113">N/D</span><span class="sxs-lookup"><span data-stu-id="c6706-113">N/A</span></span>|  
|<span data-ttu-id="c6706-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="c6706-114">Message Text</span></span>|<span data-ttu-id="c6706-115">Tempo limite excedido ao aguardar por fechamento do buffer -- tipo %d, bp %p, página %d:%d, stat %#x, id do banco de dados %d; id da unidade de alocação: %I64d%ls, tarefa 0x%p: %d, tempo de espera %d, sinalizadores 0x%I64x, tarefa proprietária 0x%p.</span><span class="sxs-lookup"><span data-stu-id="c6706-115">A time-out occurred while waiting for buffer latch -- type %d, bp %p, page %d:%d, stat %#x, database id: %d, allocation unit Id: %I64d%ls, task 0x%p : %d, waittime %d, flags 0x%I64x, owning task 0x%p.</span></span> <span data-ttu-id="c6706-116">Sem continuação de espera.</span><span class="sxs-lookup"><span data-stu-id="c6706-116">Not continuing to wait.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="c6706-117">Explicação</span><span class="sxs-lookup"><span data-stu-id="c6706-117">Explanation</span></span>  
 <span data-ttu-id="c6706-118">Um computador pode parar de responder ou o fim do tempo limite pode ser alcançado ou outra interrupção das operações regulares pode acontecer ao mesmo tempo em que o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] grava erros de fechamento de buffer no log de erros do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c6706-118">A computer might stop responding, or a time-out or some other disruption of regular operations might occur at the same time that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] writes buffer latch errors to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log.</span></span>  
  
 <span data-ttu-id="c6706-119">Se o campo stat na mensagem tiver o valor de 0x04, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] está esperando por uma operação de E/S.</span><span class="sxs-lookup"><span data-stu-id="c6706-119">If the stat field in the message has the value of 0x04 on, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is waiting for an I/O operation.</span></span> <span data-ttu-id="c6706-120">Você também pode receber a mensagem [MSSQLSERVER_833](mssqlserver-833-database-engine-error.md) no log de erros do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c6706-120">You may also receive message [MSSQLSERVER_833](mssqlserver-833-database-engine-error.md) in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log.</span></span>  
  
 <span data-ttu-id="c6706-121">Se o campo stat na mensagem não tiver o valor de 0x04, existe grande contenção para uma página.</span><span class="sxs-lookup"><span data-stu-id="c6706-121">If the stat field in the message has the value 0x04 off, there is heavy contention for a page.</span></span> <span data-ttu-id="c6706-122">Se o objeto for uma página de dados, isto pode ser causado por um design de código ineficiente.</span><span class="sxs-lookup"><span data-stu-id="c6706-122">If the object is a data page, this can be caused by inefficient code design.</span></span> <span data-ttu-id="c6706-123">Se a página estiver sem dados, o erro pode ser causado por gargalos de servidor, como recursos de hardware insuficientes.</span><span class="sxs-lookup"><span data-stu-id="c6706-123">If the page is nondata, the error might be caused by server bottlenecks, such as insufficient hardware resources.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c6706-124">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="c6706-124">User Action</span></span>  
 <span data-ttu-id="c6706-125">Para solucionar este problema, dependendo de seu ambiente, o uso de um ou mais dos passos seguintes pode reduzir ou eliminar as mensagens de erro:</span><span class="sxs-lookup"><span data-stu-id="c6706-125">To work around this problem, depending on your environment, one or more of the following steps might reduce or eliminate the error messages:</span></span>  
  
-   <span data-ttu-id="c6706-126">Determine se você tem algum gargalo de hardware.</span><span class="sxs-lookup"><span data-stu-id="c6706-126">Determine whether you have any hardware bottlenecks.</span></span> <span data-ttu-id="c6706-127">Se necessário, atualize seu hardware para que ele possa oferecer suporte à configuração, à consulta e aos requisitos de carga de seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="c6706-127">If it is necessary, upgrade your hardware so that it can support the configuration, query, and load requirements of your environment.</span></span> <span data-ttu-id="c6706-128">Para obter mais informações sobre gargalos, consulte [Identify Bottlenecks](../performance/identify-bottlenecks.md) (Identificar gargalos).</span><span class="sxs-lookup"><span data-stu-id="c6706-128">For more information about bottlenecks, see [Identify Bottlenecks](../performance/identify-bottlenecks.md).</span></span>  
  
-   <span data-ttu-id="c6706-129">Verifique quaisquer erros registrados e execute quaisquer diagnósticos fornecidos por seu fornecedor de hardware.</span><span class="sxs-lookup"><span data-stu-id="c6706-129">Check for any logged errors and run any diagnostics provided by your hardware vendor.</span></span>  
  
-   <span data-ttu-id="c6706-130">Verifique se suas unidades de disco não estão compactadas.</span><span class="sxs-lookup"><span data-stu-id="c6706-130">Make sure that your disk drives are not compressed.</span></span> <span data-ttu-id="c6706-131">Não há suporte para o armazenamento de dados ou arquivos de log em unidades compactadas.</span><span class="sxs-lookup"><span data-stu-id="c6706-131">Storing data or log files on compressed drives is not supported.</span></span> <span data-ttu-id="c6706-132">Para obter mais informações sobre arquivos físicos, consulte [Database Files and Filegroups](../databases/database-files-and-filegroups.md) (Arquivos de banco de dados e grupos de arquivos).</span><span class="sxs-lookup"><span data-stu-id="c6706-132">For more information about physical files, see [Database Files and Filegroups](../databases/database-files-and-filegroups.md).</span></span>  
  
-   <span data-ttu-id="c6706-133">Veja se as mensagens de erro desaparecem quando você define as opções a seguir como desativadas:</span><span class="sxs-lookup"><span data-stu-id="c6706-133">See whether the error messages disappear when you set the following options to off:</span></span>  
  
    -   <span data-ttu-id="c6706-134">Opção de configuração de aumento de prioridade do SQL Server</span><span class="sxs-lookup"><span data-stu-id="c6706-134">SQL Server priority boost configuration option</span></span>  
  
    -   <span data-ttu-id="c6706-135">Opção lightweight pooling (modo fibra)</span><span class="sxs-lookup"><span data-stu-id="c6706-135">Lightweight pooling (fiber mode) option</span></span>  
  
    -   <span data-ttu-id="c6706-136">Opção set working set size</span><span class="sxs-lookup"><span data-stu-id="c6706-136">Set working set size option</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c6706-137">As configurações anteriores frequentemente podem ser contraproducentes se você alterar sua configuração padrão de OFF.</span><span class="sxs-lookup"><span data-stu-id="c6706-137">The previous settings can frequently be counter-productive if you change them from their default setting of OFF.</span></span> <span data-ttu-id="c6706-138">Para obter mais informações sobre as configurações, consulte [Server Configuration Options &#40;SQL Server&#41;](../../database-engine/configure-windows/server-configuration-options-sql-server.md) [Opções de configuração do servidor (SQL Server)].</span><span class="sxs-lookup"><span data-stu-id="c6706-138">For more information about the settings, see [Server Configuration Options &#40;SQL Server&#41;](../../database-engine/configure-windows/server-configuration-options-sql-server.md).</span></span>  
  
-   <span data-ttu-id="c6706-139">Ajuste as consultas para reduzir os recursos usados no sistema.</span><span class="sxs-lookup"><span data-stu-id="c6706-139">Tune queries to reduce resources used on the system.</span></span> <span data-ttu-id="c6706-140">O ajuste do desempenho ajudará a reduzir a tensão em um sistema e melhorar o tempo de resposta para consultas individuais.</span><span class="sxs-lookup"><span data-stu-id="c6706-140">Performance tuning will help reduce the stress on a system and improve response time for individual queries.</span></span>  
  
-   <span data-ttu-id="c6706-141">Defina a opção AUTO_SHRINK como OFF para reduzir a sobrecarga de mudanças para o tamanho do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="c6706-141">Set the AUTO_SHRINK option to OFF to reduce the overhead of changes to the database size.</span></span>  
  
-   <span data-ttu-id="c6706-142">Verifique se você definiu a opção FILEGROWTH para incrementos que sejam grandes o bastante para não serem frequentes.</span><span class="sxs-lookup"><span data-stu-id="c6706-142">Make sure that you set the FILEGROWTH option to increments that are large enough to be infrequent.</span></span> <span data-ttu-id="c6706-143">Agende um trabalho para verificar o espaço disponível nos bancos de dados e, depois, aumente o tamanho do banco de dados durante horas fora do pico.</span><span class="sxs-lookup"><span data-stu-id="c6706-143">Schedule a job to check the available space in the databases, and then increase the database size during nonpeak hours.</span></span>  
  
  
