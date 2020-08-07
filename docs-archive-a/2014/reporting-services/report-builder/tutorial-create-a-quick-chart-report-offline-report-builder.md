---
title: 'Tutorial: Criar um relatório de gráficos rápido offline (Construtor de Relatórios) | Microsoft Docs'
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- reports, creating
- tutorials, getting started
- creating reports
ms.assetid: 6b1db67a-cf75-494c-b70c-09f1e6a8d414
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 51a9e648550a0108f47e3d93d75267ab0c1c24f7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571825"
---
# <a name="tutorial-create-a-quick-chart-report-offline-report-builder"></a><span data-ttu-id="39fd3-102">Tutorial: Criar um relatório de gráfico rápido offline (Construtor de Relatórios)</span><span class="sxs-lookup"><span data-stu-id="39fd3-102">Tutorial: Create a Quick Chart Report Offline (Report Builder)</span></span>
  <span data-ttu-id="39fd3-103">Neste tutorial, você criará um gráfico de pizza usando um assistente e o modificará um pouco, apenas para ter uma ideia do que é possível.</span><span class="sxs-lookup"><span data-stu-id="39fd3-103">In this tutorial, you'll create a pie chart by using a wizard, and then you'll modify it a little, just to get an idea of what's possible.</span></span> <span data-ttu-id="39fd3-104">É possível executar este tutorial de duas formas.</span><span class="sxs-lookup"><span data-stu-id="39fd3-104">You can do this tutorial two different ways.</span></span> <span data-ttu-id="39fd3-105">Ambos os métodos têm o mesmo resultado – um gráfico de pizza como o da ilustração a seguir:</span><span class="sxs-lookup"><span data-stu-id="39fd3-105">Both methods have the same outcome-a pie chart like the one in the following illustration:</span></span>

 <span data-ttu-id="39fd3-106">!["Meu Primeiro Gráfico de pizza" em modo Execução](../media/rs-my1stpierunview.gif "Meu primeiro gráfico de pizza no modo de exibição de execução")</span><span class="sxs-lookup"><span data-stu-id="39fd3-106">!["My First Pie Chart" in Run view](../media/rs-my1stpierunview.gif "My First Pie Chart in Run view")</span></span>

## <a name="prerequisites"></a><span data-ttu-id="39fd3-107">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="39fd3-107">Prerequisites</span></span>
 <span data-ttu-id="39fd3-108">Se você usa dados XML ou uma consulta [!INCLUDE[tsql](../../../includes/tsql-md.md)], precisa ter acesso ao Construtor de Relatórios da [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="39fd3-108">Whether you use XML data or a [!INCLUDE[tsql](../../../includes/tsql-md.md)] query, you need to have access to [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] Report Builder.</span></span> <span data-ttu-id="39fd3-109">Você pode executar a versão autônoma ou a versão ClickOnce, disponível no Gerenciador de Relatórios ou em um site do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="39fd3-109">You can run the stand-alone version or the ClickOnce version available from Report Manager or a SharePoint site.</span></span> <span data-ttu-id="39fd3-110">Somente a primeira etapa, como abrir o Construtor de Relatórios, é diferente para versões do ClickOnce.</span><span class="sxs-lookup"><span data-stu-id="39fd3-110">Only the first step, how to open Report Builder, is different for ClickOnce versions.</span></span> <span data-ttu-id="39fd3-111">Para obter mais informações, consulte [instalar, desinstalar e Construtor de relatórios suporte](../install-uninstall-and-report-builder-support.md).</span><span class="sxs-lookup"><span data-stu-id="39fd3-111">For more information, see [Install, Uninstall, and Report Builder Support](../install-uninstall-and-report-builder-support.md).</span></span>

##  <a name="two-ways-to-do-this-tutorial"></a><a name="TwoWays"></a><span data-ttu-id="39fd3-112">Duas maneiras de fazer este tutorial</span><span class="sxs-lookup"><span data-stu-id="39fd3-112">Two Ways To Do This Tutorial</span></span>

-   [<span data-ttu-id="39fd3-113">Criar o gráfico de pizza com dados XML</span><span class="sxs-lookup"><span data-stu-id="39fd3-113">Create the pie chart with XML data</span></span>](#CreatePieChartXML)

-   [<span data-ttu-id="39fd3-114">Criar o gráfico de pizza com uma consulta Transact-SQL que contém dados</span><span class="sxs-lookup"><span data-stu-id="39fd3-114">Create the pie chart with a Transact-SQL query that contains data</span></span>](#CreatePieQueryData)

### <a name="using-xml-data-for-this-tutorial"></a><span data-ttu-id="39fd3-115">Usando dados XML para este tutorial</span><span class="sxs-lookup"><span data-stu-id="39fd3-115">Using XML data for this tutorial</span></span>
 <span data-ttu-id="39fd3-116">Você pode usar os dados XML que copiar deste tópico e colar no assistente.</span><span class="sxs-lookup"><span data-stu-id="39fd3-116">You can use XML data that you copy from this topic and paste into the wizard.</span></span> <span data-ttu-id="39fd3-117">Não é necessário estar conectado a um servidor de relatório ou um servidor de relatório no modo integrado do SharePoint e nem ter acesso a uma instância do [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="39fd3-117">You don't need to be connected to a report server or a report server in SharePoint integrated mode, and you don't need access to an instance of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span>

 [<span data-ttu-id="39fd3-118">Criar o gráfico de pizza com dados XML</span><span class="sxs-lookup"><span data-stu-id="39fd3-118">Create the pie chart with XML data</span></span>](#CreatePieChartXML)

### <a name="using-a-transact-sql-query-that-contains-data-for-this-tutorial"></a><span data-ttu-id="39fd3-119">Usando uma consulta Transact-SQL que contenha dados para este tutorial</span><span class="sxs-lookup"><span data-stu-id="39fd3-119">Using a Transact-SQL query that contains data for this tutorial</span></span>
 <span data-ttu-id="39fd3-120">Você pode copiar uma consulta com dados incluídos neste tópico e colá-la no assistente.</span><span class="sxs-lookup"><span data-stu-id="39fd3-120">You can copy a query with data included in it from this topic and paste it into the wizard.</span></span> <span data-ttu-id="39fd3-121">Você precisará do nome de uma instância do [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] e de credenciais suficientes para ter acesso somente leitura a qualquer banco de dados.</span><span class="sxs-lookup"><span data-stu-id="39fd3-121">You will need the name of an instance of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] and credentials sufficient for read-only access to any database.</span></span> <span data-ttu-id="39fd3-122">A consulta de conjuntos de dados nos tutoriais usa dados literais, mas deve ser processada por uma instância do [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] para retornar os metadados necessários a um conjunto de dados de relatório.</span><span class="sxs-lookup"><span data-stu-id="39fd3-122">The dataset query in the tutorial uses literal data, but the query must be processed by an instance of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] to return the metadata that is required for a report dataset.</span></span>

 <span data-ttu-id="39fd3-123">A vantagem de usar a consulta [!INCLUDE[tsql](../../../includes/tsql-md.md)] é que todos os outros tutoriais do Construtor de Relatórios usam o mesmo método; portanto, quando você executar os outros tutoriais, já saberá o que fazer.</span><span class="sxs-lookup"><span data-stu-id="39fd3-123">The advantage of using the [!INCLUDE[tsql](../../../includes/tsql-md.md)] query is that all the other Report Builder tutorials use the same method, so when you do the other tutorials, you will already know what to do.</span></span>

 <span data-ttu-id="39fd3-124">A consulta [!INCLUDE[tsql](../../../includes/tsql-md.md)] requer outros pré-requisitos.</span><span class="sxs-lookup"><span data-stu-id="39fd3-124">The [!INCLUDE[tsql](../../../includes/tsql-md.md)] query does require a few other prerequisites.</span></span> <span data-ttu-id="39fd3-125">Para saber mais, veja [Pré-requisitos para tutoriais &#40;Construtor de Relatórios&#41;](../report-builder-tutorials.md).</span><span class="sxs-lookup"><span data-stu-id="39fd3-125">For more information, see [Prerequisites for Tutorials &#40;Report Builder&#41;](../report-builder-tutorials.md).</span></span>

 [<span data-ttu-id="39fd3-126">Criar o gráfico de pizza com uma consulta Transact-SQL que contém dados</span><span class="sxs-lookup"><span data-stu-id="39fd3-126">Create the pie chart with a Transact-SQL query that contains data</span></span>](#CreatePieQueryData)

## <a name="also-in-this-article"></a><span data-ttu-id="39fd3-127">Também neste artigo</span><span class="sxs-lookup"><span data-stu-id="39fd3-127">Also in This Article</span></span>
 [<span data-ttu-id="39fd3-128">Depois que você executar o assistente</span><span class="sxs-lookup"><span data-stu-id="39fd3-128">After You Run the Wizard</span></span>](#AfterWizard)

 [<span data-ttu-id="39fd3-129">O que vem a seguir</span><span class="sxs-lookup"><span data-stu-id="39fd3-129">What's Next</span></span>](#WhatsNext)

##  <a name="creating-the-pie-chart-with-xml-data"></a><a name="CreatePieChartXML"></a><span data-ttu-id="39fd3-130">Criando o gráfico de pizza com dados XML</span><span class="sxs-lookup"><span data-stu-id="39fd3-130">Creating the pie chart with XML data</span></span>

#### <a name="to-create-the-pie-chart-with-xml-data"></a><span data-ttu-id="39fd3-131">Para criar o gráfico de pizza com dados XML</span><span class="sxs-lookup"><span data-stu-id="39fd3-131">To create the pie chart with XML data</span></span>

1.  <span data-ttu-id="39fd3-132">Clique em **Iniciar**, aponte para **Programas**, para **Construtor de Relatórios do Microsoft SQL Server 2012**e clique em **Construtor de Relatórios**.</span><span class="sxs-lookup"><span data-stu-id="39fd3-132">Click **Start**, point to **Programs**, point to **Microsoft SQL Server 2012 Report Builder**, and then click **Report Builder**.</span></span>

     <span data-ttu-id="39fd3-133">A caixa de diálogo **introdução** é exibida.</span><span class="sxs-lookup"><span data-stu-id="39fd3-133">The **Getting Started** dialog box appears.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="39fd3-134">Se a caixa de diálogo **introdução** não for exibida, no botão **Construtor de relatórios** , clique em **novo**.</span><span class="sxs-lookup"><span data-stu-id="39fd3-134">If the **Getting Started** dialog box does not appear, from the **Report Builder** button, click **New**.</span></span>

2.  <span data-ttu-id="39fd3-135">No painel esquerdo, verifique se **Relatório** está selecionado.</span><span class="sxs-lookup"><span data-stu-id="39fd3-135">In the left pane, verify that **Report** is selected.</span></span>

3.  <span data-ttu-id="39fd3-136">No painel direito, clique em **Assistente de Gráfico**e em **Criar**.</span><span class="sxs-lookup"><span data-stu-id="39fd3-136">In the right pane, click **Chart Wizard**, and then click **Create**.</span></span>

4.  <span data-ttu-id="39fd3-137">Na página **Escolha um conjunto de dados** , clique em **Criar um conjunto de dados**e em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="39fd3-137">In the **Choose a dataset** page, click **Create a dataset**, and then click **Next**.</span></span>

5.  <span data-ttu-id="39fd3-138">Na página **Escolha uma conexão com uma fonte de dados** , clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="39fd3-138">In the **Choose a connection to a data source** page, click **New**.</span></span>

     <span data-ttu-id="39fd3-139">A caixa de diálogo **Propriedades da Fonte de Dados** é aberta.</span><span class="sxs-lookup"><span data-stu-id="39fd3-139">The **Data Source Properties** dialog box opens.</span></span>

6.  <span data-ttu-id="39fd3-140">Você pode atribuir qualquer nome desejado a uma fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="39fd3-140">You can name a data source anything you want.</span></span> <span data-ttu-id="39fd3-141">Na caixa **Nome** , digite **MyPieChart**.</span><span class="sxs-lookup"><span data-stu-id="39fd3-141">In the **Name** box, type **MyPieChart**.</span></span>

7.  <span data-ttu-id="39fd3-142">Na caixa **Selecionar tipo de conexão** , clique em **XML.**</span><span class="sxs-lookup"><span data-stu-id="39fd3-142">In the **Select connection type** box, click **XML.**</span></span>

8.  <span data-ttu-id="39fd3-143">Clique na guia **credenciais** , selecione **usar usuário atual do Windows. A delegação de Kerberos pode ser necessária**e, em seguida, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="39fd3-143">Click the **Credentials** tab, select **Use current Windows user. Kerberos delegation may be required**, and then click **OK**.</span></span>

9. <span data-ttu-id="39fd3-144">Na página **Escolha uma conexão com uma fonte de dados** , clique em **MyPieChart**e em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="39fd3-144">In the **Choose a connection to a data source** page, click **MyPieChart**, and then click **Next**.</span></span>

10. <span data-ttu-id="39fd3-145">Copie o texto a seguir e cole-o na caixa grande no centro da página **criar uma consulta** .</span><span class="sxs-lookup"><span data-stu-id="39fd3-145">Copy the following text and paste it in the large box in the center of the **Design a query** page.</span></span>

    ```
    <Query>
    <ElementPath>Root /S  {@Sales (Integer)} /C {@FullName} </ElementPath>
    <XmlData>
    <Root>
    <S Sales="150">
      <C FullName="Jae Pak" />
    </S>
    <S Sales="350">
      <C FullName="Jillian  Carson" />
    </S>
    <S Sales="250">
      <C FullName="Linda C Mitchell" />
    </S>
    <S Sales="500">
      <C FullName="Michael Blythe" />
    </S>
    <S Sales="450">
      <C FullName="Ranjit Varkey" />
    </S>
    </Root>
    </XmlData>
    </Query>
    ```

11. <span data-ttu-id="39fd3-146">(Opcional) Clique no botão Executar (**!**) para ver os dados em que o gráfico se baseará.</span><span class="sxs-lookup"><span data-stu-id="39fd3-146">(Optional) Click the Run button (**!**) to see the data your chart will be based on.</span></span>

12. <span data-ttu-id="39fd3-147">Clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="39fd3-147">Click **Next**.</span></span>

13. <span data-ttu-id="39fd3-148">Na página **Escolha um tipo de gráfico** , clique em **Pizza**e em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="39fd3-148">In the **Choose a chart type** page, click **Pie**, and then click **Next**.</span></span>

14. <span data-ttu-id="39fd3-149">Na página **organizar campos de gráfico** , clique duas vezes no campo **vendas** na caixa **campos disponíveis** .</span><span class="sxs-lookup"><span data-stu-id="39fd3-149">In the **Arrange chart fields** page, double-click the **Sales** field in the **Available fields** box.</span></span>

     <span data-ttu-id="39fd3-150">Observe que ela se transforma automaticamente na caixa **Valores** porque é um valor numérico.</span><span class="sxs-lookup"><span data-stu-id="39fd3-150">Note that it automatically moves to the **Values** box, because it is a numerical value.</span></span>

15. <span data-ttu-id="39fd3-151">Arraste o campo **FullName** da caixa **campos disponíveis** para a caixa **categorias** (ou clique duas vezes nele; ele vai para a caixa **categorias** ) e, em seguida, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="39fd3-151">Drag the **FullName** field from the **Available fields** box to the **Categories** box (or double-click it; it will go to the **Categories** box), and then click **Next**.</span></span>

16. <span data-ttu-id="39fd3-152">Na página **escolher um estilo** , o **oceano** é selecionado por padrão.</span><span class="sxs-lookup"><span data-stu-id="39fd3-152">In the **Choose a style** page, **Ocean** is selected by default.</span></span> <span data-ttu-id="39fd3-153">Clique nos outros estilos para visualizar sua aparência.</span><span class="sxs-lookup"><span data-stu-id="39fd3-153">Click the other styles to see what they look like.</span></span>

17. <span data-ttu-id="39fd3-154">Clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="39fd3-154">Click **Finish**.</span></span>

     <span data-ttu-id="39fd3-155">Você está olhando agora para seu novo relatório de gráfico de pizza na superfície de design.</span><span class="sxs-lookup"><span data-stu-id="39fd3-155">You're now looking at your new pie chart report on the design surface.</span></span> <span data-ttu-id="39fd3-156">O que você vê é uma representação.</span><span class="sxs-lookup"><span data-stu-id="39fd3-156">What you see is representational.</span></span> <span data-ttu-id="39fd3-157">A legenda diz Nome Completo 1, Nome Completo 2 etc., em vez dos nomes dos vendedores, e o tamanho das fatias da pizza não é exato.</span><span class="sxs-lookup"><span data-stu-id="39fd3-157">The legend reads Full Name 1, Full Name 2, etc., rather than the salespeople's names, and the size of the slices of pie are not accurate.</span></span> <span data-ttu-id="39fd3-158">Isso é apenas para lhe dar uma ideia da aparência que o relatório terá.</span><span class="sxs-lookup"><span data-stu-id="39fd3-158">This is just to give you an idea of what your report will look like.</span></span>

18. <span data-ttu-id="39fd3-159">Para ver seu gráfico de pizza real, clique em **Executar** na guia **Início** da Faixa de Opções.</span><span class="sxs-lookup"><span data-stu-id="39fd3-159">To see your actual pie chart, click **Run** on the **Home** tab of the Ribbon.</span></span>

 <span data-ttu-id="39fd3-160">![Ícone de seta usado com o link voltar ao início](../../2014-toc/media/uparrow16x16.gif "Ícone de seta usado com o link Voltar ao Início") [de volta ao início](#TwoWays)</span><span class="sxs-lookup"><span data-stu-id="39fd3-160">![Arrow icon used with Back to Top link](../../2014-toc/media/uparrow16x16.gif "Arrow icon used with Back to Top link") [Back to Top](#TwoWays)</span></span>

##  <a name="creating-the-pie-chart-with-a-tsql-query"></a><a name="CreatePieQueryData"></a> <span data-ttu-id="39fd3-161">Criando o gráfico de pizza com uma consulta [!INCLUDE[tsql](../../../includes/tsql-md.md)]</span><span class="sxs-lookup"><span data-stu-id="39fd3-161">Creating the pie chart with a [!INCLUDE[tsql](../../../includes/tsql-md.md)] query</span></span>

#### <a name="to-create-the-pie-chart-with-a-tsql-query-that-contains-data"></a><span data-ttu-id="39fd3-162">Para criar o gráfico de pizza com uma consulta [!INCLUDE[tsql](../../../includes/tsql-md.md)] que contenha dados</span><span class="sxs-lookup"><span data-stu-id="39fd3-162">To create the pie chart with a [!INCLUDE[tsql](../../../includes/tsql-md.md)] query that contains data</span></span>

1.  <span data-ttu-id="39fd3-163">Clique em **Iniciar**, aponte para **Programas**, para **Construtor de Relatórios do Microsoft SQL Server 2012**e clique em **Construtor de Relatórios**.</span><span class="sxs-lookup"><span data-stu-id="39fd3-163">Click **Start**, point to **Programs**, point to **Microsoft SQL Server 2012 Report Builder**, and then click **Report Builder**.</span></span>

2.  <span data-ttu-id="39fd3-164">Na caixa de diálogo **novo relatório ou conjunto de novos** , verifique se o **relatório** está selecionado no painel esquerdo.</span><span class="sxs-lookup"><span data-stu-id="39fd3-164">In the **New report or dataset** dialog box, verify that **Report** is selected in the left pane.</span></span>

3.  <span data-ttu-id="39fd3-165">No painel direito, clique em **Assistente de Gráfico**e em **Criar**.</span><span class="sxs-lookup"><span data-stu-id="39fd3-165">In the right pane, click **Chart Wizard**, and then click **Create**.</span></span>

4.  <span data-ttu-id="39fd3-166">Na página **Escolha um conjunto de dados** , clique em **Criar um conjunto de dados**e em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="39fd3-166">In the **Choose a dataset** page, click **Create a dataset**, and then click **Next**.</span></span>

5.  <span data-ttu-id="39fd3-167">Na página **Escolha uma conexão com uma fonte de dados** , selecione uma fonte de dados existente ou navegue até o servidor de relatório e selecione uma fonte de dados e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="39fd3-167">In the **Choose a connection to a data source** page, select an existing data source or browse to the report server and select a data source, and then click **Next**.</span></span> <span data-ttu-id="39fd3-168">Talvez seja necessário inserir um nome de usuário e uma senha.</span><span class="sxs-lookup"><span data-stu-id="39fd3-168">You may need to enter a user name and password.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="39fd3-169">A fonte de dados escolhida não tem importância, contanto que você tenha permissões suficientes.</span><span class="sxs-lookup"><span data-stu-id="39fd3-169">The data source you choose is unimportant, as long as you have adequate permissions.</span></span> <span data-ttu-id="39fd3-170">Você não obterá dados da fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="39fd3-170">You will not be getting data from the data source.</span></span> <span data-ttu-id="39fd3-171">Para saber mais, veja [Pré-requisitos para tutoriais &#40;Construtor de Relatórios&#41;](../report-builder-tutorials.md).</span><span class="sxs-lookup"><span data-stu-id="39fd3-171">For more information, see [Prerequisites for Tutorials &#40;Report Builder&#41;](../report-builder-tutorials.md).</span></span>

6.  <span data-ttu-id="39fd3-172">Na página **criar uma consulta** , clique em **Editar como texto**.</span><span class="sxs-lookup"><span data-stu-id="39fd3-172">On the **Design a Query** page, click **Edit as Text**.</span></span>

7.  <span data-ttu-id="39fd3-173">Cole a seguinte consulta no painel de consulta:</span><span class="sxs-lookup"><span data-stu-id="39fd3-173">Paste the following query into the query pane:</span></span>

    ```
    SELECT 150 AS Sales, 'Jae Pak' AS FullName 
    UNION SELECT 350 AS Sales, 'Jillian Carson' AS FullName 
    UNION SELECT 250 AS Sales, 'Linda C Mitchell' AS FullName 
    UNION SELECT 500 AS Sales, 'Michael Blythe' AS FullName 
    UNION SELECT 450 AS Sales, 'Ranjit Varkey' AS FullName 
    ```

8.  <span data-ttu-id="39fd3-174">(Opcional) Clique no botão Executar (**!**) para ver os dados em que o gráfico se baseará.</span><span class="sxs-lookup"><span data-stu-id="39fd3-174">(Optional) Click the Run button (**!**) to see the data your chart will be based on.</span></span>

9. <span data-ttu-id="39fd3-175">Clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="39fd3-175">Click **Next**.</span></span>

10. <span data-ttu-id="39fd3-176">Na página **Escolha um tipo de gráfico** , clique em **Pizza**e em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="39fd3-176">In the **Choose a chart type** page, click **Pie**, and then click **Next**.</span></span>

11. <span data-ttu-id="39fd3-177">Na página **organizar campos de gráfico** , clique duas vezes no campo **vendas** na caixa **campos disponíveis** .</span><span class="sxs-lookup"><span data-stu-id="39fd3-177">In the **Arrange chart fields** page, double-click the **Sales** field in the **Available fields** box.</span></span>

     <span data-ttu-id="39fd3-178">Observe que ela se transforma automaticamente na caixa **Valores** , porque esse é um valor numérico.</span><span class="sxs-lookup"><span data-stu-id="39fd3-178">Note that it automatically moves to the **Values** box, because it's a numerical value.</span></span>

12. <span data-ttu-id="39fd3-179">Arraste o campo **FullName** da caixa **campos disponíveis** para a caixa **categorias** (ou clique duas vezes nele; ele vai para a caixa **categorias** ) e, em seguida, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="39fd3-179">Drag the **FullName** field from the **Available fields** box to the **Categories** box (or double-click it; it will go to the **Categories** box), and then click **Next**.</span></span>

13. <span data-ttu-id="39fd3-180">Na página **Escolha um estilo** , a opção Oceano é selecionada por padrão.</span><span class="sxs-lookup"><span data-stu-id="39fd3-180">In the **Choose a style** page, Ocean is selected by default.</span></span> <span data-ttu-id="39fd3-181">Clique nos outros estilos para visualizar sua aparência.</span><span class="sxs-lookup"><span data-stu-id="39fd3-181">Click the other styles to see what they look like.</span></span>

14. <span data-ttu-id="39fd3-182">Clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="39fd3-182">Click **Finish**.</span></span>

     <span data-ttu-id="39fd3-183">Você está olhando agora para seu novo relatório de gráfico de pizza na superfície de design.</span><span class="sxs-lookup"><span data-stu-id="39fd3-183">You're now looking at your new pie chart report on the design surface.</span></span> <span data-ttu-id="39fd3-184">O que você vê é uma representação.</span><span class="sxs-lookup"><span data-stu-id="39fd3-184">What you see is representational.</span></span> <span data-ttu-id="39fd3-185">A legenda diz Nome Completo 1, Nome Completo 2 etc., em vez dos nomes dos vendedores, e o tamanho das fatias da pizza não é exato.</span><span class="sxs-lookup"><span data-stu-id="39fd3-185">The legend reads Full Name 1, Full Name 2, etc., rather than the salespeople's names, and the size of the slices of pie are not accurate.</span></span> <span data-ttu-id="39fd3-186">Isso é apenas para lhe dar uma ideia da aparência que o relatório terá.</span><span class="sxs-lookup"><span data-stu-id="39fd3-186">This is just to give you an idea of what your report will look like.</span></span>

15. <span data-ttu-id="39fd3-187">Para ver seu gráfico de pizza real, clique em **Executar** na guia **Início** da Faixa de Opções.</span><span class="sxs-lookup"><span data-stu-id="39fd3-187">To see your actual pie chart, click **Run** on the **Home** tab of the Ribbon.</span></span>

 <span data-ttu-id="39fd3-188">![Ícone de seta usado com o link voltar ao início](../../2014-toc/media/uparrow16x16.gif "Ícone de seta usado com o link Voltar ao Início") [de volta ao início](#TwoWays)</span><span class="sxs-lookup"><span data-stu-id="39fd3-188">![Arrow icon used with Back to Top link](../../2014-toc/media/uparrow16x16.gif "Arrow icon used with Back to Top link") [Back to Top](#TwoWays)</span></span>

##  <a name="after-you-run-the-wizard"></a><a name="AfterWizard"></a><span data-ttu-id="39fd3-189">Depois de executar o assistente</span><span class="sxs-lookup"><span data-stu-id="39fd3-189">After You Run the Wizard</span></span>
 <span data-ttu-id="39fd3-190">Agora que você tem seu relatório de gráfico de pizza, pode brincar com ele.</span><span class="sxs-lookup"><span data-stu-id="39fd3-190">Now that you have your pie chart report, you can play with it.</span></span> <span data-ttu-id="39fd3-191">Na guia **Executar** da Faixa de Opções, clique em **Design**, para que você possa continuar modificando-o.</span><span class="sxs-lookup"><span data-stu-id="39fd3-191">On the **Run** tab of the Ribbon, click **Design**, so you can continue modifying it.</span></span>

### <a name="make-the-chart-bigger"></a><span data-ttu-id="39fd3-192">Aumentar o gráfico</span><span class="sxs-lookup"><span data-stu-id="39fd3-192">Make the chart bigger</span></span>
 <span data-ttu-id="39fd3-193">Você optar por aumentar o tamanho do gráfico de pizza.</span><span class="sxs-lookup"><span data-stu-id="39fd3-193">You may want the pie chart to be bigger.</span></span> <span data-ttu-id="39fd3-194">Clique no gráfico, mas não em qualquer elemento do gráfico, para selecioná-lo e arraste o canto inferior direito para redimensioná-lo.</span><span class="sxs-lookup"><span data-stu-id="39fd3-194">Click the chart, but not on any element in the chart, to select it and drag the lower-right corner to resize it.</span></span>

### <a name="add-a-report-title"></a><span data-ttu-id="39fd3-195">Adicionar um título a um relatório</span><span class="sxs-lookup"><span data-stu-id="39fd3-195">Add a report title</span></span>
 <span data-ttu-id="39fd3-196">Selecione as palavras **Título do gráfico** na parte superior do gráfico e digite um título, como **Gráfico de Pizza de Vendas**.</span><span class="sxs-lookup"><span data-stu-id="39fd3-196">Select the words **Chart title** at the top of the chart, and then type a title, such as **Sales Pie Chart**.</span></span>

### <a name="add-percentages"></a><span data-ttu-id="39fd3-197">Adicionar porcentagens</span><span class="sxs-lookup"><span data-stu-id="39fd3-197">Add percentages</span></span>

##### <a name="to-display-percentage-values-as-labels-on-a-pie-chart"></a><span data-ttu-id="39fd3-198">Para exibir valores de porcentagem como rótulos em um gráfico de pizza</span><span class="sxs-lookup"><span data-stu-id="39fd3-198">To display percentage values as labels on a pie chart</span></span>

1.  <span data-ttu-id="39fd3-199">Clique com o botão direito do mouse no gráfico de pizza e selecione **Mostrar rótulos de dados**.</span><span class="sxs-lookup"><span data-stu-id="39fd3-199">Right-click on the pie chart and select **Show Data Labels**.</span></span> <span data-ttu-id="39fd3-200">Os rótulos de dados devem aparecer dentro de cada fatia do gráfico de pizza.</span><span class="sxs-lookup"><span data-stu-id="39fd3-200">The data labels should appear within each slice on the pie chart.</span></span>

2.  <span data-ttu-id="39fd3-201">Clique com o botão direito do mouse nos rótulos e selecione **Propriedades do rótulo da série**.</span><span class="sxs-lookup"><span data-stu-id="39fd3-201">Right-click on the labels and select **Series Label Properties**.</span></span> <span data-ttu-id="39fd3-202">A caixa de diálogo **Propriedades do Rótulo de Série** é exibida.</span><span class="sxs-lookup"><span data-stu-id="39fd3-202">The **Series Label Properties** dialog box appears.</span></span>

3.  <span data-ttu-id="39fd3-203">Digite `#PERCENT{P0}` para a opção **rotular dados** .</span><span class="sxs-lookup"><span data-stu-id="39fd3-203">Type `#PERCENT{P0}` for the **Label data** option.</span></span>

     <span data-ttu-id="39fd3-204">O `{P0}` fornece o percentual sem casas decimais.</span><span class="sxs-lookup"><span data-stu-id="39fd3-204">The `{P0}` gives you the percentage without decimal places.</span></span> <span data-ttu-id="39fd3-205">Se você digitar apenas `#PERCENT`, seus números terão duas casas decimais.</span><span class="sxs-lookup"><span data-stu-id="39fd3-205">If you type just `#PERCENT`, your numbers will have two decimal places.</span></span> <span data-ttu-id="39fd3-206">`#PERCENT` é uma palavra-chave que executa um cálculo ou função para você; há muitos outras.</span><span class="sxs-lookup"><span data-stu-id="39fd3-206">`#PERCENT` is a keyword that performs a calculation or function for you; there are many others.</span></span>

 <span data-ttu-id="39fd3-207">Para saber mais sobre como personalizar legendas e rótulos de gráfico, veja [Exibir valores de porcentagem em um gráfico de pizza e &#40;Construtor de Relatórios e SSRS&#41;](../report-design/display-percentage-values-on-a-pie-chart-report-builder-and-ssrs.md) e [Alterar o texto de um item de legenda &#40;Construtor de Relatórios e SSRS&#41;](../report-design/chart-legend-change-item-text-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="39fd3-207">For more information about customizing chart labels and legends, see [Display Percentage Values on a Pie Chart &#40;Report Builder and SSRS&#41;](../report-design/display-percentage-values-on-a-pie-chart-report-builder-and-ssrs.md) and [Change the Text of a Legend Item &#40;Report Builder and SSRS&#41;](../report-design/chart-legend-change-item-text-report-builder.md).</span></span>

 <span data-ttu-id="39fd3-208">![Ícone de seta usado com o link voltar ao início](../../2014-toc/media/uparrow16x16.gif "Ícone de seta usado com o link Voltar ao Início") [de volta ao início](#TwoWays)</span><span class="sxs-lookup"><span data-stu-id="39fd3-208">![Arrow icon used with Back to Top link](../../2014-toc/media/uparrow16x16.gif "Arrow icon used with Back to Top link") [Back to Top](#TwoWays)</span></span>

##  <a name="whats-next"></a><a name="WhatsNext"></a><span data-ttu-id="39fd3-209">O que vem a seguir?</span><span class="sxs-lookup"><span data-stu-id="39fd3-209">What's Next?</span></span>
 <span data-ttu-id="39fd3-210">Agora que você criou seu primeiro relatório no Construtor de Relatórios, está pronto tentar os outros tutoriais e começar a criar relatórios com seus próprios dados.</span><span class="sxs-lookup"><span data-stu-id="39fd3-210">Now that you have created your first report in Report Builder, you are ready to try the other tutorials and to start creating reports from your own data.</span></span> <span data-ttu-id="39fd3-211">Para executar Construtor de Relatórios, você precisa de permissão para acessar suas fontes de dados, como bancos de dado, com uma *cadeia de conexão*que, na verdade, conecta você à fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="39fd3-211">To run Report Builder, you need permission to access your data sources, such as databases, with a *connection string*, which actually connects you to the data source.</span></span> <span data-ttu-id="39fd3-212">O administrador do sistema terá essas informações e poderá configurá-las.</span><span class="sxs-lookup"><span data-stu-id="39fd3-212">Your system administrator will have this information and can set you up.</span></span>

 <span data-ttu-id="39fd3-213">Para trabalhar nos outros tutoriais, você precisa do nome de uma instância do [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] e de credenciais suficientes para ter acesso somente leitura a qualquer banco de dados.</span><span class="sxs-lookup"><span data-stu-id="39fd3-213">To work through the other tutorials, you need the name of an instance of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] and credentials sufficient for read-only access to any database.</span></span> <span data-ttu-id="39fd3-214">O administrador do sistema também pode definir isso para você.</span><span class="sxs-lookup"><span data-stu-id="39fd3-214">Your system administrator can also set that up for you.</span></span>

 <span data-ttu-id="39fd3-215">Finalmente, para salvar seus relatórios em um servidor de relatório ou site do SharePoint integrado a um servidor de relatório, você precisa da URL e de permissões.</span><span class="sxs-lookup"><span data-stu-id="39fd3-215">Finally, to save your reports to a report server or a SharePoint site that is integrated with a report server, you need the URL and permissions.</span></span> <span data-ttu-id="39fd3-216">Você pode executar qualquer relatório que criar diretamente de seu computador, mas os relatórios têm mais funcionalidade quando executados no servidor de relatório ou site do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="39fd3-216">You can run any report you create directly from your computer, but reports have more functionality when run from the report server or SharePoint site.</span></span> <span data-ttu-id="39fd3-217">Você precisa de permissões para executar seus relatórios ou de outras pessoas no servidor de relatório ou site do SharePoint em que eles foram publicados.</span><span class="sxs-lookup"><span data-stu-id="39fd3-217">You need permissions to run your reports or others from the report server or SharePoint site where they are published.</span></span> <span data-ttu-id="39fd3-218">Fale com o administrador do sistema para obter acesso.</span><span class="sxs-lookup"><span data-stu-id="39fd3-218">Talk to your system administrator to obtain access.</span></span>

 <span data-ttu-id="39fd3-219">Talvez seja útil ler sobre alguns dos conceitos e termos antes de começar.</span><span class="sxs-lookup"><span data-stu-id="39fd3-219">It may help to read about some of the concepts and terms before you get started.</span></span> <span data-ttu-id="39fd3-220">Para obter mais informações, consulte [conceitos de criação de relatórios &#40;Construtor de relatórios e SSRS&#41;](../report-design/report-authoring-concepts-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="39fd3-220">For more information, see [Report Authoring Concepts &#40;Report Builder and SSRS&#41;](../report-design/report-authoring-concepts-report-builder-and-ssrs.md).</span></span> <span data-ttu-id="39fd3-221">Além disso, dedique algum tempo ao planejamento, antes de criar seu primeiro relatório.</span><span class="sxs-lookup"><span data-stu-id="39fd3-221">Also, spend some time planning, before you create your first report.</span></span> <span data-ttu-id="39fd3-222">Esse será um tempo bem gasto.</span><span class="sxs-lookup"><span data-stu-id="39fd3-222">It will be time well spent.</span></span> <span data-ttu-id="39fd3-223">Para obter mais informações, consulte [planejando um relatório &#40;Construtor de Relatórios&#41;](../report-design/planning-a-report-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="39fd3-223">For more information, see [Planning a Report &#40;Report Builder&#41;](../report-design/planning-a-report-report-builder.md).</span></span>

 <span data-ttu-id="39fd3-224">![Ícone de seta usado com o link voltar ao início](../../2014-toc/media/uparrow16x16.gif "Ícone de seta usado com o link Voltar ao Início") [de volta ao início](#TwoWays)</span><span class="sxs-lookup"><span data-stu-id="39fd3-224">![Arrow icon used with Back to Top link](../../2014-toc/media/uparrow16x16.gif "Arrow icon used with Back to Top link") [Back to Top](#TwoWays)</span></span>

## <a name="see-also"></a><span data-ttu-id="39fd3-225">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="39fd3-225">See Also</span></span>
 <span data-ttu-id="39fd3-226">[Tutoriais &#40;Construtor de Relatórios&#41;](../report-builder-tutorials.md) [Construtor de Relatórios no SQL Server 2014](report-builder-in-sql-server-2016.md)</span><span class="sxs-lookup"><span data-stu-id="39fd3-226">[Tutorials &#40;Report Builder&#41;](../report-builder-tutorials.md) [Report Builder in SQL Server 2014](report-builder-in-sql-server-2016.md)</span></span>


