---
title: Outros problemas de atualização de Mecanismo de Banco de Dados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Database Engine [SQL Server], upgrading
ms.assetid: 78a1d8e8-fa97-476f-8777-84617d145340
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: db496112fc975304bb2d7da9d9ea1c52e6dd8bec
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571771"
---
# <a name="other-database-engine-upgrade-issues"></a><span data-ttu-id="e69f8-102">Outros problemas de atualização do Mecanismo de Banco de Dados</span><span class="sxs-lookup"><span data-stu-id="e69f8-102">Other Database Engine Upgrade Issues</span></span>
  <span data-ttu-id="e69f8-103">Os problemas de atualização a seguir não podem ser detectados pela versão atual do Supervisor de Atualização.</span><span class="sxs-lookup"><span data-stu-id="e69f8-103">The following upgrade issues cannot be detected by the current version of Upgrade Advisor.</span></span> <span data-ttu-id="e69f8-104">Revise os problemas listados abaixo para avaliar o impacto deles em seus sistemas.</span><span class="sxs-lookup"><span data-stu-id="e69f8-104">Review the issues listed below to evaluate their potential impact to your systems.</span></span>  
  
## <a name="multiple-database-engine-deprecated-features"></a><span data-ttu-id="e69f8-105">Vários recursos do Mecanismo de Banco de Dados removidos</span><span class="sxs-lookup"><span data-stu-id="e69f8-105">Multiple Database Engine Deprecated Features</span></span>  
 <span data-ttu-id="e69f8-106">As seguintes opções e instruções [!INCLUDE[tsql](../../includes/tsql-md.md)] são removidas:</span><span class="sxs-lookup"><span data-stu-id="e69f8-106">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] statements or options are deprecated:</span></span>  
  
-   <span data-ttu-id="e69f8-107">Opções NO_LOG e TRUNCATE_ONLY do BACKUP LOG</span><span class="sxs-lookup"><span data-stu-id="e69f8-107">NO_LOG and TRUNCATE_ONLY options of BACKUP LOG</span></span>  
  
-   <span data-ttu-id="e69f8-108">BACKUP TRANSACTION</span><span class="sxs-lookup"><span data-stu-id="e69f8-108">BACKUP TRANSACTION</span></span>  
  
-   <span data-ttu-id="e69f8-109">RESTORE TRANSACTION</span><span class="sxs-lookup"><span data-stu-id="e69f8-109">RESTORE TRANSACTION</span></span>  
  
-   <span data-ttu-id="e69f8-110">DUMP</span><span class="sxs-lookup"><span data-stu-id="e69f8-110">DUMP</span></span>  
  
-   <span data-ttu-id="e69f8-111">LOAD</span><span class="sxs-lookup"><span data-stu-id="e69f8-111">LOAD</span></span>  
  
-   <span data-ttu-id="e69f8-112">DBCC CONCURRENCYVIOLATION</span><span class="sxs-lookup"><span data-stu-id="e69f8-112">DBCC CONCURRENCYVIOLATION</span></span>  
  
-   <span data-ttu-id="e69f8-113">sp_addalias</span><span class="sxs-lookup"><span data-stu-id="e69f8-113">sp_addalias</span></span>  
  
-   <span data-ttu-id="e69f8-114">sp_addgroup</span><span class="sxs-lookup"><span data-stu-id="e69f8-114">sp_addgroup</span></span>  
  
-   <span data-ttu-id="e69f8-115">sp_changegroup</span><span class="sxs-lookup"><span data-stu-id="e69f8-115">sp_changegroup</span></span>  
  
-   <span data-ttu-id="e69f8-116">sp_dropgroup</span><span class="sxs-lookup"><span data-stu-id="e69f8-116">sp_dropgroup</span></span>  
  
-   <span data-ttu-id="e69f8-117">sp_helpgroup</span><span class="sxs-lookup"><span data-stu-id="e69f8-117">sp_helpgroup</span></span>  
  
-   <span data-ttu-id="e69f8-118">syssegments</span><span class="sxs-lookup"><span data-stu-id="e69f8-118">syssegments</span></span>  
  
 <span data-ttu-id="e69f8-119">O uso do protocolo VIA para conectar-se ao [!INCLUDE[ssDE](../../includes/ssde-md.md)] é preterido.</span><span class="sxs-lookup"><span data-stu-id="e69f8-119">Use of the VIA protocol to connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)] is deprecated.</span></span>  
  
## <a name="new-data-types"></a><span data-ttu-id="e69f8-120">Novos tipos de dados</span><span class="sxs-lookup"><span data-stu-id="e69f8-120">New Data Types</span></span>  
 <span data-ttu-id="e69f8-121">Os itens indicados a seguir serão tipos de sistema reservados.</span><span class="sxs-lookup"><span data-stu-id="e69f8-121">The following will be reserved system types.</span></span> <span data-ttu-id="e69f8-122">Renomeie os tipos conflitantes definidos pelo usuário antes ou depois da atualização.</span><span class="sxs-lookup"><span data-stu-id="e69f8-122">Rename the existing conflicting user defined types either before or after upgrade.</span></span>  
  
-   <span data-ttu-id="e69f8-123">painel Geografia do app&#39;s selecionado</span><span class="sxs-lookup"><span data-stu-id="e69f8-123">Geography</span></span>  
  
-   <span data-ttu-id="e69f8-124">Geometria</span><span class="sxs-lookup"><span data-stu-id="e69f8-124">Geometry</span></span>  
  
-   <span data-ttu-id="e69f8-125">Datetime2</span><span class="sxs-lookup"><span data-stu-id="e69f8-125">Datetime2</span></span>  
  
-   <span data-ttu-id="e69f8-126">HierarchyID</span><span class="sxs-lookup"><span data-stu-id="e69f8-126">HierarchyID</span></span>  
  
## <a name="target-table-of-the-output-into-clause-cannot-have-any-defined-triggers"></a><span data-ttu-id="e69f8-127">Target Table da cláusula OUTPUT INTO não pode ter gatilhos definidos</span><span class="sxs-lookup"><span data-stu-id="e69f8-127">Target Table of the OUTPUT INTO Clause Cannot Have Any Defined Triggers</span></span>  
 <span data-ttu-id="e69f8-128">Não há suporte para a saída em uma tabela de destino quando a tabela tem nenhum gatilho habilitado.</span><span class="sxs-lookup"><span data-stu-id="e69f8-128">OUTPUT INTO a target table when the table has any enabled triggers is not supported.</span></span>  
  
## <a name="compile-time-error-for-udfs-when-the-target-of-an-output-into-clause-is-a-table"></a><span data-ttu-id="e69f8-129">Erro de tempo de compilação para UDFs quando o destino de uma cláusula OUTPUT INTO é uma tabela</span><span class="sxs-lookup"><span data-stu-id="e69f8-129">Compile Time Error for UDFs When the Target of an OUTPUT INTO Clause is a Table</span></span>  
 <span data-ttu-id="e69f8-130">As UDFs (funções definidas pelo usuário) não podem ser usadas para executar ações que modificam o estado do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="e69f8-130">User-defined functions (UDF) cannot be used to perform actions that modify the database state.</span></span> <span data-ttu-id="e69f8-131">Por exemplo, uma UDF não pode realizar ações DDL (CREATE/ALTER/DROP) ou DML (INSERT/UPDATE/DELETE) em nenhum objeto, exceto em variáveis de tabelas.</span><span class="sxs-lookup"><span data-stu-id="e69f8-131">For example, a UDF cannot perform any DDL (CREATE/ALTER/DROP) or DML (INSERT/UPDATE/DELETE) actions on any objects, except for table variables.</span></span>  
  
## <a name="merge-is-a-reserved-keyword"></a><span data-ttu-id="e69f8-132">MERGE é uma palavra-chave reservada</span><span class="sxs-lookup"><span data-stu-id="e69f8-132">MERGE is a Reserved Keyword</span></span>  
 <span data-ttu-id="e69f8-133">MERGE agora é uma palavra-chave completamente reservada.</span><span class="sxs-lookup"><span data-stu-id="e69f8-133">MERGE is now a fully-reserved keyword.</span></span> <span data-ttu-id="e69f8-134">Os aplicativos não podem mais ter objetos (tabelas, colunas, etc.) chamados MERGE.</span><span class="sxs-lookup"><span data-stu-id="e69f8-134">Applications can no longer have objects (table, column, etc.) called MERGE.</span></span>  
  
## <a name="rename-cdc-schema"></a><span data-ttu-id="e69f8-135">Renomear esquema CDC</span><span class="sxs-lookup"><span data-stu-id="e69f8-135">Rename CDC Schema</span></span>  
 <span data-ttu-id="e69f8-136">Há um nome de esquema chamado CDC.</span><span class="sxs-lookup"><span data-stu-id="e69f8-136">There is a schema name called CDC.</span></span> <span data-ttu-id="e69f8-137">Esse nome de esquema não poderá ser usado se a **captura de dados de alteração** estiver habilitada para o banco de dado.</span><span class="sxs-lookup"><span data-stu-id="e69f8-137">This schema name cannot be in used if **Change Data Capture** is enabled for the database.</span></span>  
  
 <span data-ttu-id="e69f8-138">Você deve remover o esquema CDC antes de habilitar a **captura de dados de alteração** para o banco de dado.</span><span class="sxs-lookup"><span data-stu-id="e69f8-138">You must drop the CDC schema before you enable **Change Data Capture** for the database.</span></span> <span data-ttu-id="e69f8-139">Isso pode ser feito antes ou depois da atualização.</span><span class="sxs-lookup"><span data-stu-id="e69f8-139">This step can be done before or after the upgrade.</span></span> <span data-ttu-id="e69f8-140">Para descartar o esquema, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="e69f8-140">To drop the schema, use the following steps:</span></span>  
  
1.  <span data-ttu-id="e69f8-141">Transfira os objetos de esquema CDC para um novo nome de esquema usando ALTER SCHEMA.</span><span class="sxs-lookup"><span data-stu-id="e69f8-141">Transfer the objects from CDC schema to a new schema name using ALTER SCHEMA.</span></span>  
  
2.  <span data-ttu-id="e69f8-142">Verifique as permissões para os objetos no novo esquema.</span><span class="sxs-lookup"><span data-stu-id="e69f8-142">Verify permissions for the objects in the new schema.</span></span>  
  
3.  <span data-ttu-id="e69f8-143">Faça as modificações necessárias no aplicativo.</span><span class="sxs-lookup"><span data-stu-id="e69f8-143">Make necessary modifications to the application.</span></span>  
  
4.  <span data-ttu-id="e69f8-144">Descarte o esquema CDC usando DROP SCHEMA.</span><span class="sxs-lookup"><span data-stu-id="e69f8-144">Drop the CDC schema using DROP SCHEMA.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e69f8-145">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e69f8-145">See Also</span></span>  
 [<span data-ttu-id="e69f8-146">Problemas de atualização do Mecanismo de Banco de Dados</span><span class="sxs-lookup"><span data-stu-id="e69f8-146">Database Engine Upgrade Issues</span></span>](../../../2014/sql-server/install/database-engine-upgrade-issues.md)  
  
  
