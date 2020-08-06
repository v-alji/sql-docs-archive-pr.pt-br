---
title: Criar um conjunto de dados compartilhado ou um conjunto de dados inserido (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: d1d7bc71-f0e9-4ce5-b3ad-6fee54388a31
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: fca74e1ba7965eeef6ce562e79e378af5bb9e145
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679172"
---
# <a name="create-a-shared-dataset-or-embedded-dataset-report-builder-and-ssrs"></a><span data-ttu-id="b4725-102">Criar um conjunto de dados compartilhado ou um conjunto de dados inserido (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="b4725-102">Create a Shared Dataset or Embedded Dataset (Report Builder and SSRS)</span></span>
  <span data-ttu-id="b4725-103">É possível criar um conjunto de dados inserido para uso em um único relatório, ou criar um conjunto de dados compartilhado para ser salvo em um servidor de relatório e ser utilizado por vários relatórios.</span><span class="sxs-lookup"><span data-stu-id="b4725-103">You can create an embedded dataset for use in a single report or a shared dataset to save to a report server, for use by multiple reports.</span></span> <span data-ttu-id="b4725-104">Para criar um conjunto de dados, é necessária uma fonte de dados inserida ou compartilhada.</span><span class="sxs-lookup"><span data-stu-id="b4725-104">To create a dataset, you must have an embedded or shared data source.</span></span>

 <span data-ttu-id="b4725-105">Use o Construtor de Relatórios para executar as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="b4725-105">Use Report Builder to do the following tasks:</span></span>

-   <span data-ttu-id="b4725-106">Crie um conjunto de dados compartilhado no modo de exibição Design de Conjunto de Dados.</span><span class="sxs-lookup"><span data-stu-id="b4725-106">Create a shared dataset in Dataset Design View.</span></span> <span data-ttu-id="b4725-107">Os conjuntos de dados compartilhados devem usar fontes de dados compartilhadas publicadas.</span><span class="sxs-lookup"><span data-stu-id="b4725-107">Shared datasets must use published shared data sources.</span></span>

-   <span data-ttu-id="b4725-108">Crie um conjunto de dados inserido no modo de exibição Design de Relatório.</span><span class="sxs-lookup"><span data-stu-id="b4725-108">Create an embedded dataset in Report Design View.</span></span>

-   <span data-ttu-id="b4725-109">Salve o conjunto de dados diretamente no servidor de relatório ou no site do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="b4725-109">Save the dataset directly to the report server or SharePoint site.</span></span>

 <span data-ttu-id="b4725-110">Use o Designer de Relatórios no [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] para executar as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="b4725-110">Use Report Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] to do the following tasks:</span></span>

1.  <span data-ttu-id="b4725-111">Crie um conjunto de dados compartilhado no Gerenciador de Soluções.</span><span class="sxs-lookup"><span data-stu-id="b4725-111">Create a shared dataset in Solution Explorer.</span></span> <span data-ttu-id="b4725-112">Conjuntos de dados compartilhados devem usar fontes de dados da pasta Fontes de Dados Compartilhadas no Gerenciador de Soluções.</span><span class="sxs-lookup"><span data-stu-id="b4725-112">Shared datasets must use data sources from the Shared Data Sources folder in Solution Explorer.</span></span>

2.  <span data-ttu-id="b4725-113">Crie um conjunto de dados inserido no painel de dados do relatório.</span><span class="sxs-lookup"><span data-stu-id="b4725-113">Create an embedded dataset in the Report Data pane.</span></span>

3.  <span data-ttu-id="b4725-114">Outra opção é implantar os conjuntos de dados compartilhados e a fonte de dados compartilhada com o relatório.</span><span class="sxs-lookup"><span data-stu-id="b4725-114">Optionally deploy the shared datasets and shared data source with the report.</span></span> <span data-ttu-id="b4725-115">Para cada tipo de item, use Propriedades do Projeto para especificar caminhos para pastas no servidor de relatório ou no site do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="b4725-115">For each type of item, use Project Properties to specify paths to folders on the report server or SharePoint site.</span></span>

 <span data-ttu-id="b4725-116">Para obter mais informações, consulte [Conjuntos de dados inseridos e compartilhados de relatório &#40;Construtor de Relatórios e SSRS&#41;](report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="b4725-116">For more information, see [Report Embedded Datasets and Shared Datasets &#40;Report Builder and SSRS&#41;](report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md).</span></span>

> [!NOTE]
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]

### <a name="to-open-report-builder-and-create-a-shared-dataset"></a><span data-ttu-id="b4725-117">Para abrir o Construtor de Relatórios e criar um conjunto de dados compartilhado</span><span class="sxs-lookup"><span data-stu-id="b4725-117">To open Report Builder and create a shared dataset</span></span>

1.  <span data-ttu-id="b4725-118">Abra o Construtor de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="b4725-118">Open Report Builder.</span></span> <span data-ttu-id="b4725-119">O **Painel de novo relatório ou conjunto de dados** abre, como mostrado na figura seguinte:</span><span class="sxs-lookup"><span data-stu-id="b4725-119">The **New report or dataset pane** opens, as shown in the following figure:</span></span>

     <span data-ttu-id="b4725-120">![rs_NewSharedDataset](../media/rs-newshareddataset.gif "rs_NewSharedDataset")</span><span class="sxs-lookup"><span data-stu-id="b4725-120">![rs_NewSharedDataset](../media/rs-newshareddataset.gif "rs_NewSharedDataset")</span></span>

    > [!NOTE]
    >  <span data-ttu-id="b4725-121">Se o **painel Novo relatório ou conjunto de dados** não for exibido, no botão Construtor de Relatórios, clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="b4725-121">If the **New report or dataset pane** does not appear, from the Report Builder button, click **New**.</span></span>

2.  <span data-ttu-id="b4725-122">No painel esquerdo, sob **Criar um conjunto de dados**, clique em **Conjunto de Dados Compartilhado**.</span><span class="sxs-lookup"><span data-stu-id="b4725-122">In the left pane, under **Create a dataset**, click **Shared Dataset**.</span></span>

3.  <span data-ttu-id="b4725-123">No painel direito, clique em **Procurar** para selecionar uma fonte de dados compartilhada no servidor de relatório e clique em **Criar**.</span><span class="sxs-lookup"><span data-stu-id="b4725-123">In the right pane, click **Browse** to select a shared data source from the report server, and then click **Create**.</span></span> <span data-ttu-id="b4725-124">O designer de consulta associado à fonte de dados compartilhada é aberto.</span><span class="sxs-lookup"><span data-stu-id="b4725-124">The query designer associated with the shared data source opens.</span></span>

4.  <span data-ttu-id="b4725-125">No designer de consulta, especifique os campos a serem incluídos no conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="b4725-125">In the query designer, specify the fields to include in the dataset.</span></span>

5.  <span data-ttu-id="b4725-126">Clique em **executar** (**!**) para executar a consulta.</span><span class="sxs-lookup"><span data-stu-id="b4725-126">Click **Run** (**!**) to run the query.</span></span>

6.  <span data-ttu-id="b4725-127">No botão **Construtor de Relatórios** , clique em **Salvar** ou em **Salvar como** para salvar o conjunto de dados compartilhado no servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="b4725-127">On the **Report Builder** button, click **Save** or **Save As** to save the shared dataset to the report server.</span></span>

7.  <span data-ttu-id="b4725-128">Para sair do Construtor de Relatórios, clique em **Construtor de Relatórios**e em **Sair do Construtor de Relatórios**.</span><span class="sxs-lookup"><span data-stu-id="b4725-128">To exit Report Builder, click **Report Builder**, and then click **Exit Report Builder**.</span></span> <span data-ttu-id="b4725-129">Para trabalhar com relatórios, clique em **Construtor de Relatórios**e em **Novo** ou **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="b4725-129">To work with reports, click **Report Builder**, and then click **New** or **Open**.</span></span>

### <a name="to-set-query-parameter-options"></a><span data-ttu-id="b4725-130">Para definir opções de parâmetro de consulta</span><span class="sxs-lookup"><span data-stu-id="b4725-130">To set query parameter options</span></span>

1.  <span data-ttu-id="b4725-131">Abra o Construtor de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="b4725-131">Open Report Builder.</span></span>

2.  <span data-ttu-id="b4725-132">Clique em **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="b4725-132">Click **Open**.</span></span>

3.  <span data-ttu-id="b4725-133">Navegue até o servidor de relatório e selecione a pasta da fonte de dados compartilhada.</span><span class="sxs-lookup"><span data-stu-id="b4725-133">Browse to the report server, and select the folder for the shared data source.</span></span>

4.  <span data-ttu-id="b4725-134">Em **Itens de tipo**, clique em Conjuntos de Dados (\*.rsd) na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="b4725-134">In **Items of type**, click Datasets (\*.rsd) in the drop-down list.</span></span>

5.  <span data-ttu-id="b4725-135">Selecione o conjunto de dados compartilhado e clique em **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="b4725-135">Select the shared dataset, and then click **Open**.</span></span> <span data-ttu-id="b4725-136">O designer de consulta associado é aberto.</span><span class="sxs-lookup"><span data-stu-id="b4725-136">The associated query designer opens.</span></span>

6.  <span data-ttu-id="b4725-137">No Faixa de Opções, clique em **Propriedades do Conjunto de Dados**.</span><span class="sxs-lookup"><span data-stu-id="b4725-137">On the Ribbon, click **Dataset Properties**.</span></span>

7.  <span data-ttu-id="b4725-138">Clique em **Parâmetros**.</span><span class="sxs-lookup"><span data-stu-id="b4725-138">Click **Parameters**.</span></span> <span data-ttu-id="b4725-139">Nessa página, defina um valor padrão como uma constante ou uma expressão, marque o parâmetro como somente leitura, anulável ou **Omitir da Consulta**.</span><span class="sxs-lookup"><span data-stu-id="b4725-139">On this page, set a default value to a constant or an expression, mark the parameter as read-only, nullable, or **Omit From Query**.</span></span> <span data-ttu-id="b4725-140">Para obter mais informações, consulte [Caixa de Diálogo Propriedades de Conjunto de Dados, Parâmetros &#40;Construtor de Relatórios&#41;](../dataset-properties-dialog-box-parameters-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="b4725-140">For more information, see [Dataset Properties Dialog Box, Parameters &#40;Report Builder&#41;](../dataset-properties-dialog-box-parameters-report-builder.md).</span></span>

8.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]


### <a name="to-create-a-dataset-from-a-sql-server-relational-database"></a><span data-ttu-id="b4725-141">Para criar um conjunto de dados a partir de um banco de dados relacional do SQL Server</span><span class="sxs-lookup"><span data-stu-id="b4725-141">To create a dataset from a SQL Server relational database</span></span>

1.  <span data-ttu-id="b4725-142">No painel de dados do relatório, clique com o botão direito do mouse no nome da fonte de dados e clique em **Adicionar Conjunto de Dados**.</span><span class="sxs-lookup"><span data-stu-id="b4725-142">In the Report Data pane, right-click the name of the data source, and then click **Add Dataset**.</span></span> <span data-ttu-id="b4725-143">A página **Consulta** da caixa de diálogo **Propriedades do Conjunto de Dados** é aberta.</span><span class="sxs-lookup"><span data-stu-id="b4725-143">The **Query** page of the **Dataset Properties** dialog box opens.</span></span>

2.  <span data-ttu-id="b4725-144">Em **Nome**, digite um nome para o conjunto de dados ou aceite o nome padrão.</span><span class="sxs-lookup"><span data-stu-id="b4725-144">In **Name**, type a name for the dataset or accept the default name.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="b4725-145">O nome do conjunto de dados é usado internamente no relatório.</span><span class="sxs-lookup"><span data-stu-id="b4725-145">The dataset name is used internally within the report.</span></span> <span data-ttu-id="b4725-146">Para maior clareza, é recomendável que o nome do conjunto de dados descreva os dados retornados pela consulta.</span><span class="sxs-lookup"><span data-stu-id="b4725-146">For clarity, we recommend that the name of the dataset describe the data that the query returns.</span></span>

3.  <span data-ttu-id="b4725-147">Em **Fonte de dados**, navegue até o nome de uma fonte de dados compartilhada existente e selecione-o, ou clique em **Nova** para criar uma nova fonte de dados inserida.</span><span class="sxs-lookup"><span data-stu-id="b4725-147">In **Data source**, browse to and select the name of an existing shared data source, or click **New** to create a new embedded data source.</span></span>

4.  <span data-ttu-id="b4725-148">Selecione uma opção de **Tipo de consulta** .</span><span class="sxs-lookup"><span data-stu-id="b4725-148">Select a **Query type** option.</span></span> <span data-ttu-id="b4725-149">As opções dependem do tipo de fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="b4725-149">Options depend on the data source type.</span></span>

    -   <span data-ttu-id="b4725-150">Selecione **Texto** para gravar uma consulta usando a linguagem de consulta da fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="b4725-150">Select **Text** to write a query using the query language of the data source.</span></span>

    -   <span data-ttu-id="b4725-151">Selecione **Tabela** para retornar todos os campos em uma tabela de banco de dados relacional.</span><span class="sxs-lookup"><span data-stu-id="b4725-151">Select **Table** to return all the fields in a relational database table.</span></span>

    -   <span data-ttu-id="b4725-152">Selecione **StoredProcedure** para executar um procedimento armazenado pelo nome.</span><span class="sxs-lookup"><span data-stu-id="b4725-152">Select **StoredProcedure** to run a stored procedure by name.</span></span>

5.  <span data-ttu-id="b4725-153">Em **Consulta**, digite o nome da consulta, do procedimento armazenado ou da tabela.</span><span class="sxs-lookup"><span data-stu-id="b4725-153">In **Query**, type the query, stored procedure, or table name.</span></span> <span data-ttu-id="b4725-154">Se quiser, clique em **Designer de Consulta** para abrir a ferramenta de designer gráfico ou com base em texto, ou clique em **Importar** para importar a consulta por meio de um relatório existente.</span><span class="sxs-lookup"><span data-stu-id="b4725-154">Alternatively, click **Query Designer** to open the graphical or text-based query designer tool, or **Import** to import the query from an existing report.</span></span>

     <span data-ttu-id="b4725-155">Em alguns casos, a coleção de campos especificada pela consulta só pode ser determinada ao executar a consulta na fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="b4725-155">In a few cases, the field collection specified by the query can only be determined by running the query on the data source.</span></span> <span data-ttu-id="b4725-156">Por exemplo, um procedimento armazenado pode retornar um conjunto de campos variável no conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="b4725-156">For example, a stored procedure may return a variable set of fields in the result set.</span></span> <span data-ttu-id="b4725-157">Clique em **Atualizar Campos** para executar a consulta na fonte de dados e recuperar os nomes de campo que são necessários para preencher a coleção de campos do conjunto de dados no painel de dados do relatório.</span><span class="sxs-lookup"><span data-stu-id="b4725-157">Click **Refresh Fields** to run the query on the data source and retrieve the field names that are needed to populate the dataset field collection in the Report Data pane.</span></span> <span data-ttu-id="b4725-158">A coleção de campos é exibida abaixo do nó do conjunto de dados depois que a caixa de diálogo **Propriedades do Conjunto de Dados** é fechada.</span><span class="sxs-lookup"><span data-stu-id="b4725-158">The field collection appears under the dataset node after you close the **Dataset Properties** dialog box.</span></span>

6.  <span data-ttu-id="b4725-159">Em **Tempo Limite**, digite o número de segundos que o servidor de relatórios deve aguardar para receber uma resposta do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="b4725-159">In **Timeout**, type the number of seconds that the report server waits for a response from the database.</span></span> <span data-ttu-id="b4725-160">O valor padrão é 0 segundos.</span><span class="sxs-lookup"><span data-stu-id="b4725-160">The default value is 0 seconds.</span></span> <span data-ttu-id="b4725-161">Quando o valor do tempo limite for 0, a consulta não terá um tempo limite.</span><span class="sxs-lookup"><span data-stu-id="b4725-161">When the time out value is 0 seconds, the query does not time out.</span></span>

7.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]

     <span data-ttu-id="b4725-162">O conjunto de dados e sua coleção de campos aparecerão no painel de dados do relatório abaixo do nó da fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="b4725-162">The dataset and its field collection appear in the Report Data pane under the data source node.</span></span>

## <a name="see-also"></a><span data-ttu-id="b4725-163">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b4725-163">See Also</span></span>
 <span data-ttu-id="b4725-164">[Conjuntos de dados inseridos de relatório e conjuntos de dados compartilhados &#40;Construtor de relatórios e ssrs&#41;coleção de campos de](report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md) [conjunto de dados &#40;Construtor de Relatórios e SSRS&#41;](dataset-fields-collection-report-builder-and-ssrs.md) [designers de consultas](../query-designers-report-builder.md) &#40;Construtor de relatórios&#41;[ajuda para caixas de diálogo, painéis e assistentes](../report-builder-help-for-dialog-boxes-panes-and-wizards.md) , [adicione dados a um relatório Construtor de relatórios &#40;e](report-datasets-ssrs.md) SSRS Construtor de relatórios [as conexões de dados, fontes de dados e cadeias de conexão no&#41;](../data-connections-data-sources-and-connection-strings-in-report-builder.md) Construtor de relatórios [inserido e o SSRS](embedded-and-shared-datasets-report-builder-and-ssrs.md) &#40;</span><span class="sxs-lookup"><span data-stu-id="b4725-164">[Report Embedded Datasets and Shared Datasets &#40;Report Builder and SSRS&#41;](report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md) [Dataset Fields Collection &#40;Report Builder and SSRS&#41;](dataset-fields-collection-report-builder-and-ssrs.md) [Query Designers &#40;Report Builder&#41;](../query-designers-report-builder.md) [Report Builder Help for Dialog Boxes, Panes, and Wizards](../report-builder-help-for-dialog-boxes-panes-and-wizards.md) [Add Data to a Report &#40;Report Builder and SSRS&#41;](report-datasets-ssrs.md) [Data Connections, Data Sources, and Connection Strings in Report Builder](../data-connections-data-sources-and-connection-strings-in-report-builder.md) [Embedded and Shared Datasets &#40;Report Builder and SSRS&#41;](embedded-and-shared-datasets-report-builder-and-ssrs.md)</span></span>


