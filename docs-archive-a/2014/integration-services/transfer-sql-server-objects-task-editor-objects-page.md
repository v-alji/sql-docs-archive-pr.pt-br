---
title: Editor da tarefa transferir objetos do SQL Server (página objetos) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.transfersqlserverobjects.objects.f1
helpviewer_keywords:
- Transfer SQL Server Objects Task Editor
ms.assetid: 8cc09118-70ac-4013-8308-d87f8411ca0c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7038939b02d17b2449a374be51f7f9fa42eae7d8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681754"
---
# <a name="transfer-sql-server-objects-task-editor-objects-page"></a><span data-ttu-id="77af0-102">Editor da Tarefa Transferir Objetos do SQL Server (página Objetos)</span><span class="sxs-lookup"><span data-stu-id="77af0-102">Transfer SQL Server Objects Task Editor (Objects Page)</span></span>
  <span data-ttu-id="77af0-103">Use a página **Objetos** da caixa de diálogo **Editor da Tarefa Transferir Objetos do SQL Server** para especificar propriedades para copiar um ou mais objetos do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] de uma instância do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] para outra.</span><span class="sxs-lookup"><span data-stu-id="77af0-103">Use the **Objects** page of the **Transfer SQL Server Objects Task Editor** dialog box to specify properties for copying one or more [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] objects from one instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] to another.</span></span> <span data-ttu-id="77af0-104">Tabelas, exibições, procedimentos armazenados e funções definidas pelo usuário são alguns exemplos de objetos do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] que você pode copiar.</span><span class="sxs-lookup"><span data-stu-id="77af0-104">Tables, views, stored procedures, and user-defined functions are a few examples of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] objects that you can copy.</span></span> <span data-ttu-id="77af0-105">Para obter mais informações sobre essa tarefa, consulte [Transfer SQL Server Objects Task](control-flow/transfer-sql-server-objects-task.md).</span><span class="sxs-lookup"><span data-stu-id="77af0-105">For more information about this task, see [Transfer SQL Server Objects Task](control-flow/transfer-sql-server-objects-task.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="77af0-106">O usuário que criar a tarefa Transferir Objetos do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] deve ter permissões suficientes nos objetos do servidor de origem para selecioná-los para cópia, bem como permissão para acessar o banco de dados do servidor de destino no qual os objetos serão transferidos.</span><span class="sxs-lookup"><span data-stu-id="77af0-106">The user who creates the Transfer [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Objects task must have sufficient permissions on the source server objects to select them for copying, and permission to access the destination server database where the objects will be transferred.</span></span>  
  
## <a name="static-options"></a><span data-ttu-id="77af0-107">Opções estáticas</span><span class="sxs-lookup"><span data-stu-id="77af0-107">Static Options</span></span>  
 <span data-ttu-id="77af0-108">**SourceConnection**</span><span class="sxs-lookup"><span data-stu-id="77af0-108">**SourceConnection**</span></span>  
 <span data-ttu-id="77af0-109">Selecione um gerenciador de conexões SMO na lista ou clique em **\<New connection...>** para criar uma conexão com o servidor de origem.</span><span class="sxs-lookup"><span data-stu-id="77af0-109">Select a SMO connection manager in the list, or click **\<New connection...>** to create a new connection to the source server.</span></span>  
  
 <span data-ttu-id="77af0-110">**SourceDatabase**</span><span class="sxs-lookup"><span data-stu-id="77af0-110">**SourceDatabase**</span></span>  
 <span data-ttu-id="77af0-111">Selecione o banco de dados no servidor de origem do qual serão copiados os objetos.</span><span class="sxs-lookup"><span data-stu-id="77af0-111">Select a database on the source server from which objects will be copied.</span></span>  
  
 <span data-ttu-id="77af0-112">**DestinationConnection**</span><span class="sxs-lookup"><span data-stu-id="77af0-112">**DestinationConnection**</span></span>  
 <span data-ttu-id="77af0-113">Selecione um gerenciador de conexões SMO na lista ou clique em **\<New connection...>** para criar uma conexão com o servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="77af0-113">Select a SMO connection manager in the list, or click **\<New connection...>** to create a new connection to the destination server.</span></span>  
  
 <span data-ttu-id="77af0-114">**DestinationDatabase**</span><span class="sxs-lookup"><span data-stu-id="77af0-114">**DestinationDatabase**</span></span>  
 <span data-ttu-id="77af0-115">Selecione o banco de dados no servidor de destino para o qual serão copiados os objetos.</span><span class="sxs-lookup"><span data-stu-id="77af0-115">Select a database on the destination server to which objects will be copied.</span></span>  
  
 <span data-ttu-id="77af0-116">**DropObjectsFirst**</span><span class="sxs-lookup"><span data-stu-id="77af0-116">**DropObjectsFirst**</span></span>  
 <span data-ttu-id="77af0-117">Selecione se os objetos selecionados serão primeiro descartados no servidor de destino, antes de serem copiados.</span><span class="sxs-lookup"><span data-stu-id="77af0-117">Select whether the selected objects will be dropped first on the destination server before copying.</span></span>  
  
 <span data-ttu-id="77af0-118">**IncludeExtendedProperties**</span><span class="sxs-lookup"><span data-stu-id="77af0-118">**IncludeExtendedProperties**</span></span>  
 <span data-ttu-id="77af0-119">Selecione se as propriedades estendidas devem ser incluídas quando os objetos forem copiados da origem para o servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="77af0-119">Select whether extended properties will be included when objects are copied from the source to the destination server.</span></span>  
  
 <span data-ttu-id="77af0-120">**CopyData**</span><span class="sxs-lookup"><span data-stu-id="77af0-120">**CopyData**</span></span>  
 <span data-ttu-id="77af0-121">Selecione se os dados devem ser incluídos quando os objetos forem copiados da origem para o servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="77af0-121">Select whether data will be included when objects are copied from the source to the destination server.</span></span>  
  
 <span data-ttu-id="77af0-122">**ExistingData**</span><span class="sxs-lookup"><span data-stu-id="77af0-122">**ExistingData**</span></span>  
 <span data-ttu-id="77af0-123">Especifique como os dados serão copiados para o servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="77af0-123">Specify how data will be copied to the destination server.</span></span> <span data-ttu-id="77af0-124">As opções desta propriedade estão listadas na seguinte tabela:</span><span class="sxs-lookup"><span data-stu-id="77af0-124">This property has the options listed in the following table:</span></span>  
  
|<span data-ttu-id="77af0-125">Valor</span><span class="sxs-lookup"><span data-stu-id="77af0-125">Value</span></span>|<span data-ttu-id="77af0-126">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="77af0-126">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="77af0-127">**Substituir**</span><span class="sxs-lookup"><span data-stu-id="77af0-127">**Replace**</span></span>|<span data-ttu-id="77af0-128">Os dados no servidor de destino serão substituídos.</span><span class="sxs-lookup"><span data-stu-id="77af0-128">Data on the destination server will be overwritten.</span></span>|  
|<span data-ttu-id="77af0-129">**Acrescentar**</span><span class="sxs-lookup"><span data-stu-id="77af0-129">**Append**</span></span>|<span data-ttu-id="77af0-130">Os dados copiados do servidor de origem serão anexados aos dados existentes no servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="77af0-130">Data copied from the source server will be appended to existing data on the destination server.</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="77af0-131">A opção **ExistingData** só ficará disponível quando **CopyData** for definido como **True**.</span><span class="sxs-lookup"><span data-stu-id="77af0-131">The **ExistingData** option is only available when **CopyData** is set to **True**.</span></span>  
  
 <span data-ttu-id="77af0-132">**CopySchema**</span><span class="sxs-lookup"><span data-stu-id="77af0-132">**CopySchema**</span></span>  
 <span data-ttu-id="77af0-133">Selecione se o esquema deve ser copiado durante a tarefa Transferir Objetos do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="77af0-133">Select whether the schema is copied during the Transfer [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Objects task.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="77af0-134">**CopySchema** só está disponível para o [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="77af0-134">**CopySchema** is only available for [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="77af0-135">**UseCollation**</span><span class="sxs-lookup"><span data-stu-id="77af0-135">**UseCollation**</span></span>  
 <span data-ttu-id="77af0-136">Selecione se a transferência de objetos deve incluir a ordenação especificada no servidor de origem.</span><span class="sxs-lookup"><span data-stu-id="77af0-136">Select whether the transfer of objects should include the collation specified on the source server.</span></span>  
  
 <span data-ttu-id="77af0-137">**IncludeDependentObjects**</span><span class="sxs-lookup"><span data-stu-id="77af0-137">**IncludeDependentObjects**</span></span>  
 <span data-ttu-id="77af0-138">Selecione se a cópia dos objetos selecionados deve ser agrupada em cascata para incluir outros objetos que dependem deles para serem copiados.</span><span class="sxs-lookup"><span data-stu-id="77af0-138">Select whether copying the selected objects will cascade to include other objects that depend on the objects selected for copying.</span></span>  
  
 <span data-ttu-id="77af0-139">**CopyAllObjects**</span><span class="sxs-lookup"><span data-stu-id="77af0-139">**CopyAllObjects**</span></span>  
 <span data-ttu-id="77af0-140">Selecione se a tarefa deve copiar todos os objetos no banco de dados de origem especificado ou apenas objetos selecionados.</span><span class="sxs-lookup"><span data-stu-id="77af0-140">Select whether the task will copy all objects in the specified source database or only selected objects.</span></span>  <span data-ttu-id="77af0-141">Ao definir essa opção como Falso será possível selecionar os objetos a transferir e exibir as opções dinâmicas na seção **CopyAllObjects**.</span><span class="sxs-lookup"><span data-stu-id="77af0-141">Setting this option to False gives you the option to select the objects to transfer, and displays the dynamic options in the section, **CopyAllObjects**.</span></span>  
  
 <span data-ttu-id="77af0-142">**ObjectsToCopy**</span><span class="sxs-lookup"><span data-stu-id="77af0-142">**ObjectsToCopy**</span></span>  
 <span data-ttu-id="77af0-143">Expanda **ObjectsToCopy** para especificar quais objetos devem ser copiados do banco de dados de origem para o banco de dados de destino.</span><span class="sxs-lookup"><span data-stu-id="77af0-143">Expand **ObjectsToCopy** to specify which objects should be copied from the source database to the destination database.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="77af0-144">**ObjectsToCopy** só ficará disponível quando **CopyAllObjects** for definido como **False**.</span><span class="sxs-lookup"><span data-stu-id="77af0-144">**ObjectsToCopy** is only available when **CopyAllObjects** is set to **False**.</span></span>  
  
 <span data-ttu-id="77af0-145">As opções para copiar os seguintes tipos de objeto têm suporte apenas no [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="77af0-145">The options to copy the following types of objects are supported only on [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]:</span></span>  
  
 <span data-ttu-id="77af0-146">Assemblies</span><span class="sxs-lookup"><span data-stu-id="77af0-146">Assemblies</span></span>  
  
 <span data-ttu-id="77af0-147">Funções de partição</span><span class="sxs-lookup"><span data-stu-id="77af0-147">Partition functions</span></span>  
  
 <span data-ttu-id="77af0-148">Esquemas de partição</span><span class="sxs-lookup"><span data-stu-id="77af0-148">Partition schemes</span></span>  
  
 <span data-ttu-id="77af0-149">Esquemas</span><span class="sxs-lookup"><span data-stu-id="77af0-149">Schemas</span></span>  
  
 <span data-ttu-id="77af0-150">Agregações definidas pelo usuário</span><span class="sxs-lookup"><span data-stu-id="77af0-150">User-defined aggregates</span></span>  
  
 <span data-ttu-id="77af0-151">Tipos definidos pelo usuário</span><span class="sxs-lookup"><span data-stu-id="77af0-151">User-defined types</span></span>  
  
 <span data-ttu-id="77af0-152">Coleções de esquemas XML</span><span class="sxs-lookup"><span data-stu-id="77af0-152">XML schema collections</span></span>  
  
 <span data-ttu-id="77af0-153">**CopyDatabaseUsers**</span><span class="sxs-lookup"><span data-stu-id="77af0-153">**CopyDatabaseUsers**</span></span>  
 <span data-ttu-id="77af0-154">Especifique se os usuários do banco de dados devem ser incluídos na transferência.</span><span class="sxs-lookup"><span data-stu-id="77af0-154">Specify whether database users should be included in the transfer.</span></span>  
  
 <span data-ttu-id="77af0-155">**CopyDatabaseRoles**</span><span class="sxs-lookup"><span data-stu-id="77af0-155">**CopyDatabaseRoles**</span></span>  
 <span data-ttu-id="77af0-156">Especifique se as funções do banco de dados devem ser incluídas na transferência.</span><span class="sxs-lookup"><span data-stu-id="77af0-156">Specify whether database roles should be included in the transfer.</span></span>  
  
 <span data-ttu-id="77af0-157">**CopySqlServerLogins**</span><span class="sxs-lookup"><span data-stu-id="77af0-157">**CopySqlServerLogins**</span></span>  
 <span data-ttu-id="77af0-158">Especifique se os logons do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] devem ser incluídos na transferência.</span><span class="sxs-lookup"><span data-stu-id="77af0-158">Specify whether [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] logins should be included in the transfer.</span></span>  
  
 <span data-ttu-id="77af0-159">**CopyObjectLevelPermissions**</span><span class="sxs-lookup"><span data-stu-id="77af0-159">**CopyObjectLevelPermissions**</span></span>  
 <span data-ttu-id="77af0-160">Especifique se as permissões de nível de objeto devem ser incluídas na transferência.</span><span class="sxs-lookup"><span data-stu-id="77af0-160">Specify whether object-level permissions should be included in the transfer.</span></span>  
  
 <span data-ttu-id="77af0-161">**CopyIndexes**</span><span class="sxs-lookup"><span data-stu-id="77af0-161">**CopyIndexes**</span></span>  
 <span data-ttu-id="77af0-162">Especifique se os índices devem ser incluídos na transferência.</span><span class="sxs-lookup"><span data-stu-id="77af0-162">Specify whether indexes should be included in the transfer.</span></span>  
  
 <span data-ttu-id="77af0-163">**CopyTriggers**</span><span class="sxs-lookup"><span data-stu-id="77af0-163">**CopyTriggers**</span></span>  
 <span data-ttu-id="77af0-164">Especifique se os gatilhos devem ser incluídos na transferência.</span><span class="sxs-lookup"><span data-stu-id="77af0-164">Specify whether triggers should be included in the transfer.</span></span>  
  
 <span data-ttu-id="77af0-165">**CopyFullTextIndexes**</span><span class="sxs-lookup"><span data-stu-id="77af0-165">**CopyFullTextIndexes**</span></span>  
 <span data-ttu-id="77af0-166">Especifique se os índices de texto completo devem ser incluídos na transferência.</span><span class="sxs-lookup"><span data-stu-id="77af0-166">Specify whether full-text indexes should be included in the transfer.</span></span>  
  
 <span data-ttu-id="77af0-167">**CopyPrimaryKeys**</span><span class="sxs-lookup"><span data-stu-id="77af0-167">**CopyPrimaryKeys**</span></span>  
 <span data-ttu-id="77af0-168">Especifique se as chaves primárias devem ser incluídas na transferência.</span><span class="sxs-lookup"><span data-stu-id="77af0-168">Specify whether primary keys should be included in the transfer.</span></span>  
  
 <span data-ttu-id="77af0-169">**CopyForeignKeys**</span><span class="sxs-lookup"><span data-stu-id="77af0-169">**CopyForeignKeys**</span></span>  
 <span data-ttu-id="77af0-170">Especifique se as chaves estrangeiras devem ser incluídas na transferência.</span><span class="sxs-lookup"><span data-stu-id="77af0-170">Specify whether foreign keys should be included in the transfer.</span></span>  
  
 <span data-ttu-id="77af0-171">**GenerateScriptsInUnicode**</span><span class="sxs-lookup"><span data-stu-id="77af0-171">**GenerateScriptsInUnicode**</span></span>  
 <span data-ttu-id="77af0-172">Especifique se os scripts de transferência gerados estão em formato Unicode.</span><span class="sxs-lookup"><span data-stu-id="77af0-172">Specify whether the generated transfer scripts are in Unicode format.</span></span>  
  
## <a name="dynamic-options"></a><span data-ttu-id="77af0-173">Opções dinâmicas</span><span class="sxs-lookup"><span data-stu-id="77af0-173">Dynamic Options</span></span>  
  
### <a name="copyallobjects--false"></a><span data-ttu-id="77af0-174">CopyAllObjects = False</span><span class="sxs-lookup"><span data-stu-id="77af0-174">CopyAllObjects = False</span></span>  
 <span data-ttu-id="77af0-175">**CopyAllTables**</span><span class="sxs-lookup"><span data-stu-id="77af0-175">**CopyAllTables**</span></span>  
 <span data-ttu-id="77af0-176">Selecione se a tarefa deve copiar todas as tabelas no banco de dados de origem especificado ou apenas as tabelas selecionadas.</span><span class="sxs-lookup"><span data-stu-id="77af0-176">Select whether the task will copy all tables in the specified source database or only the selected tables.</span></span>  
  
 <span data-ttu-id="77af0-177">**TablesList**</span><span class="sxs-lookup"><span data-stu-id="77af0-177">**TablesList**</span></span>  
 <span data-ttu-id="77af0-178">Clique para abrir a caixa de diálogo **Selecionar Tabelas** .</span><span class="sxs-lookup"><span data-stu-id="77af0-178">Click to open the **Select Tables** dialog box.</span></span>  
  
 <span data-ttu-id="77af0-179">**CopyAllViews**</span><span class="sxs-lookup"><span data-stu-id="77af0-179">**CopyAllViews**</span></span>  
 <span data-ttu-id="77af0-180">Selecione se a tarefa deve copiar todas as exibições no banco de dados de origem especificado ou apenas as exibições selecionadas.</span><span class="sxs-lookup"><span data-stu-id="77af0-180">Select whether the task will copy all views in the specified source database or only the selected views.</span></span>  
  
 <span data-ttu-id="77af0-181">**ViewsList**</span><span class="sxs-lookup"><span data-stu-id="77af0-181">**ViewsList**</span></span>  
 <span data-ttu-id="77af0-182">Clique para abrir a caixa de diálogo **Selecionar Exibições** .</span><span class="sxs-lookup"><span data-stu-id="77af0-182">Click to open the **Select Views** dialog box.</span></span>  
  
 <span data-ttu-id="77af0-183">**CopyAllStoredProcedures**</span><span class="sxs-lookup"><span data-stu-id="77af0-183">**CopyAllStoredProcedures**</span></span>  
 <span data-ttu-id="77af0-184">Selecione se a tarefa deve copiar todos os procedimentos armazenados definidos pelo usuário no banco de dados de origem especificado ou apenas os procedimentos selecionados.</span><span class="sxs-lookup"><span data-stu-id="77af0-184">Select whether the task will copy all user-defined stored procedures in the specified source database or only the selected procedures.</span></span>  
  
 <span data-ttu-id="77af0-185">**StoredProceduresList**</span><span class="sxs-lookup"><span data-stu-id="77af0-185">**StoredProceduresList**</span></span>  
 <span data-ttu-id="77af0-186">Clique para abrir a caixa de diálogo **Selecionar Procedimentos Armazenados** .</span><span class="sxs-lookup"><span data-stu-id="77af0-186">Click to open the **Select Stored Procedures** dialog box.</span></span>  
  
 <span data-ttu-id="77af0-187">**CopyAllUserDefinedFunctions**</span><span class="sxs-lookup"><span data-stu-id="77af0-187">**CopyAllUserDefinedFunctions**</span></span>  
 <span data-ttu-id="77af0-188">Selecione se a tarefa deve copiar todas as funções definidas pelo usuário no banco de dados de origem especificado ou apenas as funções selecionadas.</span><span class="sxs-lookup"><span data-stu-id="77af0-188">Select whether the task will copy all user-defined functions in the specified source database or only the selected UDFs.</span></span>  
  
 <span data-ttu-id="77af0-189">**UserDefinedFunctionsList**</span><span class="sxs-lookup"><span data-stu-id="77af0-189">**UserDefinedFunctionsList**</span></span>  
 <span data-ttu-id="77af0-190">Clique para abrir a caixa de diálogo **Selecionar Funções Definidas pelo Usuário** .</span><span class="sxs-lookup"><span data-stu-id="77af0-190">Click to open the **Select User Defined Functions** dialog box.</span></span>  
  
 <span data-ttu-id="77af0-191">**CopyAllDefaults**</span><span class="sxs-lookup"><span data-stu-id="77af0-191">**CopyAllDefaults**</span></span>  
 <span data-ttu-id="77af0-192">Selecione se a tarefa deve copiar todos os padrões no banco de dados de origem especificado ou apenas os padrões selecionados.</span><span class="sxs-lookup"><span data-stu-id="77af0-192">Select whether the task will copy all defaults in the specified source database or only the selected defaults.</span></span>  
  
 <span data-ttu-id="77af0-193">**DefaultsList**</span><span class="sxs-lookup"><span data-stu-id="77af0-193">**DefaultsList**</span></span>  
 <span data-ttu-id="77af0-194">Clique para abrir a caixa de diálogo **Selecionar Padrões** .</span><span class="sxs-lookup"><span data-stu-id="77af0-194">Click to open the **Select Defaults** dialog box.</span></span>  
  
 <span data-ttu-id="77af0-195">**CopyAllUserDefinedDataTypes**</span><span class="sxs-lookup"><span data-stu-id="77af0-195">**CopyAllUserDefinedDataTypes**</span></span>  
 <span data-ttu-id="77af0-196">Selecione se a tarefa deve copiar todos os tipos de dados definidos pelo usuário no banco de dados de origem especificado ou apenas os tipos de dados selecionados.</span><span class="sxs-lookup"><span data-stu-id="77af0-196">Select whether the task will copy all user-defined data types in the specified source database or only the selected user-defined data types.</span></span>  
  
 <span data-ttu-id="77af0-197">**UserDefinedDataTypesList**</span><span class="sxs-lookup"><span data-stu-id="77af0-197">**UserDefinedDataTypesList**</span></span>  
 <span data-ttu-id="77af0-198">Clique para abrir a caixa de diálogo **Selecionar Tipos de Dados Definidos pelo Usuário** .</span><span class="sxs-lookup"><span data-stu-id="77af0-198">Click to open the **Select User-Defined Data Types** dialog box.</span></span>  
  
 <span data-ttu-id="77af0-199">**CopyAllPartitionFunctions**</span><span class="sxs-lookup"><span data-stu-id="77af0-199">**CopyAllPartitionFunctions**</span></span>  
 <span data-ttu-id="77af0-200">Selecione se a tarefa deve copiar todas as funções de partição definidas pelo usuário no banco de dados de origem especificado ou apenas as funções de partição selecionadas.</span><span class="sxs-lookup"><span data-stu-id="77af0-200">Select whether the task will copy all user-defined partition functions in the specified source database or only the selected partition functions.</span></span> <span data-ttu-id="77af0-201">Com suporte apenas no [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="77af0-201">Supported only on [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="77af0-202">**PartitionFunctionsList**</span><span class="sxs-lookup"><span data-stu-id="77af0-202">**PartitionFunctionsList**</span></span>  
 <span data-ttu-id="77af0-203">Clique para abrir a caixa de diálogo **Selecionar Funções de Partição** .</span><span class="sxs-lookup"><span data-stu-id="77af0-203">Click to open the **Select Partition Functions** dialog box.</span></span>  
  
 <span data-ttu-id="77af0-204">**CopyAllPartitionSchemes**</span><span class="sxs-lookup"><span data-stu-id="77af0-204">**CopyAllPartitionSchemes**</span></span>  
 <span data-ttu-id="77af0-205">Selecione se a tarefa deve copiar todos os esquemas de partição definidos pelo usuário no banco de dados de origem especificado ou apenas os esquemas de partição selecionados.</span><span class="sxs-lookup"><span data-stu-id="77af0-205">Select whether the task will copy all partition schemes in the specified source database or only the selected partition schemes.</span></span> <span data-ttu-id="77af0-206">Com suporte apenas no [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="77af0-206">Supported only on [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="77af0-207">**PartitionSchemesList**</span><span class="sxs-lookup"><span data-stu-id="77af0-207">**PartitionSchemesList**</span></span>  
 <span data-ttu-id="77af0-208">Clique para abrir a caixa de diálogo **Selecionar Esquemas de Partição** .</span><span class="sxs-lookup"><span data-stu-id="77af0-208">Click to open the **Select Partition Schemes** dialog box.</span></span>  
  
 <span data-ttu-id="77af0-209">**CopyAllSchemas**</span><span class="sxs-lookup"><span data-stu-id="77af0-209">**CopyAllSchemas**</span></span>  
 <span data-ttu-id="77af0-210">Selecione se a tarefa deve copiar todos os esquemas no banco de dados de origem especificado ou apenas os esquemas selecionados.</span><span class="sxs-lookup"><span data-stu-id="77af0-210">Select whether the task will copy all schemas in the specified source database or only the selected schemas.</span></span> <span data-ttu-id="77af0-211">Com suporte apenas no [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="77af0-211">Supported only on [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="77af0-212">**SchemasList**</span><span class="sxs-lookup"><span data-stu-id="77af0-212">**SchemasList**</span></span>  
 <span data-ttu-id="77af0-213">Clique para abrir a caixa de diálogo **Selecionar Esquemas** .</span><span class="sxs-lookup"><span data-stu-id="77af0-213">Click to open the **Select Schemas** dialog box.</span></span>  
  
 <span data-ttu-id="77af0-214">**CopyAllSqlAssemblies**</span><span class="sxs-lookup"><span data-stu-id="77af0-214">**CopyAllSqlAssemblies**</span></span>  
 <span data-ttu-id="77af0-215">Selecione se a tarefa deve copiar todos os assemblies do SQL no banco de dados de origem especificado ou apenas os assemblies do SQL selecionados.</span><span class="sxs-lookup"><span data-stu-id="77af0-215">Select whether the task will copy all SQL assemblies in the specified source database or only the selected SQL assemblies.</span></span> <span data-ttu-id="77af0-216">Com suporte apenas no [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="77af0-216">Supported only on [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="77af0-217">**SqlAssembliesList**</span><span class="sxs-lookup"><span data-stu-id="77af0-217">**SqlAssembliesList**</span></span>  
 <span data-ttu-id="77af0-218">Clique para abrir a caixa de diálogo **Selecionar Assemblies do SQL** .</span><span class="sxs-lookup"><span data-stu-id="77af0-218">Click to open the **Select SQL Assemblies** dialog box.</span></span>  
  
 <span data-ttu-id="77af0-219">**CopyAllUserDefinedAggregates**</span><span class="sxs-lookup"><span data-stu-id="77af0-219">**CopyAllUserDefinedAggregates**</span></span>  
 <span data-ttu-id="77af0-220">Selecione se a tarefa deve copiar todas as agregações definidas pelo usuário no banco de dados de origem especificado ou apenas as agregações selecionadas.</span><span class="sxs-lookup"><span data-stu-id="77af0-220">Select whether the task will copy all user-defined aggregates in the specified source database or only the selected user-defined aggregates.</span></span> <span data-ttu-id="77af0-221">Com suporte apenas no [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="77af0-221">Supported only on [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="77af0-222">**UserDefinedAggregatesList**</span><span class="sxs-lookup"><span data-stu-id="77af0-222">**UserDefinedAggregatesList**</span></span>  
 <span data-ttu-id="77af0-223">Clique para abrir a caixa de diálogo **Selecionar Agregações Definidas pelo Usuário** .</span><span class="sxs-lookup"><span data-stu-id="77af0-223">Click to open the **Select User-Defined Aggregates** dialog box.</span></span>  
  
 <span data-ttu-id="77af0-224">**CopyAllUserDefinedTypes**</span><span class="sxs-lookup"><span data-stu-id="77af0-224">**CopyAllUserDefinedTypes**</span></span>  
 <span data-ttu-id="77af0-225">Selecione se a tarefa deve copiar todos os tipos definidos pelo usuário no banco de dados de origem especificado ou apenas os tipos selecionados.</span><span class="sxs-lookup"><span data-stu-id="77af0-225">Select whether the task will copy all user-defined types in the specified source database or only the selected UDTs.</span></span> <span data-ttu-id="77af0-226">Com suporte apenas no [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="77af0-226">Supported only on [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="77af0-227">**UserDefinedTypes**</span><span class="sxs-lookup"><span data-stu-id="77af0-227">**UserDefinedTypes**</span></span>  
 <span data-ttu-id="77af0-228">Clique para abrir a caixa de diálogo **Selecionar Tipos Definidos pelo Usuário** .</span><span class="sxs-lookup"><span data-stu-id="77af0-228">Click to open the **Select User-Defined Types** dialog box.</span></span>  
  
 <span data-ttu-id="77af0-229">**CopyAllXmlSchemaCollections**</span><span class="sxs-lookup"><span data-stu-id="77af0-229">**CopyAllXmlSchemaCollections**</span></span>  
 <span data-ttu-id="77af0-230">Selecione se a tarefa deve copiar todas as coleções de Esquemas XML no banco de dados de origem especificado ou apenas as coleções de esquemas XML selecionadas.</span><span class="sxs-lookup"><span data-stu-id="77af0-230">Select whether the task will copy all XML Schema collections in the specified source database or only the selected XML schema collections.</span></span> <span data-ttu-id="77af0-231">Com suporte apenas no [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="77af0-231">Supported only on [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="77af0-232">**XmlSchemaCollectionsList**</span><span class="sxs-lookup"><span data-stu-id="77af0-232">**XmlSchemaCollectionsList**</span></span>  
 <span data-ttu-id="77af0-233">Clique para abrir a caixa de diálogo **Selecionar Coleções de Esquemas XML** .</span><span class="sxs-lookup"><span data-stu-id="77af0-233">Click to open the **Select XML Schema Collections** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77af0-234">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="77af0-234">See Also</span></span>  
 <span data-ttu-id="77af0-235">[Referência de mensagens e erros do Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="77af0-235">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="77af0-236">[Tarefas do Integration Services](control-flow/integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="77af0-236">[Integration Services Tasks](control-flow/integration-services-tasks.md) </span></span>  
 <span data-ttu-id="77af0-237">[Editor da Tarefa Transferir Objetos SQL Server &#40;Página Geral&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="77af0-237">[Transfer SQL Server Objects Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="77af0-238">[Página Expressões](expressions/expressions-page.md) </span><span class="sxs-lookup"><span data-stu-id="77af0-238">[Expressions Page](expressions/expressions-page.md) </span></span>  
 <span data-ttu-id="77af0-239">[Formatos de dados para importação ou exportação em massa &#40;SQL Server&#41;](../relational-databases/import-export/data-formats-for-bulk-import-or-bulk-export-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="77af0-239">[Data Formats for Bulk Import or Bulk Export &#40;SQL Server&#41;](../relational-databases/import-export/data-formats-for-bulk-import-or-bulk-export-sql-server.md) </span></span>  
 [<span data-ttu-id="77af0-240">Considerações sobre segurança para uma instalação do SQL Server</span><span class="sxs-lookup"><span data-stu-id="77af0-240">Security Considerations for a SQL Server Installation</span></span>](../../2014/sql-server/install/security-considerations-for-a-sql-server-installation.md)  
  
  
