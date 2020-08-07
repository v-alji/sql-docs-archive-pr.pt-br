---
title: Aplicar as alterações ao destino | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- incremental load [Integration Services],applying changes
ms.assetid: 338a56db-cb14-4784-a692-468eabd30f41
author: chugugrace
ms.author: chugu
ms.openlocfilehash: dd7ab93a299ffaab2259c3d462a5c0a69160ad5b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583742"
---
# <a name="apply-the-changes-to-the-destination"></a><span data-ttu-id="dd57d-102">Aplicar as alterações no destino</span><span class="sxs-lookup"><span data-stu-id="dd57d-102">Apply the Changes to the Destination</span></span>
  <span data-ttu-id="dd57d-103">No fluxo de dados de um pacote do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] que executa uma carga incremental de dados de alteração, a terceira e a última tarefa servem para aplicar as alterações no seu destino.</span><span class="sxs-lookup"><span data-stu-id="dd57d-103">In the data flow of an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that performs an incremental load of change data, the third and final task is to apply the changes to your destination.</span></span> <span data-ttu-id="dd57d-104">Você precisará de um componente para aplicar inserções, um para aplicar atualizações e um para aplicar exclusões.</span><span class="sxs-lookup"><span data-stu-id="dd57d-104">You will need one component to apply inserts, one to apply updates, and one to apply deletes.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="dd57d-105">A segunda tarefa no desenvolvimento do fluxo de dados de um pacote que realiza uma carga incremental de dados de alteração serve para separar inserções, atualizações e exclusões.</span><span class="sxs-lookup"><span data-stu-id="dd57d-105">The second task in designing the data flow of a package that performs an incremental load of change data is to separate inserts, updates, and deletes.</span></span> <span data-ttu-id="dd57d-106">Para obter mais informações sobre este componente, consulte [Processar inserções, atualizações e exclusões](process-inserts-updates-and-deletes.md).</span><span class="sxs-lookup"><span data-stu-id="dd57d-106">For more information about this component, see [Process Inserts, Updates, and Deletes](process-inserts-updates-and-deletes.md).</span></span> <span data-ttu-id="dd57d-107">Para obter uma descrição do processo geral para criar um pacote que realiza uma carga incremental de dados de alteração, consulte [Change Data Capture &#40;SSIS&#41;](change-data-capture-ssis.md).</span><span class="sxs-lookup"><span data-stu-id="dd57d-107">For a description of the overall process for creating a package that performs an incremental load of change data, see [Change Data Capture &#40;SSIS&#41;](change-data-capture-ssis.md).</span></span>  
  
## <a name="applying-inserts"></a><span data-ttu-id="dd57d-108">Aplicando inserções</span><span class="sxs-lookup"><span data-stu-id="dd57d-108">Applying Inserts</span></span>  
 <span data-ttu-id="dd57d-109">Para aplicar inserções, você usa um destino OLE DB, pois as linhas novas não requerem nenhuma manipulação especial.</span><span class="sxs-lookup"><span data-stu-id="dd57d-109">To apply inserts, you use an OLE DB destination because the new rows do not require any special handling.</span></span>  
  
#### <a name="to-process-inserts-by-using-an-ole-db-destination"></a><span data-ttu-id="dd57d-110">Para processar inserções usando um destino OLE DB</span><span class="sxs-lookup"><span data-stu-id="dd57d-110">To process inserts by using an OLE DB Destination</span></span>  
  
1.  <span data-ttu-id="dd57d-111">Na guia **Fluxo de Dados** , adicione um destino OLE DB.</span><span class="sxs-lookup"><span data-stu-id="dd57d-111">On the **Data flow** tab, add an OLE DB destination.</span></span>  
  
2.  <span data-ttu-id="dd57d-112">Conecte a saída que contém inserções da transformação de Divisão Condicional para o destino de OLE DB.</span><span class="sxs-lookup"><span data-stu-id="dd57d-112">Connect the output that contains inserts from the Conditional Split transformation to the OLE DB destination.</span></span>  
  
3.  <span data-ttu-id="dd57d-113">No **Editor de Destino de OLE DB**, na página **Gerenciador de Conexões** , selecione as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="dd57d-113">In the **OLE DB Destination Editor**, on the **Connection Manager** page, select the following options:</span></span>  
  
    1.  <span data-ttu-id="dd57d-114">Selecione ou crie um Gerenciador de Conexões de OLE DB para o banco de dados de destino.</span><span class="sxs-lookup"><span data-stu-id="dd57d-114">Select or create an OLE DB Connection Manager for the destination database.</span></span>  
  
    2.  <span data-ttu-id="dd57d-115">Selecione uma opção **Modo de acesso dos dados** e selecione a tabela de destino ou digite uma instrução SQL que contenha as colunas de destino.</span><span class="sxs-lookup"><span data-stu-id="dd57d-115">Select a **Data access mode** option, and then select the destination table or enter a SQL statement that contains the destination columns.</span></span>  
  
4.  <span data-ttu-id="dd57d-116">Na página **Mapeamentos** do editor, mapeie as colunas apropriadas a partir dos dados de alteração para a tabela de destino.</span><span class="sxs-lookup"><span data-stu-id="dd57d-116">On the **Mappings** page of the editor, map the appropriate columns from the change data to the destination table.</span></span>  
  
## <a name="applying-updates"></a><span data-ttu-id="dd57d-117">Aplicando atualizações</span><span class="sxs-lookup"><span data-stu-id="dd57d-117">Applying Updates</span></span>  
 <span data-ttu-id="dd57d-118">Para aplicar atualizações, você usa uma transformação de Comando do OLE DB.</span><span class="sxs-lookup"><span data-stu-id="dd57d-118">To apply updates, you use an OLE DB Command transformation.</span></span> <span data-ttu-id="dd57d-119">Você usa essa transformação porque tem que usar uma instrução UPDATE com parâmetros para atualizar uma linha por vez com novos valores de coluna.</span><span class="sxs-lookup"><span data-stu-id="dd57d-119">You use this transformation because you have to use a parameterized UPDATE statement to update one row at a time with the new column values.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="dd57d-120">Também é possível usar componentes de destino para aplicar atualizações.</span><span class="sxs-lookup"><span data-stu-id="dd57d-120">You can also use destination components to apply updates.</span></span> <span data-ttu-id="dd57d-121">Ao usar esse método, você usa os componentes de destino para salvar as linhas em tabelas temporárias criadas para essa finalidade.</span><span class="sxs-lookup"><span data-stu-id="dd57d-121">When using this approach, you use the destination components to save the rows to temporary tables that you create for this purpose.</span></span> <span data-ttu-id="dd57d-122">Em seguida, você usa tarefas Executar SQL para realizar operações de atualização em massa e exclusão em massa no destino a partir das tabelas temporárias.</span><span class="sxs-lookup"><span data-stu-id="dd57d-122">Then, you use Execute SQL tasks to perform bulk update and bulk delete operations against the destination from the temporary tables.</span></span>  
  
#### <a name="to-process-updates-by-using-an-ole-db-command-transformation"></a><span data-ttu-id="dd57d-123">Para processar atualizações usando uma transformação de Comando OLE DB</span><span class="sxs-lookup"><span data-stu-id="dd57d-123">To process updates by using an OLE DB Command transformation</span></span>  
  
1.  <span data-ttu-id="dd57d-124">Na guia **Fluxo de Dados** , adicione uma transformação de Comando OLE DB.</span><span class="sxs-lookup"><span data-stu-id="dd57d-124">On the **Data flow** tab, add an OLE DB Command transformation.</span></span>  
  
2.  <span data-ttu-id="dd57d-125">Conecte a saída que contém atualizações a partir da transformação de Divisão Condicional para a transformação de Comando OLE DB.</span><span class="sxs-lookup"><span data-stu-id="dd57d-125">Connect the output that contains updates from the Conditional Split transformation to the OLE DB Command transformation.</span></span>  
  
3.  <span data-ttu-id="dd57d-126">Em **Editor Avançado para o Comando OLE DB**, no **Gerenciador de Conexões** selecione ou crie um gerenciador de conexões OLE DB para o banco de dados de destino.</span><span class="sxs-lookup"><span data-stu-id="dd57d-126">In the **Advanced Editor for OLE DB Command**, on the **Connection Manager** tab, select or create an OLE DB Connection Manager for the destination database.</span></span>  
  
4.  <span data-ttu-id="dd57d-127">No **Editor Avançado para o Comando OLE DB**, na guia **Propriedades do Componente** , para **SqlCommand**, digite uma instrução UPDATE com parâmetros.</span><span class="sxs-lookup"><span data-stu-id="dd57d-127">In the **Advanced Editor for OLE DB Command**, on the **Component Properties** tab, for **SqlCommand**, enter a parameterized UPDATE statement.</span></span>  
  
     <span data-ttu-id="dd57d-128">Por exemplo, uma instrução UPDATE para uma tabela Cliente poderia ter a sintaxe seguinte:</span><span class="sxs-lookup"><span data-stu-id="dd57d-128">For example, an UPDATE statement for a Customer table might have the following syntax:</span></span>  
  
    ```  
    update CDCSample.Customer  
    set TerritoryID  = ?,  
        CustomerType  = ?,  
        rowguid  = ?,  
        ModifiedDate  = ?  
    where CustomerID = ?  
  
    ```  
  
5.  <span data-ttu-id="dd57d-129">Na página **Mapeamentos de Coluna** do editor, mapeie as colunas apropriadas a partir dos dados de alteração até os parâmetros na instrução UPDATE.</span><span class="sxs-lookup"><span data-stu-id="dd57d-129">On the **Column Mappings** tab of the editor, map the appropriate columns from the change data to the parameters in the UPDATE statement.</span></span>  
  
## <a name="applying-deletes"></a><span data-ttu-id="dd57d-130">Aplicando exclusões</span><span class="sxs-lookup"><span data-stu-id="dd57d-130">Applying Deletes</span></span>  
 <span data-ttu-id="dd57d-131">Para aplicar exclusões, você usa uma transformação de Comando OLE DB.</span><span class="sxs-lookup"><span data-stu-id="dd57d-131">To apply deletes, you use an OLE DB Command transformation.</span></span> <span data-ttu-id="dd57d-132">Você usa essa transformação porque tem que usar uma instrução DELETE com parâmetros para excluir uma única linha por vez com base no valor da coluna que identifica com exclusividade a linha.</span><span class="sxs-lookup"><span data-stu-id="dd57d-132">You use this transformation because you have to use a parameterized DELETE statement that deletes a single row at a time based on the column value that uniquely identifies the row.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="dd57d-133">Também é possível usar componentes de destino para aplicar exclusões.</span><span class="sxs-lookup"><span data-stu-id="dd57d-133">You can also use destination components to apply deletes.</span></span> <span data-ttu-id="dd57d-134">Ao usar esse método, você usa os componentes de destino para salvar as linhas em tabelas temporárias criadas para essa finalidade.</span><span class="sxs-lookup"><span data-stu-id="dd57d-134">When using this approach, you use the destination components to save the rows to temporary tables that you create for this purpose.</span></span> <span data-ttu-id="dd57d-135">Em seguida, você usa tarefas Executar SQL para realizar operações de atualização em massa e exclusão em massa no destino a partir das tabelas temporárias.</span><span class="sxs-lookup"><span data-stu-id="dd57d-135">Then, you use Execute SQL tasks to perform bulk update and bulk delete operations against the destination from the temporary tables.</span></span>  
  
#### <a name="to-process-deletes-by-using-an-ole-db-command-transformation"></a><span data-ttu-id="dd57d-136">Para processar exclusões usando uma transformação de Comando OLE DB</span><span class="sxs-lookup"><span data-stu-id="dd57d-136">To process deletes by using an OLE DB Command transformation</span></span>  
  
1.  <span data-ttu-id="dd57d-137">Na guia **Fluxo de Dados** , adicione uma transformação de Comando OLE DB ao fluxo de dados.</span><span class="sxs-lookup"><span data-stu-id="dd57d-137">On the **Data flow** tab, add an OLE DB Command transformation to the data flow.</span></span>  
  
2.  <span data-ttu-id="dd57d-138">Conecte a saída que contém exclusões a partir da transformação de Divisão Condicional para a transformação de Comando OLE DB.</span><span class="sxs-lookup"><span data-stu-id="dd57d-138">Connect the output that contains deletes from the Conditional Split transformation to the OLE DB Command transformation.</span></span>  
  
3.  <span data-ttu-id="dd57d-139">Abra o Editor Avançado para configurar a transformação.</span><span class="sxs-lookup"><span data-stu-id="dd57d-139">Open the Advanced Editor to configure the transformation.</span></span>  
  
4.  <span data-ttu-id="dd57d-140">Em **Editor Avançado para o Comando OLE DB**, no **Gerenciador de Conexões** selecione ou crie um gerenciador de conexões OLE DB para o banco de dados de destino.</span><span class="sxs-lookup"><span data-stu-id="dd57d-140">In the **Advanced Editor for OLE DB Command**, on the **Connection Manager** tab, select or create an OLE DB Connection Manager for the destination database.</span></span>  
  
5.  <span data-ttu-id="dd57d-141">No **Editor Avançado para o Comando OLE DB**, na guia **Propriedades do Componente** do editor, para **SqlCommand**, digite uma instrução DELETE com parâmetros.</span><span class="sxs-lookup"><span data-stu-id="dd57d-141">In the **Advanced Editor for OLE DB Command**, on the **Component Properties** tab of the editor, for **SqlCommand**, enter a parameterized DELETE statement.</span></span>  
  
     <span data-ttu-id="dd57d-142">Por exemplo, uma instrução DELETE para uma tabela Cliente poderia ter a sintaxe seguinte:</span><span class="sxs-lookup"><span data-stu-id="dd57d-142">For example, a DELETE statement for a Customer table might have the following syntax:</span></span>  
  
    ```  
    delete from Customer where CustomerID = ?  
  
    ```  
  
6.  <span data-ttu-id="dd57d-143">Na guia **Mapeamentos de Coluna** do editor, mapeie a coluna apropriada a partir dos dados de alteração até o parâmetro na instrução DELETE.</span><span class="sxs-lookup"><span data-stu-id="dd57d-143">On the **Column Mappings** tab of the editor, map the appropriate column from the change data to the parameter in the DELETE statement.</span></span>  
  
## <a name="optimizing-inserts-and-updates-by-using-merge-functionality"></a><span data-ttu-id="dd57d-144">Aperfeiçoando inserções e atualizações usando a funcionalidade MERGE</span><span class="sxs-lookup"><span data-stu-id="dd57d-144">Optimizing Inserts and Updates by Using MERGE Functionality</span></span>  
 <span data-ttu-id="dd57d-145">É possível otimizar o processamento de inserções e atualizações combinando determinadas opções de captura de dados de alteração com o uso da palavra-chave Transact-SQL MERGE.</span><span class="sxs-lookup"><span data-stu-id="dd57d-145">You can optimize the processing of inserts and updates by combining certain change data capture options with the use of the Transact-SQL MERGE keyword.</span></span> <span data-ttu-id="dd57d-146">Para obter mais informações sobre a palavra-chave MERGE, consulte [MERGE &#40;Transact-SQL&#41;](/sql/t-sql/statements/merge-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="dd57d-146">For more information about the MERGE keyword, see [MERGE &#40;Transact-SQL&#41;](/sql/t-sql/statements/merge-transact-sql).</span></span>  
  
 <span data-ttu-id="dd57d-147">Na instrução Transact-SQL que recupera os dados de alteração, é possível especificar *all with merge* como o valor do parâmetro *row_filter_option* ao chamar a função **cdc.fn_cdc_get_net_changes_<capture_instance>** .</span><span class="sxs-lookup"><span data-stu-id="dd57d-147">In the Transact-SQL statement that retrieves the change data, you can specify *all with merge* as the value of the *row_filter_option* parameter when you call the **cdc.fn_cdc_get_net_changes_<capture_instance>** function.</span></span> <span data-ttu-id="dd57d-148">Essa função de captura de dados de alteração opera com mais eficiência quando não tem que realizar o processamento extra, necessário para distinguir inserções de atualizações.</span><span class="sxs-lookup"><span data-stu-id="dd57d-148">This change data capture function operates more efficiently when it does not have to perform the extra processing that is required to distinguish inserts from updates.</span></span> <span data-ttu-id="dd57d-149">Ao especificar o valor do parâmetro *all with merge* , o valor de **__$operation** dos dados de alteração é 1 para exclusões ou 5 para alterações causadas por inserções ou atualizações.</span><span class="sxs-lookup"><span data-stu-id="dd57d-149">When you specify the *all with merge* parameter value, the **__$operation** value of the change data is 1 for deletes or 5 for changes that were caused by inserts or updates.</span></span> <span data-ttu-id="dd57d-150">Para obter mais informações sobre a função Transact-SQL usada para recuperar os dados de alteração, consulte [Recuperar e compreender os dados de alteração](retrieve-and-understand-the-change-data.md). Após recuperar as alterações com o valor de parâmetro *all with merge* , é possível aplicar exclusões e enviar as linhas restantes para uma tabela temporária ou uma tabela de preparo.</span><span class="sxs-lookup"><span data-stu-id="dd57d-150">For more information about the Transact-SQL function that is used to retrieve the change data, see [Retrieve and Understand the Change Data](retrieve-and-understand-the-change-data.md).After retrieving changes with the *all with merge* parameter value, you can apply deletes, and output the remaining rows to a temporary table or a staging table.</span></span> <span data-ttu-id="dd57d-151">Em seguida, em uma tarefa Executar SQL de downstream, é possível usar uma única instrução MERGE para aplicar todas as inserções ou atualizações da tabela de preparo para o destino.</span><span class="sxs-lookup"><span data-stu-id="dd57d-151">Then, in a downstream Execute SQL Task, you can use a single MERGE statement to apply all the inserts or updates from the staging table to the destination.</span></span>  
  
  
