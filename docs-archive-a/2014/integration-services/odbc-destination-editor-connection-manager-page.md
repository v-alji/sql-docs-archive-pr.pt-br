---
title: Editor de destino ODBC (página Gerenciador de conexões) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.designer.odbcdest.connection.f1
ms.assetid: f6d9c6c2-e4c4-468b-9e0d-af7b9609614d
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 6e4fc1073bb187c0864d2991459a358a7f81d066
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681798"
---
# <a name="odbc-destination-editor-connection-manager-page"></a><span data-ttu-id="40fca-102">Editor do Destino ODBC (página Gerenciador de Conexões)</span><span class="sxs-lookup"><span data-stu-id="40fca-102">ODBC Destination Editor (Connection Manager Page)</span></span>
  <span data-ttu-id="40fca-103">Use a página **Gerenciador de Conexões** da caixa de diálogo **Editor de Destino ODBC** para selecionar o gerenciador de conexões para o destino.</span><span class="sxs-lookup"><span data-stu-id="40fca-103">Use the **Connection Manager** page of the **ODBC Destination Editor** dialog box to select the ODBC connection manager for the destination.</span></span> <span data-ttu-id="40fca-104">Essa página também permite que você selecione uma tabela ou exibição a partir do banco de dados</span><span class="sxs-lookup"><span data-stu-id="40fca-104">This page also lets you select a table or view from the database</span></span>  
  
 <span data-ttu-id="40fca-105">Para obter mais informações sobre o destino ODBC, consulte [ODBC Destination](data-flow/odbc-destination.md).</span><span class="sxs-lookup"><span data-stu-id="40fca-105">For more information about the ODBC destination, see [ODBC Destination](data-flow/odbc-destination.md).</span></span>  
  
 <span data-ttu-id="40fca-106">**Para abrir a página do Gerenciador de Conexões do Editor de Destino ODBC**</span><span class="sxs-lookup"><span data-stu-id="40fca-106">**To open the ODBC Destination Editor Connection Manager Page**</span></span>  
  
## <a name="task-list"></a><span data-ttu-id="40fca-107">Lista de Tarefas</span><span class="sxs-lookup"><span data-stu-id="40fca-107">Task List</span></span>  
  
-   <span data-ttu-id="40fca-108">No [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], abra o pacote [!INCLUDE[ssISCurrent](../includes/ssiscurrent-md.md)] que tem o destino ODBC.</span><span class="sxs-lookup"><span data-stu-id="40fca-108">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], open the [!INCLUDE[ssISCurrent](../includes/ssiscurrent-md.md)] package that has the ODBC destination.</span></span>  
  
-   <span data-ttu-id="40fca-109">Na guia **Fluxo de Dados** , clique duas vezes no destino ODBC.</span><span class="sxs-lookup"><span data-stu-id="40fca-109">On the **Data Flow** tab, double-click the ODBC destination.</span></span>  
  
-   <span data-ttu-id="40fca-110">No **Editor de Destino ODBC**, clique em **Gerenciador de Conexões**.</span><span class="sxs-lookup"><span data-stu-id="40fca-110">In the **ODBC Destination Editor**, click **Connection Manager**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="40fca-111">Opções</span><span class="sxs-lookup"><span data-stu-id="40fca-111">Options</span></span>  
  
### <a name="connection-manager"></a><span data-ttu-id="40fca-112">Gerenciador de conexões</span><span class="sxs-lookup"><span data-stu-id="40fca-112">Connection manager</span></span>  
 <span data-ttu-id="40fca-113">Selecione na lista um gerenciador de conexões ODBC existente ou clique em Novo para criar uma nova conexão.</span><span class="sxs-lookup"><span data-stu-id="40fca-113">Select an existing ODBC connection manager from the list, or click New to create a new connection.</span></span> <span data-ttu-id="40fca-114">A conexão pode ser com qualquer banco de dados com suporte ODBC.</span><span class="sxs-lookup"><span data-stu-id="40fca-114">The connection can be to any ODBC-supported database.</span></span>  
  
### <a name="new"></a><span data-ttu-id="40fca-115">Novo</span><span class="sxs-lookup"><span data-stu-id="40fca-115">New</span></span>  
 <span data-ttu-id="40fca-116">Clique em **Nova**.</span><span class="sxs-lookup"><span data-stu-id="40fca-116">Click **New**.</span></span> <span data-ttu-id="40fca-117">É aberta a caixa de diálogo **Configurar Editor do Gerenciador de Conexões ODBC** , na qual você pode criar um novo gerenciador de conexões.</span><span class="sxs-lookup"><span data-stu-id="40fca-117">The **Configure ODBC Connection Manager Editor** dialog box opens where you can create a new connection manager.</span></span>  
  
### <a name="data-access-mode"></a><span data-ttu-id="40fca-118">Modo de acesso a dados</span><span class="sxs-lookup"><span data-stu-id="40fca-118">Data Access Mode</span></span>  
 <span data-ttu-id="40fca-119">Selecione o método de carregamento de dados no destino.</span><span class="sxs-lookup"><span data-stu-id="40fca-119">Select the method for loading data to the destination.</span></span> <span data-ttu-id="40fca-120">As opções são mostradas na tabela a seguir:</span><span class="sxs-lookup"><span data-stu-id="40fca-120">The options are shown in the following table:</span></span>  
  
|<span data-ttu-id="40fca-121">Opção</span><span class="sxs-lookup"><span data-stu-id="40fca-121">Option</span></span>|<span data-ttu-id="40fca-122">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="40fca-122">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="40fca-123">Nome da Tabela - Lote</span><span class="sxs-lookup"><span data-stu-id="40fca-123">Table Name - Batch</span></span>|<span data-ttu-id="40fca-124">Selecione esta opção para configurar o destino ODBC para trabalhar no modo de lote.</span><span class="sxs-lookup"><span data-stu-id="40fca-124">Select this option to configure the ODBC destination to work in batch mode.</span></span> <span data-ttu-id="40fca-125">Ao selecionar esta opção, as seguintes opções estão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="40fca-125">When you select this option the following options are available:</span></span>|  
||<span data-ttu-id="40fca-126">**Nome da tabela ou exibição**: selecione uma tabela ou exibição disponível na lista.</span><span class="sxs-lookup"><span data-stu-id="40fca-126">**Name of the table or the view**: Select an available table or view from the list.</span></span><br /><br /> <span data-ttu-id="40fca-127">Essa lista contém apenas as primeiras 1.000 tabelas.</span><span class="sxs-lookup"><span data-stu-id="40fca-127">This list contains the first 1000 tables only.</span></span> <span data-ttu-id="40fca-128">Se o banco de dados contiver mais de 1000 tabelas, você poderá digitar o início do nome de uma tabela ou usar o curinga (\*) para inserir qualquer parte do nome para exibir a tabela ou tabelas desejadas.</span><span class="sxs-lookup"><span data-stu-id="40fca-128">If your database contains more than 1000 tables, you can type the beginning of a table name or use the (\*) wild card to enter any part of the name to display the table or tables you want to use.</span></span><br /><br /> <span data-ttu-id="40fca-129">**Tamanho do lote**: digite o tamanho do lote para carregamento em massa.</span><span class="sxs-lookup"><span data-stu-id="40fca-129">**Batch size**: Type the size of the batch for bulk loading.</span></span> <span data-ttu-id="40fca-130">Esse é o número de linhas carregadas como um lote</span><span class="sxs-lookup"><span data-stu-id="40fca-130">This is the number of rows loaded as a batch</span></span>|  
|<span data-ttu-id="40fca-131">Nome da Tabela - Linha a Linha</span><span class="sxs-lookup"><span data-stu-id="40fca-131">Table Name - Row by Row</span></span>|<span data-ttu-id="40fca-132">Selecione esta opção para configurar o destino ODBC para inserir cada uma das linhas na tabela de destino, uma de cada vez.</span><span class="sxs-lookup"><span data-stu-id="40fca-132">Select this option to configure the ODBC destination to insert each of the rows into the destination table one at a time.</span></span> <span data-ttu-id="40fca-133">Ao selecionar esta opção, a seguinte opção está disponível:</span><span class="sxs-lookup"><span data-stu-id="40fca-133">When you select this option the following option is available:</span></span>|  
||<span data-ttu-id="40fca-134">**Nome da tabela ou exibição**: selecione uma tabela ou exibição disponível no banco de dados na lista.</span><span class="sxs-lookup"><span data-stu-id="40fca-134">**Name of the table or the view**: Select an available table or view from the database from the list.</span></span><br /><br /> <span data-ttu-id="40fca-135">Essa lista contém apenas as primeiras 1.000 tabelas.</span><span class="sxs-lookup"><span data-stu-id="40fca-135">This list contains the first 1000 tables only.</span></span> <span data-ttu-id="40fca-136">Se o banco de dados contiver mais de 1.000 tabelas, você poderá digitar o início do nome de uma tabela ou usar o curinga (\*) para inserir qualquer parte do nome para exibir a tabela ou tabelas desejadas.</span><span class="sxs-lookup"><span data-stu-id="40fca-136">If your database contains more than 1000 tables, you can type the beginning of a table name or use the (\*) wild card to enter any part of the name to display the table or tables you want to use.</span></span>|  
  
### <a name="preview"></a><span data-ttu-id="40fca-137">Visualização</span><span class="sxs-lookup"><span data-stu-id="40fca-137">Preview</span></span>  
 <span data-ttu-id="40fca-138">Clique em **Visualizar** para exibir até 200 linhas de dados da tabela selecionada.</span><span class="sxs-lookup"><span data-stu-id="40fca-138">Click **Preview** to view up to 200 rows of data for the table that you selected.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40fca-139">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="40fca-139">See Also</span></span>  
 <span data-ttu-id="40fca-140">[Propriedades personalizadas de destino ODBC](data-flow/odbc-destination-custom-properties.md) </span><span class="sxs-lookup"><span data-stu-id="40fca-140">[ODBC Destination Custom Properties](data-flow/odbc-destination-custom-properties.md) </span></span>  
 <span data-ttu-id="40fca-141">[Editor de destinos ODBC &#40;página Mapeamentos&#41;](../../2014/integration-services/odbc-destination-editor-mappings-page.md) </span><span class="sxs-lookup"><span data-stu-id="40fca-141">[ODBC Destination Editor &#40;Mappings Page&#41;](../../2014/integration-services/odbc-destination-editor-mappings-page.md) </span></span>  
 [<span data-ttu-id="40fca-142">Editor do Destino ODBC &#40;Página Saída de Erro&#41;</span><span class="sxs-lookup"><span data-stu-id="40fca-142">ODBC Destination Editor &#40;Error Output Page&#41;</span></span>](../../2014/integration-services/odbc-destination-editor-error-output-page.md)  
  
  
