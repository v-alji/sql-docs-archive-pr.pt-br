---
title: SQL Server, objeto Definível pelo usuário | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- User Settable object
- SQLServer:User Settable
ms.assetid: 633de3ef-533c-4f0c-9c7b-c105129d8e94
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 7243ab4767c8de93dccf4556f136a94b47554d3d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679311"
---
# <a name="sql-server-user-settable-object"></a><span data-ttu-id="35861-102">SQL Server, objeto User Settable</span><span class="sxs-lookup"><span data-stu-id="35861-102">SQL Server, User Settable Object</span></span>
  <span data-ttu-id="35861-103">O objeto **User Settable** no Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] permite criar instâncias de contador personalizadas.</span><span class="sxs-lookup"><span data-stu-id="35861-103">The **User Settable** object in Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] allows you to create custom counter instances.</span></span> <span data-ttu-id="35861-104">Use instâncias de contador personalizadas para monitorar aspectos do servidor que escapam aos contadores existentes, como componentes exclusivos de seu banco de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (por exemplo, o número de pedidos de clientes registrados em log ou o estoque de produtos).</span><span class="sxs-lookup"><span data-stu-id="35861-104">Use custom counter instances to monitor aspects of the server not monitored by existing counters, such as components unique to your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database (for example, the number of customer orders logged or the product inventory).</span></span>  
  
 <span data-ttu-id="35861-105">O objeto **Definível pelo Usuário** contém 10 instâncias do contador de consulta: **Contador de usuário 1** a **Contador do usuário 10**.</span><span class="sxs-lookup"><span data-stu-id="35861-105">The **User Settable** object contains 10 instances of the query counter: **User counter 1** through **User counter 10**.</span></span> <span data-ttu-id="35861-106">Esses contadores são mapeados para os procedimentos armazenados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de **sp_user_counter1** a **sp_user_counter10**.</span><span class="sxs-lookup"><span data-stu-id="35861-106">These counters map to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] stored procedures **sp_user_counter1** through **sp_user_counter10**.</span></span> <span data-ttu-id="35861-107">À medida que esses procedimentos armazenados são executados por aplicativos do usuário, os valores definidos por eles são exibidos no Monitor do Sistema.</span><span class="sxs-lookup"><span data-stu-id="35861-107">As these stored procedures are executed by user applications, the values set by the stored procedures are displayed in System Monitor.</span></span> <span data-ttu-id="35861-108">Um contador pode monitorar qualquer valor inteiro individual (por exemplo, um procedimento armazenado que conta quantos pedidos de um produto em particular ocorreram em um dia).</span><span class="sxs-lookup"><span data-stu-id="35861-108">A counter can monitor any single integer value (for example, a stored procedure that counts how many orders for a particular product have occurred in one day).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="35861-109">Os procedimentos armazenados de contadores do usuário não são sondados automaticamente pelo Monitor do Sistema.</span><span class="sxs-lookup"><span data-stu-id="35861-109">The user counter stored procedures are not polled automatically by System Monitor.</span></span> <span data-ttu-id="35861-110">Eles devem ser executados explicitamente por um aplicativo de usuário para obter os valores de contador a serem atualizados.</span><span class="sxs-lookup"><span data-stu-id="35861-110">They must be explicitly executed by a user application for the counter values to be updated.</span></span> <span data-ttu-id="35861-111">Use um gatilho para atualizar o valor do contador automaticamente.</span><span class="sxs-lookup"><span data-stu-id="35861-111">Use a trigger to update the value of the counter automatically.</span></span> <span data-ttu-id="35861-112">Por exemplo, para criar um contador que monitore o número de linhas em uma tabela, crie um gatilho INSERT e DELETE na tabela que executa a seguinte instrução: `SELECT COUNT(*) FROM table`.</span><span class="sxs-lookup"><span data-stu-id="35861-112">For example, to create a counter that monitors the number of rows in a table, create an INSERT and DELETE trigger on the table that executes the following statement: `SELECT COUNT(*) FROM table`.</span></span> <span data-ttu-id="35861-113">Sempre que o gatilho for acionado devido à ocorrência de operação INSERT ou DELETE na tabela, o contador do Monitor do Sistema será atualizado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="35861-113">Whenever the trigger is fired because of an INSERT or DELETE operation occurring on the table, the System Monitor counter is automatically updated.</span></span>  
  
 <span data-ttu-id="35861-114">Essa tabela descreve o objeto **User Settable** do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="35861-114">This table describes the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **User Settable** object.</span></span>  
  
|<span data-ttu-id="35861-115">Contadores do SQL Server definíveis pelo usuário</span><span class="sxs-lookup"><span data-stu-id="35861-115">SQL Server User Settable counters</span></span>|<span data-ttu-id="35861-116">Descrição</span><span class="sxs-lookup"><span data-stu-id="35861-116">Description</span></span>|  
|---------------------------------------|-----------------|  
|<span data-ttu-id="35861-117">**Consulta**</span><span class="sxs-lookup"><span data-stu-id="35861-117">**Query**</span></span>|<span data-ttu-id="35861-118">O objeto **User Settable** contém o contador da consulta.</span><span class="sxs-lookup"><span data-stu-id="35861-118">The **User Settable** object contains the query counter.</span></span> <span data-ttu-id="35861-119">Os usuários configuram os **Contadores do usuário** dentro do objeto de consulta.</span><span class="sxs-lookup"><span data-stu-id="35861-119">Users configure the **User counters** within the query object.</span></span>|  
  
 <span data-ttu-id="35861-120">Essa tabela descreve as **instâncias** do contador de **Consultas** .</span><span class="sxs-lookup"><span data-stu-id="35861-120">This table describes the **instances** of the **Query** counter.</span></span>  
  
|<span data-ttu-id="35861-121">Instâncias do contador de consultas</span><span class="sxs-lookup"><span data-stu-id="35861-121">Query counter instances</span></span>|<span data-ttu-id="35861-122">Descrição</span><span class="sxs-lookup"><span data-stu-id="35861-122">Description</span></span>|  
|-----------------------------|-----------------|  
|<span data-ttu-id="35861-123">**Contador do usuário 1**</span><span class="sxs-lookup"><span data-stu-id="35861-123">**User counter 1**</span></span>|<span data-ttu-id="35861-124">Definido usando **sp_user_counter1**.</span><span class="sxs-lookup"><span data-stu-id="35861-124">Defined using **sp_user_counter1**.</span></span>|  
|<span data-ttu-id="35861-125">**Contador do usuário 2**</span><span class="sxs-lookup"><span data-stu-id="35861-125">**User counter 2**</span></span>|<span data-ttu-id="35861-126">Definido usando **sp_user_counter2**.</span><span class="sxs-lookup"><span data-stu-id="35861-126">Defined using **sp_user_counter2**.</span></span>|  
|<span data-ttu-id="35861-127">**Contador do usuário 3**</span><span class="sxs-lookup"><span data-stu-id="35861-127">**User counter 3**</span></span>|<span data-ttu-id="35861-128">Definido usando **sp_user_counter3**.</span><span class="sxs-lookup"><span data-stu-id="35861-128">Defined using **sp_user_counter3**.</span></span>|  
|<span data-ttu-id="35861-129">...</span><span class="sxs-lookup"><span data-stu-id="35861-129">...</span></span>||  
|<span data-ttu-id="35861-130">**Contador do usuário 10**</span><span class="sxs-lookup"><span data-stu-id="35861-130">**User counter 10**</span></span>|<span data-ttu-id="35861-131">Definido usando **sp_user_counter10**.</span><span class="sxs-lookup"><span data-stu-id="35861-131">Defined using **sp_user_counter10**.</span></span>|  
  
 <span data-ttu-id="35861-132">Para usar os procedimentos armazenados de contador do usuário, execute-os a partir de seu próprio aplicativo com um único parâmetro de inteiro representando o novo valor do contador.</span><span class="sxs-lookup"><span data-stu-id="35861-132">To make use of the user counter stored procedures, execute them from your own application with a single integer parameter representing the new value for the counter.</span></span> <span data-ttu-id="35861-133">Por exemplo, para definir o **Contador do usuário 1** com o valor 10, execute essa instrução Transact-SQL:</span><span class="sxs-lookup"><span data-stu-id="35861-133">For example, to set **User counter 1** to the value 10, execute this Transact-SQL statement:</span></span>  
  
```  
EXECUTE sp_user_counter1 10  
```  
  
 <span data-ttu-id="35861-134">Os procedimentos armazenados de contador do usuário podem ser chamados a partir de qualquer lugar onde normalmente podem ser chamados os outros procedimentos armazenados, como os seus próprios procedimentos armazenados.</span><span class="sxs-lookup"><span data-stu-id="35861-134">The user counter stored procedures can be called from anywhere other stored procedures can be called, such as your own stored procedures.</span></span> <span data-ttu-id="35861-135">Por exemplo, é possível criar o seguinte procedimento armazenado para contar o número de conexões e tentativas de conexão desde que foi iniciada a instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="35861-135">For example, you can create the following stored procedure to count the number of connections and attempted connections since an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] was started:</span></span>  
  
```  
DROP PROC My_Proc  
GO  
CREATE PROC My_Proc  
AS   
   EXECUTE sp_user_counter1 @@CONNECTIONS  
GO  
```  
  
 <span data-ttu-id="35861-136">A função @[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] retorna o número de conexões ou tentativas de conexão desde o início de uma instância de @CONNECTIONS.</span><span class="sxs-lookup"><span data-stu-id="35861-136">The @@CONNECTIONS function returns the number of connections or attempted connections since an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] started.</span></span> <span data-ttu-id="35861-137">Esse valor é passado ao procedimento armazenado **sp_user_counter1** como parâmetro.</span><span class="sxs-lookup"><span data-stu-id="35861-137">This value is passed to the **sp_user_counter1** stored procedure as the parameter.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="35861-138">Torne as consultas definidas nos procedimentos armazenados de contador do usuário o mais simples possível.</span><span class="sxs-lookup"><span data-stu-id="35861-138">Make the queries defined in the user counter stored procedures as simple as possible.</span></span> <span data-ttu-id="35861-139">Consultas que consomem muita memória e realizam operações substanciais de classificação ou hash ou grandes quantidades de E/S são de execução dispendiosa e podem influir no desempenho.</span><span class="sxs-lookup"><span data-stu-id="35861-139">Memory-intensive queries that perform substantial sort or hash operations or queries that perform large amounts of I/O are expensive to execute and can impact performance.</span></span>  
  
## <a name="permissions"></a><span data-ttu-id="35861-140">Permissões</span><span class="sxs-lookup"><span data-stu-id="35861-140">Permissions</span></span>  
 <span data-ttu-id="35861-141">**sp_user_counter** está disponível para todos os usuários, mas pode ser restringido para qualquer contador de consultas.</span><span class="sxs-lookup"><span data-stu-id="35861-141">**sp_user_counter** is available for all users but can be restricted for any query counter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35861-142">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="35861-142">See Also</span></span>  
 [<span data-ttu-id="35861-143">Monitorar o uso de recursos &#40;Monitor do Sistema&#41;</span><span class="sxs-lookup"><span data-stu-id="35861-143">Monitor Resource Usage &#40;System Monitor&#41;</span></span>](monitor-resource-usage-system-monitor.md)  
  
  
