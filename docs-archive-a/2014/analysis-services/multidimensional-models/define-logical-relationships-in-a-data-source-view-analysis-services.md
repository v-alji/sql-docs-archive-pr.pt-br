---
title: Definir relações lógicas em uma exibição da fonte de dados (Analysis Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- adding relationships
- relationships [Analysis Services], data source views
- data source views [Analysis Services], relationships
ms.assetid: a20d6dae-e769-4131-8a59-7ef56f174220
author: minewiskan
ms.author: owend
ms.openlocfilehash: c46c2b360a4528aeb0eb88348d0d1242b22d8ef5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574388"
---
# <a name="define-logical-relationships-in-a-data-source-view-analysis-services"></a><span data-ttu-id="23d72-102">Definir relações lógicas em uma exibição da fonte de dados (Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="23d72-102">Define Logical Relationships in a Data Source View (Analysis Services)</span></span>
  <span data-ttu-id="23d72-103">O Assistente de Exibição da Fonte de Dados e o Designer de Exibição da Fonte de Dados definem relações entre as tabelas adicionadas a uma DSV (exibição da fonte de dados) com base nas relações do banco de dados subjacente ou nos critérios de correspondência de nomes que você especificar.</span><span class="sxs-lookup"><span data-stu-id="23d72-103">The Data Source View Wizard and Data Source View Designer automatically define relationships between tables added to a data source view (DSV) based on underlying database relationships or name matching criteria you specify.</span></span>  
  
 <span data-ttu-id="23d72-104">Nos casos em que você está trabalhando com dados de diversas fontes de dados, pode ser necessário definir manualmente relações lógicas na DSV (exibição da fonte de dados) para complementar essas relações que são definidas automaticamente.</span><span class="sxs-lookup"><span data-stu-id="23d72-104">In cases where you are working with data from multiple data sources, you may need to manually define logical relationships in the DSV to supplement those relationships that are defined automatically.</span></span> <span data-ttu-id="23d72-105">O [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] precisa de relações para identificar tabelas de fatos e dimensões, construir consultas para recuperar dados e metadados de fontes de dados subjacentes e aproveitar os recursos avançados de business intelligence.</span><span class="sxs-lookup"><span data-stu-id="23d72-105">Relationships are required in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] to identify fact and dimension tables, to construct queries for retrieving data and metadata from underlying data sources, and to take advantage of advanced business intelligence features.</span></span>  
  
 <span data-ttu-id="23d72-106">Você pode definir os tipos de relações a seguir no Designer de Exibição da Fonte de Dados:</span><span class="sxs-lookup"><span data-stu-id="23d72-106">You can define the following types of relationships in Data Source View Designer:</span></span>  
  
-   <span data-ttu-id="23d72-107">Uma relação de uma tabela para outra na mesma fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="23d72-107">A relationship from one table to another table in the same data source.</span></span>  
  
-   <span data-ttu-id="23d72-108">Uma relação de uma tabela para ela mesma, como em uma relação pai-filho.</span><span class="sxs-lookup"><span data-stu-id="23d72-108">A relationship from one table to itself, as in a parent-child relationship.</span></span>  
  
-   <span data-ttu-id="23d72-109">Uma relação de uma tabela de uma fonte de dados para outra tabela de outra fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="23d72-109">A relationship from one table in a data source to another table in a different data source.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="23d72-110">As relações definidas em uma DSV são lógicas e não podem refletir as relações atuais definidas na fonte de dados subjacente.</span><span class="sxs-lookup"><span data-stu-id="23d72-110">The relationships defined in a DSV are logical and may not reflect the actual relationships defined in the underlying data source.</span></span> <span data-ttu-id="23d72-111">É possível criar relações no Designer de Exibição da Fonte de Dados que não existem na fonte de dados subjacente e remover relações criadas pelo Designer da Exibição da Fonte de Dados a partir de relações de chave estrangeira existentes na fonte de dados subjacente.</span><span class="sxs-lookup"><span data-stu-id="23d72-111">You can create relationships in Data Source View Designer that do not exist in the underlying data source, and remove relationships created by Data Source View Designer from existing foreign key relationships in the underlying data source.</span></span>  
  
 <span data-ttu-id="23d72-112">As relações são direcionadas.</span><span class="sxs-lookup"><span data-stu-id="23d72-112">Relationships are directed.</span></span> <span data-ttu-id="23d72-113">Para cada valor da coluna de origem, existe um valor correspondente na coluna de destino.</span><span class="sxs-lookup"><span data-stu-id="23d72-113">For every value in the source column, there is a corresponding value in the destination column.</span></span> <span data-ttu-id="23d72-114">Em um diagrama da exibição da fonte de dados, como os diagramas exibidos no painel **Diagrama** , uma seta na linha entre duas tabelas indica a direção da relação.</span><span class="sxs-lookup"><span data-stu-id="23d72-114">In a data source view diagram, such as the diagrams displayed in the **Diagram** pane, an arrow on the line between two tables indicates the direction of the relationship.</span></span>  
  
 <span data-ttu-id="23d72-115">Este tópico inclui as seções a seguir:</span><span class="sxs-lookup"><span data-stu-id="23d72-115">This topic includes the following sections:</span></span>  
  
 [<span data-ttu-id="23d72-116">Adicionar uma relação entre tabelas, consultas nomeadas ou exibições</span><span class="sxs-lookup"><span data-stu-id="23d72-116">To add a relationship between tables, named queries, or views</span></span>](#bkmk_addRel)  
  
 [<span data-ttu-id="23d72-117">Para exibir ou modificar uma relação no painel diagrama</span><span class="sxs-lookup"><span data-stu-id="23d72-117">To view or modify a relationship in the Diagram pane</span></span>](#bkmk_diagrampane)  
  
 [<span data-ttu-id="23d72-118">Para exibir ou modificar uma relação no painel tabelas</span><span class="sxs-lookup"><span data-stu-id="23d72-118">To view or modify a relationship in the Tables pane</span></span>](#bkmk_tablespane)  
  
##  <a name="to-add-a-relationship-between-tables-named-queries-or-views"></a><a name="bkmk_addRel"></a><span data-ttu-id="23d72-119">Para adicionar uma relação entre tabelas, consultas nomeadas ou exibições</span><span class="sxs-lookup"><span data-stu-id="23d72-119">To add a relationship between tables, named queries, or views</span></span>  
  
1.  <span data-ttu-id="23d72-120">No [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], abra o projeto ou conecte-se ao banco de dados que contém a exibição da fonte de dados à qual você deseja adicionar uma relação lógica.</span><span class="sxs-lookup"><span data-stu-id="23d72-120">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the project or connect to the database that contains the data source view in which you wish to add a logical relationship.</span></span>  
  
2.  <span data-ttu-id="23d72-121">No Gerenciador de Soluções, expanda a pasta **Exibições da Fonte de Dados** e clique duas vezes na exibição da fonte de dados para abri-la no **Designer de Exibição da Fonte de Dados**.</span><span class="sxs-lookup"><span data-stu-id="23d72-121">In Solution Explorer, expand the **Data Source Views** folder, then double-click the data source view to open it in **Data Source View Designer**.</span></span>  
  
3.  <span data-ttu-id="23d72-122">Clique com o botão direito do mouse na tabela, consulta nomeada ou exibição a que você deseja adicionar uma relação no painel **Tabelas** e, em seguida, clique em **Nova Relação**.</span><span class="sxs-lookup"><span data-stu-id="23d72-122">Right-click the table, named query or view to which you want to add a relationship in either the **Tables** pane and then click **New Relationship**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="23d72-123">Para localizar uma tabela, exibição ou consulta nomeada, use a opção **Localizar Tabela** clicando no menu **Exibição da Fonte de Dados** ou clicando com o botão direito do mouse em uma área livre do painel **Tabelas** ou de **Diagrama** .</span><span class="sxs-lookup"><span data-stu-id="23d72-123">To locate a table, view or named query, you can use the **Find Table** option by either clicking the **Data Source View** menu or right-clicking in an open area of the **Tables** or **Diagram** panes.</span></span>  
  
4.  <span data-ttu-id="23d72-124">Na caixa de diálogo **Especificar Relação** , faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="23d72-124">In the **Specify Relationship** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="23d72-125">Selecione a tabela, consulta nomeada ou exibição apropriada na lista **Tabela de origem (chave estrangeira)** .</span><span class="sxs-lookup"><span data-stu-id="23d72-125">Select the appropriate table, named query, or view in the **Source (foreign key) table** list.</span></span>  
  
    2.  <span data-ttu-id="23d72-126">Selecione a tabela, consulta nomeada ou exibição apropriada na lista **Tabela de destino (chave primária)** .</span><span class="sxs-lookup"><span data-stu-id="23d72-126">Select the appropriate table, named query, or view in the **Destination (primary key) table** lists.</span></span>  
  
    3.  <span data-ttu-id="23d72-127">Selecione as colunas nas listas **Colunas de Origem** e **Colunas de Destino** para criar uma relação entre as duas tabelas.</span><span class="sxs-lookup"><span data-stu-id="23d72-127">Select columns from the **Source Columns** and **Destination Columns** lists to create a relationship between the two tables.</span></span>  
  
         <span data-ttu-id="23d72-128">Se o [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] detectar, pela amostragem dos dados da tabela, exibição ou consulta nomeada subjacente, que você definiu a relação na direção errada (da chave primária para a chave estrangeira em vez do contrário), será solicitada a inversão da ordem.</span><span class="sxs-lookup"><span data-stu-id="23d72-128">If [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] detects, by sampling the data in the underlying table, view, or named query, that you have defined the relationship in the wrong direction (from the primary key to the foreign key rather than from the foreign key to the primary key), you will be prompted to reverse the order.</span></span> <span data-ttu-id="23d72-129">Para invertê-la rapidamente, clique em **Inverter**.</span><span class="sxs-lookup"><span data-stu-id="23d72-129">To quickly reverse the order, click **Reverse**.</span></span>  
  
         <span data-ttu-id="23d72-130">Se o [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] detectar que já existe uma relação entre as colunas selecionadas, você será avisado.</span><span class="sxs-lookup"><span data-stu-id="23d72-130">If [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] detects that a relationship already exists for the columns you have selected, you will be prompted.</span></span> <span data-ttu-id="23d72-131">Não é possível definir relações duplicadas.</span><span class="sxs-lookup"><span data-stu-id="23d72-131">You cannot define duplicate relationships.</span></span>  
  
    4.  <span data-ttu-id="23d72-132">Opcionalmente, na caixa **Descrição** , digite uma descrição para a relação.</span><span class="sxs-lookup"><span data-stu-id="23d72-132">Optionally, in the **Description** box, type a description for the relationship.</span></span>  
  
##  <a name="to-view-or-modify-a-relationship-in-the-diagram-pane"></a><a name="bkmk_diagrampane"></a> <span data-ttu-id="23d72-133">Para exibir ou modificar uma relação no painel de Diagrama</span><span class="sxs-lookup"><span data-stu-id="23d72-133">To view or modify a relationship in the Diagram pane</span></span>  
  
-   <span data-ttu-id="23d72-134">No painel **Diagrama** no **Designer de Exibição da Fonte de Dados**, clique com o botão direito do mouse na relação que você deseja exibir e clique em **Editar Relação** (ou simplesmente clique duas vezes na seta da relação).</span><span class="sxs-lookup"><span data-stu-id="23d72-134">In the **Diagram** pane in **Data Source View Designer**, right-click the relationship that you want to view and click **Edit Relationship** (or simply double-click the relationship arrow).</span></span>  <span data-ttu-id="23d72-135">Use a caixa de diálogo **Editar Relação** para modificar a relação.</span><span class="sxs-lookup"><span data-stu-id="23d72-135">Use the **Edit Relationship** dialog box to modify the relationship.</span></span>  
  
##  <a name="to-view-or-modify-a-relationship-in-the-tables-pane"></a><a name="bkmk_tablespane"></a> <span data-ttu-id="23d72-136">Para exibir ou modificar uma relação no painel de Tabelas</span><span class="sxs-lookup"><span data-stu-id="23d72-136">To view or modify a relationship in the Tables pane</span></span>  
  
1.  <span data-ttu-id="23d72-137">No painel **Tabelas** no **Designer de Exibição da Fonte de Dados**, localize e expanda a tabela, exibição ou consulta nomeada que contém a relação que você deseja exibir ou modificar.</span><span class="sxs-lookup"><span data-stu-id="23d72-137">In the **Tables** pane in **Data Source View Designer**, locate and then expand the table, view or named query containing the relationship that you wish to view or modify.</span></span>  
  
2.  <span data-ttu-id="23d72-138">Expanda a pasta **Relações** .</span><span class="sxs-lookup"><span data-stu-id="23d72-138">Expand the **Relationships** folder.</span></span>  <span data-ttu-id="23d72-139">As relações entre a tabela, exibição ou consulta nomeada selecionada e outras tabelas, exibições ou consultas nomeadas aparecem com a coluna de relações listada.</span><span class="sxs-lookup"><span data-stu-id="23d72-139">The relationships between the selected table, view or named query and other tables, views and named queries appear with the relationship column listed.</span></span>  
  
3.  <span data-ttu-id="23d72-140">Clique com o botão direito do mouse na relação que você deseja modificar e, em seguida, clique em **Editar Relação**.</span><span class="sxs-lookup"><span data-stu-id="23d72-140">Right-click the relationship you want to modify, and then click **Edit Relationship**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23d72-141">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="23d72-141">See Also</span></span>  
 [<span data-ttu-id="23d72-142">Exibições de fontes de dados em modelos multidimensionais</span><span class="sxs-lookup"><span data-stu-id="23d72-142">Data Source Views in Multidimensional Models</span></span>](data-source-views-in-multidimensional-models.md)  
  
  
