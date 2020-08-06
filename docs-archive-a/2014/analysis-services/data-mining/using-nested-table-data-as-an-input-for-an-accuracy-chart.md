---
title: Usando dados de tabela aninhada como uma entrada para um gráfico de precisão | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Mining Accuracy Chart [Analysis Services], nested tables
- Mining Accuracy Chart [Analysis Services], input tables
- nested tables
- adding nested tables
ms.assetid: 162e0686-ada3-4dd3-9151-9589926e6613
author: minewiskan
ms.author: owend
ms.openlocfilehash: 97d5bbd75d09b1a9e4276c4723ad6986dbabf9e4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568880"
---
# <a name="using-nested-table-data-as-an-input-for-an-accuracy-chart"></a><span data-ttu-id="dce23-102">Usando dados de uma tabela aninhada como entrada para um gráfico de precisão</span><span class="sxs-lookup"><span data-stu-id="dce23-102">Using Nested Table Data as an Input for an Accuracy Chart</span></span>
  <span data-ttu-id="dce23-103">Quando você testar a precisão de um modelo de mineração usando dados externos, se o modelo de mineração contiver tabelas aninhadas, os dados externos também deverão contar uma tabela de casos e uma tabela aninhada associada.</span><span class="sxs-lookup"><span data-stu-id="dce23-103">When you test the accuracy of a mining model by using external data, if the mining model contains nested tables, the external data must also contain a case table and an associated nested table.</span></span>  
  
 <span data-ttu-id="dce23-104">Este tópico descreve como trabalhar com tabelas aninhadas usadas para testar modelos, como mapear tabelas de casos e aninhadas no modo e nos dados externos e como aplicar um filtro a uma tabela aninhada.</span><span class="sxs-lookup"><span data-stu-id="dce23-104">This topic describes how to work with nested tables used for model testing, how to map nested and case tables in the mode and in the external data, and how to apply a filter to a nested table.</span></span>  
  
 <span data-ttu-id="dce23-105">Ao trabalhar com tabelas aninhadas, lembre-se destas dicas:</span><span class="sxs-lookup"><span data-stu-id="dce23-105">When working with nested tables, keep in mind these tips:</span></span>  
  
-   <span data-ttu-id="dce23-106">Se você selecionar a opção **Usar casos de teste do modelo de mineração** ou **Usar casos de teste da estrutura de mineração**, não será necessário especificar uma tabela de casos ou aninhada.</span><span class="sxs-lookup"><span data-stu-id="dce23-106">If you select the option **Use mining model test cases** or **Use mining structure test cases**, you do not need to specify a case table or nested table.</span></span> <span data-ttu-id="dce23-107">Com essas opções, a definição dos dados de teste é armazenada na estrutura de mineração e os dados de teste serão selecionados automaticamente quando você criar o gráfico de precisão.</span><span class="sxs-lookup"><span data-stu-id="dce23-107">With those options, the definition of the test data is stored in the mining structure and the test data is automatically selected when you create the accuracy chart.</span></span>  
  
-   <span data-ttu-id="dce23-108">Se já existir uma relação entre a tabela de caso e a tabela aninhada na fonte de dados, as colunas da estrutura de mineração serão mapeadas automaticamente para as colunas que têm o mesmo nome na tabela de entrada.</span><span class="sxs-lookup"><span data-stu-id="dce23-108">If a relationship already exists between the case and nested table in the data source, the columns in the mining structure are automatically mapped to the columns that have the same name in the input table.</span></span>  
  
-   <span data-ttu-id="dce23-109">Não será possível selecionar uma tabela aninhada até que você especifique a tabela de casos.</span><span class="sxs-lookup"><span data-stu-id="dce23-109">You cannot select a nested table until you have specified the case table.</span></span> <span data-ttu-id="dce23-110">Além disso, você não pode especificar uma tabela aninhada como uma entrada, a menos que o modelo de mineração também use uma estrutura de tabela de casos e tabela aninhada.</span><span class="sxs-lookup"><span data-stu-id="dce23-110">Also, you cannot specify a nested table as an input unless the mining model also uses a case table and nested table structure.</span></span>  
  
### <a name="use-a-nested-table-as-input-to-an-accuracy-chart"></a><span data-ttu-id="dce23-111">Usar uma tabela aninhada como entrada para um gráfico de precisão</span><span class="sxs-lookup"><span data-stu-id="dce23-111">Use a nested table as input to an accuracy chart</span></span>  
  
1.  <span data-ttu-id="dce23-112">Clique duas vezes na estrutura de mineração para abri-la no Designer de Mineração de Dados.</span><span class="sxs-lookup"><span data-stu-id="dce23-112">Double-click the mining structure to open it in Data Mining Designer.</span></span>  
  
2.  <span data-ttu-id="dce23-113">Selecione a guia **Gráfico de Precisão da Mineração** e, em seguida, selecione a guia **Seleção de Entrada** .</span><span class="sxs-lookup"><span data-stu-id="dce23-113">Select the **Mining Accuracy Chart** tab, and then select the **Input Selection** tab.</span></span>  
  
3.  <span data-ttu-id="dce23-114">Em **Selecionar conjunto de dados a ser usado para o Gráfico de Precisão**, selecione a opção **Especificar um conjunto de dados diferente**.</span><span class="sxs-lookup"><span data-stu-id="dce23-114">In **Select data set to be used for accuracy chart**, select the option **Specify a different data set**.</span></span>  
  
4.  <span data-ttu-id="dce23-115">Clique no botão procurar **(...)** para escolher o conjunto de dados externos em uma lista de exibições da fonte de dados no servidor atual.</span><span class="sxs-lookup"><span data-stu-id="dce23-115">Click the browse button **(...)** to choose the external data set from a list of data source views on the current server.</span></span>  
  
5.  <span data-ttu-id="dce23-116">Clique em **Selecionar Tabela de Casos**.</span><span class="sxs-lookup"><span data-stu-id="dce23-116">Click **Select Case Table**.</span></span> <span data-ttu-id="dce23-117">Na caixa de diálogo **Selecionar Tabela** , escolha a tabela na exibição da fonte de dados que contém os dados do caso e, em seguida, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="dce23-117">In the **Select Table** dialog box, choose the table from the data source view that contains the case data, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="dce23-118">Clique em **Selecionar Tabela Aninhada**.</span><span class="sxs-lookup"><span data-stu-id="dce23-118">Click **Select Nested Table**.</span></span> <span data-ttu-id="dce23-119">Na caixa de diálogo **Selecionar Tabela** , selecione a tabela que contém os dados aninhados e, em seguida, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="dce23-119">In the **Select Table** dialog box, select the table that contains the nested data, and then click **OK**.</span></span>  
  
7.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
     <span data-ttu-id="dce23-120">Se você precisar modificar a relação entre a tabela aninhada e a tabela de casos, clique em **Modificar Junção** para abrir a caixa de diálogo **Criar Relação** .</span><span class="sxs-lookup"><span data-stu-id="dce23-120">If you need to modify the relationship between the nested table and the case table, click **Modify Join** to open the **Create Relationship** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dce23-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="dce23-121">See Also</span></span>  
 <span data-ttu-id="dce23-122">[Escolher e mapear dados de teste de modelo](choose-and-map-model-testing-data.md) </span><span class="sxs-lookup"><span data-stu-id="dce23-122">[Choose and Map Model Testing Data](choose-and-map-model-testing-data.md) </span></span>  
 [<span data-ttu-id="dce23-123">Aplicar filtros a dados de testes de modelo</span><span class="sxs-lookup"><span data-stu-id="dce23-123">Apply Filters to Model Testing Data</span></span>](apply-filters-to-model-testing-data.md)  
  
  
