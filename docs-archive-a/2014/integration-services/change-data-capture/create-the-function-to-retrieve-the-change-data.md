---
title: Criar a função para recuperar os dados de alteração | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- incremental load [Integration Services],creating function
ms.assetid: 55dd0946-bd67-4490-9971-12dfb5b9de94
author: chugugrace
ms.author: chugu
ms.openlocfilehash: cc1d5af0a64225aca4ff54570ad6504d25d62812
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684831"
---
# <a name="create-the-function-to-retrieve-the-change-data"></a><span data-ttu-id="9293d-102">Criar a função para recuperar os dados de alteração</span><span class="sxs-lookup"><span data-stu-id="9293d-102">Create the Function to Retrieve the Change Data</span></span>
  <span data-ttu-id="9293d-103">Após concluir o fluxo de controle de um pacote [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] que executa uma carga incremental de dados de alteração, a próxima tarefa é criar uma função com valor de tabela que recupera os dados de alteração.</span><span class="sxs-lookup"><span data-stu-id="9293d-103">After completing the control flow for an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that performs an incremental load of change data, the next task is to create a table-valued function that retrieves the change data.</span></span> <span data-ttu-id="9293d-104">É preciso criar esta função apenas uma vez antes da primeira carga incremental.</span><span class="sxs-lookup"><span data-stu-id="9293d-104">You only have to create this function one time before the first incremental load.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9293d-105">A criação de uma função para recuperar os dados de alteração é a segunda etapa no processo de criação de um pacote que realize uma carga incremental de dados de alteração.</span><span class="sxs-lookup"><span data-stu-id="9293d-105">The creation of a function to retrieve the change data is the second step in the process of creating a package that performs an incremental load of change data.</span></span> <span data-ttu-id="9293d-106">Para obter uma descrição do processo geral para criar este pacote, consulte [Captura de dados de alteração &#40;SSIS&#41;](change-data-capture-ssis.md).</span><span class="sxs-lookup"><span data-stu-id="9293d-106">For a description of the overall process for creating this package, see [Change Data Capture &#40;SSIS&#41;](change-data-capture-ssis.md).</span></span>  
  
## <a name="design-considerations-for-change-data-capture-functions"></a><span data-ttu-id="9293d-107">Considerações de design para funções de captura de dados de alteração</span><span class="sxs-lookup"><span data-stu-id="9293d-107">Design Considerations for Change Data Capture Functions</span></span>  
 <span data-ttu-id="9293d-108">Para recuperar dados de alteração, um componente de origem no fluxo de dados do pacote chama uma das seguintes funções de consulta de captura de dados de alteração:</span><span class="sxs-lookup"><span data-stu-id="9293d-108">To retrieve change data, a source component in the data flow of the package calls one of the following change data capture query functions:</span></span>  
  
-   <span data-ttu-id="9293d-109">**cdc.fn_cdc_get_net_changes_<capture_instance>** Para essa consulta, a única linha retornada para cada atualização contém o estado final de cada linha alterada.</span><span class="sxs-lookup"><span data-stu-id="9293d-109">**cdc.fn_cdc_get_net_changes_<capture_instance>** For this query, the single row returned for each update contains the final state of each changed row.</span></span> <span data-ttu-id="9293d-110">Na maioria dos casos, você precisa apenas dos dados retornados por uma consulta para alterações líquidas.</span><span class="sxs-lookup"><span data-stu-id="9293d-110">In most cases, you only need the data returned by a query for net changes.</span></span> <span data-ttu-id="9293d-111">Para obter mais informações, veja [cdc.fn_cdc_get_net_changes_&#60;capture_instance&#62; &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/cdc-fn-cdc-get-net-changes-capture-instance-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="9293d-111">For more information, see [cdc.fn_cdc_get_net_changes_&#60;capture_instance&#62; &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/cdc-fn-cdc-get-net-changes-capture-instance-transact-sql).</span></span>  
  
-   <span data-ttu-id="9293d-112">**cdc.fn_cdc_get_all_changes_<capture_instance>** Essa consulta retorna todas as alterações que ocorreram em cada linha durante o intervalo de captura.</span><span class="sxs-lookup"><span data-stu-id="9293d-112">**cdc.fn_cdc_get_all_changes_<capture_instance>** This query returns all the changes that have occurred in each row during the capture interval.</span></span> <span data-ttu-id="9293d-113">Para obter mais informações, veja [cdc.fn_cdc_get_all_changes_&#60;capture_instance&#62; &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/cdc-fn-cdc-get-all-changes-capture-instance-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="9293d-113">For more information, see [cdc.fn_cdc_get_all_changes_&#60;capture_instance&#62;  &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/cdc-fn-cdc-get-all-changes-capture-instance-transact-sql).</span></span>  
  
 <span data-ttu-id="9293d-114">O componente de origem que recebe os resultados retornados pela função e os passa para transformações e destinos downstream, que aplicam os dados da alteração no destino final.</span><span class="sxs-lookup"><span data-stu-id="9293d-114">The source component then takes the results returned by the function and passes them to downstream transformations and destinations, which apply the change data to the final destination.</span></span>  
  
 <span data-ttu-id="9293d-115">No entanto, um componente de origem [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] não pode chamar estas funções de captura de dados de alteração diretamente.</span><span class="sxs-lookup"><span data-stu-id="9293d-115">However, an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] source component cannot call these change data capture functions directly.</span></span> <span data-ttu-id="9293d-116">Um componente de origem [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] requer metadados sobre as colunas retornadas pela consulta.</span><span class="sxs-lookup"><span data-stu-id="9293d-116">An [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] source component requires metadata about the columns that the query returns.</span></span> <span data-ttu-id="9293d-117">As funções de captura de dados de alteração não definem as colunas de suas tabelas de saída.</span><span class="sxs-lookup"><span data-stu-id="9293d-117">The change data capture functions do not define the columns of their output table.</span></span> <span data-ttu-id="9293d-118">Dessa forma, estas funções não retornam metadados suficientes para um componente de origem [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9293d-118">Thus, these functions do not return sufficient metadata for an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] source component.</span></span>  
  
 <span data-ttu-id="9293d-119">Em vez disso, use uma função de invólucro com valor de tabela, pois esse tipo de função define explicitamente as colunas de sua tabela de saída em sua cláusula RETURNS.</span><span class="sxs-lookup"><span data-stu-id="9293d-119">Instead, you use a table-valued wrapper function because this kind of function explicitly defines the columns of its output table in its RETURNS clause.</span></span> <span data-ttu-id="9293d-120">Esta definição explícita de colunas fornece os metadados que uma componente de origem [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] precisa.</span><span class="sxs-lookup"><span data-stu-id="9293d-120">This explicit definition of columns provides the metadata that an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] source component needs.</span></span> <span data-ttu-id="9293d-121">É necessário criar esta função para cada tabela para a qual você deseja recuperar os dados de alteração.</span><span class="sxs-lookup"><span data-stu-id="9293d-121">You have to create this function for each table for which you want to retrieve change data.</span></span>  
  
 <span data-ttu-id="9293d-122">Você tem duas opções para criar a função de invólucro com valor de tabela que chama a função de consulta de captura de dados de alteração:</span><span class="sxs-lookup"><span data-stu-id="9293d-122">You have two options for creating the table-valued wrapper function that calls the change data capture query function:</span></span>  
  
-   <span data-ttu-id="9293d-123">Você chamar o procedimento armazenado de sistema **sys.sp_cdc_generate_wrapper_function** para criar as funções com valor de tabela.</span><span class="sxs-lookup"><span data-stu-id="9293d-123">You can call the **sys.sp_cdc_generate_wrapper_function** system stored procedure to create the table-valued functions for you.</span></span>  
  
-   <span data-ttu-id="9293d-124">Você pode escrever sua própria função com valor de tabela usando as diretrizes e o exemplo neste tópico.</span><span class="sxs-lookup"><span data-stu-id="9293d-124">You can write your own table-valued function by using the guidelines and the example in this topic.</span></span>  
  
## <a name="calling-a-stored-procedure-to-create-the-table-valued-function"></a><span data-ttu-id="9293d-125">Chamando um procedimento armazenado para criar a função com valor de tabela</span><span class="sxs-lookup"><span data-stu-id="9293d-125">Calling a Stored Procedure to Create the Table-valued Function</span></span>  
 <span data-ttu-id="9293d-126">A maneira mais rápida e fácil de criar funções com valor de tabela de que você precisa é chamar o procedimento armazenado de sistema **sys.sp_cdc_generate_wrapper_function** .</span><span class="sxs-lookup"><span data-stu-id="9293d-126">The quickest and easiest way to create the table-valued functions that you need is to call the **sys.sp_cdc_generate_wrapper_function** system stored procedure.</span></span> <span data-ttu-id="9293d-127">Esse procedimento armazenado gera scripts para criar funções de invólucro projetadas especificamente para atender às necessidades de um componente de origem do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9293d-127">This stored procedure generates scripts to create wrapper functions that are designed specifically to meet the needs of an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] source component.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="9293d-128">O procedimento armazenado de sistema **sys.sp_cdc_generate_wrapper_function** não cria as funções de invólucro diretamente.</span><span class="sxs-lookup"><span data-stu-id="9293d-128">The **sys.sp_cdc_generate_wrapper_function** system stored procedure does not directly create the wrapper functions.</span></span> <span data-ttu-id="9293d-129">Em vez disso, o procedimento armazenado gera os scripts CREATE para as funções de invólucro.</span><span class="sxs-lookup"><span data-stu-id="9293d-129">Instead, the stored procedure generates the CREATE scripts for the wrapper functions.</span></span> <span data-ttu-id="9293d-130">O desenvolvedor deve executar os scripts CREATE gerados pelo procedimento armazenado antes de um pacote de carregamento incremental chamar as funções de invólucro.</span><span class="sxs-lookup"><span data-stu-id="9293d-130">The developer must run the CREATE scripts that the stored procedure generates before an incremental load package can call the wrapper functions.</span></span>  
  
 <span data-ttu-id="9293d-131">Para entender como usar esse procedimento armazenado de sistema, você deve entender o que o procedimento faz, quais scripts o procedimento gera e quais funções de invólucro os scripts criam.</span><span class="sxs-lookup"><span data-stu-id="9293d-131">To understand how to use this system stored procedure, you should understand what the procedure does, what scripts the procedure generates, and what wrapper functions the scripts create.</span></span>  
  
### <a name="understanding-and-using-the-stored-procedure"></a><span data-ttu-id="9293d-132">Entendendo e usando o procedimento armazenado</span><span class="sxs-lookup"><span data-stu-id="9293d-132">Understanding and Using the Stored Procedure</span></span>  
 <span data-ttu-id="9293d-133">O procedimento armazenado de sistema **sys.sp_cdc_generate_wrapper_function** gera scripts para criar funções de invólucro para uso por pacotes [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9293d-133">The **sys.sp_cdc_generate_wrapper_function** system stored procedure generates scripts to create wrapper functions for use by [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages.</span></span>  
  
 <span data-ttu-id="9293d-134">Estas são as primeiras linhas da definição do procedimento armazenado:</span><span class="sxs-lookup"><span data-stu-id="9293d-134">Here are the first few lines of the definition of the stored procedure:</span></span>  
  
 `CREATE PROCEDURE sys.sp_cdc_generate_wrapper_function`  
  
 `(`  
  
 `@capture_instance sysname = null`  
  
 `@closed_high_end_point bit = 1,`  
  
 `@column_list = null,`  
  
 `@update_flag_list = null`  
  
 `)`  
  
 <span data-ttu-id="9293d-135">Todos os parâmetros do procedimento armazenado são opcionais.</span><span class="sxs-lookup"><span data-stu-id="9293d-135">All the parameters for the stored procedure are optional.</span></span> <span data-ttu-id="9293d-136">Se você chamar o procedimento armazenado sem fornecer valores para nenhum dos parâmetros, o procedimento armazenado criará funções de invólucro para todas as instâncias de captura às quais você tem acesso.</span><span class="sxs-lookup"><span data-stu-id="9293d-136">If you call the stored procedure without supplying values for any of the parameters, the stored procedure creates wrapper functions for all the capture instances to which you have access.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9293d-137">Para obter mais informações sobre a sintaxe desse procedimento armazenado e seus parâmetros, consulte [sys.sp_cdc_generate_wrapper_function &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sys-sp-cdc-generate-wrapper-function-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="9293d-137">For more information about the syntax of this stored procedure and its parameters, see [sys.sp_cdc_generate_wrapper_function &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sys-sp-cdc-generate-wrapper-function-transact-sql).</span></span>  
  
 <span data-ttu-id="9293d-138">O procedimento armazenado sempre gera uma função de invólucro para retornar todas as alterações de cada instância de captura.</span><span class="sxs-lookup"><span data-stu-id="9293d-138">The stored procedure always generates a wrapper function to return all changes from each capture instance.</span></span> <span data-ttu-id="9293d-139">Se o *@supports_net_changes* parâmetro foi definido quando a instância de captura foi criada, o procedimento armazenado também gera uma função de wrapper para retornar as alterações líquidas de cada instância de captura aplicável.</span><span class="sxs-lookup"><span data-stu-id="9293d-139">If the *@supports_net_changes* parameter was set when the capture instance was created, the stored procedure also generates a wrapper function to return net changes from each applicable capture instance.</span></span>  
  
 <span data-ttu-id="9293d-140">O procedimento armazenado retorna um conjunto de resultados com duas colunas:</span><span class="sxs-lookup"><span data-stu-id="9293d-140">The stored procedure returns a result set with two columns:</span></span>  
  
-   <span data-ttu-id="9293d-141">O nome da função de invólucro que o procedimento armazenado gerou.</span><span class="sxs-lookup"><span data-stu-id="9293d-141">The name of the wrapper function that the stored procedure has generated.</span></span> <span data-ttu-id="9293d-142">Esse procedimento armazenado deriva o nome da função do nome do nome da instância de captura.</span><span class="sxs-lookup"><span data-stu-id="9293d-142">This stored procedure derives the function name from the name of the capture instance name.</span></span> <span data-ttu-id="9293d-143">(O nome da função é 'fn_all_changes_' seguido pelo nome da instância de captura.</span><span class="sxs-lookup"><span data-stu-id="9293d-143">(The function name is 'fn_all_changes_' followed by the capture instance name.</span></span> <span data-ttu-id="9293d-144">O prefixo usado para a função de alterações globais, se for criado, será 'fn_net_changes_'.)</span><span class="sxs-lookup"><span data-stu-id="9293d-144">The prefix used for the net changes function, if it is created, is 'fn_net_changes_'.)</span></span>  
  
-   <span data-ttu-id="9293d-145">A instrução CREATE da função de invólucro.</span><span class="sxs-lookup"><span data-stu-id="9293d-145">The CREATE statement for the wrapper function.</span></span>  
  
### <a name="understanding-and-using-the-scripts-created-by-the-stored-procedure"></a><span data-ttu-id="9293d-146">Entendendo e usando os scripts criados pelo procedimento armazenado</span><span class="sxs-lookup"><span data-stu-id="9293d-146">Understanding and Using the Scripts Created by the Stored Procedure</span></span>  
 <span data-ttu-id="9293d-147">Em geral, um desenvolvedor usa uma instrução INSERT...EXEC para chamar o procedimento armazenado **sys.sp_cdc_generate_wrapper_function** e salvar os scripts criados por esse procedimento em uma tabela temporária.</span><span class="sxs-lookup"><span data-stu-id="9293d-147">Typically, a developer would use an INSERT...EXEC statement to call the **sys.sp_cdc_generate_wrapper_function** stored procedure and save the scripts that the stored procedure creates to a temporary table.</span></span> <span data-ttu-id="9293d-148">Cada script pode ser selecionado executado individualmente para criar a função de invólucro correspondente.</span><span class="sxs-lookup"><span data-stu-id="9293d-148">Each script could then be individually selected and run to create the corresponding wrapper function.</span></span> <span data-ttu-id="9293d-149">No entanto, um desenvolvedor também pode usar um conjunto de comandos SQL para executar todos os scripts CREATE, conforme mostrado no código de exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="9293d-149">However, a developer could also use one set of SQL commands to run all the CREATE scripts, as shown in the following sample code:</span></span>  
  
```  
create table #wrapper_functions  
      (function_name sysname, create_stmt nvarchar(max))  
insert into #wrapper_functions  
exec sys.sp_cdc_generate_wrapper_function  
  
declare @stmt nvarchar(max)  
declare #hfunctions cursor local fast_forward for   
      select create_stmt from #wrapper_functions  
open #hfunctions  
fetch #hfunctions into @stmt  
while (@@fetch_status <> -1)  
begin  
      exec sp_executesql @stmt  
      fetch #hfunctions into @stmt  
end  
close #hfunctions  
deallocate #hfunctions  
```  
  
### <a name="understanding-and-using-the-functions-created-by-the-stored-procedure"></a><span data-ttu-id="9293d-150">Entendendo e usando as funções criadas pelo procedimento armazenado</span><span class="sxs-lookup"><span data-stu-id="9293d-150">Understanding and Using the Functions Created by the Stored Procedure</span></span>  
 <span data-ttu-id="9293d-151">Para percorrer sistematicamente a linha do tempo dos dados de alteração capturados, as funções de wrapper geradas esperam que o *@end_time* parâmetro de um intervalo seja o *@start_time* parâmetro para o intervalo subsequente.</span><span class="sxs-lookup"><span data-stu-id="9293d-151">To systematically walk the timeline of captured change data, the generated wrapper functions expect that the *@end_time* parameter for one interval will be the *@start_time* parameter for the subsequent interval.</span></span> <span data-ttu-id="9293d-152">Quando essa convenção é seguida, as funções de invólucro geradas podem executar as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="9293d-152">When this convention is followed, the generated wrapper functions can do the following tasks:</span></span>  
  
-   <span data-ttu-id="9293d-153">Mapear os valores de data/hora para os valores LSN usados interiormente.</span><span class="sxs-lookup"><span data-stu-id="9293d-153">Map the date/time values to the LSN values that are used internally.</span></span>  
  
-   <span data-ttu-id="9293d-154">Assegurar que nenhum dado seja perdido ou repetido.</span><span class="sxs-lookup"><span data-stu-id="9293d-154">Ensure that no data is lost or repeated.</span></span>  
  
 <span data-ttu-id="9293d-155">Para simplificar a consulta a todas as linhas de uma alteração, as funções de invólucro geradas também dão suporte às seguintes convenções:</span><span class="sxs-lookup"><span data-stu-id="9293d-155">To make querying for all rows of a change table simpler, the generated wrapper functions also support the following conventions:</span></span>  
  
-   <span data-ttu-id="9293d-156">Se o parâmetro @start_time for nulo, as funções wrapper usarão o valor LSN mais baixo na instância de captura do limite inferior da consulta.</span><span class="sxs-lookup"><span data-stu-id="9293d-156">If the @start_time parameter is null, the wrapper functions use the lowest LSN value in the capture instance as the lower bound of the query.</span></span>  
  
-   <span data-ttu-id="9293d-157">Se o parâmetro @end_time for nulo, as funções do wrapper usarão o valor LSN mais baixo na instância de captura do limite inferior da consulta.</span><span class="sxs-lookup"><span data-stu-id="9293d-157">If the @end_time parameter is null, the wrapper functions use the highest LSN value in the capture instance as the upper bound of the query.</span></span>  
  
 <span data-ttu-id="9293d-158">A maioria dos usuários deverá poder usar as funções de invólucro que o procedimento armazenado de sistema **sys.sp_cdc_generate_wrapper_function** cria sem modificação.</span><span class="sxs-lookup"><span data-stu-id="9293d-158">Most users should be able to use the wrapper functions that the **sys.sp_cdc_generate_wrapper_function** system stored procedure creates without modification.</span></span> <span data-ttu-id="9293d-159">No entanto, para personalizar as funções de invólucro, você tem que personalizar os scripts CREATE antes de executar os scripts.</span><span class="sxs-lookup"><span data-stu-id="9293d-159">However, to customize the wrapper functions, you have to customize the CREATE scripts before you run the scripts.</span></span>  
  
 <span data-ttu-id="9293d-160">Quando seu pacote chama as funções de invólucro, o pacote deve fornecer valores para três parâmetros.</span><span class="sxs-lookup"><span data-stu-id="9293d-160">When your package calls the wrapper functions, the package must supply values for three parameters.</span></span> <span data-ttu-id="9293d-161">Esses três parâmetros são como os três parâmetros que as funções de captura de dados de alteração usam.</span><span class="sxs-lookup"><span data-stu-id="9293d-161">These three parameters are like the three parameters that the change data capture functions use.</span></span> <span data-ttu-id="9293d-162">Esses três parâmetros são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="9293d-162">These three parameters are as follows:</span></span>  
  
-   <span data-ttu-id="9293d-163">O valor de data/hora inicial e o valor de data/hora final do intervalo.</span><span class="sxs-lookup"><span data-stu-id="9293d-163">The starting date/time value and the ending date/time value for the interval.</span></span> <span data-ttu-id="9293d-164">Enquanto as funções de invólucro usam valores de data/hora como os pontos finais do intervalo de consulta, as funções de captura de dados de alteração usam dois valores LSN como os pontos finais.</span><span class="sxs-lookup"><span data-stu-id="9293d-164">While the wrapper functions use date/time values as the end points for the query interval, the change data capture functions use two LSN values as the end points.</span></span>  
  
-   <span data-ttu-id="9293d-165">O filtro de linha.</span><span class="sxs-lookup"><span data-stu-id="9293d-165">The row filter.</span></span> <span data-ttu-id="9293d-166">Para as funções de wrapper e as funções de captura de dados de alteração, o *@row_filter_option* parâmetro é o mesmo.</span><span class="sxs-lookup"><span data-stu-id="9293d-166">For both the wrapper functions and the change data capture functions, the *@row_filter_option* parameter is the same.</span></span> <span data-ttu-id="9293d-167">Para obter mais informações, consulte [cdc.fn_cdc_get_all_changes_&#60;capture_instance&#62;  &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/cdc-fn-cdc-get-all-changes-capture-instance-transact-sql) e [cdc.fn_cdc_get_net_changes_&#60;capture_instance&#62; &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/cdc-fn-cdc-get-net-changes-capture-instance-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="9293d-167">For more information, see [cdc.fn_cdc_get_all_changes_&#60;capture_instance&#62;  &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/cdc-fn-cdc-get-all-changes-capture-instance-transact-sql) and [cdc.fn_cdc_get_net_changes_&#60;capture_instance&#62; &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/cdc-fn-cdc-get-net-changes-capture-instance-transact-sql).</span></span>  
  
 <span data-ttu-id="9293d-168">O conjunto de resultados retornado pelas funções de invólucro inclui os seguintes dados:</span><span class="sxs-lookup"><span data-stu-id="9293d-168">The result set returned by the wrapper functions includesthe following data:</span></span>  
  
-   <span data-ttu-id="9293d-169">Todas as colunas solicitadas de dados de alteração.</span><span class="sxs-lookup"><span data-stu-id="9293d-169">All of the requested columns of change data.</span></span>  
  
-   <span data-ttu-id="9293d-170">Uma coluna denominada __CDC_OPERATION que usa um campo de um ou dois caracteres para identificar a operação associada à linha.</span><span class="sxs-lookup"><span data-stu-id="9293d-170">A column named __CDC_OPERATION that uses a one- or two-character field to identify the operation that is associated with the row.</span></span> <span data-ttu-id="9293d-171">Os valores válidos para esse campo são os seguintes: “I” de inserir, “D” de excluir, “UO” de atualizar valores antigos e “UN” de atualizar valores novos.</span><span class="sxs-lookup"><span data-stu-id="9293d-171">The valid values for this field are as follows: 'I' for insert, 'D' for delete, 'UO' for update old values, and 'UN' for update new values.</span></span>  
  
-   <span data-ttu-id="9293d-172">Os sinalizadores de atualização, quando solicitados, que aparecem como colunas de bits após o código da operação e na ordem especificada no *@update_flag_list* parâmetro.</span><span class="sxs-lookup"><span data-stu-id="9293d-172">Update flags, when you request them, that appear as bit columns after the operation code and in the order that is specified in the *@update_flag_list* parameter.</span></span> <span data-ttu-id="9293d-173">Essas colunas são denominadas com a anexação de '_uflag' ao nome de coluna associado.</span><span class="sxs-lookup"><span data-stu-id="9293d-173">These columns are named by appending '_uflag' to the associated column name.</span></span>  
  
 <span data-ttu-id="9293d-174">Se o pacote chamar uma função de wrapper que consulte todas as alterações, essa função também retornará as colunas __CDC_STARTLSN e \__CDC_SEQVAL.</span><span class="sxs-lookup"><span data-stu-id="9293d-174">If your package calls a wrapper function that queries for all changes, the wrapper function also returns the columns, __CDC_STARTLSN and \__CDC_SEQVAL.</span></span> <span data-ttu-id="9293d-175">Essas duas colunas se tornam a primeira e a segunda colunas, respectivamente, do conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="9293d-175">These two columns become the first and second columns, respectively, of the result set.</span></span> <span data-ttu-id="9293d-176">A função de invólucro também classifica o conjunto de resultados com base nessas duas colunas.</span><span class="sxs-lookup"><span data-stu-id="9293d-176">The wrapper function also sorts the result set based on these two columns.</span></span>  
  
## <a name="writing-your-own-table-value-function"></a><span data-ttu-id="9293d-177">Escrevendo sua própria função do valor de tabela</span><span class="sxs-lookup"><span data-stu-id="9293d-177">Writing Your Own Table-Value Function</span></span>  
 <span data-ttu-id="9293d-178">Também é possível usar [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] para escrever sua própria função de wrapper com valor de tabela que chama a função de consulta de captura dos dados de alteração e armazena a função de wrapper com valor de tabela no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9293d-178">You can also use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to write your own table-valued wrapper function that calls the change data capture query function, and store the table-valued wrapper function in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="9293d-179">Para obter mais informações sobre como criar uma função Transact-SQL, consulte [CREATE FUNCTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-function-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="9293d-179">For more information about how to create a Transact-SQL function, see [CREATE FUNCTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-function-transact-sql).</span></span>  
  
 <span data-ttu-id="9293d-180">O seguinte exemplo define uma função com valor de tabela que recupera alterações de uma tabela Cliente para o intervalo de alteração especificado.</span><span class="sxs-lookup"><span data-stu-id="9293d-180">The following example defines a table-valued function that retrieves changes from a Customer table for the specified change interval.</span></span> <span data-ttu-id="9293d-181">Essa função usa funções de captura de dados de alteração para mapear os valores `datetime` para os valores LSN (número de sequência de log) binários usados pelas tabelas de alteração internamente.</span><span class="sxs-lookup"><span data-stu-id="9293d-181">This function uses change data capture functions to map the `datetime` values to the binary log sequence number (LSN) values that the change tables use internally.</span></span> <span data-ttu-id="9293d-182">Esta função também controla diversas condições especiais:</span><span class="sxs-lookup"><span data-stu-id="9293d-182">This function also handles several special conditions:</span></span>  
  
-   <span data-ttu-id="9293d-183">Quando um valor nulo é passado como a hora inicial, essa função usa o valor mais baixo disponível.</span><span class="sxs-lookup"><span data-stu-id="9293d-183">When a null value is passed for the starting time, this function uses the earliest available value.</span></span>  
  
-   <span data-ttu-id="9293d-184">Quando um valor nulo é passado como a hora final, essa função usa o valor mais alto disponível.</span><span class="sxs-lookup"><span data-stu-id="9293d-184">When a null value is passed for the ending time, this function uses the latest available value.</span></span>  
  
-   <span data-ttu-id="9293d-185">Quando o LSN inicial é igual ao LSN final, que normalmente indica que não existe registros para o intervalo selecionado, essa função é encerrada.</span><span class="sxs-lookup"><span data-stu-id="9293d-185">When the starting LSN is equal to the ending LSN, which usually indicates that there are no records for the selected interval, this function exits.</span></span>  
  
### <a name="example-of-a-table-value-function-that-queries-for-change-data"></a><span data-ttu-id="9293d-186">Exemplo de uma função com valor de tabela que consulta a existência de dados de alteração</span><span class="sxs-lookup"><span data-stu-id="9293d-186">Example of a Table-Value Function that Queries for Change Data</span></span>  
  
```  
CREATE function CDCSample.uf_Customer (  
     @start_time datetime  
    ,@end_time datetime  
)  
returns @Customer table (  
     CustomerID int  
    ,TerritoryID int  
    ,CustomerType nchar(1)  
    ,rowguid uniqueidentifier  
    ,ModifiedDate datetime  
    ,CDC_OPERATION varchar(1)  
) as  
begin  
    declare @from_lsn binary(10), @to_lsn binary(10)  
  
    if (@start_time is null)  
        select @from_lsn = sys.fn_cdc_get_min_lsn('Customer')  
    else  
        select @from_lsn = sys.fn_cdc_increment_lsn(sys.fn_cdc_map_time_to_lsn('largest less than or equal',@start_time))  
  
    if (@end_time is null)  
        select @to_lsn = sys.fn_cdc_get_max_lsn()  
    else  
        select @to_lsn = sys.fn_cdc_map_time_to_lsn('largest less than or equal',@end_time)  
  
    if (@from_lsn = sys.fn_cdc_increment_lsn(@to_lsn))  
        return  
  
    -- Query for change data  
    insert into @Customer  
    select   
        CustomerID,      
        TerritoryID,   
        CustomerType,   
        rowguid,   
        ModifiedDate,   
        case __$operation  
                when 1 then 'D'  
                when 2 then 'I'  
                when 4 then 'U'  
                else null  
         end as CDC_OPERATION  
    from   
        cdc.fn_cdc_get_net_changes_Customer(@from_lsn, @to_lsn, 'all')  
  
    return  
end   
go  
  
```  
  
### <a name="retrieving-additional-metadata-with-the-change-data"></a><span data-ttu-id="9293d-187">Recuperando metadados adicionais com os dados de alteração</span><span class="sxs-lookup"><span data-stu-id="9293d-187">Retrieving Additional Metadata with the Change Data</span></span>  
 <span data-ttu-id="9293d-188">Embora a função com valor de tabela criada pelo usuário mostrada anteriormente use apenas a coluna **__$operation**, a função **cdc.fn_cdc_get_net_changes_<capture_instance>** retorna quatro colunas de metadados para cada linha de alteração.</span><span class="sxs-lookup"><span data-stu-id="9293d-188">Although the user-created table-valued function shown earlier uses only the **__$operation** column, the **cdc.fn_cdc_get_net_changes_<capture_instance>** function returns four columns of metadata for each change row.</span></span> <span data-ttu-id="9293d-189">Se quiser usar esses valores no seu fluxo de dados, poderá retorná-los como colunas adicionais com a função de invólucro com valor de tabela.</span><span class="sxs-lookup"><span data-stu-id="9293d-189">If you want to use these values in your data flow, you can return them as additional columns from the table-valued wrapper function.</span></span>  
  
|<span data-ttu-id="9293d-190">Nome da coluna</span><span class="sxs-lookup"><span data-stu-id="9293d-190">Column name</span></span>|<span data-ttu-id="9293d-191">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="9293d-191">Data type</span></span>|<span data-ttu-id="9293d-192">Descrição</span><span class="sxs-lookup"><span data-stu-id="9293d-192">Description</span></span>|  
|-----------------|---------------|-----------------|  
|<span data-ttu-id="9293d-193">**__$start_lsn**</span><span class="sxs-lookup"><span data-stu-id="9293d-193">**__$start_lsn**</span></span>|`binary(10)`|<span data-ttu-id="9293d-194">LSN associado à transação de confirmação da alteração.</span><span class="sxs-lookup"><span data-stu-id="9293d-194">LSN associated with the commit transaction for the change.</span></span><br /><br /> <span data-ttu-id="9293d-195">Todas as alterações confirmadas na mesma transação compartilham o mesmo LSN de confirmação.</span><span class="sxs-lookup"><span data-stu-id="9293d-195">All changes committed in the same transaction share the same commit LSN.</span></span> <span data-ttu-id="9293d-196">Por exemplo, se uma operação de atualização na tabela de origem modificar duas linhas diferentes, a tabela de alteração conterá quatro linhas (duas com os valores antigos e duas com os valores novos), cada uma com o mesmo valor de **__$start_lsn** .</span><span class="sxs-lookup"><span data-stu-id="9293d-196">For example, if an update operation on the source table modifies two different rows, the change table will contain four rows (two with the old values and two with the new values), each with the same **__$start_lsn** value.</span></span>|  
|<span data-ttu-id="9293d-197">**__$seqval**</span><span class="sxs-lookup"><span data-stu-id="9293d-197">**__$seqval**</span></span>|`binary(10)`|<span data-ttu-id="9293d-198">Valor de sequência usado para organizar as alterações de linha em uma transação.</span><span class="sxs-lookup"><span data-stu-id="9293d-198">Sequence value that is used to order the row changes in a transaction.</span></span>|  
|<span data-ttu-id="9293d-199">**__$operation**</span><span class="sxs-lookup"><span data-stu-id="9293d-199">**__$operation**</span></span>|`int`|<span data-ttu-id="9293d-200">A operação DML (linguagem de manipulação de dados) associada à alteração.</span><span class="sxs-lookup"><span data-stu-id="9293d-200">The data manipulation language (DML) operation associated with the change.</span></span> <span data-ttu-id="9293d-201">Um dos seguintes pode ser feito:</span><span class="sxs-lookup"><span data-stu-id="9293d-201">Can be one of the following:</span></span><br /><br /> <span data-ttu-id="9293d-202">1 = excluir</span><span class="sxs-lookup"><span data-stu-id="9293d-202">1 = delete</span></span><br /><br /> <span data-ttu-id="9293d-203">2 = inserir</span><span class="sxs-lookup"><span data-stu-id="9293d-203">2 = insert</span></span><br /><br /> <span data-ttu-id="9293d-204">3 = atualizar (valores anteriores à operação de atualização).</span><span class="sxs-lookup"><span data-stu-id="9293d-204">3 = update (Values before the update operation.)</span></span><br /><br /> <span data-ttu-id="9293d-205">4 = atualizar (valores posteriores à operação de atualização).</span><span class="sxs-lookup"><span data-stu-id="9293d-205">4 = update (Values after the update operation.)</span></span>|  
|<span data-ttu-id="9293d-206">**__$update_mask**</span><span class="sxs-lookup"><span data-stu-id="9293d-206">**__$update_mask**</span></span>|`varbinary(128)`|<span data-ttu-id="9293d-207">Uma máscara de bits com base nos ordinais de coluna da tabela de alteração identificando as colunas que foram alteradas.</span><span class="sxs-lookup"><span data-stu-id="9293d-207">A bitmask that is based on the column ordinals of the change table identifying those columns that changed.</span></span> <span data-ttu-id="9293d-208">Você poderia examinar este valor se você tivesse que determinar quais colunas foram alteradas.</span><span class="sxs-lookup"><span data-stu-id="9293d-208">You could examine this value if you had to determine which columns have changed.</span></span>|  
|**\<captured source table columns>**|<span data-ttu-id="9293d-209">varia</span><span class="sxs-lookup"><span data-stu-id="9293d-209">varies</span></span>|<span data-ttu-id="9293d-210">As colunas restantes retornadas pela função são as colunas da tabela de origem que foram identificadas como colunas capturadas quando a instância de captura foi criada.</span><span class="sxs-lookup"><span data-stu-id="9293d-210">The remaining columns returned by the function are the columns from the source table that were identified as captured columns when the capture instance was created.</span></span> <span data-ttu-id="9293d-211">Se nenhuma coluna tiver sido especificada originalmente na lista de colunas capturadas, todas as colunas da tabela de origem serão retornadas.</span><span class="sxs-lookup"><span data-stu-id="9293d-211">If no columns were originally specified in the captured column list, all columns in the source table are returned.</span></span>|  
  
 <span data-ttu-id="9293d-212">Para obter mais informações, veja [cdc.fn_cdc_get_net_changes_&#60;capture_instance&#62; &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/cdc-fn-cdc-get-net-changes-capture-instance-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="9293d-212">For more information, see [cdc.fn_cdc_get_net_changes_&#60;capture_instance&#62; &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/cdc-fn-cdc-get-net-changes-capture-instance-transact-sql).</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="9293d-213">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="9293d-213">Next Step</span></span>  
 <span data-ttu-id="9293d-214">Após ter criado a função com valor de tabela que consulta a existência de dados de alteração, a próxima etapa será iniciar a criação do fluxo de dados no pacote.</span><span class="sxs-lookup"><span data-stu-id="9293d-214">After you have created the table-valued function that queries for change data, the next step is to start designing the data flow in the package.</span></span>  
  
 <span data-ttu-id="9293d-215">**Próximo tópico:** [Recuperar e compreender os dados de alterações](retrieve-and-understand-the-change-data.md)</span><span class="sxs-lookup"><span data-stu-id="9293d-215">**Next topic:** [Retrieve and Understand the Change Data](retrieve-and-understand-the-change-data.md)</span></span>  
  
  
