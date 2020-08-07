---
title: Editor de origem ODBC (página Gerenciador de conexões) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.designer.odbcsource.connection.f1
ms.assetid: e2c8dc83-6394-4d6c-9232-97e94be72431
author: chugugrace
ms.author: chugu
ms.openlocfilehash: c8b54ce4a1c1b3fea0afb51f1cbf7447971ccab4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681792"
---
# <a name="odbc-source-editor-connection-manager-page"></a><span data-ttu-id="d4b08-102">Editor de Origem ODBC (página Gerenciador de Conexões)</span><span class="sxs-lookup"><span data-stu-id="d4b08-102">ODBC Source Editor (Connection Manager Page)</span></span>
  <span data-ttu-id="d4b08-103">Use a página **Gerenciador de Conexões** da caixa de diálogo **Editor de Origem ODBC** para selecionar o gerenciador de conexões ODBC para a origem.</span><span class="sxs-lookup"><span data-stu-id="d4b08-103">Use the **Connection Manager** page of the **ODBC Source Editor** dialog box to select the ODBC connection manager for the source.</span></span> <span data-ttu-id="d4b08-104">Essa página também permite que você selecione uma tabela ou exibição a partir do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="d4b08-104">This page also lets you select a table or view from the database.</span></span>  
  
 <span data-ttu-id="d4b08-105">Para obter mais informações sobre essa fonte ODBC, consulte [Fonte ODBC](data-flow/odbc-source.md).</span><span class="sxs-lookup"><span data-stu-id="d4b08-105">For more information about the ODBC source, see [ODBC Source](data-flow/odbc-source.md).</span></span>  
  
## <a name="task-list"></a><span data-ttu-id="d4b08-106">Lista de Tarefas</span><span class="sxs-lookup"><span data-stu-id="d4b08-106">Task List</span></span>  
 <span data-ttu-id="d4b08-107">**Para abrir a página do Gerenciador de Conexões do Editor de Origem ODBC**</span><span class="sxs-lookup"><span data-stu-id="d4b08-107">**To open the ODBC Source Editor Connection Manager Page**</span></span>  
  
-   <span data-ttu-id="d4b08-108">No [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], abra o pacote [!INCLUDE[ssISCurrent](../includes/ssiscurrent-md.md)] que tem a fonte ODBC.</span><span class="sxs-lookup"><span data-stu-id="d4b08-108">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], open the [!INCLUDE[ssISCurrent](../includes/ssiscurrent-md.md)] package that has the ODBC source.</span></span>  
  
-   <span data-ttu-id="d4b08-109">Na guia **Fluxo de Dados** , clique duas vezes na fonte ODBC.</span><span class="sxs-lookup"><span data-stu-id="d4b08-109">On the **Data Flow** tab, double-click the ODBC source.</span></span>  
  
## <a name="options"></a><span data-ttu-id="d4b08-110">Opções</span><span class="sxs-lookup"><span data-stu-id="d4b08-110">Options</span></span>  
  
### <a name="connection-manager"></a><span data-ttu-id="d4b08-111">Gerenciador de conexões</span><span class="sxs-lookup"><span data-stu-id="d4b08-111">Connection manager</span></span>  
 <span data-ttu-id="d4b08-112">Selecione um Gerenciador de conexões ODBC existente na lista ou clique em **novo** para criar uma nova conexão.</span><span class="sxs-lookup"><span data-stu-id="d4b08-112">Select an existing ODBC connection manager from the list, or click **New** to create a new connection.</span></span> <span data-ttu-id="d4b08-113">A conexão pode ser com qualquer banco de dados com suporte ODBC.</span><span class="sxs-lookup"><span data-stu-id="d4b08-113">The connection can be to any ODBC-supported database.</span></span>  
  
### <a name="new"></a><span data-ttu-id="d4b08-114">Novo</span><span class="sxs-lookup"><span data-stu-id="d4b08-114">New</span></span>  
 <span data-ttu-id="d4b08-115">Clique em **Nova**.</span><span class="sxs-lookup"><span data-stu-id="d4b08-115">Click **New**.</span></span> <span data-ttu-id="d4b08-116">É aberta a caixa de diálogo **Configurar Editor do Gerenciador de Conexões ODBC** , na qual você pode criar um novo gerenciador de conexões ODBC.</span><span class="sxs-lookup"><span data-stu-id="d4b08-116">The **Configure ODBC Connection Manager Editor** dialog box opens where you can create a new ODBC connection manager.</span></span>  
  
### <a name="data-access-mode"></a><span data-ttu-id="d4b08-117">Modo de acesso a dados</span><span class="sxs-lookup"><span data-stu-id="d4b08-117">Data Access Mode</span></span>  
 <span data-ttu-id="d4b08-118">Especifique o método para selecionar dados da origem.</span><span class="sxs-lookup"><span data-stu-id="d4b08-118">Select the method for selecting data from the source.</span></span> <span data-ttu-id="d4b08-119">As opções são mostradas na tabela a seguir:</span><span class="sxs-lookup"><span data-stu-id="d4b08-119">The options are shown in the following table:</span></span>  
  
|<span data-ttu-id="d4b08-120">Opção</span><span class="sxs-lookup"><span data-stu-id="d4b08-120">Option</span></span>|<span data-ttu-id="d4b08-121">Descrição</span><span class="sxs-lookup"><span data-stu-id="d4b08-121">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="d4b08-122">Nome da tabela</span><span class="sxs-lookup"><span data-stu-id="d4b08-122">Table Name</span></span>|<span data-ttu-id="d4b08-123">Recupere os dados de uma tabela ou exibição na fonte de dados ODBC.</span><span class="sxs-lookup"><span data-stu-id="d4b08-123">Retrieve data from a table or view in the ODBC data source.</span></span> <span data-ttu-id="d4b08-124">Quando você selecionar esta opção, selecione um valor na lista para o seguinte:</span><span class="sxs-lookup"><span data-stu-id="d4b08-124">When you select this option, select a value from the list for the following:</span></span>|  
||<span data-ttu-id="d4b08-125">**Nome da tabela ou exibição**: selecione uma tabela ou exibição disponível na lista ou digite uma expressão regular para identificar a tabela.</span><span class="sxs-lookup"><span data-stu-id="d4b08-125">**Name of the table or the view**: Select an available table or view from the list or type a regular expression to identify the table.</span></span>|  
||<span data-ttu-id="d4b08-126">Essa lista contém apenas as primeiras 1.000 tabelas.</span><span class="sxs-lookup"><span data-stu-id="d4b08-126">This list contains the first 1000 tables only.</span></span> <span data-ttu-id="d4b08-127">Se o banco de dados contiver mais de 1.000 tabelas, você poderá digitar o início do nome de uma tabela ou usar o curinga (\*) para inserir qualquer parte do nome para exibir a tabela ou tabelas desejadas.</span><span class="sxs-lookup"><span data-stu-id="d4b08-127">If your database contains more than 1000 tables, you can type the beginning of a table name or use the (\*) wild card to enter any part of the name to display the table or tables you want to use.</span></span>|  
|<span data-ttu-id="d4b08-128">Comando SQL</span><span class="sxs-lookup"><span data-stu-id="d4b08-128">SQL command</span></span>|<span data-ttu-id="d4b08-129">Recupere os dados da fonte de dados ODBC usando uma consulta SQL.</span><span class="sxs-lookup"><span data-stu-id="d4b08-129">Retrieve data from the ODBC data source by using an SQL query.</span></span> <span data-ttu-id="d4b08-130">Você deve escrever a consulta na sintaxe do banco de dados de origem com o qual está trabalhando.</span><span class="sxs-lookup"><span data-stu-id="d4b08-130">You should write the query in the syntax of the source database you are working with.</span></span> <span data-ttu-id="d4b08-131">Quando selecionar esta opção, insira uma consulta de uma das seguintes maneiras:</span><span class="sxs-lookup"><span data-stu-id="d4b08-131">When you select this option, enter a query in one of the following ways:</span></span>|  
||<span data-ttu-id="d4b08-132">Insira o texto da consulta SQL no campo **Texto do comando do SQL** .</span><span class="sxs-lookup"><span data-stu-id="d4b08-132">Enter the text of the SQL query in the **SQL command text** field.</span></span>|  
||<span data-ttu-id="d4b08-133">Clique em **Procurar** para carregar a consulta SQL de um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="d4b08-133">Click **Browse** to load the SQL query from a text file.</span></span>|  
||<span data-ttu-id="d4b08-134">Clique em **Analisar consulta** para verificar a sintaxe do texto da consulta.</span><span class="sxs-lookup"><span data-stu-id="d4b08-134">Click **Parse query** to verify the syntax of the query text.</span></span>|  
  
### <a name="preview"></a><span data-ttu-id="d4b08-135">Visualização</span><span class="sxs-lookup"><span data-stu-id="d4b08-135">Preview</span></span>  
 <span data-ttu-id="d4b08-136">Clique em **Visualizar** para exibir até as primeiras 200 linhas dos dados extraídos da tabela ou exibição selecionada.</span><span class="sxs-lookup"><span data-stu-id="d4b08-136">Click **Preview** to view up to the first 200 rows of the data extracted from the table or view you selected.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4b08-137">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d4b08-137">See Also</span></span>  
 <span data-ttu-id="d4b08-138">[Propriedades personalizadas de origem ODBC](data-flow/odbc-source-custom-properties.md) </span><span class="sxs-lookup"><span data-stu-id="d4b08-138">[ODBC Source Custom Properties](data-flow/odbc-source-custom-properties.md) </span></span>  
 <span data-ttu-id="d4b08-139">[Editor de origem ODBC &#40;página colunas&#41;](../../2014/integration-services/odbc-source-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="d4b08-139">[ODBC Source Editor &#40;Columns Page&#41;](../../2014/integration-services/odbc-source-editor-columns-page.md) </span></span>  
 [<span data-ttu-id="d4b08-140">Editor de Fonte ODBC &#40;Página Saída de Erro&#41;</span><span class="sxs-lookup"><span data-stu-id="d4b08-140">ODBC Source Editor &#40;Error Output Page&#41;</span></span>](../../2014/integration-services/odbc-source-editor-error-output-page.md)  
  
  
