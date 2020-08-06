---
title: Adicionar e verificar uma conexão de dados ou fonte de dados (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 1d3b2573-e29d-480d-9dde-d26379c86618
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d86b3e6598c12545f0e24ef1d162eeb1131bd15d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569149"
---
# <a name="add-and-verify-a-data-connection-or-data-source-report-builder-and-ssrs"></a><span data-ttu-id="781c9-102">Adicionar e verificar uma conexão de dados ou uma fonte de dados (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="781c9-102">Add and Verify a Data Connection or Data Source (Report Builder and SSRS)</span></span>
  <span data-ttu-id="781c9-103">No Construtor de Relatórios, você pode adicionar uma fonte de dados compartilhada do servidor de relatório ou criar uma fonte de dados inserida no relatório.</span><span class="sxs-lookup"><span data-stu-id="781c9-103">In Report Builder, you can add a shared data source from the report server or create an embedded data source for your report.</span></span> <span data-ttu-id="781c9-104">No Designer de Relatórios, você pode criar uma fonte de dados compartilhada ou uma fonte de dados inserida e implantá-la em um servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="781c9-104">In Report Designer, you can create a shared data source or an embedded data source and deploy it to a report server.</span></span>  
  
 <span data-ttu-id="781c9-105">Para adicionar uma fonte de dados compartilhada ao relatório, procure um servidor de relatório e selecione uma fonte de dados compartilhada.</span><span class="sxs-lookup"><span data-stu-id="781c9-105">To add a shared data source to your report, browse to a report server and select a shared data source.</span></span> <span data-ttu-id="781c9-106">A fonte de dados compartilhada no seu relatório aponta para a definição de fonte de dados compartilhada no servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="781c9-106">The shared data source in your report points to the shared data source definition on the report server.</span></span>  
  
 <span data-ttu-id="781c9-107">Para criar uma fonte de dados inserida, você deve ter informações de conexão com a fonte de dados externa e deve saber quais permissões são necessárias para acessar os dados.</span><span class="sxs-lookup"><span data-stu-id="781c9-107">To create an embedded data source, you must have connection information to the external source of data and you must know which permissions you need to access the data.</span></span> <span data-ttu-id="781c9-108">Em geral, essas informações derivam do proprietário da fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="781c9-108">This information usually comes from the owner of the data source.</span></span> <span data-ttu-id="781c9-109">Você pode testar a conexão para verificar se as credenciais especificadas são suficientes.</span><span class="sxs-lookup"><span data-stu-id="781c9-109">You can test the connection to verify that the credentials that are specified are sufficient.</span></span>  
  
 <span data-ttu-id="781c9-110">Para obter mais informações, consulte [conexões de dados, fontes de dados e cadeias de conexão em Construtor de relatórios](../data-connections-data-sources-and-connection-strings-in-report-builder.md) e [especificar credenciais no construtor de relatórios](../specify-credentials-in-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="781c9-110">For more information, see [Data Connections, Data Sources, and Connection Strings in Report Builder](../data-connections-data-sources-and-connection-strings-in-report-builder.md) and [Specify Credentials in Report Builder](../specify-credentials-in-report-builder.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-create-a-reference-to-a-shared-data-source"></a><span data-ttu-id="781c9-111">Para criar uma referência a uma fonte de dados compartilhada</span><span class="sxs-lookup"><span data-stu-id="781c9-111">To create a reference to a shared data source</span></span>  
  
1.  <span data-ttu-id="781c9-112">Na barra de ferramentas do painel Dados do Relatório, clique em **Nova** e em **Fonte de Dados**.</span><span class="sxs-lookup"><span data-stu-id="781c9-112">On the toolbar in the Report Data pane, click **New,** and then click **Data Source**.</span></span> <span data-ttu-id="781c9-113">A caixa de diálogo **Propriedades da Fonte de Dados** é aberta.</span><span class="sxs-lookup"><span data-stu-id="781c9-113">The **Data Source Properties** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="781c9-114">Na caixa de texto **Nome** , digite um nome para a fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="781c9-114">In the **Name** text box, type a name for the data source.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="781c9-115">Esse é o nome salvo na definição de relatório local.</span><span class="sxs-lookup"><span data-stu-id="781c9-115">This name is saved in the local report definition.</span></span> <span data-ttu-id="781c9-116">Esse nome não é o nome da fonte de dados compartilhada no servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="781c9-116">This name is not the name of the shared data source on the report server.</span></span>  
  
3.  <span data-ttu-id="781c9-117">Selecione **Usar uma conexão compartilhada ou modelo de relatório**.</span><span class="sxs-lookup"><span data-stu-id="781c9-117">Select **Use a shared connection or report model**.</span></span> <span data-ttu-id="781c9-118">A lista de fontes de dados compartilhadas e modelos de relatório usados recentemente é exibida.</span><span class="sxs-lookup"><span data-stu-id="781c9-118">The list of recently used shared data sources and report models appears.</span></span> <span data-ttu-id="781c9-119">Para selecionar uma em um servidor de relatório, clique em **Procurar** e procure a pasta no servidor de relatório em que as fontes de dados compartilhadas estão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="781c9-119">To select one from a report server, click **Browse** and browse to the folder on the report server where shared data sources are available.</span></span>  
  
4.  <span data-ttu-id="781c9-120">Selecione a fonte de dados compartilhada e clique em **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="781c9-120">Select the shared data source and then click **Open**.</span></span>  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
 <span data-ttu-id="781c9-121">A fonte de dados será exibida no painel de dados do relatório.</span><span class="sxs-lookup"><span data-stu-id="781c9-121">The data source appears in the Report Data pane.</span></span>  
  
### <a name="to-create-an-embedded-data-source"></a><span data-ttu-id="781c9-122">Para criar uma fonte de dados inserida</span><span class="sxs-lookup"><span data-stu-id="781c9-122">To create an embedded data source</span></span>  
  
1.  <span data-ttu-id="781c9-123">Na barra de ferramentas do painel dados do relatório, clique em **novo**e em **fonte de dados**.</span><span class="sxs-lookup"><span data-stu-id="781c9-123">On the toolbar in the Report Data pane, click **New**, and then click **Data Source**.</span></span> <span data-ttu-id="781c9-124">A caixa de diálogo **Propriedades da Fonte de Dados** é aberta.</span><span class="sxs-lookup"><span data-stu-id="781c9-124">The **Data Source Properties** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="781c9-125">Na caixa de texto **Nome** , digite um nome para a fonte de dados ou aceite o padrão.</span><span class="sxs-lookup"><span data-stu-id="781c9-125">In the **Name** text box, type a name for the data source or accept the default.</span></span>  
  
3.  <span data-ttu-id="781c9-126">Verifique se a opção **Usar uma conexão inserida em meu relatório** está marcada.</span><span class="sxs-lookup"><span data-stu-id="781c9-126">Verify that **Use a connection embedded in my report** is selected.</span></span>  
  
    1.  <span data-ttu-id="781c9-127">Na lista suspensa **Selecionar o tipo de conexão** , selecione um tipo de fonte de dados; por exemplo, **Microsoft SQL Server** ou **OLE DB**.</span><span class="sxs-lookup"><span data-stu-id="781c9-127">From the **Select connection type** drop-down list, select a data source type; for example, **Microsoft SQL Server** or **OLE DB**.</span></span>  
  
    2.  <span data-ttu-id="781c9-128">Especifique uma cadeia de conexão usando uma das alternativas a seguir:</span><span class="sxs-lookup"><span data-stu-id="781c9-128">Specify a connection string by using one of the following alternatives:</span></span>  
  
    -   <span data-ttu-id="781c9-129">Digite a cadeia de conexão diretamente na caixa de texto **Cadeia de conexão** .</span><span class="sxs-lookup"><span data-stu-id="781c9-129">Type the connection string directly in the **Connection string** text box.</span></span> <span data-ttu-id="781c9-130">Para obter uma lista de exemplos de cadeias de conexão, consulte [Conexões de dados, fontes de dados e cadeias de conexão no Construtor de Relatórios](../data-connections-data-sources-and-connection-strings-in-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="781c9-130">For a list of example connection strings, see [Data Connections, Data Sources, and Connection Strings in Report Builder](../data-connections-data-sources-and-connection-strings-in-report-builder.md).</span></span>  
  
    -   <span data-ttu-id="781c9-131">Clique no botão de expressão (**fx)** para criar uma expressão que seja avaliada como uma cadeia de conexão.</span><span class="sxs-lookup"><span data-stu-id="781c9-131">Click the expression (**fx)** button to create an expression that evaluates to a connection string.</span></span> <span data-ttu-id="781c9-132">Na caixa de diálogo **Expressão** , digite a expressão no painel Expressão.</span><span class="sxs-lookup"><span data-stu-id="781c9-132">In the **Expression** dialog box, type the expression in the Expression pane.</span></span> [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
    -   <span data-ttu-id="781c9-133">Clique em **Criar** para abrir a caixa de diálogo **Propriedades de Conexão** para o tipo de fonte de dados escolhido na etapa 2.</span><span class="sxs-lookup"><span data-stu-id="781c9-133">Click **Build** to open the **Connection Properties** dialog box for the data source type that you chose in step 2.</span></span>  
  
         <span data-ttu-id="781c9-134">Preencha os campos na caixa de diálogo **Propriedades de Conexão** , conforme adequado, para o tipo de fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="781c9-134">Fill in the fields in the **Connection Properties** dialog box as appropriate for the data source type.</span></span> <span data-ttu-id="781c9-135">As propriedades de conexão incluem o tipo de fonte de dados, o nome da fonte de dados e as credenciais a serem usadas.</span><span class="sxs-lookup"><span data-stu-id="781c9-135">Connection properties include the type of data source, the name of the data source, and the credentials to use.</span></span> <span data-ttu-id="781c9-136">Depois de especificar valores nesta caixa de diálogo, clique em **Testar Conexão** para verificar se a fonte de dados está disponível e se as credenciais especificadas estão corretas.</span><span class="sxs-lookup"><span data-stu-id="781c9-136">After you specify values in this dialog box, click **Test Connection** to verify that the data source is available and that the credentials you specified are correct.</span></span>  
  
4.  <span data-ttu-id="781c9-137">Clique em **Credenciais**.</span><span class="sxs-lookup"><span data-stu-id="781c9-137">Click **Credentials**.</span></span>  
  
     <span data-ttu-id="781c9-138">Especifique as credenciais que serão usadas para essa fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="781c9-138">Specify the credentials to use for this data source.</span></span> <span data-ttu-id="781c9-139">O proprietário da fonte de dados escolhe o tipo de credenciais com suporte.</span><span class="sxs-lookup"><span data-stu-id="781c9-139">The owner of the data source chooses the type of credentials that are supported.</span></span> <span data-ttu-id="781c9-140">Em alguns casos, o proprietário da fonte de dados mantém uma fonte de dados compartilhada em um servidor de relatório e configura a fonte de dados com credenciais que você pode usar.</span><span class="sxs-lookup"><span data-stu-id="781c9-140">In some cases, the owner of the data source maintains a shared data source on a report server and configures the data source with credentials that you can use.</span></span> <span data-ttu-id="781c9-141">Contate o proprietário da fonte de dados para obter essas informações.</span><span class="sxs-lookup"><span data-stu-id="781c9-141">Contact the data source owner for this information.</span></span> <span data-ttu-id="781c9-142">Para obter mais informações, consulte [Especificar as credenciais no Construtor de Relatórios](../specify-credentials-in-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="781c9-142">For more information, see [Specify Credentials in Report Builder](../specify-credentials-in-report-builder.md).</span></span>  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
 <span data-ttu-id="781c9-143">A fonte de dados será exibida no painel de dados do relatório.</span><span class="sxs-lookup"><span data-stu-id="781c9-143">The data source appears in the Report Data pane.</span></span>  
  
### <a name="to-verify-a-data-connection"></a><span data-ttu-id="781c9-144">Para verificar uma conexão de dados</span><span class="sxs-lookup"><span data-stu-id="781c9-144">To verify a data connection</span></span>  
  
1.  <span data-ttu-id="781c9-145">Na barra de ferramentas no painel de dados do relatório, clique duas vezes na fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="781c9-145">On the toolbar in the Report Data pane, double-click the data source.</span></span> <span data-ttu-id="781c9-146">A caixa de diálogo **Propriedades da Fonte de Dados** é aberta.</span><span class="sxs-lookup"><span data-stu-id="781c9-146">The **Data Source Properties** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="781c9-147">Clique em **Testar Conexão**.</span><span class="sxs-lookup"><span data-stu-id="781c9-147">Click **Test Connection**.</span></span>  
  
3.  <span data-ttu-id="781c9-148">Se a conexão for bem-sucedida, a seguinte mensagem aparecerá: Conexão criada com êxito".</span><span class="sxs-lookup"><span data-stu-id="781c9-148">If the connection is successful, the following message appears: "Connection created successfully".</span></span> [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
4.  <span data-ttu-id="781c9-149">Se a conexão não for bem-sucedida, a seguinte mensagem aparecerá: "Não é possível conectar à fonte de dados".</span><span class="sxs-lookup"><span data-stu-id="781c9-149">If the connection is not successful, the following message appears: "Unable to connect to the data source."</span></span>  
  
5.  <span data-ttu-id="781c9-150">Clique em **Detalhes**e use as informações para corrigir o problema.</span><span class="sxs-lookup"><span data-stu-id="781c9-150">Click **Details**, and use the information to correct the issue.</span></span>  
  
     <span data-ttu-id="781c9-151">Para obter mais informações, consulte [Especificar as credenciais no Construtor de Relatórios](../specify-credentials-in-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="781c9-151">For more information, see [Specify Credentials in Report Builder](../specify-credentials-in-report-builder.md).</span></span>  
  
6.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="781c9-152">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="781c9-152">See Also</span></span>  
 <span data-ttu-id="781c9-153">[Adicionar dados a um relatório &#40;Construtor de Relatórios e SSRS&#41;](report-datasets-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="781c9-153">[Add Data to a Report &#40;Report Builder and SSRS&#41;](report-datasets-ssrs.md) </span></span>  
 <span data-ttu-id="781c9-154">[Conjuntos de itens de relatório inseridos e conjuntos de &#40;compartilhados Construtor de Relatórios e SSRS&#41;](report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="781c9-154">[Report Embedded Datasets and Shared Datasets &#40;Report Builder and SSRS&#41;](report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="781c9-155">[Localizando, exibindo e gerenciando relatórios &#40;Construtor de Relatórios e SSRS &#41;](../report-builder/finding-viewing-and-managing-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="781c9-155">[Finding, Viewing, and Managing Reports &#40;Report Builder and SSRS &#41;](../report-builder/finding-viewing-and-managing-reports-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="781c9-156">Conexões de dados, fontes de dados e cadeias de conexão no Construtor de Relatórios</span><span class="sxs-lookup"><span data-stu-id="781c9-156">Data Connections, Data Sources, and Connection Strings in Report Builder</span></span>](../data-connections-data-sources-and-connection-strings-in-report-builder.md)  
  
  
