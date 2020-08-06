---
title: Criar uma nova estrutura de mineração relacional | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining structures [Analysis Services], relational
- mining structures [Analysis Services], creating
- relational mining models [Analysis Services]
ms.assetid: 55bac3bd-700e-4f91-bcc6-f3cd8c026da1
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2b41dd3ac2e6144011c1b3acde27c4b5829a1661
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570340"
---
# <a name="create-a-new-relational-mining-structure"></a><span data-ttu-id="2a2f2-102">Criar uma nova estrutura de mineração relacional</span><span class="sxs-lookup"><span data-stu-id="2a2f2-102">Create a New Relational Mining Structure</span></span>
  <span data-ttu-id="2a2f2-103">Use o assistente de mineração de dados para criar uma nova estrutura de mineração, usando dados de um banco de dado relacional ou outra fonte e, em seguida, salve a estrutura e todos os modelos relacionados em um [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] banco de dados.</span><span class="sxs-lookup"><span data-stu-id="2a2f2-103">Use the Data Mining Wizard to create a new mining structure, using data from a relational database or other source, and then save the structure and any related models to a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database.</span></span>  
  
### <a name="to-create-a-relational-mining-structure"></a><span data-ttu-id="2a2f2-104">Para criar uma estrutura de mineração relacional</span><span class="sxs-lookup"><span data-stu-id="2a2f2-104">To create a relational mining structure</span></span>  
  
1.  <span data-ttu-id="2a2f2-105">No gerenciador de soluções, clique com o botão direito do mouse na pasta **Estruturas de Mineração** no projeto de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] e depois clique em **Nova Estrutura de Mineração**.</span><span class="sxs-lookup"><span data-stu-id="2a2f2-105">In Solution Explorer, right-click the **Mining Structures** folder in an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project, and then click **New Mining Structure**.</span></span>  
  
     <span data-ttu-id="2a2f2-106">O Assistente de Mineração de Dados é exibido.</span><span class="sxs-lookup"><span data-stu-id="2a2f2-106">The Data Mining Wizard opens.</span></span>  
  
2.  <span data-ttu-id="2a2f2-107">Na página **Bem-vindo ao Assistente de Mineração de Dados** , clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="2a2f2-107">On the **Welcome to the Data Mining Wizard** page, click **Next**.</span></span>  
  
3.  <span data-ttu-id="2a2f2-108">Na página **Selecionar Método de Definição** , selecione **De banco de dados relacional ou data warehouse existente**e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="2a2f2-108">On the **Select the Definition Method** page, select **From existing relational database or data warehouse**, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="2a2f2-109">Na página **Selecionar Técnica de Mineração de Dados** , selecione o algoritmo de mineração de dados que deseja usar e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="2a2f2-109">On the **Select the Data Mining Technique** page, select the data mining algorithm that you want to use, and then click **Next**.</span></span>  
  
     <span data-ttu-id="2a2f2-110">Para obter mais informações sobre os algoritmos de mineração de dados, consulte [Algoritmos de mineração de dados &#40;Analysis Services – Mineração de dados&#41;](data-mining-algorithms-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="2a2f2-110">For more information about data mining algorithms, see [Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](data-mining-algorithms-analysis-services-data-mining.md).</span></span>  
  
5.  <span data-ttu-id="2a2f2-111">Na página **Selecionar a Exibição da Fonte de Dados** , em **Exibições de fonte de dados disponíveis**, clique na exibição da fonte de dados que deseja usar e, em seguida, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="2a2f2-111">On the **Select Data Source View** page, under **Available data source views**, click the data source view that you want to use, and then click **Next**.</span></span>  
  
     <span data-ttu-id="2a2f2-112">Para obter mais informações sobre exibições de fonte de dados, consulte [Exibições de Fonte de Dados em Modelos Multidimensionais](../multidimensional-models/data-source-views-in-multidimensional-models.md).</span><span class="sxs-lookup"><span data-stu-id="2a2f2-112">For more information about creating a data source view, see [Data Source Views in Multidimensional Models](../multidimensional-models/data-source-views-in-multidimensional-models.md).</span></span>  
  
6.  <span data-ttu-id="2a2f2-113">Na página **Especificar Tipos de Tabelas** , em **Tabelas de entrada**, selecione uma tabela de casos e uma tabela aninhada.</span><span class="sxs-lookup"><span data-stu-id="2a2f2-113">On the **Specify Table Types** page, under **Input tables**, select a case table and a nested table.</span></span>  
  
7.  <span data-ttu-id="2a2f2-114">Na página **Especificar os Dados de Treinamento** , em **Estrutura de modelo de mineração**, selecione as colunas de chave, de entrada e as colunas previsíveis.</span><span class="sxs-lookup"><span data-stu-id="2a2f2-114">On the **Specify the Training Data** page, under **Mining model structure**, select the key, input, and predictable columns.</span></span>  
  
     <span data-ttu-id="2a2f2-115">Depois de selecionar a coluna previsível, você pode clicar no botão **Sugerir** para abrir a caixa de diálogo **Sugerir Colunas Relacionadas** .</span><span class="sxs-lookup"><span data-stu-id="2a2f2-115">After you select the predictable column, you can click the **Suggest** button to open the **Suggest Related Columns** dialog box.</span></span> <span data-ttu-id="2a2f2-116">Você pode aceitar as colunas sugeridas clicando em **OK** nessa caixa de diálogo, para incluir as colunas selecionadas na estrutura de mineração ou pode alterar as seleções na coluna **Entrada** primeiro e, em seguida, clicar em **OK**.</span><span class="sxs-lookup"><span data-stu-id="2a2f2-116">You can accept the suggested columns by clicking **OK** in this dialog box to include the selected columns in the mining structure, or you can change the selections in the **Input** column first, and then click **OK**.</span></span> <span data-ttu-id="2a2f2-117">Para ignorar as sugestões, clique em **Cancelar**.</span><span class="sxs-lookup"><span data-stu-id="2a2f2-117">To ignore the suggestions, click **Cancel**.</span></span>  
  
8.  <span data-ttu-id="2a2f2-118">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="2a2f2-118">Click **Next**.</span></span>  
  
9. <span data-ttu-id="2a2f2-119">Na página **Especificar Conteúdo e Tipos de Dados das Colunas** , em **Estrutura de modelo de mineração**, você pode ajustar o tipo de conteúdo e o tipo de dados para cada coluna.</span><span class="sxs-lookup"><span data-stu-id="2a2f2-119">On the **Specify Columns' Content and Data Type** page, under **Mining model structure**, you can adjust the content type and data type for each column.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="2a2f2-120">Você pode clicar em **Detectar** para detectar automaticamente se uma coluna contém dados contínuos ou distintos.</span><span class="sxs-lookup"><span data-stu-id="2a2f2-120">You can click **Detect** to automatically detect whether a column contains continuous or discrete data.</span></span> <span data-ttu-id="2a2f2-121">Depois de clicar nesse botão, o conteúdo e os tipos de dados da coluna serão atualizado nas colunas **Tipo de Conteúdo** e **Tipo de Dados** .</span><span class="sxs-lookup"><span data-stu-id="2a2f2-121">After you click this button, the column content and data types will be updated in the **Content Type** and **Data Type** columns.</span></span> <span data-ttu-id="2a2f2-122">Para obter mais informações sobre tipos de conteúdo e de dados, consulte [Tipos de conteúdo &#40;Mineração de dados&#41;](content-types-data-mining.md) e [Tipos de dados &#40;Mineração de dados&#41;](data-types-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="2a2f2-122">For more information about content types and data types, see [Content Types &#40;Data Mining&#41;](content-types-data-mining.md) and [Data Types &#40;Data Mining&#41;](data-types-data-mining.md).</span></span>  
  
10. <span data-ttu-id="2a2f2-123">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="2a2f2-123">Click **Next**.</span></span>  
  
11. <span data-ttu-id="2a2f2-124">Na página **Concluindo o Assistente** , forneça um nome para a estrutura de mineração e o modelo de mineração inicial correspondente a ser criado e, em seguida, clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="2a2f2-124">On the **Completing the Wizard** page, provide a name for the mining structure and the related initial mining model that will be created, and then click **Finish**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a2f2-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2a2f2-125">See Also</span></span>  
 [<span data-ttu-id="2a2f2-126">Tarefas e instruções da estrutura de mineração</span><span class="sxs-lookup"><span data-stu-id="2a2f2-126">Mining Structure Tasks and How-tos</span></span>](mining-structure-tasks-and-how-tos.md)  
  
  
