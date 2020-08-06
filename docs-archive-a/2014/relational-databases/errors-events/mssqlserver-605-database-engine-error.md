---
title: MSSQLSERVER_605 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 605 (Database Engine error)
ms.assetid: d8d3a22e-1ff8-48a4-891f-4c8619437e24
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e196fba84af492b25e798629d3e808b1bf22857e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581829"
---
# <a name="mssqlserver_605"></a><span data-ttu-id="4f328-102">MSSQLSERVER_605</span><span class="sxs-lookup"><span data-stu-id="4f328-102">MSSQLSERVER_605</span></span>
    
## <a name="details"></a><span data-ttu-id="4f328-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="4f328-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4f328-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="4f328-104">Product Name</span></span>|<span data-ttu-id="4f328-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="4f328-105">SQL Server</span></span>|  
|<span data-ttu-id="4f328-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="4f328-106">Event ID</span></span>|<span data-ttu-id="4f328-107">605</span><span class="sxs-lookup"><span data-stu-id="4f328-107">605</span></span>|  
|<span data-ttu-id="4f328-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="4f328-108">Event Source</span></span>|<span data-ttu-id="4f328-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="4f328-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="4f328-110">Componente</span><span class="sxs-lookup"><span data-stu-id="4f328-110">Component</span></span>|<span data-ttu-id="4f328-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="4f328-111">SQLEngine</span></span>|  
|<span data-ttu-id="4f328-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="4f328-112">Symbolic Name</span></span>|<span data-ttu-id="4f328-113">WRONGPAGE</span><span class="sxs-lookup"><span data-stu-id="4f328-113">WRONGPAGE</span></span>|  
|<span data-ttu-id="4f328-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="4f328-114">Message Text</span></span>|<span data-ttu-id="4f328-115">Falha na tentativa de buscar a página lógica %S_PGID no banco de dados %d.</span><span class="sxs-lookup"><span data-stu-id="4f328-115">Attempt to fetch logical page %S_PGID in database %d failed.</span></span> <span data-ttu-id="4f328-116">Ela pertence à unidade de alocação %I64d não a %I64d.</span><span class="sxs-lookup"><span data-stu-id="4f328-116">It belongs to allocation unit %I64d not to %I64d.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="4f328-117">Explicação</span><span class="sxs-lookup"><span data-stu-id="4f328-117">Explanation</span></span>  
 <span data-ttu-id="4f328-118">Esse erro geralmente indica um dano na página ou na alocação do banco de dados especificado.</span><span class="sxs-lookup"><span data-stu-id="4f328-118">This error generally signifies page or allocation corruption in the specified database.</span></span> <span data-ttu-id="4f328-119">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] detecta danos quando lê páginas que pertencem a uma tabela, seguindo os vínculos de página ou usando a página IAM.</span><span class="sxs-lookup"><span data-stu-id="4f328-119">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] detects corruption when reading pages belonging to a table either by following the page linkages or by using the Index Allocation Map (IAM).</span></span> <span data-ttu-id="4f328-120">Todas as páginas alocadas para uma tabela devem pertencer a uma das unidades de alocação associadas à tabela.</span><span class="sxs-lookup"><span data-stu-id="4f328-120">All pages allocated to a table must belong to one of the allocation units associated with the table.</span></span> <span data-ttu-id="4f328-121">Se a ID da unidade de alocação contida no cabeçalho da página não corresponder a uma ID de unidade de alocação associada à tabela, essa exceção será gerada.</span><span class="sxs-lookup"><span data-stu-id="4f328-121">If the allocation unit ID contained in the page header does not match an allocation unit ID associated with the table, this exception is raised.</span></span> <span data-ttu-id="4f328-122">A primeira ID de unidade de alocação listada na mensagem de erro é a ID presente no cabeçalho da página, e o segundo valor da unidade de alocação é a ID associada com a tabela.</span><span class="sxs-lookup"><span data-stu-id="4f328-122">The first allocation unit ID listed in the error message is the ID present in the page header, and the second allocation unit value is the ID associated with the table.</span></span>  
  
 <span data-ttu-id="4f328-123">**Erros de dados corrompidos**</span><span class="sxs-lookup"><span data-stu-id="4f328-123">**Data Corruption Errors**</span></span>  
  
 <span data-ttu-id="4f328-124">Um nível de gravidade 21 indica a possibilidade de os dados estarem corrompidos.</span><span class="sxs-lookup"><span data-stu-id="4f328-124">A severity level of 21 indicates potential data corruption.</span></span> <span data-ttu-id="4f328-125">As possíveis causas são uma cadeia de páginas danificada, uma página IAM corrompida ou uma entrada inválida na exibição de catálogo [sys.objects](/sql/relational-databases/system-catalog-views/sys-objects-transact-sql) do objeto em questão.</span><span class="sxs-lookup"><span data-stu-id="4f328-125">Possible causes are a damaged page chain, a corrupt IAM, or an invalid entry in the [sys.objects](/sql/relational-databases/system-catalog-views/sys-objects-transact-sql) catalog view for that object.</span></span> <span data-ttu-id="4f328-126">Esses erros geralmente são causados por falha de hardware ou do driver de dispositivo do disco.</span><span class="sxs-lookup"><span data-stu-id="4f328-126">These errors are often caused by hardware or disk device driver failure.</span></span>  
  
 <span data-ttu-id="4f328-127">**Erros transitórios**</span><span class="sxs-lookup"><span data-stu-id="4f328-127">**Transient Errors**</span></span>  
  
 <span data-ttu-id="4f328-128">Um nível de gravidade 12 indica um possível erro transitório; ou seja, ele ocorre no cache e não indica dano nos dados armazenados em disco.</span><span class="sxs-lookup"><span data-stu-id="4f328-128">A severity level of 12 indicates a potential transient error; that is, it occurs in the cache and does not indicate damage to data on disk.</span></span> <span data-ttu-id="4f328-129">Os erros transitórios 605 podem ser causados pelas seguintes condições:</span><span class="sxs-lookup"><span data-stu-id="4f328-129">Transient 605 errors can be caused by the following conditions:</span></span>  
  
-   <span data-ttu-id="4f328-130">O sistema operacional prematuramente notifica o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de que uma operação de E/S foi concluída; a mensagem de erro é exibida mesmo que os dados não estejam corrompidos.</span><span class="sxs-lookup"><span data-stu-id="4f328-130">The operating system prematurely notifies [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that an I/O operation has completed; the error message is displayed even though no actual data corruption exists.</span></span>  
  
 <span data-ttu-id="4f328-131">Executar uma consulta com a dica de otimização NOLOCK ou definir o nível de isolamento da transação como READ UNCOMMITTED.</span><span class="sxs-lookup"><span data-stu-id="4f328-131">Running a query with the Optimizer hint NOLOCK or setting the transaction isolation level to READ UNCOMMITTED.</span></span> <span data-ttu-id="4f328-132">Quando uma consulta que não usa NOLOCK ou READ UNCOMMITTED tenta ler dados que estão sendo movidos ou alterados por outro usuário, ocorre um erro 605.</span><span class="sxs-lookup"><span data-stu-id="4f328-132">When a query that is using NOLOCK or READ UNCOMMITTED tries to read data that is being moved or changed by another user, a 605 error occurs.</span></span> <span data-ttu-id="4f328-133">Para verificar se é um erro 605 transitório, reexecute a consulta posteriormente.</span><span class="sxs-lookup"><span data-stu-id="4f328-133">To verify that it is a transient 605 error, rerun the query later.</span></span> <span data-ttu-id="4f328-134">Para saber mais, confira o artigo [235880](https://support.microsoft.com/kb/235880/en-us) da base de dados: "Você recebe uma mensagem de erro 'Erro 605' quando executa uma consulta com a dica de otimização NOLOCK ou define o nível de isolamento da transação como READ UNCOMMITTED no SQL Server."</span><span class="sxs-lookup"><span data-stu-id="4f328-134">For more information, see this KB article [235880](https://support.microsoft.com/kb/235880/en-us): "You receive an "Error 605" error message when you run a query with the optimizer hint NOLOCK or you set the transaction isolation level to READ UNCOMMITTED in SQL Server."</span></span>  
  
 <span data-ttu-id="4f328-135">Em geral, se o erro ocorreu durante o acesso aos dados, mas as operações DBCC CHECKDB subsequentes foram concluídas com êxito, provavelmente o erro 605 era transitório.</span><span class="sxs-lookup"><span data-stu-id="4f328-135">In general, if the error occurs during data access but subsequent DBCC CHECKDB operations complete without error, the 605 error was probably transient.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="4f328-136">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="4f328-136">User Action</span></span>  
 <span data-ttu-id="4f328-137">Se o erro 605 não é transitório, o problema é grave e deve ser corrigido por meio das seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="4f328-137">If the 605 error is not transient, the problem is severe and must be corrected by performing the following tasks:</span></span>  
  
1.  <span data-ttu-id="4f328-138">Identifique as tabelas associadas com as unidades de alocação especificadas na mensagem executando a consulta a seguir.</span><span class="sxs-lookup"><span data-stu-id="4f328-138">Identify the tables associated with the allocation units specified in the message by running the following query.</span></span> <span data-ttu-id="4f328-139">Substitua `allocation_unit_id` pelas unidades de alocação especificadas na mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="4f328-139">Replace `allocation_unit_id` with the allocation units specified in the error message.</span></span>  
  
     <span data-ttu-id="4f328-140">USE`database_name`;</span><span class="sxs-lookup"><span data-stu-id="4f328-140">USE`database_name`;</span></span>  
  
     <span data-ttu-id="4f328-141">GO</span><span class="sxs-lookup"><span data-stu-id="4f328-141">GO</span></span>  
  
     <span data-ttu-id="4f328-142">SELECT au.allocation_unit_id, OBJECT_NAME(p.object_id) AS table_name, fg.name AS filegroup_name,</span><span class="sxs-lookup"><span data-stu-id="4f328-142">SELECT au.allocation_unit_id, OBJECT_NAME(p.object_id) AS table_name, fg.name AS filegroup_name,</span></span>  
  
     <span data-ttu-id="4f328-143">au.type_desc AS allocation_type, au.data_pages, partition_number</span><span class="sxs-lookup"><span data-stu-id="4f328-143">au.type_desc AS allocation_type, au.data_pages, partition_number</span></span>  
  
     <span data-ttu-id="4f328-144">FROM sys.allocation_units AS au</span><span class="sxs-lookup"><span data-stu-id="4f328-144">FROM sys.allocation_units AS au</span></span>  
  
     <span data-ttu-id="4f328-145">JOIN sys.partitions AS p ON au.container_id = p.partition_id</span><span class="sxs-lookup"><span data-stu-id="4f328-145">JOIN sys.partitions AS p ON au.container_id = p.partition_id</span></span>  
  
     <span data-ttu-id="4f328-146">JOIN sys.filegroups AS fg ON fg.data_space_id = au.data_space_id</span><span class="sxs-lookup"><span data-stu-id="4f328-146">JOIN sys.filegroups AS fg ON fg.data_space_id = au.data_space_id</span></span>  
  
     <span data-ttu-id="4f328-147">WHERE au.allocation_unit_id = `allocation_unit_id` OR au.allocation_unit_id = `allocation_unit_id`</span><span class="sxs-lookup"><span data-stu-id="4f328-147">WHERE au.allocation_unit_id = `allocation_unit_id` OR au.allocation_unit_id = `allocation_unit_id`</span></span>  
  
     <span data-ttu-id="4f328-148">ORDER BY au.allocation_unit_id;</span><span class="sxs-lookup"><span data-stu-id="4f328-148">ORDER BY au.allocation_unit_id;</span></span>  
  
     <span data-ttu-id="4f328-149">GO</span><span class="sxs-lookup"><span data-stu-id="4f328-149">GO</span></span>  
  
2.  <span data-ttu-id="4f328-150">Execute DBCC CHECKTABLE sem uma cláusula REPAIR na tabela associada com a segunda ID de unidade de alocação especificada na mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="4f328-150">Execute DBCC CHECKTABLE without a REPAIR clause on the table associated with the second allocation unit ID specified in the error message.</span></span>  
  
3.  <span data-ttu-id="4f328-151">Execute DBCC CHECKDB sem uma cláusula REPAIR o mais rápido possível para determinar toda a extensão do dano causado no banco de dados inteiro.</span><span class="sxs-lookup"><span data-stu-id="4f328-151">Execute DBCC CHECKDB without a REPAIR clause as soon as possible to determine the full extent of the corruption in the entire database.</span></span>  
  
4.  <span data-ttu-id="4f328-152">Verifique no log de erros se existem outros erros que costumam acompanhar um erro 605 e examine o Log de Eventos do Windows para identificar problemas de sistema ou relacionados ao hardware.</span><span class="sxs-lookup"><span data-stu-id="4f328-152">Check the error log for other errors that often accompany a 605 error and examine the Windows Event Log for any system or hardware related issues.</span></span> <span data-ttu-id="4f328-153">Corrija quaisquer problemas relacionados a hardware existentes nos logs.</span><span class="sxs-lookup"><span data-stu-id="4f328-153">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="4f328-154">Se o problema não estiver relacionado ao hardware, execute uma das seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="4f328-154">If the problem is not hardware related, perform one of the following tasks:</span></span>  
  
1.  <span data-ttu-id="4f328-155">Restaure o banco de dados de um backup limpo conhecido.</span><span class="sxs-lookup"><span data-stu-id="4f328-155">Restore the database from a known clean backup.</span></span> <span data-ttu-id="4f328-156">Use o recurso de backup de restauração de página para restaurar somente as páginas danificadas.</span><span class="sxs-lookup"><span data-stu-id="4f328-156">You can leverage the page restore backup feature to restore just the damaged pages.</span></span>  
  
2.  <span data-ttu-id="4f328-157">Execute DBCC CHECKDB com a cláusula REPAIR recomendada pela operação DBCC CHECKDB executada na etapa 3 para reparar o dano.</span><span class="sxs-lookup"><span data-stu-id="4f328-157">Run DBCC CHECKDB with the REPAIR clause recommended by the DBCC CHECKDB operation performed in step 3 to repair the corruption.</span></span> <span data-ttu-id="4f328-158">Se a execução de DBCC CHECKDB com uma das cláusulas REPAIR não corrigir o problema, contate seu provedor de suporte.</span><span class="sxs-lookup"><span data-stu-id="4f328-158">If running DBCC CHECKDB with one of the REPAIR clauses does not correct the problem, contact your primary support provider.</span></span> <span data-ttu-id="4f328-159">Revise a saída gerada por DBCC CHECKDB.</span><span class="sxs-lookup"><span data-stu-id="4f328-159">Have the output from DBCC CHECKDB available for review.</span></span>  
  
    > [!CAUTION]  
    >  <span data-ttu-id="4f328-160">Se você não tiver certeza do efeito de DBCC CHECKDB com uma cláusula REPAIR sobre seus dados, contate o provedor de suporte antes de executar essa instrução.</span><span class="sxs-lookup"><span data-stu-id="4f328-160">If you are not sure what effect DBCC CHECKDB with a REPAIR clause has on your data, contact your primary support provider before running this statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f328-161">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="4f328-161">See Also</span></span>  
 [<span data-ttu-id="4f328-162">DBCC CHECKTABLE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="4f328-162">DBCC CHECKTABLE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/database-console-commands/dbcc-checktable-transact-sql)  
  
  
