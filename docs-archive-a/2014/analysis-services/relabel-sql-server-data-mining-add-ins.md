---
title: Rotular novamente (SQL Server suplementos de mineração de dados) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- data preparation
- relabel
- data cleaning
ms.assetid: af041b39-fdd1-4cb5-a5ef-2f3ddab84614
author: minewiskan
ms.author: owend
ms.openlocfilehash: a625676f60e2da32e19b85a94002b51eeb9ac816
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574294"
---
# <a name="relabel-sql-server-data-mining-add-ins"></a><span data-ttu-id="9a4b4-102">Rotular novamente (Suplementos de Mineração de Dados do SQL Server)</span><span class="sxs-lookup"><span data-stu-id="9a4b4-102">Relabel (SQL Server Data Mining Add-ins)</span></span>
  <span data-ttu-id="9a4b4-103">![Ícone do Office 13 para a ferramenta Rotular Novamente](media/dm13-relabel.gif "Ícone do Office 13 para a ferramenta Rotular Novamente")</span><span class="sxs-lookup"><span data-stu-id="9a4b4-103">![Office 13 icon for Relabel tool](media/dm13-relabel.gif "Office 13 icon for Relabel tool")</span></span>

 <span data-ttu-id="9a4b4-104">O Cliente de Mineração de Dados para Excel o ajuda a criar novos rótulos para os dados para facilitar o entendimento dos resultados da análise.</span><span class="sxs-lookup"><span data-stu-id="9a4b4-104">The Data Mining Client for Excel helps you create new labels for data to make it easier to understand the results of analysis.</span></span>

 <span data-ttu-id="9a4b4-105">Motivos para a nova rotulagem:</span><span class="sxs-lookup"><span data-stu-id="9a4b4-105">Reasons for relabeling include:</span></span>

-   <span data-ttu-id="9a4b4-106">Os dados incluem os resultados que foram codificados, como 1 para masculino e 2 para feminino.</span><span class="sxs-lookup"><span data-stu-id="9a4b4-106">The data includes results that were coded, such as 1 for Male and 2 for Female.</span></span>

-   <span data-ttu-id="9a4b4-107">Você está particionando valores numéricos e quer atribuir aos intervalos um nome descritivo.</span><span class="sxs-lookup"><span data-stu-id="9a4b4-107">You are bucketing numeric values and want to give the ranges a descriptive name.</span></span>

-   <span data-ttu-id="9a4b4-108">Você deseja simplificar nomes longos.</span><span class="sxs-lookup"><span data-stu-id="9a4b4-108">You want to simplify long names.</span></span>

## <a name="using-the-relabel-wizard"></a><span data-ttu-id="9a4b4-109">Usando o Assistente de Rotular Novamente</span><span class="sxs-lookup"><span data-stu-id="9a4b4-109">Using the Relabel Wizard</span></span>

1.  <span data-ttu-id="9a4b4-110">Na faixa de opções **mineração de dados** , clique em **limpar** e, em seguida, selecione **rotular novamente**.</span><span class="sxs-lookup"><span data-stu-id="9a4b4-110">In the **Data Mining** ribbon, click **Clean** and then select **Re-Label**.</span></span>

2.  <span data-ttu-id="9a4b4-111">Selecione a tabela ou o intervalo de dados com os dados que você deseja corrigir.</span><span class="sxs-lookup"><span data-stu-id="9a4b4-111">Select the table or data range that has the data you want to fix.</span></span>

3.  <span data-ttu-id="9a4b4-112">Na página de **novo rótulo** do assistente, selecione uma única coluna, escolhendo a coluna na lista suspensa ou clicando na coluna no painel **amostras de dados** .</span><span class="sxs-lookup"><span data-stu-id="9a4b4-112">In the **Re-label** page of the wizard, select a single column, either by choosing the column from the dropdown list, or by clicking the column in the **Data samples** pane.</span></span>

     <span data-ttu-id="9a4b4-113">O painel **amostras de dados** mostra apenas cerca de 50 linhas de dados, mas eles são amostrados para garantir que você veja uma boa propagação de valores.</span><span class="sxs-lookup"><span data-stu-id="9a4b4-113">The **Data samples** pane only shows about 50 rows of data, but they are sampled to ensure that you see a good spread of values.</span></span>

     <span data-ttu-id="9a4b4-114">Clique no cabeçalho da coluna para **contagem** a ser classificada pela contagem de cada valor.</span><span class="sxs-lookup"><span data-stu-id="9a4b4-114">Click the column header for **Count** to sort by the count of each value.</span></span>

     <span data-ttu-id="9a4b4-115">Você também pode classificar por **Rótulos originais**, o que é útil se você quiser rotular novamente todos os valores mais altos ou mais baixos primeiro.</span><span class="sxs-lookup"><span data-stu-id="9a4b4-115">You can also sort by **Original Labels**, which is handy if you want to re-label all the highest or lowest values first.</span></span>

4.  <span data-ttu-id="9a4b4-116">Na página **rotular dados novamente** do assistente, examine os valores na coluna **Rótulos originais** e decida como deseja agrupá-los ou editá-los.</span><span class="sxs-lookup"><span data-stu-id="9a4b4-116">In the **Re-label** data page of the wizard, review the values in the **Original Labels** column, and decide how you want to group or edit them.</span></span>

5.  <span data-ttu-id="9a4b4-117">Digite um novo valor na linha em **novos rótulos**.</span><span class="sxs-lookup"><span data-stu-id="9a4b4-117">Type a new value into the row under **New Labels**.</span></span> <span data-ttu-id="9a4b4-118">Você também pode escolher um valor na lista de valores existentes.</span><span class="sxs-lookup"><span data-stu-id="9a4b4-118">You can also choose a value from the list of existing values.</span></span> <span data-ttu-id="9a4b4-119">À medida que você digita novos valores, eles são disponibilizados para reutilização imediatamente.</span><span class="sxs-lookup"><span data-stu-id="9a4b4-119">As you type new values, they become available for re-use right away.</span></span>

6.  <span data-ttu-id="9a4b4-120">Quando você tiver inserido linhas suficientes, clique em **Avançar**e, na página **Selecionar destino** , escolha onde você salvará os dados rerotulados.</span><span class="sxs-lookup"><span data-stu-id="9a4b4-120">When you have entered enough rows, click **Next**, and on the **Select Destination** page, choose where you'll save the relabeled data.</span></span>

    -   <span data-ttu-id="9a4b4-121">**Adicionar como uma nova coluna à planilha atual**</span><span class="sxs-lookup"><span data-stu-id="9a4b4-121">**Add as a new column to the current worksheet**</span></span>

         <span data-ttu-id="9a4b4-122">Clique para adicionar uma nova coluna à tabela que contém os novos valores.</span><span class="sxs-lookup"><span data-stu-id="9a4b4-122">Click to add a new column to the table that contains the new values.</span></span>

    -   <span data-ttu-id="9a4b4-123">**Copiar os dados da planilha com alterações em uma nova planilha**</span><span class="sxs-lookup"><span data-stu-id="9a4b4-123">**Copy sheet data with changes to a new worksheet**</span></span>

         <span data-ttu-id="9a4b4-124">Clique para criar uma nova planilha que contenha os dados atualizados.</span><span class="sxs-lookup"><span data-stu-id="9a4b4-124">Click to create a new worksheet that contains the updated data.</span></span>

    -   <span data-ttu-id="9a4b4-125">**Alterar dados no local**</span><span class="sxs-lookup"><span data-stu-id="9a4b4-125">**Change data in place**</span></span>

         <span data-ttu-id="9a4b4-126">Clique para substituir os dados originais pelos novos valores.</span><span class="sxs-lookup"><span data-stu-id="9a4b4-126">Click to replace the original data with the new values.</span></span>

## <a name="see-also"></a><span data-ttu-id="9a4b4-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9a4b4-127">See Also</span></span>
 [<span data-ttu-id="9a4b4-128">Explorando e limpando dados</span><span class="sxs-lookup"><span data-stu-id="9a4b4-128">Exploring and Cleaning Data</span></span>](exploring-and-cleaning-data.md)


