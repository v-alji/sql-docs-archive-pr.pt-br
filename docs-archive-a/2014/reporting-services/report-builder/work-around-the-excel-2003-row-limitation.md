---
title: Contornar a limitação de linha do Excel | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: a4c8700b-bef5-4440-a99c-bba5dcc46bfd
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 128f65cf09833d23234da10bf7744c6ce30065ca
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571316"
---
# <a name="work-around-the-excel-row-limitation"></a><span data-ttu-id="da2ac-102">Solução do problema de limitação de linhas do Excel</span><span class="sxs-lookup"><span data-stu-id="da2ac-102">Work Around the Excel Row Limitation</span></span>
  <span data-ttu-id="da2ac-103">Este tópico explica como resolver a limitação de linhas do Excel 2003 quando você exporta relatórios para o Excel.</span><span class="sxs-lookup"><span data-stu-id="da2ac-103">This topic explains how to work around the Excel 2003 row limitation when you export reports to Excel.</span></span> <span data-ttu-id="da2ac-104">A solução alternativa é para um relatório que contém apenas uma tabela.</span><span class="sxs-lookup"><span data-stu-id="da2ac-104">The workaround is for a report that contains only a table.</span></span>  
  
 <span data-ttu-id="da2ac-105">O Excel 2003 oferece suporte a um máximo de 65.536 linhas por planilha.</span><span class="sxs-lookup"><span data-stu-id="da2ac-105">Excel 2003 supports a maximum of 65,536 rows per worksheet.</span></span> <span data-ttu-id="da2ac-106">Você pode solucionar essa limitação forçando uma quebra de página explícita depois de um determinado número de linhas.</span><span class="sxs-lookup"><span data-stu-id="da2ac-106">You can work around this limitation by forcing an explicit page break after a certain number of rows.</span></span> <span data-ttu-id="da2ac-107">O renderizador do Excel cria uma nova planilha para cada quebra de página explícita.</span><span class="sxs-lookup"><span data-stu-id="da2ac-107">The Excel renderer creates a new worksheet for each explicit page break.</span></span>  
  
### <a name="to-create-an-explicit-page-break"></a><span data-ttu-id="da2ac-108">Para criar uma quebra de página explícita</span><span class="sxs-lookup"><span data-stu-id="da2ac-108">To create an explicit page break</span></span>  
  
1.  <span data-ttu-id="da2ac-109">Abra o relatório no [!INCLUDE[ss_dtbi](../../includes/ss-dtbi-md.md)] ou no Gerenciador de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="da2ac-109">Open the report in [!INCLUDE[ss_dtbi](../../includes/ss-dtbi-md.md)] or Report Manager.</span></span>  
  
2.  <span data-ttu-id="da2ac-110">Clique com o botão direito do mouse na linha de dados na tabela e clique em **Adicionar**grupo  >  **pai grupo** para adicionar um grupo de tabelas externo.</span><span class="sxs-lookup"><span data-stu-id="da2ac-110">Right click the Data row in the table, and then click **Add Group** > **Parent Group** to add an outer table group.</span></span>  
  
     <span data-ttu-id="da2ac-111">![Selecionar o grupo pai](../media/datarow-selectparentgroup.png "Selecionar o grupo pai")</span><span class="sxs-lookup"><span data-stu-id="da2ac-111">![Select the Parent Group](../media/datarow-selectparentgroup.png "Select the Parent Group")</span></span>  
  
3.  <span data-ttu-id="da2ac-112">Digite a fórmula a seguir na caixa de expressão **Agrupar por** e clique em **OK** para adicionar o grupo pai.</span><span class="sxs-lookup"><span data-stu-id="da2ac-112">Enter the following formula in the **Group by** expression box, and then click **OK** to add the parent group.</span></span>  
  
     <span data-ttu-id="da2ac-113">=Int((RowNumber(Nothing)-1)/65000)</span><span class="sxs-lookup"><span data-stu-id="da2ac-113">=Int((RowNumber(Nothing)-1)/65000)</span></span>  
  
     <span data-ttu-id="da2ac-114">A fórmula atribui um número a cada conjunto de 65000 linhas no conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="da2ac-114">The formula assigns a number to each set of 65000 rows in the dataset.</span></span> <span data-ttu-id="da2ac-115">Quando uma quebra de página é definida para o grupo, a expressão resulta em uma quebra de página a cada 65000 linhas.</span><span class="sxs-lookup"><span data-stu-id="da2ac-115">When a page break is defined for the group, the expression results in a page break every 65000 rows.</span></span>  
  
     <span data-ttu-id="da2ac-116">A adição do grupo de tabelas externo adiciona uma coluna de grupo ao relatório.</span><span class="sxs-lookup"><span data-stu-id="da2ac-116">Adding the outer table group adds a group column to the report.</span></span>  
  
4.  <span data-ttu-id="da2ac-117">Exclua a coluna de grupo clicando com o botão direito do mouse no cabeçalho de coluna, clicando em **Excluir Colunas**, selecionando **Excluir colunas apenas**e clicando em **OK**.</span><span class="sxs-lookup"><span data-stu-id="da2ac-117">Delete the group column by right-clicking on the column header, clicking **Delete Columns**, selecting **Delete columns only**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="da2ac-118">![Excluir uma coluna do grupo](../media/groupcolumn-delete-updated.png "Excluir uma coluna do grupo")</span><span class="sxs-lookup"><span data-stu-id="da2ac-118">![Delete a group column](../media/groupcolumn-delete-updated.png "Delete a group column")</span></span>  
  
5.  <span data-ttu-id="da2ac-119">Clique com o botão direito do mouse em **Grupo 1** na seção **Grupos de Linhas** e clique em **Propriedades do Grupo**.</span><span class="sxs-lookup"><span data-stu-id="da2ac-119">Right click **Group 1** in the **Row Groups** section, and then click **Group Properties**.</span></span>  
  
     <span data-ttu-id="da2ac-120">![Exibir propriedades do grupo](../media/groupproperties-updated.png "Exibir propriedades do grupo")</span><span class="sxs-lookup"><span data-stu-id="da2ac-120">![View group properties](../media/groupproperties-updated.png "View group properties")</span></span>  
  
6.  <span data-ttu-id="da2ac-121">Na página **Classificação** da caixa de diálogo **Propriedades do Grupo** , selecione a opção de classificação padrão e clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="da2ac-121">On the **Sorting** page of the **Group Properties** dialog box, select the default sorting option and click **Delete**.</span></span>  
  
     <span data-ttu-id="da2ac-122">![Excluir classificação padrão](../media/groupproperties-sorting-updated.png "Excluir classificação padrão")</span><span class="sxs-lookup"><span data-stu-id="da2ac-122">![Delete default sorting](../media/groupproperties-sorting-updated.png "Delete default sorting")</span></span>  
  
7.  <span data-ttu-id="da2ac-123">Na página **Quebras de Página** , clique em **Entre cada instância de um grupo** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="da2ac-123">On the **Page Breaks** page, click **Between each instance of a group** and then click **OK**.</span></span>  
  
     <span data-ttu-id="da2ac-124">![Definir quebras de página](../media/groupproperties-pagebreaks-updated.png "Definir quebras de página")</span><span class="sxs-lookup"><span data-stu-id="da2ac-124">![Set page breaks](../media/groupproperties-pagebreaks-updated.png "Set page breaks")</span></span>  
  
8.  <span data-ttu-id="da2ac-125">Salve o relatório.</span><span class="sxs-lookup"><span data-stu-id="da2ac-125">Save the report.</span></span> <span data-ttu-id="da2ac-126">Quando você exportá-lo para o Excel, a exportação será realizada para várias planilhas, e cada planilha conterá um máximo de 65000 linhas.</span><span class="sxs-lookup"><span data-stu-id="da2ac-126">When you export it to Excel, it exports to multiple worksheets and each worksheet contains a maximum of 65000 rows.</span></span>  
  
  
