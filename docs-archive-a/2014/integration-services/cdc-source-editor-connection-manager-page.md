---
title: Editor de origem CDC (página Gerenciador de conexões) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.designer.cdcsource.connection.f1
ms.assetid: 304e6717-e160-4a7b-a06f-32182449fef8
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5b0ed4792f13006bb9013771c69053b04539bc0e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582576"
---
# <a name="cdc-source-editor-connection-manager-page"></a><span data-ttu-id="2c00e-102">Editor de Origem CDC (página Gerenciador de Conexões)</span><span class="sxs-lookup"><span data-stu-id="2c00e-102">CDC Source Editor (Connection Manager Page)</span></span>
  <span data-ttu-id="2c00e-103">Use a página **Gerenciador de Conexões** da caixa de diálogo **Editor de Origem CDC** para selecionar o gerenciador de conexões do ADO.NET para o banco de dados do [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] do qual a origem CDC lê as linhas de alteração (o banco de dados CDC).</span><span class="sxs-lookup"><span data-stu-id="2c00e-103">Use the **Connection Manager** page of the **CDC Source Editor** dialog box to select the ADO.NET connection manager for the [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] database that the CDC source reads change rows from (the CDC database).</span></span> <span data-ttu-id="2c00e-104">Quando o banco de dados CDC é selecionado, você precisa selecionar uma tabela capturada no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="2c00e-104">Once the CDC database is selected you need to select a captured table in the database.</span></span>  
  
 <span data-ttu-id="2c00e-105">Para obter mais informações sobre a origem CDC, consulte [Origem CDC](data-flow/cdc-source.md).</span><span class="sxs-lookup"><span data-stu-id="2c00e-105">For more information about the CDC source, see [CDC Source](data-flow/cdc-source.md).</span></span>  
  
## <a name="task-list"></a><span data-ttu-id="2c00e-106">Lista de Tarefas</span><span class="sxs-lookup"><span data-stu-id="2c00e-106">Task List</span></span>  
 <span data-ttu-id="2c00e-107">**Para abrir a página do Gerenciador de Conexões do Editor de Origem CDC**</span><span class="sxs-lookup"><span data-stu-id="2c00e-107">**To open the CDC Source Editor Connection Manager Page**</span></span>  
  
1.  <span data-ttu-id="2c00e-108">No [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], abra o pacote [!INCLUDE[ssISCurrent](../includes/ssiscurrent-md.md)] que tem a origem CDC.</span><span class="sxs-lookup"><span data-stu-id="2c00e-108">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], open the [!INCLUDE[ssISCurrent](../includes/ssiscurrent-md.md)] package that has the CDC source.</span></span>  
  
2.  <span data-ttu-id="2c00e-109">Na guia **Fluxo de Dados** , clique duas vezes na origem CDC.</span><span class="sxs-lookup"><span data-stu-id="2c00e-109">On the **Data Flow** tab, double-click the CDC source.</span></span>  
  
3.  <span data-ttu-id="2c00e-110">No **Editor de Origem CDC**, clique em **Gerenciador de Conexões**.</span><span class="sxs-lookup"><span data-stu-id="2c00e-110">In the **CDC Source Editor**, click **Connection Manager**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="2c00e-111">Opções</span><span class="sxs-lookup"><span data-stu-id="2c00e-111">Options</span></span>  
 <span data-ttu-id="2c00e-112">**Gerenciador de conexões ADO.NET**</span><span class="sxs-lookup"><span data-stu-id="2c00e-112">**ADO.NET connection manager**</span></span>  
 <span data-ttu-id="2c00e-113">Selecione na lista um gerenciador de conexões existente ou clique em **Novo** para criar uma nova conexão.</span><span class="sxs-lookup"><span data-stu-id="2c00e-113">Select an existing connection manager from the list, or click **New** to create a new connection.</span></span> <span data-ttu-id="2c00e-114">A conexão deve ser a um banco de dados do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] que está habilitado para CDC e onde a tabela de alteração selecionada está localizada.</span><span class="sxs-lookup"><span data-stu-id="2c00e-114">The connection must be to a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] database that is enabled for CDC and where the selected change table is located.</span></span>  
  
 <span data-ttu-id="2c00e-115">**Novo**</span><span class="sxs-lookup"><span data-stu-id="2c00e-115">**New**</span></span>  
 <span data-ttu-id="2c00e-116">Clique em **Nova**.</span><span class="sxs-lookup"><span data-stu-id="2c00e-116">Click **New**.</span></span> <span data-ttu-id="2c00e-117">A caixa de diálogo **Configurar Editor do Gerenciador de Conexões ADO.NET** é aberta, na qual você pode criar um novo gerenciador de conexões</span><span class="sxs-lookup"><span data-stu-id="2c00e-117">The **Configure ADO.NET Connection Manager Editor** dialog box opens where you can create a new connection manager</span></span>  
  
 <span data-ttu-id="2c00e-118">**Tabela CDC**</span><span class="sxs-lookup"><span data-stu-id="2c00e-118">**CDC Table**</span></span>  
 <span data-ttu-id="2c00e-119">Selecione a tabela de origem CDC que contém as alterações capturadas que você deseja ler e alimente os componentes SSIS downstream para serem processados.</span><span class="sxs-lookup"><span data-stu-id="2c00e-119">Select the CDC source table that contains the captured changes that you want read and feed to downstream SSIS components for processing.</span></span>  
  
 <span data-ttu-id="2c00e-120">**Instância de captura**</span><span class="sxs-lookup"><span data-stu-id="2c00e-120">**Capture instance**</span></span>  
 <span data-ttu-id="2c00e-121">Selecione ou digite o nome da instância de captura CDC com a tabela CDC que deve ser lida.</span><span class="sxs-lookup"><span data-stu-id="2c00e-121">Select or type in the name of the CDC capture instance with the CDC table to be read.</span></span>  
  
 <span data-ttu-id="2c00e-122">Uma tabela de origem capturada pode ter uma ou duas instâncias capturadas para tratar diretamente a transição da definição de tabela por meio de alterações de esquema.</span><span class="sxs-lookup"><span data-stu-id="2c00e-122">A captured source table can have one or two captured instances to handle seamless transitioning of table definition through schema changes.</span></span> <span data-ttu-id="2c00e-123">Se mais de uma instância de captura for definida para a tabela de origem que está sendo capturada, selecione a instância de captura que você deseja usar aqui.</span><span class="sxs-lookup"><span data-stu-id="2c00e-123">If more than one capture instance is defined for the source table being captured, select the capture instance you want to use here.</span></span> <span data-ttu-id="2c00e-124">O nome padrão da instância de captura de uma tabela [esquema].[tabela] é \<schema>_\<table>, mas os nomes reais da instância de captura em uso podem ser diferentes.</span><span class="sxs-lookup"><span data-stu-id="2c00e-124">The default capture instance name for a table [schema].[table] is \<schema>_\<table> but that actual capture instance names in use may be different.</span></span> <span data-ttu-id="2c00e-125">A tabela real da qual é feita a leitura é a tabela CDC **cdc .\<capture-instance>_CT**.</span><span class="sxs-lookup"><span data-stu-id="2c00e-125">The actual table that is read from is the CDC table **cdc .\<capture-instance>_CT**.</span></span>  
  
 <span data-ttu-id="2c00e-126">**Modo de processamento CDC**</span><span class="sxs-lookup"><span data-stu-id="2c00e-126">**CDC Processing Mode**</span></span>  
 <span data-ttu-id="2c00e-127">Selecione o modo de processamento que melhor trata suas necessidades de processamento.</span><span class="sxs-lookup"><span data-stu-id="2c00e-127">Select the processing mode that best handles your processing needs.</span></span> <span data-ttu-id="2c00e-128">As opções possíveis são:</span><span class="sxs-lookup"><span data-stu-id="2c00e-128">The possible options are:</span></span>  
  
-   <span data-ttu-id="2c00e-129">**Tudo**: retorna as alterações no intervalo CDC atual sem os valores **Antes da Atualização** .</span><span class="sxs-lookup"><span data-stu-id="2c00e-129">**All**: Returns the changes in the current CDC range without the **Before Update** values.</span></span>  
  
-   <span data-ttu-id="2c00e-130">**Todos com valores antigos**: retorna as alterações no intervalo de processamento CDC atual, incluindo os valores antigos (**Antes da Atualização**).</span><span class="sxs-lookup"><span data-stu-id="2c00e-130">**All with old values**: Returns the changes in the current CDC processing range including the old values (**Before Update**).</span></span> <span data-ttu-id="2c00e-131">Para cada operação de atualização, haverá duas linhas, uma com os valores antes da atualização e outra com o valor depois da atualização.</span><span class="sxs-lookup"><span data-stu-id="2c00e-131">For each Update operation, there will be two rows, one with the before-update values and one with the after-update value.</span></span>  
  
-   <span data-ttu-id="2c00e-132">**Líquido**: retorna somente uma linha de alteração por linha de origem modificada no intervalo de processamento CDC atual.</span><span class="sxs-lookup"><span data-stu-id="2c00e-132">**Net**: Returns only one change row per source row modified in the current CDC processing range.</span></span> <span data-ttu-id="2c00e-133">Se uma linha de origem tiver sido atualizada várias vezes, a alteração combinada será gerada (por exemplo, insert+update é gerado como uma única atualização e update+delete é gerado como uma única exclusão).</span><span class="sxs-lookup"><span data-stu-id="2c00e-133">If a source row was updated multiple times, the combined change is produced (for example, insert+update is produced as a single update and update+delete is produced as a single delete).</span></span> <span data-ttu-id="2c00e-134">Ao trabalhar em modo de processamento de alteração Líquido, é possível dividir as alterações para saídas Excluir, Inserir e Atualizar, e tratá-las em paralelo porque a única linha de origem aparece em mais de uma saída.</span><span class="sxs-lookup"><span data-stu-id="2c00e-134">When working in Net change processing mode, it is possible to split the changes to Delete, Insert and Update outputs and handle them in parallel because the single source row appears in more than one output.</span></span>  
  
-   <span data-ttu-id="2c00e-135">**Líquido com máscara atualizada**: este modo é semelhante ao modo Líquido normal, mas também adiciona colunas boolianas com o nome padrão **__$\<column-name>\__Changed**, que indica as colunas alteradas na linha de alteração atual.</span><span class="sxs-lookup"><span data-stu-id="2c00e-135">**Net with update mask**: This mode is similar to the regular Net mode but it also adds boolean columns with the name pattern **__$\<column-name>\__Changed** that indicate changed columns in the current change row.</span></span>  
  
-   <span data-ttu-id="2c00e-136">**Líquido com mesclagem**: este modo é semelhante ao modo Líquido normal, mas com operações de inserção e atualização mescladas em uma única operação de mesclagem (UPSERT).</span><span class="sxs-lookup"><span data-stu-id="2c00e-136">**Net with merge**: This mode is similar to the regular Net mode but with Insert and Update operations merged into a single Merge operation (UPSERT).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2c00e-137">Para todas as opções de alteração Net, a tabela de origem deve ter uma chave primária ou índice exclusivo.</span><span class="sxs-lookup"><span data-stu-id="2c00e-137">For all Net change options, the source table must have a primary key or unique index.</span></span> <span data-ttu-id="2c00e-138">Para tabelas sem uma chave primária ou um índice exclusivo, você deve use a opção **Tudo** .</span><span class="sxs-lookup"><span data-stu-id="2c00e-138">For tables without a primary key or unique indes, you must yse the **All** option.</span></span>  
  
 <span data-ttu-id="2c00e-139">**Variável contendo o estado de CDC**</span><span class="sxs-lookup"><span data-stu-id="2c00e-139">**Variable containing the CDC state**</span></span>  
 <span data-ttu-id="2c00e-140">Selecione a variável de pacote de cadeia de caracteres SSIS que mantém o estado CDC para o contexto CDC atual.</span><span class="sxs-lookup"><span data-stu-id="2c00e-140">Select the SSIS string package variable that maintains the CDC state for the current CDC context.</span></span> <span data-ttu-id="2c00e-141">Para obter mais informações sobre a variável de estado CDC, consulte [Definir uma variável de estado](data-flow/define-a-state-variable.md).</span><span class="sxs-lookup"><span data-stu-id="2c00e-141">For more information about the CDC state variable, see [Define a State Variable](data-flow/define-a-state-variable.md).</span></span>  
  
 <span data-ttu-id="2c00e-142">**Incluir coluna de indicador de reprocessamento**</span><span class="sxs-lookup"><span data-stu-id="2c00e-142">**Include reprocessing indicator column**</span></span>  
 <span data-ttu-id="2c00e-143">Marque esta caixa de seleção para criar uma coluna de saída especial chamada **__$reprocessing**.</span><span class="sxs-lookup"><span data-stu-id="2c00e-143">Select this check box to create a special output column called **__$reprocessing**.</span></span>  
  
 <span data-ttu-id="2c00e-144">Esta coluna apresenta um valor de **true** quando o intervalo de processamento CDC sobrepõe o intervalo de processamento inicial (o intervalo de LSNs que corresponde ao período de carga inicial) ou quando um intervalo de processamento CDC é reprocessado após um erro em uma execução anterior.</span><span class="sxs-lookup"><span data-stu-id="2c00e-144">This column has a value of **true** when the CDC processing range overlaps with the initial processing range (the range of LSNs corresponding to the period of initial load) or when a CDC processing range is reprocessed following an error in a previous run.</span></span> <span data-ttu-id="2c00e-145">Esta coluna de indicador permite que o desenvolvedor do SSIS trate erros diferentemente ao reprocessar alterações (por exemplo, ações como excluir de uma linha não existente e uma inserção com falha em uma chave duplicada podem ser ignoradas).</span><span class="sxs-lookup"><span data-stu-id="2c00e-145">This indicator column lets the SSIS developer handle errors differently when reprocessing changes (for example, actions such as a delete of a non-existing row and an insert that failed on a duplicate key can be ignored).</span></span>  
  
 <span data-ttu-id="2c00e-146">Para obter mais informações, consulte [Propriedades personalizadas da origem CDC](data-flow/cdc-source-custom-properties.md).</span><span class="sxs-lookup"><span data-stu-id="2c00e-146">For more information, see [CDC Source Custom Properties](data-flow/cdc-source-custom-properties.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c00e-147">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2c00e-147">See Also</span></span>  
 <span data-ttu-id="2c00e-148">[Editor de Origem CDC &#40;página Colunas&#41;](../../2014/integration-services/cdc-source-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="2c00e-148">[CDC Source Editor &#40;Columns Page&#41;](../../2014/integration-services/cdc-source-editor-columns-page.md) </span></span>  
 [<span data-ttu-id="2c00e-149">Editor de Origem CDC &#40;Página Saída de Erro&#41;</span><span class="sxs-lookup"><span data-stu-id="2c00e-149">CDC Source Editor &#40;Error Output Page&#41;</span></span>](../../2014/integration-services/cdc-source-editor-error-output-page.md)  
  
  
