---
title: Adicionar um parâmetro com vários valores a um relatório | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 12ad0e77-4c28-4bbb-ab11-473ae89ec9f1
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 5269293b6a21f3b1d82eb6835efbd275e3be9620
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679155"
---
# <a name="add-a-multi-value-parameter-to-a-report"></a><span data-ttu-id="12ce1-102">Adicionar um parâmetro com vários valores a um relatório</span><span class="sxs-lookup"><span data-stu-id="12ce1-102">Add a multi-value parameter to a Report</span></span>
  <span data-ttu-id="12ce1-103">É possível adicionar um parâmetro a um relatório que permite ao usuário selecionar mais de um valor para o parâmetro.</span><span class="sxs-lookup"><span data-stu-id="12ce1-103">You can add a parameter to a report that allows the user to select more than one value for the parameter.</span></span>  
  
 <span data-ttu-id="12ce1-104">Você pode passar vários valores de parâmetro para o relatório na URL de relatório.</span><span class="sxs-lookup"><span data-stu-id="12ce1-104">You can pass multiple parameter values to the report within the report URL.</span></span> <span data-ttu-id="12ce1-105">Para um exemplo de URL que inclui um parâmetro com vários valores, consulte [Passar um parâmetro de relatório em uma URL](../pass-a-report-parameter-within-a-url.md).</span><span class="sxs-lookup"><span data-stu-id="12ce1-105">For a URL example includes a multi-value parameter, see [Pass a Report Parameter Within a URL](../pass-a-report-parameter-within-a-url.md).</span></span>  
  
 <span data-ttu-id="12ce1-106">Para obter informações sobre como passar vários valores de parâmetro para um procedimento armazenado, consulte [Trabalhando com parâmetros de seleções múltiplas para relatórios SSRS](https://go.microsoft.com/fwlink/?LinkId=321529) em mssqltips.com.</span><span class="sxs-lookup"><span data-stu-id="12ce1-106">For information on how to pass multiple parameter values to a stored procedure, see [Working With Multi-Select Parameters for SSRS Reports](https://go.microsoft.com/fwlink/?LinkId=321529) on mssqltips.com.</span></span>  
  
### <a name="to-add-a-multi-value-parameter"></a><span data-ttu-id="12ce1-107">Para adicionar um parâmetro com vários valores</span><span class="sxs-lookup"><span data-stu-id="12ce1-107">To add a multi-value parameter</span></span>  
  
1.  <span data-ttu-id="12ce1-108">No Construtor de Relatórios, abra o relatório no qual você deseja adicionar o parâmetro com vários valores.</span><span class="sxs-lookup"><span data-stu-id="12ce1-108">In Report Builder, open the report that you want to add the multi-value parameter to.</span></span>  
  
2.  <span data-ttu-id="12ce1-109">Clique com o botão direito do mouse no conjunto de dados do relatório e clique em **Propriedades do Conjunto de Dados**</span><span class="sxs-lookup"><span data-stu-id="12ce1-109">Right-click the report dataset, and then click **Dataset Properties**</span></span>  
  
3.  <span data-ttu-id="12ce1-110">Adicione uma variável à consulta do conjunto de dados editando o texto da consulta na caixa **Consulta** , ou adicionando um filtro através do designer de consulta.</span><span class="sxs-lookup"><span data-stu-id="12ce1-110">Add a variable to the dataset query by either editing the query text in the **Query** box, or by adding a filter by using the query designer.</span></span> <span data-ttu-id="12ce1-111">Para obter mais informações, consulte [Criar uma consulta no Designer de Consultas Relacionais &#40;Construtor de Relatórios e SSRS&#41;](../report-data/build-a-query-in-the-relational-query-designer-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="12ce1-111">For more information, see [Build a Query in the Relational Query Designer &#40;Report Builder and SSRS&#41;](../report-data/build-a-query-in-the-relational-query-designer-report-builder-and-ssrs.md).</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="12ce1-112">O texto da consulta não deve incluir uma instrução DECLARE para a variável de consulta.</span><span class="sxs-lookup"><span data-stu-id="12ce1-112">The query text must not include the DECLARE statement for the query variable.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="12ce1-113">O texto da variável de consulta deve incluir o operador `IN`, como mostrado no exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="12ce1-113">The text for the query variable must include the `IN` operator, as shown in the following example.</span></span>  
  
    ```  
    WHERE  
      Production.ProductInventory.ProductID IN (@ProductID)  
    ```  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="12ce1-114">Se você não incluir os parênteses em volta da variável, como mostrado acima, o relatório não será renderizado e o erro "é necessário declarar a variável escalar" será exibido.</span><span class="sxs-lookup"><span data-stu-id="12ce1-114">If you don't include the parentheses around the variable as shown above, the report fails to render and the "must declare the scalar variable" error is displayed.</span></span>  
  
     <span data-ttu-id="12ce1-115">Um parâmetro de conjunto de dados para um conjunto de dados inserido ou um conjunto de dados compartilhado é criado automaticamente para a variável de consulta.</span><span class="sxs-lookup"><span data-stu-id="12ce1-115">A dataset parameter for an embedded dataset or a shared dataset is created automatically for the query variable.</span></span> <span data-ttu-id="12ce1-116">Um parâmetro de relatório é criado automaticamente para o parâmetro de conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="12ce1-116">A report parameter is created automatically for the dataset parameter.</span></span>  
  
4.  <span data-ttu-id="12ce1-117">No painel **Dados do Relatório** , expanda o nó **Parâmetros** , clique com o botão direito do mouse no parâmetro de relatório criado automaticamente para o parâmetro do conjunto de dados e clique em **Propriedades do Parâmetro**.</span><span class="sxs-lookup"><span data-stu-id="12ce1-117">In the **Report Data** pane, expand the **Parameters** node, right-click the report parameter that was automatically created for the dataset parameter, and then click **Parameter Properties**.</span></span>  
  
5.  <span data-ttu-id="12ce1-118">Na guia **Geral** , selecione **Permitir vários valores** para permitir que um usuário selecione mais de um valor para o parâmetro.</span><span class="sxs-lookup"><span data-stu-id="12ce1-118">In the **General** tab, select **Allow multiple values** to allow a user to select more than one value for the parameter.</span></span>  
  
6.  <span data-ttu-id="12ce1-119">(Opcionalmente) Na guia **Valores disponíveis** , especifique uma lista de valores disponíveis a serem exibidos para o usuário.</span><span class="sxs-lookup"><span data-stu-id="12ce1-119">(Optionally) In the **Available** values tab, specify a list of available values to display to the user.</span></span>  
  
     <span data-ttu-id="12ce1-120">Uma lista de valores disponíveis limita as escolhas do usuário aos valores válidos para o parâmetro.</span><span class="sxs-lookup"><span data-stu-id="12ce1-120">An available values list limits the choices a user can make to only valid values for the parameter.</span></span> <span data-ttu-id="12ce1-121">No caso de diversos valores, a lista começa com um recurso **Selecionar Tudo** , através do qual o usuário pode selecionar ou desmarcar todos os valores com um só clique.</span><span class="sxs-lookup"><span data-stu-id="12ce1-121">For multiple values, the top of list begins with a **Select All** feature so the user can select or clear all values with a single click.</span></span> <span data-ttu-id="12ce1-122">Se você optar por obter os valores disponíveis para o parâmetro de relatório de uma consulta de conjunto de dados, selecione um conjunto de dados que não contenha a variável de consulta que está associada ao mesmo parâmetro de relatório.</span><span class="sxs-lookup"><span data-stu-id="12ce1-122">If you choose to get the available values for the report parameter from a dataset query, be sure to select a dataset that does not contain the query variable that is associated with the same report parameter.</span></span>  
  
     <span data-ttu-id="12ce1-123">Para obter mais informações, consulte [Adicionar, alterar ou excluir os valores disponíveis de um parâmetro de relatório &#40;Construtor de Relatórios e SSRS&#41;](add-change-or-delete-available-values-for-a-report-parameter.md).</span><span class="sxs-lookup"><span data-stu-id="12ce1-123">For more information, see [Add, Change, or Delete Available Values for a Report Parameter &#40;Report Builder and SSRS&#41;](add-change-or-delete-available-values-for-a-report-parameter.md).</span></span>  
  
### <a name="to-add-a-multi-value-parameter"></a><span data-ttu-id="12ce1-124">Para adicionar um parâmetro com vários valores</span><span class="sxs-lookup"><span data-stu-id="12ce1-124">To add a multi-value parameter</span></span>  
  
1.  <span data-ttu-id="12ce1-125">No Construtor de Relatórios, abra o relatório no qual você deseja adicionar o parâmetro com vários valores.</span><span class="sxs-lookup"><span data-stu-id="12ce1-125">In Report Builder, open the report that you want to add the multi-value parameter to.</span></span>  
  
2.  <span data-ttu-id="12ce1-126">Clique com o botão direito do mouse no conjunto de dados do relatório e clique em **Propriedades do Conjunto de Dados**</span><span class="sxs-lookup"><span data-stu-id="12ce1-126">Right-click the report dataset, and then click **Dataset Properties**</span></span>  
  
3.  <span data-ttu-id="12ce1-127">Adicione uma variável à consulta do conjunto de dados editando o texto da consulta na caixa **Consulta** , ou adicionando um filtro através do designer de consulta.</span><span class="sxs-lookup"><span data-stu-id="12ce1-127">Add a variable to the dataset query by either editing the query text in the **Query** box, or by adding a filter by using the query designer.</span></span> <span data-ttu-id="12ce1-128">Para obter mais informações, consulte [Criar uma consulta no Designer de Consultas Relacionais &#40;Construtor de Relatórios e SSRS&#41;](../report-data/build-a-query-in-the-relational-query-designer-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="12ce1-128">For more information, see [Build a Query in the Relational Query Designer &#40;Report Builder and SSRS&#41;](../report-data/build-a-query-in-the-relational-query-designer-report-builder-and-ssrs.md).</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="12ce1-129">O texto da consulta não deve incluir uma instrução DECLARE para a variável de consulta.</span><span class="sxs-lookup"><span data-stu-id="12ce1-129">The query text must not include the DECLARE statement for the query variable.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="12ce1-130">O texto da variável de consulta deve incluir o operador `IN`, como mostrado no exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="12ce1-130">The text for the query variable must include the `IN` operator, as shown in the following example.</span></span>  
  
    ```  
    WHERE  
      Production.ProductInventory.ProductID IN (@ProductID)  
    ```  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="12ce1-131">Se você não incluir os parênteses em volta da variável, como mostrado acima, o relatório não será renderizado e o erro "é necessário declarar a variável escalar" será exibido.</span><span class="sxs-lookup"><span data-stu-id="12ce1-131">If you don't include the parentheses around the variable as shown above, the report fails to render and the "must declare the scalar variable" error is displayed.</span></span>  
  
     <span data-ttu-id="12ce1-132">Um parâmetro de conjunto de dados para um conjunto de dados inserido ou um conjunto de dados compartilhado é criado automaticamente para a variável de consulta.</span><span class="sxs-lookup"><span data-stu-id="12ce1-132">A dataset parameter for an embedded dataset or a shared dataset is created automatically for the query variable.</span></span> <span data-ttu-id="12ce1-133">Um parâmetro de relatório é criado automaticamente para o parâmetro de conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="12ce1-133">A report parameter is created automatically for the dataset parameter.</span></span>  
  
4.  <span data-ttu-id="12ce1-134">No painel **Dados do Relatório** , expanda o nó **Parâmetros** , clique com o botão direito do mouse no parâmetro de relatório criado automaticamente para o parâmetro do conjunto de dados e clique em **Propriedades do Parâmetro**.</span><span class="sxs-lookup"><span data-stu-id="12ce1-134">In the **Report Data** pane, expand the **Parameters** node, right-click the report parameter that was automatically created for the dataset parameter, and then click **Parameter Properties**.</span></span>  
  
5.  <span data-ttu-id="12ce1-135">Na guia **Geral** , selecione **Permitir vários valores** para permitir que um usuário selecione mais de um valor para o parâmetro.</span><span class="sxs-lookup"><span data-stu-id="12ce1-135">In the **General** tab, select **Allow multiple values** to allow a user to select more than one value for the parameter.</span></span>  
  
6.  <span data-ttu-id="12ce1-136">(Opcionalmente) Na guia **Valores disponíveis** , especifique uma lista de valores disponíveis a serem exibidos para o usuário.</span><span class="sxs-lookup"><span data-stu-id="12ce1-136">(Optionally) In the **Available** values tab, specify a list of available values to display to the user.</span></span>  
  
     <span data-ttu-id="12ce1-137">Uma lista de valores disponíveis limita as escolhas do usuário aos valores válidos para o parâmetro.</span><span class="sxs-lookup"><span data-stu-id="12ce1-137">An available values list limits the choices a user can make to only valid values for the parameter.</span></span> <span data-ttu-id="12ce1-138">No caso de diversos valores, a lista começa com um recurso **Selecionar Tudo** , através do qual o usuário pode selecionar ou desmarcar todos os valores com um só clique.</span><span class="sxs-lookup"><span data-stu-id="12ce1-138">For multiple values, the top of list begins with a **Select All** feature so the user can select or clear all values with a single click.</span></span> <span data-ttu-id="12ce1-139">Se você optar por obter os valores disponíveis para o parâmetro de relatório de uma consulta de conjunto de dados, selecione um conjunto de dados que não contenha a variável de consulta que está associada ao mesmo parâmetro de relatório.</span><span class="sxs-lookup"><span data-stu-id="12ce1-139">If you choose to get the available values for the report parameter from a dataset query, be sure to select a dataset that does not contain the query variable that is associated with the same report parameter.</span></span>  
  
     <span data-ttu-id="12ce1-140">Para obter mais informações, consulte [Adicionar, alterar ou excluir os valores disponíveis de um parâmetro de relatório &#40;Construtor de Relatórios e SSRS&#41;](add-change-or-delete-available-values-for-a-report-parameter.md).</span><span class="sxs-lookup"><span data-stu-id="12ce1-140">For more information, see [Add, Change, or Delete Available Values for a Report Parameter &#40;Report Builder and SSRS&#41;](add-change-or-delete-available-values-for-a-report-parameter.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12ce1-141">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="12ce1-141">See Also</span></span>  
 <span data-ttu-id="12ce1-142">[Adicionar parâmetros em cascata a um relatório &#40;Construtor de Relatórios e SSRS&#41;](add-cascading-parameters-to-a-report-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="12ce1-142">[Add Cascading Parameters to a Report &#40;Report Builder and SSRS&#41;](add-cascading-parameters-to-a-report-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="12ce1-143">Adicionar, alterar ou excluir um parâmetro de relatório &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="12ce1-143">Add, Change, or Delete a Report Parameter &#40;Report Builder and SSRS&#41;</span></span>](add-change-or-delete-a-report-parameter-report-builder-and-ssrs.md)  
  
  
