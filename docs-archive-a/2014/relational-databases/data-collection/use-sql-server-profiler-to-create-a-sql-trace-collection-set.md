---
title: Usar SQL Server Profiler para criar um conjunto de coleta de rastreamento do SQL (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- SQL Trace collector set
ms.assetid: b6941dc0-50f5-475d-82eb-ce7c68117489
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e9c9514fef8069cef615d1480aad1e0acd1582cd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581959"
---
# <a name="use-sql-server-profiler-to-create-a-sql-trace-collection-set-sql-server-management-studio"></a><span data-ttu-id="7fd24-102">Usar o SQL Server Profiler para criar um conjunto de coleta de Rastreamento do SQL (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="7fd24-102">Use SQL Server Profiler to Create a SQL Trace Collection Set (SQL Server Management Studio)</span></span>
  <span data-ttu-id="7fd24-103">No [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] , você pode explorar as funcionalidades de rastreamento do lado do servidor do [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] para exportar uma definição de rastreamento que pode ser usada para criar um conjunto de coleta que usa o tipo de coletor de Rastreamento do SQL Genérico.</span><span class="sxs-lookup"><span data-stu-id="7fd24-103">In [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] you can exploit the server-side trace capabilities of [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] to export a trace definition that you can use to create a collection set that uses the Generic SQL Trace collector type.</span></span> <span data-ttu-id="7fd24-104">Há duas partes nesse processo:</span><span class="sxs-lookup"><span data-stu-id="7fd24-104">There are two parts to this process:</span></span>  
  
1.  <span data-ttu-id="7fd24-105">Crie e exporte um rastreamento [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7fd24-105">Create and export a [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] trace.</span></span>  
  
2.  <span data-ttu-id="7fd24-106">Faça o script de um novo conjunto de coleta baseado em um rastreamento exportado.</span><span class="sxs-lookup"><span data-stu-id="7fd24-106">Script a new collection set based on an exported trace.</span></span>  
  
 <span data-ttu-id="7fd24-107">O cenário para os procedimentos a seguir envolve a coleta de dados sobre qualquer procedimento armazenado que exija 80 milissegundos ou mais para ser concluído.</span><span class="sxs-lookup"><span data-stu-id="7fd24-107">The scenario for the following procedures involves collecting data about any stored procedure that requires 80 milliseconds or longer to complete.</span></span> <span data-ttu-id="7fd24-108">Para concluir esses procedimentos você deve ser capaz de:</span><span class="sxs-lookup"><span data-stu-id="7fd24-108">In order to complete these procedures you should be able to:</span></span>  
  
-   <span data-ttu-id="7fd24-109">Usar o [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] para criar e configurar um rastreamento.</span><span class="sxs-lookup"><span data-stu-id="7fd24-109">Use [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] to create and configure a trace.</span></span>  
  
-   <span data-ttu-id="7fd24-110">Usar o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] para abrir, editar e executar uma consulta.</span><span class="sxs-lookup"><span data-stu-id="7fd24-110">Use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to open, edit, and execute a query.</span></span>  
  
### <a name="create-and-export-a-sql-server-profiler-trace"></a><span data-ttu-id="7fd24-111">Criar e exportar um rastreamento do SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="7fd24-111">Create and export a SQL Server Profiler trace</span></span>  
  
1.  <span data-ttu-id="7fd24-112">No [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], abra [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7fd24-112">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], open [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span> <span data-ttu-id="7fd24-113">(No menu **Ferramentas** clique em **SQL Server Profiler**.)</span><span class="sxs-lookup"><span data-stu-id="7fd24-113">(On the **Tools** menu, click **SQL Server Profiler**.)</span></span>  
  
2.  <span data-ttu-id="7fd24-114">Na caixa de diálogo **Conectar ao Servidor** , clique em **Cancelar**.</span><span class="sxs-lookup"><span data-stu-id="7fd24-114">In the **Connect to Server** dialog box, click **Cancel**.</span></span>  
  
3.  <span data-ttu-id="7fd24-115">Para este cenário, verifique se os valores de duração estão configurados para serem exibidos em milissegundos (o padrão).</span><span class="sxs-lookup"><span data-stu-id="7fd24-115">For this scenario, ensure that duration values are configured to display in milliseconds (the default).</span></span> <span data-ttu-id="7fd24-116">Para fazer isso, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="7fd24-116">To do this, follow these steps:</span></span>  
  
    1.  <span data-ttu-id="7fd24-117">No menu **Ferramentas** , clique em **Opções**.</span><span class="sxs-lookup"><span data-stu-id="7fd24-117">On the **Tools** menu, click **Options**.</span></span>  
  
    2.  <span data-ttu-id="7fd24-118">Na área **Opções de Exibição** , verifique se a caixa de seleção Mostrar valores na coluna Duração em microssegundos está selecionada.</span><span class="sxs-lookup"><span data-stu-id="7fd24-118">In the **Display Options** area, ensure that the Show values in Duration column in microseconds check box is cleared.</span></span>  
  
    3.  <span data-ttu-id="7fd24-119">Clique em **OK** para fechar a caixa de diálogo **Opções Gerais** .</span><span class="sxs-lookup"><span data-stu-id="7fd24-119">Click **OK** to close the **General Options** dialog box.</span></span>  
  
4.  <span data-ttu-id="7fd24-120">No menu **Arquivo** , clique em **Novo Rastreamento**.</span><span class="sxs-lookup"><span data-stu-id="7fd24-120">On the **File** menu, click **New Trace**.</span></span>  
  
5.  <span data-ttu-id="7fd24-121">Na caixa de diálogo **Conectar ao Servidor** , selecione o servidor com o qual deseja se conectar e clique em **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="7fd24-121">In the **Connect to Server** dialog box, select the server that you want to connect to, and then click **Connect**.</span></span>  
  
     <span data-ttu-id="7fd24-122">É exibida a caixa de diálogo **Propriedades do Rastreamento** .</span><span class="sxs-lookup"><span data-stu-id="7fd24-122">The **Trace Properties** dialog box appears.</span></span>  
  
6.  <span data-ttu-id="7fd24-123">Na guia **Geral** , faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="7fd24-123">On the **General** tab, do the following:</span></span>  
  
    1.  <span data-ttu-id="7fd24-124">Na caixa **Nome do rastreamento** , digite o nome a ser usado para o rastreamento.</span><span class="sxs-lookup"><span data-stu-id="7fd24-124">In the **Trace name** box, type the name that you want to use for the trace.</span></span> <span data-ttu-id="7fd24-125">Para este exemplo, o nome do rastreamento é `SPgt80`.</span><span class="sxs-lookup"><span data-stu-id="7fd24-125">For this example, the trace name is `SPgt80`.</span></span>  
  
    2.  <span data-ttu-id="7fd24-126">Em **Usar a lista do modelo**, selecione o modelo a ser usado para o rastreamento.</span><span class="sxs-lookup"><span data-stu-id="7fd24-126">In the **Use the template list**, select the template to use for the trace.</span></span> <span data-ttu-id="7fd24-127">Para este exemplo, clique em **TSQL_SPs**.</span><span class="sxs-lookup"><span data-stu-id="7fd24-127">For this example, click **TSQL_SPs**.</span></span>  
  
7.  <span data-ttu-id="7fd24-128">Na guia **Seleção de Eventos** , faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="7fd24-128">On the **Events Selection** tab, do the following:</span></span>  
  
    1.  <span data-ttu-id="7fd24-129">Identifique os eventos a serem usados para o rastreamento.</span><span class="sxs-lookup"><span data-stu-id="7fd24-129">Identify the events to use for the trace.</span></span> <span data-ttu-id="7fd24-130">Para este exemplo, desmarque todas as caixas de seleção na coluna **Events** , exceto por **ExistingConnection** e **SP:Completed**.</span><span class="sxs-lookup"><span data-stu-id="7fd24-130">For this example, clear all check boxes in the **Events** column, except for **ExistingConnection** and **SP:Completed**.</span></span>  
  
    2.  <span data-ttu-id="7fd24-131">No canto inferior direito, selecione a caixa de seleção **Mostrar todas as colunas** .</span><span class="sxs-lookup"><span data-stu-id="7fd24-131">In the lower-right corner, select the **Show all columns** check box.</span></span>  
  
    3.  <span data-ttu-id="7fd24-132">Clique na linha **SP:Completed** .</span><span class="sxs-lookup"><span data-stu-id="7fd24-132">Click the **SP:Completed** row.</span></span>  
  
    4.  <span data-ttu-id="7fd24-133">Role pela linha até a coluna **Duration** e selecione a caixa de seleção **Duração** .</span><span class="sxs-lookup"><span data-stu-id="7fd24-133">Scroll across the row to the **Duration** column, and then select the **Duration** check box.</span></span>  
  
8.  <span data-ttu-id="7fd24-134">No canto inferior direito, clique em **Filtros de Coluna** para abrir a caixa de diálogo **Editar Filtro** .</span><span class="sxs-lookup"><span data-stu-id="7fd24-134">In the lower-right corner, click **Column Filters** to open the **Edit Filter** dialog box.</span></span> <span data-ttu-id="7fd24-135">Na caixa de diálogo **Editar Filtro** , proceda da maneira a seguir:</span><span class="sxs-lookup"><span data-stu-id="7fd24-135">In the **Edit Filter** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="7fd24-136">Na lista de filtros, clique em **Duração**.</span><span class="sxs-lookup"><span data-stu-id="7fd24-136">In the filter list, click **Duration**.</span></span>  
  
    2.  <span data-ttu-id="7fd24-137">Na janela do operador booliano, expanda o nó **maior que ou igual** , digite `80` como o valor e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="7fd24-137">In the Boolean operator window, expand the **Greater than or equal** node, type `80` as the value, and then click **OK**.</span></span>  
  
9. <span data-ttu-id="7fd24-138">Clique em **Executar** para iniciar o rastreamento.</span><span class="sxs-lookup"><span data-stu-id="7fd24-138">Click **Run** to start the trace.</span></span>  
  
10. <span data-ttu-id="7fd24-139">Na barra de ferramentas, clique em **Parar Rastreamento Selecionado** ou **Pausar Rastreamento Selecionado**.</span><span class="sxs-lookup"><span data-stu-id="7fd24-139">On the toolbar, click **Stop Selected Trace** or **Pause Selected Trace**.</span></span>  
  
11. <span data-ttu-id="7fd24-140">No menu **Arquivo** , aponte para **Exportar**, para **Definição de Rastreamento de Script**e clique em **Para o Conjunto de Coleta de Rastreamento do SQL**.</span><span class="sxs-lookup"><span data-stu-id="7fd24-140">On the **File** menu, point to **Export**, point to **Script Trace Definition**, and then click **For SQL Trace Collection Set**.</span></span>  
  
12. <span data-ttu-id="7fd24-141">Na caixa de diálogo **Salvar como** , digite o nome desejado para a definição de rastreamento na caixa **Nome do arquivo** e salve-o no local desejado.</span><span class="sxs-lookup"><span data-stu-id="7fd24-141">In the **Save As** dialog box, type the name that you want to use for the trace definition in the **File name** box, and then save it in the location that you want.</span></span> <span data-ttu-id="7fd24-142">Para este exemplo, o nome do arquivo é o mesmo que o nome do rastreamento (SPgt80).</span><span class="sxs-lookup"><span data-stu-id="7fd24-142">For this example, the file name is the same as the trace name (SPgt80).</span></span>  
  
13. <span data-ttu-id="7fd24-143">Clique em **OK** quando receber uma mensagem que o arquivo foi salvo com êxito e feche o [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7fd24-143">Click **OK** when you receive a message that the file was successfully saved, and then close [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>  
  
### <a name="script-a-new-collection-set-from-a-sql-server-profiler-trace"></a><span data-ttu-id="7fd24-144">Gere o script de um novo conjunto de coleta de um rastreamento do SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="7fd24-144">Script a new collection set from a SQL Server Profiler trace</span></span>  
  
1.  <span data-ttu-id="7fd24-145">No [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], no menu **Arquivo** , aponte para **Abrir** e clique em **Arquivo**.</span><span class="sxs-lookup"><span data-stu-id="7fd24-145">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], on the **File** menu, point to **Open,** and then click **File**.</span></span>  
  
2.  <span data-ttu-id="7fd24-146">Na caixa de diálogo **Abrir Arquivo** , localize e abra o arquivo criado no procedimento anterior (SPgt80).</span><span class="sxs-lookup"><span data-stu-id="7fd24-146">In the **Open File** dialog box, locate and then open the file that you created in the previous procedure (SPgt80).</span></span>  
  
     <span data-ttu-id="7fd24-147">As informações de rastreamento que você salvou são abertas em uma janela de Consulta e mescladas em um script que você pode executar para criar o novo conjunto de coleta.</span><span class="sxs-lookup"><span data-stu-id="7fd24-147">The trace information that you saved is opened in a Query window and merged into a script that you can run to create the new collection set.</span></span>  
  
3.  <span data-ttu-id="7fd24-148">Role pelo script e faça as substituições a seguir, que são observadas no texto de comentários do script:</span><span class="sxs-lookup"><span data-stu-id="7fd24-148">Scroll through the script and make the following replacements, which are noted in the script comment text:</span></span>  
  
    -   <span data-ttu-id="7fd24-149">Substitua **Nome do Conjunto de Coleta SQLTrace Aqui** pelo nome que você deseja usar para o conjunto de coleta.</span><span class="sxs-lookup"><span data-stu-id="7fd24-149">Replace **SQLTrace Collection Set Name Here** with the name that you want to use for the collection set.</span></span> <span data-ttu-id="7fd24-150">Para este exemplo, o nome do conjunto de coleta é `SPROC_CollectionSet`.</span><span class="sxs-lookup"><span data-stu-id="7fd24-150">For this example, name the collection set `SPROC_CollectionSet`.</span></span>  
  
    -   <span data-ttu-id="7fd24-151">Substitua **Nome do Item de Coleta SQLTrace Aqui** pelo nome que você deseja usar para o item de coleta.</span><span class="sxs-lookup"><span data-stu-id="7fd24-151">Replace **SQLTrace Collection Item Name Here** with the name that you want to use for the collection item.</span></span> <span data-ttu-id="7fd24-152">Para este exemplo, o nome do item de coleta é `SPROC_Collection_Item`.</span><span class="sxs-lookup"><span data-stu-id="7fd24-152">For this example, name the collection item `SPROC_Collection_Item`.</span></span>  
  
4.  <span data-ttu-id="7fd24-153">Clique em **Executar** para executar a consulta e criar o conjunto de coleta.</span><span class="sxs-lookup"><span data-stu-id="7fd24-153">Click **Execute** to run the query and to create the collection set.</span></span>  
  
5.  <span data-ttu-id="7fd24-154">No Pesquisador de Objetos, verifique se o conjunto de coleta foi criado.</span><span class="sxs-lookup"><span data-stu-id="7fd24-154">In Object Explorer, verify that the collection set was created.</span></span> <span data-ttu-id="7fd24-155">Para fazer isso, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="7fd24-155">To do this, follow these steps:</span></span>  
  
    1.  <span data-ttu-id="7fd24-156">Clique com o botão direito do mouse em **Gerenciamento**e clique em **Atualizar**.</span><span class="sxs-lookup"><span data-stu-id="7fd24-156">Right-click **Management**, and then click **Refresh**.</span></span>  
  
    2.  <span data-ttu-id="7fd24-157">Expanda **Gerenciamento**e expanda **Coleta de Dados**.</span><span class="sxs-lookup"><span data-stu-id="7fd24-157">Expand **Management**, and then expand **Data Collection**.</span></span>  
  
     <span data-ttu-id="7fd24-158">O `SPROC_CollectionSet` conjunto de coleta aparece no mesmo nível que o nó **conjuntos de coleta de dados do sistema** .</span><span class="sxs-lookup"><span data-stu-id="7fd24-158">The `SPROC_CollectionSet` collection set appears at the same level as the **System Data Collection Sets** node.</span></span> <span data-ttu-id="7fd24-159">Por padrão, o conjunto de coleta é desabilitado.</span><span class="sxs-lookup"><span data-stu-id="7fd24-159">By default, the collection set is disabled.</span></span>  
  
6.  <span data-ttu-id="7fd24-160">Use o Pesquisador de Objetos para editar as propriedades de SPROC_CollectionSet, como o modo de coleta e a agenda de carregamento.</span><span class="sxs-lookup"><span data-stu-id="7fd24-160">Use Object Explorer to edit the properties of SPROC_CollectionSet, such as the collection mode and upload schedule.</span></span> <span data-ttu-id="7fd24-161">Siga os mesmos procedimentos que você usaria para os conjuntos de coleta de Dados do Sistema que são fornecidos com o coletor de dados.</span><span class="sxs-lookup"><span data-stu-id="7fd24-161">Follow the same procedures that you would for the System Data collection sets that are provided with the data collector.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7fd24-162">Exemplo</span><span class="sxs-lookup"><span data-stu-id="7fd24-162">Example</span></span>  
 <span data-ttu-id="7fd24-163">O exemplo de código a seguir é o script final resultante das etapas documentadas nos procedimentos anteriores.</span><span class="sxs-lookup"><span data-stu-id="7fd24-163">The following code sample is the final script resulting from the steps documented in the preceding procedures.</span></span>  
  
```  
/*************************************************************/  
-- SQL Trace collection set generated from SQL Server Profiler  
-- Date: 11/19/2007  12:55:31 AM  
/*************************************************************/  
  
USE msdb  
GO  
  
BEGIN TRANSACTION  
BEGIN TRY  
  
-- Define collection set  
-- ***  
-- *** Replace 'SqlTrace Collection Set Name Here' in the   
-- *** following script with the name you want  
-- *** to use for the collection set.  
-- ***  
DECLARE @collection_set_id int;  
EXEC [dbo].[sp_syscollector_create_collection_set]  
    @name = N'SPROC_CollectionSet',  
    @schedule_name = N'CollectorSchedule_Every_15min',  
    @collection_mode = 0, -- cached mode needed for Trace collections  
    @logging_level = 0, -- minimum logging  
    @days_until_expiration = 5,  
    @description = N'Collection set generated by SQL Server Profiler',  
    @collection_set_id = @collection_set_id output;  
SELECT @collection_set_id;  
  
-- Define input and output variables for the collection item.  
DECLARE @trace_definition xml;  
DECLARE @collection_item_id int;  
  
-- Define the trace parameters as an XML variable  
SELECT @trace_definition = convert(xml,   
N'<ns:SqlTraceCollector xmlns:ns"DataCollectorType" use_default="0">  
<Events>  
  <EventType name="Sessions">  
    <Event id="17" name="ExistingConnection" columnslist="1,2,14,26,3,35,12" />  
  </EventType>  
  <EventType name="Stored Procedures">  
    <Event id="43" name="SP:Completed" columnslist="1,2,26,34,3,35,12,13,14,22" />  
  </EventType>  
</Events>  
<Filters>  
  <Filter columnid="13" columnname="Duration" logical_operator="AND" comparison_operator="GE" value="80000L" />  
</Filters>  
</ns:SqlTraceCollector>  
');  
  
-- Retrieve the collector type GUID for the trace collector type.  
DECLARE @collector_type_GUID uniqueidentifier;  
SELECT @collector_type_GUID = collector_type_uid FROM [dbo].[syscollector_collector_types] WHERE name = N'Generic SQL Trace Collector Type';  
  
-- Create the trace collection item.  
-- ***  
-- *** Replace 'SqlTrace Collection Item Name Here' in   
-- *** the following script with the name you want to  
-- *** use for the collection item.  
-- ***  
EXEC [dbo].[sp_syscollector_create_collection_item]  
   @collection_set_id = @collection_set_id,  
   @collector_type_uid = @collector_type_GUID,  
   @name = N'SPROC_Collection_Item',  
   @frequency = 900, -- specified the frequency for checking to see if trace is still running  
   @parameters = @trace_definition,  
   @collection_item_id = @collection_item_id output;  
SELECT @collection_item_id;  
  
COMMIT TRANSACTION;  
END TRY  
  
BEGIN CATCH  
ROLLBACK TRANSACTION;  
DECLARE @ErrorMessage nvarchar(4000);  
DECLARE @ErrorSeverity int;  
DECLARE @ErrorState int;  
DECLARE @ErrorNumber int;  
DECLARE @ErrorLine int;  
DECLARE @ErrorProcedure nvarchar(200);  
SELECT @ErrorLine = ERROR_LINE(),  
       @ErrorSeverity = ERROR_SEVERITY(),  
       @ErrorState = ERROR_STATE(),  
       @ErrorNumber = ERROR_NUMBER(),  
       @ErrorMessage = ERROR_MESSAGE(),  
       @ErrorProcedure = ISNULL(ERROR_PROCEDURE(), '-');  
RAISERROR (14684, @ErrorSeverity, 1 , @ErrorNumber, @ErrorSeverity, @ErrorState, @ErrorProcedure, @ErrorLine, @ErrorMessage);  
END CATCH;  
GO  
```  
  
  
