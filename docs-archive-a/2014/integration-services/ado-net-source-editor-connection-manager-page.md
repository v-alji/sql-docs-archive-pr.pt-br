---
title: Editor de origem ADO NET (página Gerenciador de conexões) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.adonetsource.connection.f1
ms.assetid: 7de3f438-bdd6-49b5-937a-47369e754943
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 19dd9c256f15bc9022f7267cb38b6f91bd4d8a5c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683648"
---
# <a name="ado-net-source-editor-connection-manager-page"></a><span data-ttu-id="e67aa-102">Editor de origem ADO NET (Página Gerenciador de Conexões)</span><span class="sxs-lookup"><span data-stu-id="e67aa-102">ADO NET Source Editor (Connection Manager Page)</span></span>
  <span data-ttu-id="e67aa-103">Use a página **Gerenciador de Conexões** da caixa de diálogo **Editor de Origem ADO NET** para selecionar o gerenciador de conexões [!INCLUDE[vstecado](../includes/vstecado-md.md)] para a origem.</span><span class="sxs-lookup"><span data-stu-id="e67aa-103">Use the **Connection Manager** page of the **ADO NET Source Editor** dialog box to select the [!INCLUDE[vstecado](../includes/vstecado-md.md)] connection manager for the source.</span></span> <span data-ttu-id="e67aa-104">Essa página também permite que você selecione uma tabela ou exibição a partir do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="e67aa-104">This page also lets you select a table or view from the database.</span></span>  
  
 <span data-ttu-id="e67aa-105">Para obter mais informações sobre a origem ADO NET, consulte [ADO NET Source](data-flow/ado-net-source.md).</span><span class="sxs-lookup"><span data-stu-id="e67aa-105">To learn more about the ADO NET source, see [ADO NET Source](data-flow/ado-net-source.md).</span></span>  
  
 <span data-ttu-id="e67aa-106">**Para abrir a página Gerenciador de Conexões**</span><span class="sxs-lookup"><span data-stu-id="e67aa-106">**To open the Connection Manager page**</span></span>  
  
1.  <span data-ttu-id="e67aa-107">No [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], abra o pacote [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] que tenha a origem ADO NET.</span><span class="sxs-lookup"><span data-stu-id="e67aa-107">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package that has the ADO NET source.</span></span>  
  
2.  <span data-ttu-id="e67aa-108">Na guia **Fluxo de Dados** , clique duas vezes na origem ADO NET.</span><span class="sxs-lookup"><span data-stu-id="e67aa-108">On the **Data Flow** tab, double-click the ADO NET source.</span></span>  
  
3.  <span data-ttu-id="e67aa-109">No **Editor de Origem ADO NET**, clique em **Gerenciador de Conexões**.</span><span class="sxs-lookup"><span data-stu-id="e67aa-109">In the **ADO NET Source Editor**, click **Connection Manager**.</span></span>  
  
## <a name="static-options"></a><span data-ttu-id="e67aa-110">Opções estáticas</span><span class="sxs-lookup"><span data-stu-id="e67aa-110">Static Options</span></span>  
 <span data-ttu-id="e67aa-111">**Gerenciador de conexões ADO.NET**</span><span class="sxs-lookup"><span data-stu-id="e67aa-111">**ADO.NET connection manager**</span></span>  
 <span data-ttu-id="e67aa-112">Selecione um gerenciador de conexões existente na lista ou crie uma nova conexão clicando em **Nova**.</span><span class="sxs-lookup"><span data-stu-id="e67aa-112">Select an existing connection manager from the list, or create a new connection by clicking **New**.</span></span>  
  
 <span data-ttu-id="e67aa-113">**Novo**</span><span class="sxs-lookup"><span data-stu-id="e67aa-113">**New**</span></span>  
 <span data-ttu-id="e67aa-114">Crie um novo gerenciador de conexões usando a caixa de diálogo **Configurar Gerenciador de Conexões ADO NET** .</span><span class="sxs-lookup"><span data-stu-id="e67aa-114">Create a new connection manager by using the **Configure ADO.NET Connection Manager** dialog box.</span></span>  
  
 <span data-ttu-id="e67aa-115">**Modo de acesso aos dados**</span><span class="sxs-lookup"><span data-stu-id="e67aa-115">**Data access mode**</span></span>  
 <span data-ttu-id="e67aa-116">Especifique o método para selecionar os dados da origem.</span><span class="sxs-lookup"><span data-stu-id="e67aa-116">Specify the method for selecting data from the source.</span></span>  
  
|<span data-ttu-id="e67aa-117">Opção</span><span class="sxs-lookup"><span data-stu-id="e67aa-117">Option</span></span>|<span data-ttu-id="e67aa-118">Descrição</span><span class="sxs-lookup"><span data-stu-id="e67aa-118">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="e67aa-119">Tabela ou exibição</span><span class="sxs-lookup"><span data-stu-id="e67aa-119">Table or view</span></span>|<span data-ttu-id="e67aa-120">Recupere os dados de uma tabela ou visualize na fonte de dados [!INCLUDE[vstecado](../includes/vstecado-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e67aa-120">Retrieve data from a table or view in the [!INCLUDE[vstecado](../includes/vstecado-md.md)] data source.</span></span>|  
|<span data-ttu-id="e67aa-121">Comando SQL</span><span class="sxs-lookup"><span data-stu-id="e67aa-121">SQL command</span></span>|<span data-ttu-id="e67aa-122">Recupere os dados da fonte de dados [!INCLUDE[vstecado](../includes/vstecado-md.md)] usando uma consulta SQL.</span><span class="sxs-lookup"><span data-stu-id="e67aa-122">Retrieve data from the [!INCLUDE[vstecado](../includes/vstecado-md.md)] data source by using a SQL query.</span></span>|  
  
 <span data-ttu-id="e67aa-123">**Visualização**</span><span class="sxs-lookup"><span data-stu-id="e67aa-123">**Preview**</span></span>  
 <span data-ttu-id="e67aa-124">Visualize os resultados usando a caixa de diálogo **Exibição de Dados** .</span><span class="sxs-lookup"><span data-stu-id="e67aa-124">Preview results by using the **Data View** dialog box.</span></span> <span data-ttu-id="e67aa-125">A**visualização** pode exibir até 200 linhas.</span><span class="sxs-lookup"><span data-stu-id="e67aa-125">**Preview** can display up to 200 rows.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e67aa-126">Quando você visualiza os dados, as colunas com um tipo de dado CLR definido pelo usuário não contêm dados.</span><span class="sxs-lookup"><span data-stu-id="e67aa-126">When you preview data, columns with a CLR user-defined type do not contain data.</span></span> <span data-ttu-id="e67aa-127">Em vez disso, os valores de \<value too big to display> ou System.Byte[] são exibidos.</span><span class="sxs-lookup"><span data-stu-id="e67aa-127">Instead the values \<value too big to display> or System.Byte[] display.</span></span> <span data-ttu-id="e67aa-128">O primeiro é exibido quando a fonte de dados é acessada usando o provedor [!INCLUDE[vstecado](../includes/vstecado-md.md)] , o último ao usar o provedor Native Client do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e67aa-128">The former displays when the data source is accessed by using the [!INCLUDE[vstecado](../includes/vstecado-md.md)] provider, the latter when using the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Native Client provider.</span></span>  
  
## <a name="data-access-mode-dynamic-options"></a><span data-ttu-id="e67aa-129">Opções dinâmicas de modo de acesso aos dados</span><span class="sxs-lookup"><span data-stu-id="e67aa-129">Data Access Mode Dynamic Options</span></span>  
  
### <a name="data-access-mode--table-or-view"></a><span data-ttu-id="e67aa-130">Modo de acesso aos dados = Tabela ou exibição</span><span class="sxs-lookup"><span data-stu-id="e67aa-130">Data access mode = Table or view</span></span>  
 <span data-ttu-id="e67aa-131">**Nome da tabela ou da exibição**</span><span class="sxs-lookup"><span data-stu-id="e67aa-131">**Name of the table or the view**</span></span>  
 <span data-ttu-id="e67aa-132">Selecione o nome da tabela ou da exibição na lista de tabelas ou exibições disponíveis na fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="e67aa-132">Select the name of the table or view from a list of those available in the data source.</span></span>  
  
### <a name="data-access-mode--sql-command"></a><span data-ttu-id="e67aa-133">Modo de acesso aos dados = Comando SQL</span><span class="sxs-lookup"><span data-stu-id="e67aa-133">Data access mode = SQL command</span></span>  
 <span data-ttu-id="e67aa-134">**Texto do comando SQL**</span><span class="sxs-lookup"><span data-stu-id="e67aa-134">**SQL command text**</span></span>  
 <span data-ttu-id="e67aa-135">Digite o texto de uma consulta SQL, crie a consulta clicando em **Construir Consulta**ou localize o arquivo que contém o texto da consulta clicando em **Procurar**.</span><span class="sxs-lookup"><span data-stu-id="e67aa-135">Enter the text of a SQL query, build the query by clicking **Build Query**, or locate the file that contains the query text by clicking **Browse**.</span></span>  
  
 <span data-ttu-id="e67aa-136">**Construir consulta**</span><span class="sxs-lookup"><span data-stu-id="e67aa-136">**Build query**</span></span>  
 <span data-ttu-id="e67aa-137">Use a caixa de diálogo **Construtor de Consultas** para construir a consulta SQL visualmente.</span><span class="sxs-lookup"><span data-stu-id="e67aa-137">Use the **Query Builder** dialog box to construct the SQL query visually.</span></span>  
  
 <span data-ttu-id="e67aa-138">**Procurar**</span><span class="sxs-lookup"><span data-stu-id="e67aa-138">**Browse**</span></span>  
 <span data-ttu-id="e67aa-139">Use a caixa de diálogo **Abrir** para localizar o arquivo com contém o texto da consulta SQL.</span><span class="sxs-lookup"><span data-stu-id="e67aa-139">Use the **Open** dialog box to locate the file that contains the text of the SQL query.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e67aa-140">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e67aa-140">See Also</span></span>  
 <span data-ttu-id="e67aa-141">[Editor de origem ADO NET &#40;página colunas&#41;](../../2014/integration-services/ado-net-source-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="e67aa-141">[ADO NET Source Editor &#40;Columns Page&#41;](../../2014/integration-services/ado-net-source-editor-columns-page.md) </span></span>  
 <span data-ttu-id="e67aa-142">[Editor de origem ADO NET &#40;página saída de erro&#41;](../../2014/integration-services/ado-net-source-editor-error-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="e67aa-142">[ADO NET Source Editor &#40;Error Output Page&#41;](../../2014/integration-services/ado-net-source-editor-error-output-page.md) </span></span>  
 [<span data-ttu-id="e67aa-143">Gerenciador de conexões ADO.NET</span><span class="sxs-lookup"><span data-stu-id="e67aa-143">ADO.NET Connection Manager</span></span>](connection-manager/ado-net-connection-manager.md)  
  
  
