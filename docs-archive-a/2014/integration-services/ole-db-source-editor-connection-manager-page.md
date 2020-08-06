---
title: Editor de origem de OLE DB (página Gerenciador de conexões) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.oledbsourceadapter.connection.f1
helpviewer_keywords:
- OLE DB Source Editor
ms.assetid: 53699902-8699-4547-b56b-a5b2079e98b6
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e6b9d841ff902107847a9d85779af41f476315db
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582539"
---
# <a name="ole-db-source-editor-connection-manager-page"></a><span data-ttu-id="d387d-102">Editor de Origem OLE DB (página Gerenciador de Conexões)</span><span class="sxs-lookup"><span data-stu-id="d387d-102">OLE DB Source Editor (Connection Manager Page)</span></span>
  <span data-ttu-id="d387d-103">Use a página **Gerenciador de Conexões** da caixa de diálogo **Editor de Origem OLE DB** para selecionar o gerenciador de conexões OLE DB para a origem.</span><span class="sxs-lookup"><span data-stu-id="d387d-103">Use the **Connection Manager** page of the **OLE DB Source Editor** dialog box to select the OLE DB connection manager for the source.</span></span> <span data-ttu-id="d387d-104">Essa página também permite que você selecione uma tabela ou exibição a partir do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="d387d-104">This page also lets you select a table or view from the database.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d387d-105">Para carregar dados de uma fonte de dados que usa o [!INCLUDE[msCoName](../includes/msconame-md.md)] Office Excel 2007, use uma origem OLE DB.</span><span class="sxs-lookup"><span data-stu-id="d387d-105">To load data from a data source that uses [!INCLUDE[msCoName](../includes/msconame-md.md)] Office Excel 2007, use an OLE DB source.</span></span> <span data-ttu-id="d387d-106">Você não pode usar uma origem do Excel para carregar dados de uma fonte de dados do Excel 2007.</span><span class="sxs-lookup"><span data-stu-id="d387d-106">You cannot use an Excel source to load data from an Excel 2007 data source.</span></span> <span data-ttu-id="d387d-107">Para obter mais informações, consulte [Configurar Gerenciador de Conexões OLE DB](configure-ole-db-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="d387d-107">For more information, see [Configure OLE DB Connection Manager](configure-ole-db-connection-manager.md).</span></span>  
>   
>  <span data-ttu-id="d387d-108">Para carregar dados de uma fonte de dados que usa o [!INCLUDE[msCoName](../includes/msconame-md.md)] Office Excel 2003 ou uma versão anterior, use uma origem do Excel.</span><span class="sxs-lookup"><span data-stu-id="d387d-108">To load data from a data source that uses [!INCLUDE[msCoName](../includes/msconame-md.md)] Office Excel 2003 or earlier, use an Excel source.</span></span> <span data-ttu-id="d387d-109">Para obter mais informações, consulte [Editor de Fonte Excel &#40;Página Gerenciador de Conexões&#41;](../../2014/integration-services/excel-source-editor-connection-manager-page.md).</span><span class="sxs-lookup"><span data-stu-id="d387d-109">For more information, see [Excel Source Editor &#40;Connection Manager Page&#41;](../../2014/integration-services/excel-source-editor-connection-manager-page.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d387d-110">A `CommandTimeout` propriedade da fonte de OLE DB não está disponível no **Editor de fonte de OLE DB**, mas pode ser definida usando o **Editor avançado**.</span><span class="sxs-lookup"><span data-stu-id="d387d-110">The `CommandTimeout` property of the OLE DB source is not available in the **OLE DB Source Editor**, but can be set by using the **Advanced Editor**.</span></span> <span data-ttu-id="d387d-111">Para obter mais informações sobre esta propriedade, consulte a seção Origem do Excel em [Propriedades personalizadas do OLE DB](data-flow/ole-db-custom-properties.md).</span><span class="sxs-lookup"><span data-stu-id="d387d-111">For more information on this property, see the Excel Source section of [OLE DB Custom Properties](data-flow/ole-db-custom-properties.md).</span></span>  
  
 <span data-ttu-id="d387d-112">Para saber mais sobre a origem de OLE DB, consulte [OLE DB Source](data-flow/ole-db-source.md).</span><span class="sxs-lookup"><span data-stu-id="d387d-112">To learn more about the OLE DB source, see [OLE DB Source](data-flow/ole-db-source.md).</span></span>  
  
## <a name="open-the-ole-db-source-editor-connection-manager-page"></a><span data-ttu-id="d387d-113">Abrir a página do Gerenciador de Conexões do Editor de Origem OLE DB</span><span class="sxs-lookup"><span data-stu-id="d387d-113">Open the OLE DB Source Editor (Connection Manager Page</span></span>  
  
1.  <span data-ttu-id="d387d-114">Adicione a origem OLE DB ao pacote do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , no [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d387d-114">Add the OLE DB source to the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package, in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="d387d-115">Clique com o botão direito do mouse no componente de origem e clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="d387d-115">Right-click the source component and when click **Edit**.</span></span>  
  
3.  <span data-ttu-id="d387d-116">Clique em **Gerenciador de Conexões**.</span><span class="sxs-lookup"><span data-stu-id="d387d-116">Click **Connection Manager**.</span></span>  
  
## <a name="static-options"></a><span data-ttu-id="d387d-117">Opções estáticas</span><span class="sxs-lookup"><span data-stu-id="d387d-117">Static Options</span></span>  
 <span data-ttu-id="d387d-118">**Gerenciador de conexões OLE DB**</span><span class="sxs-lookup"><span data-stu-id="d387d-118">**OLE DB connection manager**</span></span>  
 <span data-ttu-id="d387d-119">Selecione um gerenciador de conexões existente na lista ou crie uma nova conexão clicando em **Nova**.</span><span class="sxs-lookup"><span data-stu-id="d387d-119">Select an existing connection manager from the list, or create a new connection by clicking **New**.</span></span>  
  
 <span data-ttu-id="d387d-120">**Novo**</span><span class="sxs-lookup"><span data-stu-id="d387d-120">**New**</span></span>  
 <span data-ttu-id="d387d-121">Crie um novo gerenciador de conexões usando a caixa de diálogo **Configurar Gerenciador de Conexões OLE DB** .</span><span class="sxs-lookup"><span data-stu-id="d387d-121">Create a new connection manager by using the **Configure OLE DB Connection Manager** dialog box.</span></span>  
  
 <span data-ttu-id="d387d-122">**Modo de acesso aos dados**</span><span class="sxs-lookup"><span data-stu-id="d387d-122">**Data access mode**</span></span>  
 <span data-ttu-id="d387d-123">Especifique o método para selecionar os dados da origem.</span><span class="sxs-lookup"><span data-stu-id="d387d-123">Specify the method for selecting data from the source.</span></span>  
  
|<span data-ttu-id="d387d-124">Opção</span><span class="sxs-lookup"><span data-stu-id="d387d-124">Option</span></span>|<span data-ttu-id="d387d-125">Descrição</span><span class="sxs-lookup"><span data-stu-id="d387d-125">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="d387d-126">Tabela ou exibição</span><span class="sxs-lookup"><span data-stu-id="d387d-126">Table or view</span></span>|<span data-ttu-id="d387d-127">Recupere os dados de uma tabela ou exibição na fonte de dados OLE DB.</span><span class="sxs-lookup"><span data-stu-id="d387d-127">Retrieve data from a table or view in the OLE DB data source.</span></span>|  
|<span data-ttu-id="d387d-128">Nome da tabela ou variável do nome de exibição</span><span class="sxs-lookup"><span data-stu-id="d387d-128">Table name or view name variable</span></span>|<span data-ttu-id="d387d-129">Especifique a tabela ou nome de exibição em uma variável.</span><span class="sxs-lookup"><span data-stu-id="d387d-129">Specify the table or view name in a variable.</span></span><br /><br /> <span data-ttu-id="d387d-130">**Informações relacionadas:** [Usar variáveis em pacotes](../../2014/integration-services/use-variables-in-packages.md)</span><span class="sxs-lookup"><span data-stu-id="d387d-130">**Related information:** [Use Variables in Packages](../../2014/integration-services/use-variables-in-packages.md)</span></span>|  
|<span data-ttu-id="d387d-131">Comando SQL</span><span class="sxs-lookup"><span data-stu-id="d387d-131">SQL command</span></span>|<span data-ttu-id="d387d-132">Recupere os dados da fonte de dados OLE DB usando uma consulta SQL.</span><span class="sxs-lookup"><span data-stu-id="d387d-132">Retrieve data from the OLE DB data source by using a SQL query.</span></span>|  
|<span data-ttu-id="d387d-133">Comando SQL a partir da variável</span><span class="sxs-lookup"><span data-stu-id="d387d-133">SQL command from variable</span></span>|<span data-ttu-id="d387d-134">Especifique o texto da consulta SQL em uma variável.</span><span class="sxs-lookup"><span data-stu-id="d387d-134">Specify the SQL query text in a variable.</span></span>|  
  
 <span data-ttu-id="d387d-135">**Visualização**</span><span class="sxs-lookup"><span data-stu-id="d387d-135">**Preview**</span></span>  
 <span data-ttu-id="d387d-136">Visualize os resultados usando a caixa de diálogo **Exibição de Dados** .</span><span class="sxs-lookup"><span data-stu-id="d387d-136">Preview results by using the **Data View** dialog box.</span></span> <span data-ttu-id="d387d-137">A**visualização** pode exibir até 200 linhas.</span><span class="sxs-lookup"><span data-stu-id="d387d-137">**Preview** can display up to 200 rows.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d387d-138">Quando você visualiza os dados, as colunas com um tipo de dado CLR definido pelo usuário não contêm dados.</span><span class="sxs-lookup"><span data-stu-id="d387d-138">When you preview data, columns with a CLR user-defined type do not contain data.</span></span> <span data-ttu-id="d387d-139">Em vez disso, os valores de \<value too big to display> ou System.Byte[] são exibidos.</span><span class="sxs-lookup"><span data-stu-id="d387d-139">Instead the values \<value too big to display> or System.Byte[] display.</span></span> <span data-ttu-id="d387d-140">O primeiro é exibido quando a fonte de dados é acessada usando o provedor SQL OLE DB e o segundo, usando o provedor [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="d387d-140">The former displays when the data source is accessed using the SQL OLE DB provider, the latter when using the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Native Client provider.</span></span>  
  
## <a name="data-access-mode-dynamic-options"></a><span data-ttu-id="d387d-141">Opções dinâmicas de modo de acesso aos dados</span><span class="sxs-lookup"><span data-stu-id="d387d-141">Data Access Mode Dynamic Options</span></span>  
  
### <a name="data-access-mode--table-or-view"></a><span data-ttu-id="d387d-142">Modo de acesso aos dados = Tabela ou exibição</span><span class="sxs-lookup"><span data-stu-id="d387d-142">Data access mode = Table or view</span></span>  
 <span data-ttu-id="d387d-143">**Nome da tabela ou da exibição**</span><span class="sxs-lookup"><span data-stu-id="d387d-143">**Name of the table or the view**</span></span>  
 <span data-ttu-id="d387d-144">Selecione o nome da tabela ou da exibição na lista de tabelas ou exibições disponíveis na fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="d387d-144">Select the name of the table or view from a list of those available in the data source.</span></span>  
  
### <a name="data-access-mode--table-name-or-view-name-variable"></a><span data-ttu-id="d387d-145">Modo de acesso aos dados = Variável do nome da tabela ou do nome de exibição</span><span class="sxs-lookup"><span data-stu-id="d387d-145">Data access mode = Table name or view name variable</span></span>  
 <span data-ttu-id="d387d-146">**Nome da variável**</span><span class="sxs-lookup"><span data-stu-id="d387d-146">**Variable name**</span></span>  
 <span data-ttu-id="d387d-147">Selecione a variável que contém o nome da tabela ou da exibição.</span><span class="sxs-lookup"><span data-stu-id="d387d-147">Select the variable that contains the name of the table or view.</span></span>  
  
### <a name="data-access-mode--sql-command"></a><span data-ttu-id="d387d-148">Modo de acesso aos dados = Comando SQL</span><span class="sxs-lookup"><span data-stu-id="d387d-148">Data access mode = SQL command</span></span>  
 <span data-ttu-id="d387d-149">**Texto do comando SQL**</span><span class="sxs-lookup"><span data-stu-id="d387d-149">**SQL command text**</span></span>  
 <span data-ttu-id="d387d-150">Digite o texto de uma consulta SQL, crie a consulta clicando em **Construir Consulta**ou localize o arquivo que contém o texto da consulta clicando em **Procurar**.</span><span class="sxs-lookup"><span data-stu-id="d387d-150">Enter the text of a SQL query, build the query by clicking **Build Query**, or locate the file that contains the query text by clicking **Browse**.</span></span>  
  
 <span data-ttu-id="d387d-151">**Parâmetros**</span><span class="sxs-lookup"><span data-stu-id="d387d-151">**Parameters**</span></span>  
 <span data-ttu-id="d387d-152">Se você inseriu uma consulta parametrizada usando ?</span><span class="sxs-lookup"><span data-stu-id="d387d-152">If you have entered a parameterized query by using ?</span></span> <span data-ttu-id="d387d-153">como um espaço reservado para o parâmetro no texto da consulta, use a caixa de diálogo **Definir Parâmetros da Consulta** para mapear os parâmetros de entrada da consulta para as variáveis do pacote.</span><span class="sxs-lookup"><span data-stu-id="d387d-153">as a parameter placeholder in the query text, use the **Set Query Parameters** dialog box to map query input parameters to package variables.</span></span>  
  
 <span data-ttu-id="d387d-154">**Construir consulta**</span><span class="sxs-lookup"><span data-stu-id="d387d-154">**Build query**</span></span>  
 <span data-ttu-id="d387d-155">Use a caixa de diálogo **Construtor de Consultas** para construir a consulta SQL visualmente.</span><span class="sxs-lookup"><span data-stu-id="d387d-155">Use the **Query Builder** dialog box to construct the SQL query visually.</span></span>  
  
 <span data-ttu-id="d387d-156">**Procurar**</span><span class="sxs-lookup"><span data-stu-id="d387d-156">**Browse**</span></span>  
 <span data-ttu-id="d387d-157">Use a caixa de diálogo **Abrir** para localizar o arquivo com contém o texto da consulta SQL.</span><span class="sxs-lookup"><span data-stu-id="d387d-157">Use the **Open** dialog box to locate the file that contains the text of the SQL query.</span></span>  
  
 <span data-ttu-id="d387d-158">**Analisar consulta**</span><span class="sxs-lookup"><span data-stu-id="d387d-158">**Parse query**</span></span>  
 <span data-ttu-id="d387d-159">Verifique a sintaxe do texto da consulta.</span><span class="sxs-lookup"><span data-stu-id="d387d-159">Verify the syntax of the query text.</span></span>  
  
### <a name="data-access-mode--sql-command-from-variable"></a><span data-ttu-id="d387d-160">Modo de acesso aos dados = Comando SQL a partir da variável</span><span class="sxs-lookup"><span data-stu-id="d387d-160">Data access mode = SQL command from variable</span></span>  
 <span data-ttu-id="d387d-161">**Nome da variável**</span><span class="sxs-lookup"><span data-stu-id="d387d-161">**Variable name**</span></span>  
 <span data-ttu-id="d387d-162">Selecione a variável que contém o texto da consulta SQL.</span><span class="sxs-lookup"><span data-stu-id="d387d-162">Select the variable that contains the text of the SQL query.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d387d-163">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d387d-163">See Also</span></span>  
 <span data-ttu-id="d387d-164">[Referência de mensagens e erros do Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="d387d-164">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="d387d-165">[Editor de fonte de OLE DB &#40;página colunas&#41;](../../2014/integration-services/ole-db-source-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="d387d-165">[OLE DB Source Editor &#40;Columns Page&#41;](../../2014/integration-services/ole-db-source-editor-columns-page.md) </span></span>  
 <span data-ttu-id="d387d-166">[Editor de origem OLE DB &#40;página saída de erro&#41;](../../2014/integration-services/ole-db-source-editor-error-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="d387d-166">[OLE DB Source Editor &#40;Error Output Page&#41;](../../2014/integration-services/ole-db-source-editor-error-output-page.md) </span></span>  
 <span data-ttu-id="d387d-167">[Extrair dados usando a fonte de OLE DB](data-flow/extract-data-by-using-the-ole-db-source.md) </span><span class="sxs-lookup"><span data-stu-id="d387d-167">[Extract Data by Using the OLE DB Source](data-flow/extract-data-by-using-the-ole-db-source.md) </span></span>  
 [<span data-ttu-id="d387d-168">Gerenciador de conexões OLE DB</span><span class="sxs-lookup"><span data-stu-id="d387d-168">OLE DB Connection Manager</span></span>](connection-manager/ole-db-connection-manager.md)  
  
  
