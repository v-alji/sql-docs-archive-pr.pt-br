---
title: Especificar os dados de treinamento (Assistente de mineração de dados) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.dmwizard.specifytrainingdata.f1
ms.assetid: cb04deeb-0f89-4bba-b3f1-efccada16825
author: minewiskan
ms.author: owend
ms.openlocfilehash: 87a802256d287a3e8e9e7fb65bbd91687cb71a4a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581488"
---
# <a name="specify-the-training-data-data-mining-wizard"></a><span data-ttu-id="aefbd-102">Especificar os dados de treinamento (Assistente de Mineração de Dados)</span><span class="sxs-lookup"><span data-stu-id="aefbd-102">Specify the Training Data (Data Mining Wizard)</span></span>
  <span data-ttu-id="aefbd-103">Use a página **Especificar os Dados de Treinamento** para identificar quais as colunas a incluir na estrutura de mineração.</span><span class="sxs-lookup"><span data-stu-id="aefbd-103">Use the **Specify the Training Data** page to identify which columns to include in the mining structure.</span></span> <span data-ttu-id="aefbd-104">Você pode selecionar colunas a serem incluídas na estrutura mesmo se não usá-las em todos os modelos.</span><span class="sxs-lookup"><span data-stu-id="aefbd-104">You can select columns to include in the structure even if you do not use them in all models.</span></span> <span data-ttu-id="aefbd-105">Por exemplo, para detalhar até as colunas a partir do modelo de mineração, você pode incluí-las na estrutura, mas não no modelo.</span><span class="sxs-lookup"><span data-stu-id="aefbd-105">For example, if you want to drill through to the columns from the mining model, you can include them in the structure but not in the model.</span></span>  
  
 <span data-ttu-id="aefbd-106">Pelo menos uma coluna de chave é obrigatória para cada tabela incluída na estrutura.</span><span class="sxs-lookup"><span data-stu-id="aefbd-106">At least one key column is required for each table that is included in the structure.</span></span> <span data-ttu-id="aefbd-107">A coluna escolhida como chave depende de a tabela ser a tabela de casos ou uma tabela aninhada.</span><span class="sxs-lookup"><span data-stu-id="aefbd-107">The column that you pick as the key depends on whether the table is a case table or a nested table.</span></span> <span data-ttu-id="aefbd-108">Se for uma tabela aninhada, a chave frequentemente também será a coluna previsível, não a chave estrangeira relacional.</span><span class="sxs-lookup"><span data-stu-id="aefbd-108">If the table is a nested table, the key is often also the predictable column, not the relational foreign key.</span></span> <span data-ttu-id="aefbd-109">Para saber mais sobre chaves aninhadas, consulte [Tabelas aninhadas &#40;Analysis Services – Data Mining&#41;](data-mining/nested-tables-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="aefbd-109">To learn about nested keys, see [Nested Tables &#40;Analysis Services - Data Mining&#41;](data-mining/nested-tables-analysis-services-data-mining.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="aefbd-110">Algoritmos de mineração diferentes usam as chaves de maneira diferente.</span><span class="sxs-lookup"><span data-stu-id="aefbd-110">Different mining algorithms use keys differently.</span></span> <span data-ttu-id="aefbd-111">Para saber mais sobre os tipos diferentes de chaves, consulte [Tipos de conteúdo &#40;Data Mining&#41;](data-mining/content-types-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="aefbd-111">To learn about the different kinds of keys, see [Content Types &#40;Data Mining&#41;](data-mining/content-types-data-mining.md).</span></span>  
  
 <span data-ttu-id="aefbd-112">**Para obter mais informações:** [Estruturas de mineração &#40;Analysis Services – Mineração de dados&#41;](data-mining/mining-structures-analysis-services-data-mining.md), [Colunas do modelo de mineração](data-mining/mining-model-columns.md), [Assistente de Mineração de dados &#40;Analysis Services – Mineração de dados&#41;](data-mining/data-mining-wizard-analysis-services-data-mining.md) e [Criar uma estrutura de mineração relacional](data-mining/create-a-relational-mining-structure.md)</span><span class="sxs-lookup"><span data-stu-id="aefbd-112">**For More Information:** [Mining Structures &#40;Analysis Services - Data Mining&#41;](data-mining/mining-structures-analysis-services-data-mining.md), [Mining Model Columns](data-mining/mining-model-columns.md), [Data Mining Wizard &#40;Analysis Services - Data Mining&#41;](data-mining/data-mining-wizard-analysis-services-data-mining.md), [Create a Relational Mining Structure](data-mining/create-a-relational-mining-structure.md)</span></span>  
  
## <a name="options"></a><span data-ttu-id="aefbd-113">Opções</span><span class="sxs-lookup"><span data-stu-id="aefbd-113">Options</span></span>  
 <span data-ttu-id="aefbd-114">**Tabelas/Colunas**</span><span class="sxs-lookup"><span data-stu-id="aefbd-114">**Tables/Columns**</span></span>  
 <span data-ttu-id="aefbd-115">Exibe as tabelas e colunas que você selecionou na página anterior do assistente.</span><span class="sxs-lookup"><span data-stu-id="aefbd-115">Displays the tables and columns that you selected on the previous page of the wizard.</span></span>  
  
 **\<check box>**  
 <span data-ttu-id="aefbd-116">Selecione as colunas a serem incluídas na estrutura de mineração.</span><span class="sxs-lookup"><span data-stu-id="aefbd-116">Select the columns to include in the mining structure.</span></span>  
  
 <span data-ttu-id="aefbd-117">Se sua fonte de dados incluir tabelas aninhadas ou várias exibições, expanda a lista de colunas para exibir as tabelas aninhadas.</span><span class="sxs-lookup"><span data-stu-id="aefbd-117">If your data source includes nested tables or multiple views, expand the column list to view the nested tables.</span></span>  
  
 <span data-ttu-id="aefbd-118">**Chave**</span><span class="sxs-lookup"><span data-stu-id="aefbd-118">**Key**</span></span>  
 <span data-ttu-id="aefbd-119">Selecione para usar a coluna como um identificador exclusivo para os dados.</span><span class="sxs-lookup"><span data-stu-id="aefbd-119">Select to use the column as a unique identifier for the data.</span></span>  
  
 <span data-ttu-id="aefbd-120">Em uma tabela de casos, a chave normalmente é o identificador exclusivo.</span><span class="sxs-lookup"><span data-stu-id="aefbd-120">For a case table, the key is usually the unique identifier.</span></span>  
  
 <span data-ttu-id="aefbd-121">Na tabela aninhada, a **Chave** indica o identificador de uma linha no contexto do caso associado.</span><span class="sxs-lookup"><span data-stu-id="aefbd-121">For nested table, the **Key** indicates the identifier of a row in the context of the associated case.</span></span>  
  
 <span data-ttu-id="aefbd-122">**Entrada**</span><span class="sxs-lookup"><span data-stu-id="aefbd-122">**Input**</span></span>  
 <span data-ttu-id="aefbd-123">Selecione para usar a coluna ao criar previsões.</span><span class="sxs-lookup"><span data-stu-id="aefbd-123">Select to use the column in creating predictions.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="aefbd-124">Essa coluna só estará disponível quando você estiver criando um modelo de mineração com a estrutura de mineração.</span><span class="sxs-lookup"><span data-stu-id="aefbd-124">This column is only available when you are creating a mining model together with the mining structure.</span></span>  
  
 <span data-ttu-id="aefbd-125">**Previsível**</span><span class="sxs-lookup"><span data-stu-id="aefbd-125">**Predictable**</span></span>  
 <span data-ttu-id="aefbd-126">Selecione para habilitar a tabela ou a coluna a ser prevista com base na entrada futura adicional.</span><span class="sxs-lookup"><span data-stu-id="aefbd-126">Select to enable the table or column to be predicted based on additional future input.</span></span>  
  
 <span data-ttu-id="aefbd-127">Se você também marcar uma tabela aninhada como previsível, toda a tabela aninhada se tornará previsível.</span><span class="sxs-lookup"><span data-stu-id="aefbd-127">If you also mark a nested table as predictable, the whole nested table becomes predictable.</span></span> <span data-ttu-id="aefbd-128">Se não houver colunas marcadas na tabela aninhada como de entrada ou previsível, a tabela aninhada será exibida na estrutura de mineração, mas será ignorada no modelo.</span><span class="sxs-lookup"><span data-stu-id="aefbd-128">If no columns in the nested table are marked as input or predictable, the nested table will appear in the mining structure, but will be ignored in the model.</span></span>  
  
 <span data-ttu-id="aefbd-129">**Observação** Essa coluna só estará disponível quando você estiver criando um modelo de mineração com a estrutura de mineração.</span><span class="sxs-lookup"><span data-stu-id="aefbd-129">**Note** This column is only available when you are creating a mining model together with the mining structure.</span></span>  
  
 <span data-ttu-id="aefbd-130">**Sugerir**</span><span class="sxs-lookup"><span data-stu-id="aefbd-130">**Suggest**</span></span>  
 <span data-ttu-id="aefbd-131">Clique para abrir a caixa de diálogo **Sugerir Colunas Relacionadas** , que faz uma análise de uma amostra de dados para identificar colunas de entrada que mostram a relação maior com a coluna **Previsível** selecionada com base na entropia.</span><span class="sxs-lookup"><span data-stu-id="aefbd-131">Click to open the **Suggest Related Columns** dialog box, which performs an analysis on a sample of data to identify input columns that show the greatest relationship to the selected **Predictable** column based on entropy.</span></span> <span data-ttu-id="aefbd-132">Essa análise também se aplica a colunas de tabela aninhadas ou a estruturas de mineração baseadas em fontes OLAP.</span><span class="sxs-lookup"><span data-stu-id="aefbd-132">This analysis also applies to nested table columns or mining structures that are based on OLAP sources.</span></span>  
  
 <span data-ttu-id="aefbd-133">**Observação** Essa coluna só estará disponível quando você estiver criando um modelo de mineração com a estrutura de mineração.</span><span class="sxs-lookup"><span data-stu-id="aefbd-133">**Note** This column only available when you are creating a mining model together with the mining structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aefbd-134">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="aefbd-134">See Also</span></span>  
 <span data-ttu-id="aefbd-135">[Ajuda F1 do assistente de mineração de dados &#40;Analysis Services Data Mining&#41;](data-mining-wizard-f1-help-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="aefbd-135">[Data Mining Wizard F1 Help &#40;Analysis Services - Data Mining&#41;](data-mining-wizard-f1-help-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="aefbd-136">[Sugerir colunas relacionadas &#40;assistente de mineração de dados&#41;](suggest-related-columns-data-mining-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="aefbd-136">[Suggest Related Columns &#40;Data Mining Wizard&#41;](suggest-related-columns-data-mining-wizard.md) </span></span>  
 <span data-ttu-id="aefbd-137">[Especificar tipos de tabela &#40;assistente de mineração de dados&#41;](specify-table-types-data-mining-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="aefbd-137">[Specify Table Types &#40;Data Mining Wizard&#41;](specify-table-types-data-mining-wizard.md) </span></span>  
 [<span data-ttu-id="aefbd-138">Especifique o tipo de conteúdo e de dados da coluna &#40;assistente de mineração de dados&#41;</span><span class="sxs-lookup"><span data-stu-id="aefbd-138">Specify the Column's Content and Data Type &#40;Data Mining Wizard&#41;</span></span>](specify-the-column-s-content-and-data-type-data-mining-wizard.md)  
  
  
