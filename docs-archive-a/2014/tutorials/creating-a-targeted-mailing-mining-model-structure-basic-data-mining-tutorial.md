---
title: Criando uma estrutura de modelo de mineração de endereçamento direcionada (tutorial de mineração de dados básico) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: a9c67f29-0c47-4a5a-862b-db0f5213c2c9
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 6a27f818b29120e40248044091c78205dad945bb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681979"
---
# <a name="creating-a-targeted-mailing-mining-model-structure-basic-data-mining-tutorial"></a><span data-ttu-id="570ee-102">Criando uma estrutura de modelo de mineração de mala direta (Tutorial de mineração de dados básico)</span><span class="sxs-lookup"><span data-stu-id="570ee-102">Creating a Targeted Mailing Mining Model Structure (Basic Data Mining Tutorial)</span></span>
  <span data-ttu-id="570ee-103">A primeira etapa para criar um cenário de correspondência destinada é usar o Assistente de Mineração de Dados no [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] para criar uma nova estrutura de mineração e um modelo de mineração de árvore de decisão.</span><span class="sxs-lookup"><span data-stu-id="570ee-103">The first step in creating a targeted mailing scenario is to use the Data Mining Wizard in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] to create a new mining structure and decision tree mining model.</span></span>  
  
 <span data-ttu-id="570ee-104">Nesta tarefa, você irá configurar uma nova estrutura de mineração e adicionar um modelo de mineração inicial com base no [!INCLUDE[msCoName](../includes/msconame-md.md)] algoritmo árvores de decisão.</span><span class="sxs-lookup"><span data-stu-id="570ee-104">In this task you will set up a new mining structure, and add an initial mining model based on the [!INCLUDE[msCoName](../includes/msconame-md.md)] Decision Trees algorithm.</span></span> <span data-ttu-id="570ee-105">Para criar a estrutura, primeiro você selecionará tabelas e exibições e depois identificará as colunas que serão usadas no treinamento e as que serão usadas para teste.</span><span class="sxs-lookup"><span data-stu-id="570ee-105">To create the structure, you will first select tables and views and then identify which columns will be used for training and which for testing.</span></span>  
  
### <a name="to-create-a-mining-structure-for-the-targeted-mailing-scenario"></a><span data-ttu-id="570ee-106">Para criar uma estrutura de mineração para o cenário de mala direta</span><span class="sxs-lookup"><span data-stu-id="570ee-106">To create a mining structure for the targeted mailing scenario</span></span>  
  
1.  <span data-ttu-id="570ee-107">Em Gerenciador de Soluções, clique com o botão direito do mouse em **estruturas de mineração** e selecione **nova estrutura de mineração** para iniciar o assistente de mineração de dados.</span><span class="sxs-lookup"><span data-stu-id="570ee-107">In Solution Explorer, right-click **Mining Structures** and select **New Mining Structure** to start the Data Mining Wizard.</span></span>  
  
2.  <span data-ttu-id="570ee-108">Na página **Bem-vindo ao Assistente de Mineração de Dados** , clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="570ee-108">On the **Welcome to the Data Mining Wizard** page, click **Next**.</span></span>  
  
3.  <span data-ttu-id="570ee-109">Na página **selecionar o método de definição** , verifique se a **partir de banco de dados relacional existente ou data warehouse** está selecionada e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="570ee-109">On the **Select the Definition Method** page, verify that **From existing relational database or data warehouse** is selected, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="570ee-110">Na página **criar a estrutura de mineração de dados** , sob a **qual data mining técnica você deseja usar?**, selecione **árvores de decisão da Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="570ee-110">On the **Create the Data Mining Structure** page, under **Which data mining technique do you want to use?**, select **Microsoft Decision Trees**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="570ee-111">Se você receber um aviso de que não é possível encontrar nenhum algoritmo de mineração de dados, as propriedades do projeto talvez não sejam configuradas corretamente.</span><span class="sxs-lookup"><span data-stu-id="570ee-111">If you get a warning that no data mining algorithms can be found, the project properties might not be configured correctly.</span></span> <span data-ttu-id="570ee-112">Esse aviso ocorre quando o projeto tenta recuperar uma lista de algoritmos de mineração de dados do servidor do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] e não consegue encontrá-lo.</span><span class="sxs-lookup"><span data-stu-id="570ee-112">This warning occurs when the project attempts to retrieve a list of data mining algorithms from the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] server and cannot find the server.</span></span> <span data-ttu-id="570ee-113">Por padrão, [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)] o usará **localhost** como o servidor.</span><span class="sxs-lookup"><span data-stu-id="570ee-113">By default, [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)] will use **localhost** as the server.</span></span> <span data-ttu-id="570ee-114">Se você estiver usando uma instância diferente ou uma instância nomeada, altere as propriedades do projeto.</span><span class="sxs-lookup"><span data-stu-id="570ee-114">If you are using a different instance, or a named instance, you must change the project properties.</span></span> <span data-ttu-id="570ee-115">Para obter mais informações, consulte [criando um projeto de Analysis Services &#40;tutorial de mineração de dados básico&#41;](../../2014/tutorials/creating-an-analysis-services-project-basic-data-mining-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="570ee-115">For more information, see [Creating an Analysis Services Project &#40;Basic Data Mining Tutorial&#41;](../../2014/tutorials/creating-an-analysis-services-project-basic-data-mining-tutorial.md).</span></span>  
  
5.  <span data-ttu-id="570ee-116">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="570ee-116">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="570ee-117">Na página **selecionar exibição da fonte de dados** , no painel **exibições da fonte de dados disponíveis** , selecione **endereçamento direcionado**.</span><span class="sxs-lookup"><span data-stu-id="570ee-117">On the **Select Data Source View** page, in the **Available data source views** pane, select **Targeted Mailing**.</span></span> <span data-ttu-id="570ee-118">Você pode clicar em **procurar** para exibir as tabelas na exibição da fonte de dados e, em seguida, clicar em **fechar** para retornar ao assistente.</span><span class="sxs-lookup"><span data-stu-id="570ee-118">You can click **Browse** to view the tables in the data source view and then click **Close** to return to the wizard.</span></span>  
  
7.  <span data-ttu-id="570ee-119">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="570ee-119">Click **Next**.</span></span>  
  
8.  <span data-ttu-id="570ee-120">Na página **especificar tipos de tabela** , marque a caixa de seleção na coluna **caso** de vTargetMail para usá-la como a tabela de casos e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="570ee-120">On the **Specify Table Types** page, select the check box in the **Case** column for vTargetMail to use it as the case table, and then click **Next**.</span></span> <span data-ttu-id="570ee-121">Você usará a tabela ProspectiveBuyer posteriormente para testes; ignore-a por enquanto.</span><span class="sxs-lookup"><span data-stu-id="570ee-121">You will use the ProspectiveBuyer table later for testing; ignore it for now.</span></span>  
  
9. <span data-ttu-id="570ee-122">Na página **especificar os dados de treinamento** , você identificará pelo menos uma coluna previsível, uma coluna de chave e uma coluna de entrada para o modelo.</span><span class="sxs-lookup"><span data-stu-id="570ee-122">On the **Specify the Training Data** page, you will identify at least one predictable column, one key column, and one input column for your model.</span></span> <span data-ttu-id="570ee-123">Marque a caixa de seleção na coluna **previsível** na linha **BikeBuyer** .</span><span class="sxs-lookup"><span data-stu-id="570ee-123">Select the check box in the **Predictable** column in the **BikeBuyer** row.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="570ee-124">Observe o aviso na parte inferior da janela.</span><span class="sxs-lookup"><span data-stu-id="570ee-124">Notice the warning at the bottom of the window.</span></span> <span data-ttu-id="570ee-125">Você não poderá navegar para a próxima página até selecionar pelo menos uma **entrada** e uma coluna **previsível** .</span><span class="sxs-lookup"><span data-stu-id="570ee-125">You will not be able to navigate to the next page until you select at least one **Input** and one **Predictable** column.</span></span>  
  
10. <span data-ttu-id="570ee-126">Clique em **sugerir** para abrir a caixa de diálogo **sugerir colunas relacionadas** .</span><span class="sxs-lookup"><span data-stu-id="570ee-126">Click **Suggest** to open the **Suggest Related Columns** dialog box.</span></span>  
  
     <span data-ttu-id="570ee-127">O botão **sugerir** é habilitado sempre que pelo menos um atributo previsível tiver sido selecionado.</span><span class="sxs-lookup"><span data-stu-id="570ee-127">The **Suggest** button is enabled whenever at least one predictable attribute has been selected.</span></span> <span data-ttu-id="570ee-128">A caixa de diálogo **sugerir colunas relacionadas** lista as colunas mais próximas à coluna previsível e ordena os atributos por sua correlação com o atributo previsível.</span><span class="sxs-lookup"><span data-stu-id="570ee-128">The **Suggest Related Columns** dialog box lists the columns that are most closely related to the predictable column, and orders the attributes by their correlation with the predictable attribute.</span></span> <span data-ttu-id="570ee-129">As colunas com uma correlação significativa (confiança acima de 95%) são selecionadas automaticamente para serem incluídas no modelo.</span><span class="sxs-lookup"><span data-stu-id="570ee-129">Columns with a significant correlation (confidence greater than 95%) are automatically selected to be included in the model.</span></span>  
  
     <span data-ttu-id="570ee-130">Revise as sugestões e, em seguida, clique em **Cancelar** ignorar as sugestões.</span><span class="sxs-lookup"><span data-stu-id="570ee-130">Review the suggestions, and then click **Cancel** toignore the suggestions.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="570ee-131">Se você clicar em **OK**, todas as sugestões listadas serão marcadas como colunas de entrada no assistente.</span><span class="sxs-lookup"><span data-stu-id="570ee-131">If you click **OK**, all listed suggestions will be marked as input columns in the wizard.</span></span> <span data-ttu-id="570ee-132">Se você concordar com apenas algumas das sugestões, deverá alterar os valores manualmente.</span><span class="sxs-lookup"><span data-stu-id="570ee-132">If you agree with only some of the suggestions, you must change the values manually.</span></span>  
  
11. <span data-ttu-id="570ee-133">Verifique se a caixa de seleção na coluna **chave** está selecionada na linha **CustomerKey** .</span><span class="sxs-lookup"><span data-stu-id="570ee-133">Verify that the check box in the **Key** column is selected in the **CustomerKey** row.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="570ee-134">Se a tabela de origem na exibição de fonte de dados indicar uma chave, o Assistente de Mineração de Dados escolherá automaticamente essa coluna como uma chave para o modelo.</span><span class="sxs-lookup"><span data-stu-id="570ee-134">If the source table from the data source view indicates a key, the Data Mining Wizard automatically chooses that column as a key for the model.</span></span>  
  
12. <span data-ttu-id="570ee-135">Marque as caixas de seleção na coluna **entrada** nas linhas a seguir.</span><span class="sxs-lookup"><span data-stu-id="570ee-135">Select the check boxes in the **Input** column in the following rows.</span></span> <span data-ttu-id="570ee-136">Você pode marcar várias colunas ao realçar um intervalo de células e pressionar CTRL durante a marcação de uma caixa de seleção.</span><span class="sxs-lookup"><span data-stu-id="570ee-136">You can check multiple columns by highlighting a range of cells and pressing CTRL while selecting a check box.</span></span>  
  
    -   <span data-ttu-id="570ee-137">**Idade**</span><span class="sxs-lookup"><span data-stu-id="570ee-137">**Age**</span></span>  
  
    -   <span data-ttu-id="570ee-138">**CommuteDistance**</span><span class="sxs-lookup"><span data-stu-id="570ee-138">**CommuteDistance**</span></span>  
  
    -   <span data-ttu-id="570ee-139">**EnglishEducation**</span><span class="sxs-lookup"><span data-stu-id="570ee-139">**EnglishEducation**</span></span>  
  
    -   <span data-ttu-id="570ee-140">**EnglishOccupation**</span><span class="sxs-lookup"><span data-stu-id="570ee-140">**EnglishOccupation**</span></span>  
  
    -   <span data-ttu-id="570ee-141">**Sexo**</span><span class="sxs-lookup"><span data-stu-id="570ee-141">**Gender**</span></span>  
  
    -   <span data-ttu-id="570ee-142">**GeographyKey**</span><span class="sxs-lookup"><span data-stu-id="570ee-142">**GeographyKey**</span></span>  
  
    -   <span data-ttu-id="570ee-143">**HouseOwnerFlag**</span><span class="sxs-lookup"><span data-stu-id="570ee-143">**HouseOwnerFlag**</span></span>  
  
    -   <span data-ttu-id="570ee-144">**MaritalStatus**</span><span class="sxs-lookup"><span data-stu-id="570ee-144">**MaritalStatus**</span></span>  
  
    -   <span data-ttu-id="570ee-145">**NumberCarsOwned**</span><span class="sxs-lookup"><span data-stu-id="570ee-145">**NumberCarsOwned**</span></span>  
  
    -   <span data-ttu-id="570ee-146">**NumberChildrenAtHome**</span><span class="sxs-lookup"><span data-stu-id="570ee-146">**NumberChildrenAtHome**</span></span>  
  
    -   <span data-ttu-id="570ee-147">**Região**</span><span class="sxs-lookup"><span data-stu-id="570ee-147">**Region**</span></span>  
  
    -   <span data-ttu-id="570ee-148">**TotalChildren**</span><span class="sxs-lookup"><span data-stu-id="570ee-148">**TotalChildren**</span></span>  
  
    -   <span data-ttu-id="570ee-149">**YearlyIncome**</span><span class="sxs-lookup"><span data-stu-id="570ee-149">**YearlyIncome**</span></span>  
  
13. <span data-ttu-id="570ee-150">Na coluna mais à esquerda da página, marque as caixas de seleção nas linhas a seguir.</span><span class="sxs-lookup"><span data-stu-id="570ee-150">On the far left column of the page, select the check boxes in the following rows.</span></span>  
  
    -   <span data-ttu-id="570ee-151">**AddressLine1**</span><span class="sxs-lookup"><span data-stu-id="570ee-151">**AddressLine1**</span></span>  
  
    -   <span data-ttu-id="570ee-152">**AddressLine2**</span><span class="sxs-lookup"><span data-stu-id="570ee-152">**AddressLine2**</span></span>  
  
    -   <span data-ttu-id="570ee-153">**DateFirstPurchase**</span><span class="sxs-lookup"><span data-stu-id="570ee-153">**DateFirstPurchase**</span></span>  
  
    -   <span data-ttu-id="570ee-154">**EmailAddress**</span><span class="sxs-lookup"><span data-stu-id="570ee-154">**EmailAddress**</span></span>  
  
    -   <span data-ttu-id="570ee-155">**Nome**</span><span class="sxs-lookup"><span data-stu-id="570ee-155">**FirstName**</span></span>  
  
    -   <span data-ttu-id="570ee-156">**Sobrenome**</span><span class="sxs-lookup"><span data-stu-id="570ee-156">**LastName**</span></span>  
  
     <span data-ttu-id="570ee-157">Verifique se essas linhas só possuem marcações na coluna à esquerda.</span><span class="sxs-lookup"><span data-stu-id="570ee-157">Ensure that these rows have checks only in the left column.</span></span> <span data-ttu-id="570ee-158">Essas colunas serão adicionadas à sua estrutura mas não serão incluídas no modelo.</span><span class="sxs-lookup"><span data-stu-id="570ee-158">These columns will be added to your structure but will not be included in the model.</span></span> <span data-ttu-id="570ee-159">No entanto, depois que o modelo for criado, elas estarão disponíveis para detalhamento e teste.</span><span class="sxs-lookup"><span data-stu-id="570ee-159">However, after the model is built, they will be available for drillthrough and testing.</span></span> <span data-ttu-id="570ee-160">Para obter mais informações sobre detalhamento, consulte [consultas de detalhamento &#40;mineração de dados&#41;](../../2014/analysis-services/data-mining/drillthrough-queries-data-mining.md)</span><span class="sxs-lookup"><span data-stu-id="570ee-160">For more information about drillthrough, see [Drillthrough Queries &#40;Data Mining&#41;](../../2014/analysis-services/data-mining/drillthrough-queries-data-mining.md)</span></span>  
  
14. <span data-ttu-id="570ee-161">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="570ee-161">Click **Next**.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="570ee-162">Próxima tarefa da lição</span><span class="sxs-lookup"><span data-stu-id="570ee-162">Next Task in Lesson</span></span>  
 [<span data-ttu-id="570ee-163">Especificando o tipo de dados e o tipo de conteúdo &#40;tutorial de mineração de dados básico&#41;</span><span class="sxs-lookup"><span data-stu-id="570ee-163">Specifying the Data Type and Content Type &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/specifying-the-data-type-and-content-type-basic-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="570ee-164">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="570ee-164">See Also</span></span>  
 <span data-ttu-id="570ee-165">[Especificar tipos de tabela &#40;assistente de mineração de dados&#41;](../../2014/analysis-services/specify-table-types-data-mining-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="570ee-165">[Specify Table Types &#40;Data Mining Wizard&#41;](../../2014/analysis-services/specify-table-types-data-mining-wizard.md) </span></span>  
 <span data-ttu-id="570ee-166">[Designer de mineração de dados](../../2014/analysis-services/data-mining/data-mining-designer.md) </span><span class="sxs-lookup"><span data-stu-id="570ee-166">[Data Mining Designer](../../2014/analysis-services/data-mining/data-mining-designer.md) </span></span>  
 [<span data-ttu-id="570ee-167">Algoritmo Árvores de Decisão da Microsoft</span><span class="sxs-lookup"><span data-stu-id="570ee-167">Microsoft Decision Trees Algorithm</span></span>](../../2014/analysis-services/data-mining/microsoft-decision-trees-algorithm.md)  
  
  
