---
title: Extrair dados de alteração por meio da origem CDC | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 604fbafb-15fa-4d11-8487-77d7b626eed8
author: chugugrace
ms.author: chugu
ms.openlocfilehash: ef981a22e286f519c9b93b3181b47df43321548b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685867"
---
# <a name="extract-change-data-using-the-cdc-source"></a><span data-ttu-id="24729-102">Extrair dados de alteração por meio da origem CDC</span><span class="sxs-lookup"><span data-stu-id="24729-102">Extract Change Data Using the CDC Source</span></span>
  <span data-ttu-id="24729-103">Para adicionar e configurar uma origem de CDC, o pacote já deve incluir pelo menos uma tarefa de Fluxo de Dados e uma tarefa Controle de CDC.</span><span class="sxs-lookup"><span data-stu-id="24729-103">To add and configure a CDC source, the package must already include at least one Data Flow task and a CDC Control task.</span></span>  
  
 <span data-ttu-id="24729-104">Para obter mais informações sobre a tarefa Controle de CDC, consulte [Tarefa Controle de CDC](../control-flow/cdc-control-task.md).</span><span class="sxs-lookup"><span data-stu-id="24729-104">For more information about the CDC Control task, see [CDC Control Task](../control-flow/cdc-control-task.md).</span></span>  
  
 <span data-ttu-id="24729-105">Para obter mais informações sobre a origem CDC, consulte [Origem CDC](cdc-source.md).</span><span class="sxs-lookup"><span data-stu-id="24729-105">For more information about the CDC source, see [CDC Source](cdc-source.md).</span></span>  
  
### <a name="to-extract-change-data-using-a-cdc-source"></a><span data-ttu-id="24729-106">Para extrair dados usando uma origem CDC</span><span class="sxs-lookup"><span data-stu-id="24729-106">To extract change data using a CDC source</span></span>  
  
1.  <span data-ttu-id="24729-107">No [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], abra o projeto do [!INCLUDE[ssISCurrent](../../includes/ssiscurrent-md.md)] que contém o pacote desejado.</span><span class="sxs-lookup"><span data-stu-id="24729-107">In [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], open the [!INCLUDE[ssISCurrent](../../includes/ssiscurrent-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="24729-108">No Gerenciador de Soluções, clique duas vezes no pacote para abri-lo.</span><span class="sxs-lookup"><span data-stu-id="24729-108">In the Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="24729-109">Clique na guia **Fluxo de Dados** e, na **Caixa de Ferramentas**, arraste a origem CDC para a superfície de design.</span><span class="sxs-lookup"><span data-stu-id="24729-109">Click the **Data Flow** tab, and then from the **Toolbox**, drag the CDC source to the design surface.</span></span>  
  
4.  <span data-ttu-id="24729-110">Clique duas vezes na origem CDC.</span><span class="sxs-lookup"><span data-stu-id="24729-110">Double-click the CDC source.</span></span>  
  
5.  <span data-ttu-id="24729-111">Na caixa de diálogo **Editor de Origem de CDC** , na página **Gerenciador de Conexões** , selecione um gerenciador de conexões ADO.NET na lista ou clique em **Novo** para criar uma nova conexão.</span><span class="sxs-lookup"><span data-stu-id="24729-111">In the **CDC Source Editor** dialog box, on the **Connection Manager** page, select an existing ADO.NET connection manager from the list, or click **New** to create a new connection.</span></span> <span data-ttu-id="24729-112">A conexão deve ser estabelecida com um banco de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que contém as tabelas de alteração a serem lidas.</span><span class="sxs-lookup"><span data-stu-id="24729-112">The connection should be to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database that contains the change tables to read.</span></span>  
  
6.  <span data-ttu-id="24729-113">Selecione a **tabela CDC** em que você quer processar alterações.</span><span class="sxs-lookup"><span data-stu-id="24729-113">Select the **CDC table** where you want to process changes.</span></span>  
  
7.  <span data-ttu-id="24729-114">Selecione ou digite o nome da **instância de captura CDC** com a tabela CDC que deve ser lida.</span><span class="sxs-lookup"><span data-stu-id="24729-114">Select or type in the name of the **CDC capture instance** with the CDC table to be read.</span></span>  
  
     <span data-ttu-id="24729-115">Uma tabela de origem capturada pode ter uma ou duas instâncias capturadas para tratar diretamente a transição da definição de tabela por meio de alterações de esquema.</span><span class="sxs-lookup"><span data-stu-id="24729-115">A captured source table can have one or two captured instances to handle seamless transitioning of table definition through schema changes.</span></span> <span data-ttu-id="24729-116">Se mais de uma instância de captura for definida para a tabela de origem que está sendo capturada, selecione a instância de captura que você deseja usar aqui.</span><span class="sxs-lookup"><span data-stu-id="24729-116">If more than one capture instance is defined for the source table being captured, select the capture instance you want to use here.</span></span> <span data-ttu-id="24729-117">O nome padrão da instância de captura de uma tabela [esquema].[tabela] é \<schema>_\<table>, mas os nomes reais da instância de captura em uso podem ser diferentes.</span><span class="sxs-lookup"><span data-stu-id="24729-117">The default capture instance name for a table [schema].[table] is \<schema>_\<table> but that actual capture instance names in use may be different.</span></span> <span data-ttu-id="24729-118">A tabela real da qual é feita a leitura é a tabela CDC **cdc .\<capture-instance>_CT**.</span><span class="sxs-lookup"><span data-stu-id="24729-118">The actual table that is read from is the CDC table **cdc .\<capture-instance>_CT**.</span></span>  
  
8.  <span data-ttu-id="24729-119">Selecione o modo de processamento que melhor trata suas necessidades de processamento.</span><span class="sxs-lookup"><span data-stu-id="24729-119">Select the processing mode that best handles your processing needs.</span></span> <span data-ttu-id="24729-120">As opções possíveis são:</span><span class="sxs-lookup"><span data-stu-id="24729-120">The possible options are:</span></span>  
  
    -   <span data-ttu-id="24729-121">**Tudo**: retorna as alterações no intervalo CDC atual sem os valores **Antes da Atualização** .</span><span class="sxs-lookup"><span data-stu-id="24729-121">**All**: Returns the changes in the current CDC range without the **Before Update** values.</span></span>  
  
    -   <span data-ttu-id="24729-122">**Todos com valores antigos**: retorna as alterações no intervalo de processamento CDC atual, incluindo os valores antigos (**Antes da Atualização**).</span><span class="sxs-lookup"><span data-stu-id="24729-122">**All with old values**: Returns the changes in the current CDC processing range including the old values (**Before Update**).</span></span> <span data-ttu-id="24729-123">Para cada operação de atualização, haverá duas linhas, uma com os valores antes da atualização e outra com o valor depois da atualização.</span><span class="sxs-lookup"><span data-stu-id="24729-123">For each Update operation, there will be two rows, one with the before-update values and one with the after-update value.</span></span>  
  
    -   <span data-ttu-id="24729-124">**Líquido**: retorna somente uma linha de alteração por linha de origem modificada no intervalo de processamento CDC atual.</span><span class="sxs-lookup"><span data-stu-id="24729-124">**Net**: Returns only one change row per source row modified in the current CDC processing range.</span></span> <span data-ttu-id="24729-125">Se uma linha de origem tiver sido atualizada várias vezes, a alteração combinada será gerada (por exemplo, insert+update é gerado como uma única atualização e update+delete é gerado como uma única exclusão).</span><span class="sxs-lookup"><span data-stu-id="24729-125">If a source row was updated multiple times, the combined change is produced (for example, insert+update is produced as a single update and update+delete is produced as a single delete).</span></span> <span data-ttu-id="24729-126">Ao trabalhar em modo de processamento de alteração Líquido, é possível dividir as alterações para saídas Excluir, Inserir e Atualizar, e tratá-las em paralelo porque a única linha de origem aparece em mais de uma saída.</span><span class="sxs-lookup"><span data-stu-id="24729-126">When working in Net change processing mode, it is possible to split the changes to Delete, Insert and Update outputs and handle them in parallel because the single source row appears in more than one output.</span></span>  
  
    -   <span data-ttu-id="24729-127">**Líquido com máscara atualizada**: este modo é semelhante ao modo Líquido normal, mas também adiciona colunas boolianas com o nome padrão **__$\<column-name>\__Changed**, que indica as colunas alteradas na linha de alteração atual.</span><span class="sxs-lookup"><span data-stu-id="24729-127">**Net with update mask**: This mode is similar to the regular Net mode but it also adds boolean columns with the name pattern **__$\<column-name>\__Changed** that indicate changed columns in the current change row.</span></span>  
  
    -   <span data-ttu-id="24729-128">**Líquido com mesclagem**: este modo é semelhante ao modo Líquido normal, mas com operações de inserção e atualização mescladas em uma única operação de mesclagem (UPSERT).</span><span class="sxs-lookup"><span data-stu-id="24729-128">**Net with merge**: This mode is similar to the regular Net mode but with Insert and Update operations merged into a single Merge operation (UPSERT).</span></span>  
  
9. <span data-ttu-id="24729-129">Selecione a variável de pacote de cadeia de caracteres SSIS que mantém o estado CDC para o contexto CDC atual.</span><span class="sxs-lookup"><span data-stu-id="24729-129">Select the SSIS string package variable that maintains the CDC state for the current CDC context.</span></span> <span data-ttu-id="24729-130">Para obter mais informações sobre a variável de estado CDC, consulte [Definir uma variável de estado](define-a-state-variable.md).</span><span class="sxs-lookup"><span data-stu-id="24729-130">For more information about the CDC state variable, see [Define a State Variable](define-a-state-variable.md).</span></span>  
  
10. <span data-ttu-id="24729-131">Marque esta caixa de seleção **Incluir coluna do indicador de reprocessamento** para criar uma coluna de saída especial chamada **__$reprocessing**.</span><span class="sxs-lookup"><span data-stu-id="24729-131">Select the **Include reprocessing indicator column** check box to create a special output column called **__$reprocessing**.</span></span> <span data-ttu-id="24729-132">Esta coluna apresenta um valor de **true** quando o intervalo de processamento CDC sobrepõe o intervalo de processamento inicial (o intervalo de LSNs que corresponde ao período de carga inicial) ou quando um intervalo de processamento CDC é reprocessado após um erro em uma execução anterior.</span><span class="sxs-lookup"><span data-stu-id="24729-132">This column has a value of **true** when the CDC processing range overlaps with the initial processing range (the range of LSNs corresponding to the period of initial load) or when a CDC processing range is reprocessed following an error in a previous run.</span></span> <span data-ttu-id="24729-133">Esta coluna de indicador permite que o desenvolvedor do SSIS trate erros diferentemente ao reprocessar alterações (por exemplo, ações como excluir de uma linha não existente e uma inserção com falha em uma chave duplicada podem ser ignoradas).</span><span class="sxs-lookup"><span data-stu-id="24729-133">This indicator column lets the SSIS developer handle errors differently when reprocessing changes (for example, actions such as a delete of a non-existing row and an insert that failed on a duplicate key can be ignored).</span></span>  
  
     <span data-ttu-id="24729-134">Para obter mais informações, consulte [Propriedades personalizadas da origem CDC](cdc-source-custom-properties.md).</span><span class="sxs-lookup"><span data-stu-id="24729-134">For more information, see [CDC Source Custom Properties](cdc-source-custom-properties.md).</span></span>  
  
11. <span data-ttu-id="24729-135">Para atualizar o mapeamento entre colunas externas e de saída, clique em **Colunas** e selecione colunas diferentes na lista **Coluna Externa** .</span><span class="sxs-lookup"><span data-stu-id="24729-135">To update the mapping between external and output columns, click **Columns** and select different columns in the **External Column** list.</span></span>  
  
12. <span data-ttu-id="24729-136">Opcionalmente, atualize os valores das colunas de saída excluindo os valores na lista **Coluna de Saída** .</span><span class="sxs-lookup"><span data-stu-id="24729-136">Optionally update the values of the output columns by deleting values in the **Output Column** list.</span></span>  
  
13. <span data-ttu-id="24729-137">Para configurar a saída de erro, clique em **Saída de Erro**.</span><span class="sxs-lookup"><span data-stu-id="24729-137">To configure the error output, click **Error Output**.</span></span>  
  
14. <span data-ttu-id="24729-138">É possível clicar em **Visualizar** para exibir até 200 linhas dos dados extraídos pela origem CDC.</span><span class="sxs-lookup"><span data-stu-id="24729-138">You can click **Preview** to view up to 200 rows of data extracted by the CDC source.</span></span>  
  
15. <span data-ttu-id="24729-139">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="24729-139">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24729-140">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="24729-140">See Also</span></span>  
 <span data-ttu-id="24729-141">[Editor de Origem CDC &#40;Página Gerenciador de Conexões&#41;](../cdc-source-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="24729-141">[CDC Source Editor &#40;Connection Manager Page&#41;](../cdc-source-editor-connection-manager-page.md) </span></span>  
 <span data-ttu-id="24729-142">[Editor de Origem CDC &#40;página Colunas&#41;](../cdc-source-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="24729-142">[CDC Source Editor &#40;Columns Page&#41;](../cdc-source-editor-columns-page.md) </span></span>  
 [<span data-ttu-id="24729-143">Editor de Origem CDC &#40;Página Saída de Erro&#41;</span><span class="sxs-lookup"><span data-stu-id="24729-143">CDC Source Editor &#40;Error Output Page&#41;</span></span>](../cdc-source-editor-error-output-page.md)  
  
  
