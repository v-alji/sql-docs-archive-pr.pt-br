---
title: Origem CDC | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.designer.cdcsource.f1
ms.assetid: 99775608-e177-44ed-bb44-aaccb0f4f327
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 064c25b129364dfcd813d71a462586303dd4ff60
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582569"
---
# <a name="cdc-source"></a><span data-ttu-id="c02cc-102">Origem CDC</span><span class="sxs-lookup"><span data-stu-id="c02cc-102">CDC Source</span></span>
  <span data-ttu-id="c02cc-103">A origem CDC lê um intervalo de dados de alteração de tabelas de alteração do [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] e entrega o downstream de alterações a outros SSIS componentes.</span><span class="sxs-lookup"><span data-stu-id="c02cc-103">The CDC source reads a range of change data from [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] change tables and delivers the changes downstream to other SSIS components.</span></span>  
  
 <span data-ttu-id="c02cc-104">O intervalo de leitura de dados de alteração pela origem CDC é chamado Intervalo de Processamento CDC e é determinado pela tarefa Controle de CDC que é executada antes do início do fluxo de dados atual.</span><span class="sxs-lookup"><span data-stu-id="c02cc-104">The range of change data read by the CDC source is called the CDC Processing Range and is determine by the CDC Control task that is executed before the current data flow starts.</span></span> <span data-ttu-id="c02cc-105">O Intervalo de Processamento CDC é derivado do valor de uma variável de pacote que mantém o estado do processamento CDC para um grupo de tabelas.</span><span class="sxs-lookup"><span data-stu-id="c02cc-105">The CDC Processing Range is derived from the value of a package variable that maintains the state of the CDC processing for a group of tables.</span></span>  
  
 <span data-ttu-id="c02cc-106">A origem CDC extrai dados de um banco de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usando uma tabela de banco de dados, uma exibição ou uma instrução SQL.</span><span class="sxs-lookup"><span data-stu-id="c02cc-106">The CDC source extracts data from a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database by using a database table, a view, or an SQL statement.</span></span>  
  
 <span data-ttu-id="c02cc-107">A origem CDC usa as configurações seguintes:</span><span class="sxs-lookup"><span data-stu-id="c02cc-107">The CDC source uses the following configurations:</span></span>  
  
-   <span data-ttu-id="c02cc-108">Um gerenciador de conexões [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ADO.NET para acessar o banco de dados [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] CDC.</span><span class="sxs-lookup"><span data-stu-id="c02cc-108">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ADO.NET connection manager to access the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] CDC database.</span></span> <span data-ttu-id="c02cc-109">Para obter mais informações sobre como configurar a conexão de origem CDC, consulte [Editor de Origem CDC &#40;Página Gerenciador de Conexões&#41;](../cdc-source-editor-connection-manager-page.md).</span><span class="sxs-lookup"><span data-stu-id="c02cc-109">For more information about configuring the CDC source connection, see [CDC Source Editor &#40;Connection Manager Page&#41;](../cdc-source-editor-connection-manager-page.md).</span></span>  
  
-   <span data-ttu-id="c02cc-110">Uma tabela habilitada para CDC.</span><span class="sxs-lookup"><span data-stu-id="c02cc-110">A table enabled for CDC.</span></span>  
  
-   <span data-ttu-id="c02cc-111">O nome da instância de captura da tabela selecionada (se houver mais de uma).</span><span class="sxs-lookup"><span data-stu-id="c02cc-111">The name of the capture instance of the selected table (if more-than-one exists).</span></span>  
  
-   <span data-ttu-id="c02cc-112">O modo de processamento de alteração.</span><span class="sxs-lookup"><span data-stu-id="c02cc-112">The change processing mode.</span></span>  
  
-   <span data-ttu-id="c02cc-113">O nome da variável de pacote do estado CDC com base no qual o intervalo de Processamento CDC é determinado.</span><span class="sxs-lookup"><span data-stu-id="c02cc-113">The name of the CDC state package variable based on which the CDC Processing range is determined.</span></span> <span data-ttu-id="c02cc-114">A origem CDC não modifica essa variável.</span><span class="sxs-lookup"><span data-stu-id="c02cc-114">The CDC source does not modify that variable.</span></span>  
  
 <span data-ttu-id="c02cc-115">Os dados retornados pela Origem CDC são iguais aos retornados pelas funções do CDC [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **cdc.fn_cdc_get_all_changes_\<capture-instance-name>** ou **cdc.fn_cdc_get_net_changes_\<capture-instance-name>** (quando disponível).</span><span class="sxs-lookup"><span data-stu-id="c02cc-115">The data returned by the CDC Source is the same as that returned by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] CDC functions **cdc.fn_cdc_get_all_changes_\<capture-instance-name>** or **cdc.fn_cdc_get_net_changes_\<capture-instance-name>** (when available).</span></span> <span data-ttu-id="c02cc-116">A única adição opcional é a coluna, **__$initial_processing** , que indica se o intervalo de processamento atual pode se sobrepor a uma carga inicial da tabela.</span><span class="sxs-lookup"><span data-stu-id="c02cc-116">The only optional addition is the column, **__$initial_processing** that indicates whether the current processing range can overlap with an initial load of the table.</span></span> <span data-ttu-id="c02cc-117">Para obter mais informações sobre o processamento inicial, consulte [CDC Control Task](../control-flow/cdc-control-task.md).</span><span class="sxs-lookup"><span data-stu-id="c02cc-117">For more information about initial processing, see [CDC Control Task](../control-flow/cdc-control-task.md).</span></span>  
  
 <span data-ttu-id="c02cc-118">A origem CDC tem uma saída regular e uma saída de erro.</span><span class="sxs-lookup"><span data-stu-id="c02cc-118">The CDC source has one regular output and one error output.</span></span>  
  
## <a name="error-handling"></a><span data-ttu-id="c02cc-119">Tratamento de erros</span><span class="sxs-lookup"><span data-stu-id="c02cc-119">Error Handling</span></span>  
 <span data-ttu-id="c02cc-120">A origem CDC tem uma saída de erro.</span><span class="sxs-lookup"><span data-stu-id="c02cc-120">The CDC source has an error output.</span></span> <span data-ttu-id="c02cc-121">A saída de erro de componente inclui as colunas de saída seguintes:</span><span class="sxs-lookup"><span data-stu-id="c02cc-121">The component error output includes the following output columns:</span></span>  
  
-   <span data-ttu-id="c02cc-122">**Código de Erro**: o valor sempre é -1.</span><span class="sxs-lookup"><span data-stu-id="c02cc-122">**Error Code**: The value is always -1.</span></span>  
  
-   <span data-ttu-id="c02cc-123">**Coluna de Erro**: a coluna de origem que causa o erro (para erros de conversão).</span><span class="sxs-lookup"><span data-stu-id="c02cc-123">**Error Column**: The source column causing the error (for conversion errors).</span></span>  
  
-   <span data-ttu-id="c02cc-124">**Colunas de Linha de Erro**: os dados de registro que causam o erro.</span><span class="sxs-lookup"><span data-stu-id="c02cc-124">**Error Row Columns**: The record data that causes the error.</span></span>  
  
 <span data-ttu-id="c02cc-125">Dependendo da configuração de comportamento de erro, a origem CDC oferece suporte ao retorno de erros (conversão de dados, truncamento) que ocorre durante o processo de extração na saída de erro.</span><span class="sxs-lookup"><span data-stu-id="c02cc-125">Depending on the error behavior setting, the CDC source supports returning errors (data conversion, truncation) that occur during the extraction process in the error output.</span></span> <span data-ttu-id="c02cc-126">Para obter mais informações, consulte [Editor de Origem CDC &#40;Página Saída de Erro&#41;](../cdc-source-editor-error-output-page.md).</span><span class="sxs-lookup"><span data-stu-id="c02cc-126">For more information, see [CDC Source Editor &#40;Error Output Page&#41;](../cdc-source-editor-error-output-page.md).</span></span>  
  
## <a name="data-type-support"></a><span data-ttu-id="c02cc-127">Suporte do tipo de dados</span><span class="sxs-lookup"><span data-stu-id="c02cc-127">Data Type Support</span></span>  
 <span data-ttu-id="c02cc-128">O componente origem CDC para Microsoft oferece suporte a todos os tipos de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que estão mapeados para os tipos de dados SSIS corretos.</span><span class="sxs-lookup"><span data-stu-id="c02cc-128">The CDC source component for Microsoft supports all [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data types, which are mapped to the correct SSIS data types.</span></span>  
  
## <a name="troubleshooting-the-cdc-source"></a><span data-ttu-id="c02cc-129">Solucionando problemas da origem CDC</span><span class="sxs-lookup"><span data-stu-id="c02cc-129">Troubleshooting the CDC Source</span></span>  
 <span data-ttu-id="c02cc-130">A seguir são apresentadas informações sobre como solucionar problemas de origem CDC.</span><span class="sxs-lookup"><span data-stu-id="c02cc-130">The following contains information on troubleshooting the CDC source.</span></span>  
  
### <a name="use-this-script-to-isolate-problems-and-reproduce-them-in-sql-server-management-studio"></a><span data-ttu-id="c02cc-131">Use este script para isolar problemas e reproduzi-los no SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c02cc-131">Use this script to isolate problems and reproduce them in SQL Server Management Studio</span></span>  
 <span data-ttu-id="c02cc-132">Uma operação de origem CDC é governada pela operação da tarefa Controle CDC executada antes da chamada à origem CDC.</span><span class="sxs-lookup"><span data-stu-id="c02cc-132">The CDC source operation is governed by the operation of the CDC Control task executed before invoking the CDC source.</span></span> <span data-ttu-id="c02cc-133">A tarefa Controle CDC prepara o valor da variável de pacote do estado CDC para conter LSNs de início e término.</span><span class="sxs-lookup"><span data-stu-id="c02cc-133">The CDC Control task prepares the value of the CDC state package variable to contain the start and end LSNs.</span></span> <span data-ttu-id="c02cc-134">Ela executa uma função equivalente ao seguinte script:</span><span class="sxs-lookup"><span data-stu-id="c02cc-134">It performs function equivalent to the following script:</span></span>  
  
```  
use <cdc-enabled-database-name>  
               declare @start_lsn binary(10), @end_lsn binary(10)  
               set @start_lsn = sys.fn_cdc_increment_lsn(  
                       convert(binary(10),'0x' + '<value-from-state-cs>', 1))  
               set @end_lsn =   
                       convert(binary(10),'0x' + '<value-from-state-ce>', 1)  
               select * from cdc.fn_cdc_get_net_changes_dbo_Table1(@start_lsn,  
@end_lsn, '<mode>')  
```  
  
 <span data-ttu-id="c02cc-135">onde:</span><span class="sxs-lookup"><span data-stu-id="c02cc-135">where:</span></span>  
  
-   <span data-ttu-id="c02cc-136">\<cdc-enabled-database-name> é o nome do banco de dados [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que contém a tabela de alteração.</span><span class="sxs-lookup"><span data-stu-id="c02cc-136">\<cdc-enabled-database-name> is the name of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database containing the change tables.</span></span>  
  
-   <span data-ttu-id="c02cc-137">\<value-from-state-cs> é o valor que aparece na variável de estado CDC como CS/\<value-from-state-cs>/ (CS significa Current-processing-range-Start, ou seja, início do intervalo de processamento atual).</span><span class="sxs-lookup"><span data-stu-id="c02cc-137">\<value-from-state-cs> is the value that appears in the CDC state variable as CS/\<value-from-state-cs>/ (CS stands for Current-processing-range-Start).</span></span>  
  
-   <span data-ttu-id="c02cc-138">\<value-from-state-ce> é o valor que aparece na variável de estado CDC como em CE/\<value-from-state-cs>/ (CE significa Current-processing-range-End, ou seja, fim do intervalo de processamento atual).</span><span class="sxs-lookup"><span data-stu-id="c02cc-138">\<value-from-state-ce> is the value that appears in the CDC state variable as CE/\<value-from-state-cs>/ (CE stands for Current-processing-range-End).</span></span>  
  
-   <span data-ttu-id="c02cc-139">\<mode> são aos modos de processamento CDC.</span><span class="sxs-lookup"><span data-stu-id="c02cc-139">\<mode> are the CDC processing modes.</span></span> <span data-ttu-id="c02cc-140">Os modos de processamento têm um dos seguintes valores: **Tudo**, **Tudo com Valores Antigos**, **Rede**, **Rede com Máscara de Atualização**, **Rede com Mesclagem**.</span><span class="sxs-lookup"><span data-stu-id="c02cc-140">The processing modes have one of the following values **All**, **All with Old Values**, **Net**, **Net with Update Mask**, **Net with Merge**.</span></span>  
  
 <span data-ttu-id="c02cc-141">Este script ajuda a isolar problemas reproduzindo-os no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], onde é fácil reproduzir e identificar erros.</span><span class="sxs-lookup"><span data-stu-id="c02cc-141">This script helps isolate problems by reproducing them in the [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], where it is easy to reproduce and identify errors.</span></span>  
  
#### <a name="sql-server-error-message"></a><span data-ttu-id="c02cc-142">Mensagem de erro do SQL Server</span><span class="sxs-lookup"><span data-stu-id="c02cc-142">SQL Server Error Message</span></span>  
 <span data-ttu-id="c02cc-143">A mensagem seguinte poderá ser retornada pelo [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="c02cc-143">The following message may be returned by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
 <span data-ttu-id="c02cc-144">**Um número insuficiente de argumentos foram fornecidos ao procedimento ou função cdc.fn_cdc_get_net_changes_\<..>.**</span><span class="sxs-lookup"><span data-stu-id="c02cc-144">**An insufficient number of arguments were supplied for the procedure or function cdc.fn_cdc_get_net_changes_\<..>.**</span></span>  
  
 <span data-ttu-id="c02cc-145">Esse erro não indica que um argumento está faltando.</span><span class="sxs-lookup"><span data-stu-id="c02cc-145">This error does not indicate that an argument is missing.</span></span> <span data-ttu-id="c02cc-146">Significa que os valores de LSN de início ou fim na variável de estado CDC são inválidos.</span><span class="sxs-lookup"><span data-stu-id="c02cc-146">It means that the start or end LSN values in the CDC state variable are invalid.</span></span>  
  
## <a name="configuring-the-cdc-source"></a><span data-ttu-id="c02cc-147">Configurando a origem CDC</span><span class="sxs-lookup"><span data-stu-id="c02cc-147">Configuring the CDC Source</span></span>  
 <span data-ttu-id="c02cc-148">Você pode configurar a origem CDC programaticamente ou por meio do SSIS Designer.</span><span class="sxs-lookup"><span data-stu-id="c02cc-148">You can configure the CDC source programmatically or through the SSIS Designer.</span></span>  
  
 <span data-ttu-id="c02cc-149">Para obter mais informações, consulte um dos tópicos a seguir.</span><span class="sxs-lookup"><span data-stu-id="c02cc-149">For more information, see one of the following topics:</span></span>  
  
-   [<span data-ttu-id="c02cc-150">Editor de Origem CDC &#40;Página Gerenciador de Conexões&#41;</span><span class="sxs-lookup"><span data-stu-id="c02cc-150">CDC Source Editor &#40;Connection Manager Page&#41;</span></span>](../cdc-source-editor-connection-manager-page.md)  
  
-   [<span data-ttu-id="c02cc-151">Editor de Origem CDC &#40;página Colunas&#41;</span><span class="sxs-lookup"><span data-stu-id="c02cc-151">CDC Source Editor &#40;Columns Page&#41;</span></span>](../cdc-source-editor-columns-page.md)  
  
-   [<span data-ttu-id="c02cc-152">Editor de Origem CDC &#40;Página Saída de Erro&#41;</span><span class="sxs-lookup"><span data-stu-id="c02cc-152">CDC Source Editor &#40;Error Output Page&#41;</span></span>](../cdc-source-editor-error-output-page.md)  
  
 <span data-ttu-id="c02cc-153">A caixa de diálogo **Editor Avançado** contém as propriedades que podem ser definidas programaticamente.</span><span class="sxs-lookup"><span data-stu-id="c02cc-153">The **Advanced Editor** dialog box contains the properties that can be set programmatically.</span></span>  
  
 <span data-ttu-id="c02cc-154">Para abrir a caixa de diálogo **Editor Avançado** :</span><span class="sxs-lookup"><span data-stu-id="c02cc-154">To open the **Advanced Editor** dialog box:</span></span>  
  
-   <span data-ttu-id="c02cc-155">Na tela **Fluxo de Dados** do seu projeto do [!INCLUDE[ssISCurrent](../../includes/ssiscurrent-md.md)] , clique com o botão direito do mouse na origem CDC e selecione **Mostrar Editor Avançado**.</span><span class="sxs-lookup"><span data-stu-id="c02cc-155">In the **Data Flow** screen of your [!INCLUDE[ssISCurrent](../../includes/ssiscurrent-md.md)] project, right click the CDC source and select **Show Advanced Editor**.</span></span>  
  
 <span data-ttu-id="c02cc-156">Para obter mais informações sobre as propriedades que podem ser definidas na caixa de diálogo **Editor Avançado** , consulte [CDC Source Custom Properties](cdc-source-custom-properties.md).</span><span class="sxs-lookup"><span data-stu-id="c02cc-156">For more information about the properties that you can set in the **Advanced Editor** dialog box, see [CDC Source Custom Properties](cdc-source-custom-properties.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c02cc-157">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="c02cc-157">In This Section</span></span>  
  
-   [<span data-ttu-id="c02cc-158">Editor de Origem CDC &#40;Página Gerenciador de Conexões&#41;</span><span class="sxs-lookup"><span data-stu-id="c02cc-158">CDC Source Editor &#40;Connection Manager Page&#41;</span></span>](../cdc-source-editor-connection-manager-page.md)  
  
-   [<span data-ttu-id="c02cc-159">Editor de Origem CDC &#40;página Colunas&#41;</span><span class="sxs-lookup"><span data-stu-id="c02cc-159">CDC Source Editor &#40;Columns Page&#41;</span></span>](../cdc-source-editor-columns-page.md)  
  
-   [<span data-ttu-id="c02cc-160">Editor de Origem CDC &#40;Página Saída de Erro&#41;</span><span class="sxs-lookup"><span data-stu-id="c02cc-160">CDC Source Editor &#40;Error Output Page&#41;</span></span>](../cdc-source-editor-error-output-page.md)  
  
-   [<span data-ttu-id="c02cc-161">Propriedades personalizadas da origem CDC</span><span class="sxs-lookup"><span data-stu-id="c02cc-161">CDC Source Custom Properties</span></span>](cdc-source-custom-properties.md)  
  
-   [<span data-ttu-id="c02cc-162">Extrair dados de alteração por meio da origem CDC</span><span class="sxs-lookup"><span data-stu-id="c02cc-162">Extract Change Data Using the CDC Source</span></span>](cdc-source.md)  
  
## <a name="related-content"></a><span data-ttu-id="c02cc-163">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="c02cc-163">Related Content</span></span>  
  
-   <span data-ttu-id="c02cc-164">Entrada de blog, [Modos de processamento para a origem de CDC](https://www.mattmasson.com/2012/01/processing-modes-for-the-cdc-source/), em mattmasson.com.</span><span class="sxs-lookup"><span data-stu-id="c02cc-164">Blog entry, [Processing Modes for the CDC Source](https://www.mattmasson.com/2012/01/processing-modes-for-the-cdc-source/), on mattmasson.com.</span></span>  
  
  
