---
title: Recuperar dados de um modelo de mineração de dados (DMX) (SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- retrieving report data
- datasets [Reporting Services], with DMX queries
- datasets [Reporting Services], Analysis Services
- queries [Reporting Services], data mining prediction
ms.assetid: d9cd3624-1594-4707-8887-55437dd7e07c
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: a59184524967a9bfe772e41890afc3b900cc9e32
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684092"
---
# <a name="retrieve-data-from-a-data-mining-model-dmx-ssrs"></a><span data-ttu-id="1448f-102">Recuperar dados de um modelo de mineração de dados (DMX) (SSRS)</span><span class="sxs-lookup"><span data-stu-id="1448f-102">Retrieve Data from a Data Mining Model (DMX) (SSRS)</span></span>
  <span data-ttu-id="1448f-103">Para usar os dados de um modelo de mineração de dados do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] em seu relatório, defina uma fonte de dados do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] e um ou mais conjuntos de dados de relatório.</span><span class="sxs-lookup"><span data-stu-id="1448f-103">To use data from a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] data mining model in your report, you must define a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] data source and one or more report datasets.</span></span> <span data-ttu-id="1448f-104">Ao criar a definição da fonte de dados, é preciso especificar uma cadeia de conexão e as credenciais para que possa acessar a fonte de dados a partir de seu computador cliente.</span><span class="sxs-lookup"><span data-stu-id="1448f-104">When you create the data source definition, you must specify a connection string and credentials so that you can access the data source from your client computer.</span></span>  
  
 <span data-ttu-id="1448f-105">É possível criar uma definição de fonte de dados inserida para ser usada em um único relatório ou uma definição de fonte de dados compartilhada que pode ser usada por vários relatórios.</span><span class="sxs-lookup"><span data-stu-id="1448f-105">You can create an embedded data source definition for use by a single report or a shared data source definition that can be used by multiple reports.</span></span> <span data-ttu-id="1448f-106">Os procedimentos contidos neste tópico descrevem como criar uma fonte de dados inserida.</span><span class="sxs-lookup"><span data-stu-id="1448f-106">The procedures in this topic describe how to create an embedded data source.</span></span> <span data-ttu-id="1448f-107">Para obter mais informações sobre fontes de dados compartilhadas, consulte [Conexões ou fontes de dados inseridas e compartilhadas &#40;Construtor de Relatórios e SSRS&#41;](../embedded-and-shared-data-connections-or-data-sources-report-builder-and-ssrs.md) e [Criar, modificar e excluir fontes de dados compartilhadas &#40;SSRS&#41;](create-modify-and-delete-shared-data-sources-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="1448f-107">For more information about shared data sources, see [Embedded and Shared Data Connections or Data Sources &#40;Report Builder and SSRS&#41;](../embedded-and-shared-data-connections-or-data-sources-report-builder-and-ssrs.md) and [Create, Modify, and Delete Shared Data Sources &#40;SSRS&#41;](create-modify-and-delete-shared-data-sources-ssrs.md).</span></span>  
  
 <span data-ttu-id="1448f-108">Depois de criar uma fonte de dados do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)], você poderá criar um ou mais conjuntos de dados.</span><span class="sxs-lookup"><span data-stu-id="1448f-108">After you create a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] data source, you can create one or more datasets.</span></span> <span data-ttu-id="1448f-109">Para cada conjunto de dados, use um designer de consulta DMX (Data Mining Prediction Expression) para criar uma consulta DMX que especifica a coleção de campos.</span><span class="sxs-lookup"><span data-stu-id="1448f-109">For each dataset, you use a Data Mining Prediction Expression (DMX) query designer to create a DMX query that specifies the field collection.</span></span> <span data-ttu-id="1448f-110">Para obter mais informações, consulte [Interface do usuário do Designer de Consultas DMX do Analysis Services](analysis-services-dmx-query-designer-user-interface.md).</span><span class="sxs-lookup"><span data-stu-id="1448f-110">For more information, see [Analysis Services DMX Query Designer User Interface](analysis-services-dmx-query-designer-user-interface.md).</span></span>  
  
 <span data-ttu-id="1448f-111">Assim que você criar um conjunto de dados, o nome dele aparecerá no painel de dados do relatório como um nó abaixo da fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="1448f-111">After you create a dataset, the name of the dataset appears in the Report Data pane as a node under its data source.</span></span>  
  
 <span data-ttu-id="1448f-112">Após a publicação do relatório, talvez seja necessário alterar as credenciais da fonte de dados para que, quando o relatório for executado no servidor de relatório, as permissões recuperadas sejam válidas.</span><span class="sxs-lookup"><span data-stu-id="1448f-112">After you publish your report, you may need to change the credentials for the data source so that when the report runs on the report server, the permissions to retrieve the data are valid.</span></span>  
  
### <a name="to-create-an-embedded-microsoft-sql-server-analysis-services-data-source"></a><span data-ttu-id="1448f-113">Para criar uma fonte de dados do Microsoft SQL Server Analysis Services</span><span class="sxs-lookup"><span data-stu-id="1448f-113">To create an embedded Microsoft SQL Server Analysis Services data source</span></span>  
  
1.  <span data-ttu-id="1448f-114">Na barra de ferramentas do painel Dados do Relatório, clique em **Nova**e em **Fonte de Dados**.</span><span class="sxs-lookup"><span data-stu-id="1448f-114">On the toolbar in the Report Data pane, click **New**, and then click **Data Source**.</span></span>  
  
2.  <span data-ttu-id="1448f-115">Na caixa de diálogo **Propriedades da Fonte de Dados** , digite um nome na caixa de texto **Nome** ou aceite o nome padrão.</span><span class="sxs-lookup"><span data-stu-id="1448f-115">In the **Data Source Properties** dialog box, type a name in the **Name** text box, or accept the default name.</span></span>  
  
3.  <span data-ttu-id="1448f-116">Verifique se a opção **Conexão inserida** está selecionada.</span><span class="sxs-lookup"><span data-stu-id="1448f-116">Verify that **Embedded connection** is selected.</span></span>  
  
4.  <span data-ttu-id="1448f-117">Na lista suspensa **Tipo** , selecione **Microsoft SQL Server Analysis Services**.</span><span class="sxs-lookup"><span data-stu-id="1448f-117">From the **Type** drop-down list, select **Microsoft SQL Server Analysis Services**.</span></span>  
  
5.  <span data-ttu-id="1448f-118">Especifique uma cadeia de conexão que funcione com a sua fonte de dados do [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1448f-118">Specify a connection string that works with your [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] data source.</span></span>  
  
     <span data-ttu-id="1448f-119">Contate o administrador do banco de dados para obter informações sobre a conexão e as credenciais que devem ser usadas para se conectar à fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="1448f-119">Contact your database administrator for connection information and for the credentials to use to connect to the data source.</span></span> <span data-ttu-id="1448f-120">O exemplo de cadeia de conexão a seguir especifica o banco de dados do [!INCLUDE[ssSampleDBDWobject](../../includes/sssampledbdwobject-md.md)] de amostra no cliente local.</span><span class="sxs-lookup"><span data-stu-id="1448f-120">The following connection string example specifies the sample [!INCLUDE[ssSampleDBDWobject](../../includes/sssampledbdwobject-md.md)] database on the local client.</span></span>  
  
    ```  
    Data Source=localhost;Initial Catalog=AdventureWorksDW2012  
    ```  
  
6.  <span data-ttu-id="1448f-121">Clique em **Credenciais**.</span><span class="sxs-lookup"><span data-stu-id="1448f-121">Click **Credentials**.</span></span>  
  
     <span data-ttu-id="1448f-122">Defina as credenciais que serão usadas na conexão com a fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="1448f-122">Set the credentials to use to connect to the data source.</span></span> <span data-ttu-id="1448f-123">Para obter mais informações, consulte [Especificar informações de credenciais e de conexão para fontes de dados de relatório](../../integration-services/connection-manager/data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="1448f-123">For more information, see [Specify Credential and Connection Information for Report Data Sources](../../integration-services/connection-manager/data-sources.md).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1448f-124">Para testar a conexão da fonte de dados, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="1448f-124">To test the data source connection, click **Edit**.</span></span> <span data-ttu-id="1448f-125">Na caixa de diálogo **Propriedades de Conexão** , clique em **Testar Conexão**.</span><span class="sxs-lookup"><span data-stu-id="1448f-125">In the **Connection Properties** dialog box, click **Test Connection**.</span></span> <span data-ttu-id="1448f-126">Se o teste for bem-sucedido, você verá a mensagem informativa “Teste de conexão bem-sucedido”.</span><span class="sxs-lookup"><span data-stu-id="1448f-126">If the test is successful, you will see the information message "Test connection succeeded."</span></span> <span data-ttu-id="1448f-127">Se o teste não for bem-sucedido, a mensagem de aviso informará o motivo pelo qual o teste não foi bem-sucedido.</span><span class="sxs-lookup"><span data-stu-id="1448f-127">If the test fails, you will see a warning message with more information about why the test was not successful.</span></span>  
  
7.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
     <span data-ttu-id="1448f-128">A fonte de dados será exibida no painel de dados do relatório.</span><span class="sxs-lookup"><span data-stu-id="1448f-128">The data source appears in the Report Data pane.</span></span>  
  
### <a name="to-create-a-dataset-for-a-microsoft-sql-server-analysis-services"></a><span data-ttu-id="1448f-129">Para criar um conjunto de dados no Microsoft SQL Server Analysis Services</span><span class="sxs-lookup"><span data-stu-id="1448f-129">To create a dataset for a Microsoft SQL Server Analysis Services</span></span>  
  
1.  <span data-ttu-id="1448f-130">No painel **Dados do Relatório**, clique com o botão direito do mouse no nome da fonte de dados que se conecta a uma fonte de dados do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] e, em seguida, clique em **Adicionar Conjunto de Dados**.</span><span class="sxs-lookup"><span data-stu-id="1448f-130">In the **Report Data** pane, right-click the name of the data source that connects to a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] data source, and then click **Add Dataset**.</span></span>  
  
2.  <span data-ttu-id="1448f-131">Na caixa de diálogo **Propriedades do Conjunto de Dados** , digite um nome na caixa de texto **Nome** .</span><span class="sxs-lookup"><span data-stu-id="1448f-131">In the **Dataset Properties** dialog box, type a name in the **Name** text box.</span></span>  
  
3.  <span data-ttu-id="1448f-132">Na caixa **Fonte de dados**, verifique se o nome exibido é o nome da fonte de dados conectada a uma fonte de dados do [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1448f-132">In the **Data source box**, verify that the name is the name of a data source that connects to an [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] data source.</span></span>  
  
4.  <span data-ttu-id="1448f-133">Clique em **Designer de Consulta** para abrir o designer de consultas gráficas e criar uma consulta de maneira interativa.</span><span class="sxs-lookup"><span data-stu-id="1448f-133">Click **Query Designer** to open the graphical query designer to build a query interactively.</span></span> <span data-ttu-id="1448f-134">Se o designer de consultas for aberto no modo MDX, clique em **Tipo de Comando DMX** (![Alterar para a exibição de linguagem de consulta DMX](../media/rsqdicon-commandtypedmx.gif "Alterar para o modo de exibição de linguagem de consulta DMX")) na barra de ferramentas para alternar para o designer de consultas de mineração de dados.</span><span class="sxs-lookup"><span data-stu-id="1448f-134">If the query designer opens in MDX mode, click **Command Type DMX** (![Change to DMX query language view](../media/rsqdicon-commandtypedmx.gif "Change to DMX query language view")) on the toolbar to switch to the data mining query designer.</span></span> <span data-ttu-id="1448f-135">Para obter mais informações, consulte [Interface do usuário do Designer de Consultas DMX do Analysis Services](analysis-services-dmx-query-designer-user-interface.md).</span><span class="sxs-lookup"><span data-stu-id="1448f-135">For more information, see [Analysis Services DMX Query Designer User Interface](analysis-services-dmx-query-designer-user-interface.md).</span></span>  
  
     <span data-ttu-id="1448f-136">Opcionalmente, para importar uma consulta DMX existente de outro relatório, clique em **Importar**e navegue até o arquivo .rdl com a consulta DMX.</span><span class="sxs-lookup"><span data-stu-id="1448f-136">Alternatively, to import an existing DMX query from another report, click **Import**, and then navigate to the .rdl file with the DMX query.</span></span> <span data-ttu-id="1448f-137">Não há suporte para a importação de uma consulta a partir de um arquivo .dmx.</span><span class="sxs-lookup"><span data-stu-id="1448f-137">Importing a query from an .dmx file is not supported.</span></span>  
  
5.  <span data-ttu-id="1448f-138">Depois de criar e executar sua consulta para ver os resultados do exemplo, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="1448f-138">After you create and run your query to see sample results, click **OK**.</span></span>  
  
6.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
     <span data-ttu-id="1448f-139">O conjunto de dados e sua coleção de campos aparecerão no painel de dados do relatório abaixo do nó da fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="1448f-139">The dataset and its field collection appear in the Report Data pane under the data source node.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1448f-140">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="1448f-140">See Also</span></span>  
 <span data-ttu-id="1448f-141">[Tipo de conexão Analysis Services para DMX &#40;SSRS&#41;](analysis-services-connection-type-for-dmx-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="1448f-141">[Analysis Services Connection Type for DMX &#40;SSRS&#41;](analysis-services-connection-type-for-dmx-ssrs.md) </span></span>  
 <span data-ttu-id="1448f-142">[Conexões de dados, fontes de dados e cadeias de conexão no Reporting Services](../data-connections-data-sources-and-connection-strings-in-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="1448f-142">[Data Connections, Data Sources, and Connection Strings in Reporting Services](../data-connections-data-sources-and-connection-strings-in-reporting-services.md) </span></span>  
 <span data-ttu-id="1448f-143">[Coleção de campos de conjuntos de dados &#40;Construtor de Relatórios e SSRS&#41;](dataset-fields-collection-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="1448f-143">[Dataset Fields Collection &#40;Report Builder and SSRS&#41;](dataset-fields-collection-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="1448f-144">Conjuntos de dados inseridos e compartilhados de relatório &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="1448f-144">Report Embedded Datasets and Shared Datasets &#40;Report Builder and SSRS&#41;</span></span>](report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md)  
  
  
