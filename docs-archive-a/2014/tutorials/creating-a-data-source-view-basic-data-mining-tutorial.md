---
title: Criando uma exibição da fonte de dados (tutorial de mineração de dados básico) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: c1e68a88-0f82-415d-becc-78d180d4f845
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 4582845c905ef95601cbff2c810633f0cc901e3e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572290"
---
# <a name="creating-a-data-source-view-basic-data-mining-tutorial"></a><span data-ttu-id="50a31-102">Criando uma exibição da fonte de dados (Tutorial de mineração de dados básico)</span><span class="sxs-lookup"><span data-stu-id="50a31-102">Creating a Data Source View (Basic Data Mining Tutorial)</span></span>
  <span data-ttu-id="50a31-103">Uma exibição de fonte de dados é criada em uma fonte de dados e define um subconjunto dos dados, que você pode então usar em suas estruturas de mineração.</span><span class="sxs-lookup"><span data-stu-id="50a31-103">A data source view is built on a data source and defines a subset of the data, which you can then use in your mining structures.</span></span> <span data-ttu-id="50a31-104">Você também pode usar a exibição da fonte de dados para adicionar colunas, criar colunas calculadas e agregações, e adicionar exibições nomeadas.</span><span class="sxs-lookup"><span data-stu-id="50a31-104">You can also use the data source view to add columns, create calculated columns and aggregates, and add named views.</span></span> <span data-ttu-id="50a31-105">Usando as exibições de fonte de dados, você pode selecionar os dados que se relacionam ao seu projeto, estabelecer relações entre as tabelas e modificar a estrutura dos dados sem modificar a fonte de dados original.</span><span class="sxs-lookup"><span data-stu-id="50a31-105">By using data source views, you can select the data that relates to your project, establish relationships between tables, and modify the structure of the data, without modifying the original data source.</span></span> <span data-ttu-id="50a31-106">Para obter mais informações, consulte [Exibições de fontes de dados em modelos multidimensionais](https://docs.microsoft.com/analysis-services/multidimensional-models/data-source-views-in-multidimensional-models).</span><span class="sxs-lookup"><span data-stu-id="50a31-106">For more information, see [Data Source Views in Multidimensional Models](https://docs.microsoft.com/analysis-services/multidimensional-models/data-source-views-in-multidimensional-models).</span></span>  
  
### <a name="to-create-a-data-source-view"></a><span data-ttu-id="50a31-107">Para criar uma exibição da fonte de dados</span><span class="sxs-lookup"><span data-stu-id="50a31-107">To create a data source view</span></span>  
  
1.  <span data-ttu-id="50a31-108">Em **Gerenciador de soluções**, clique com o botão direito do mouse em **exibições da fonte de dados**e selecione **nova exibição da fonte de dados**.</span><span class="sxs-lookup"><span data-stu-id="50a31-108">In **Solution Explorer**, right-click **Data Source Views**, and select **New Data Source View**.</span></span>  
  
2.  <span data-ttu-id="50a31-109">Na página **Bem-vindo ao Assistente de Exibição da Fonte de Dados** , clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="50a31-109">On the **Welcome to the Data Source View Wizard** page, click **Next**.</span></span>  
  
3.  <span data-ttu-id="50a31-110">Na página **selecionar uma fonte de dados** , em **fontes de dados relacionais**, selecione a fonte de dados Adventure Works DW 2012 que você criou na última tarefa.</span><span class="sxs-lookup"><span data-stu-id="50a31-110">On the **Select a Data Source** page, under **Relational data sources**, select the Adventure Works DW 2012 data source that you created in the last task.</span></span> <span data-ttu-id="50a31-111">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="50a31-111">Click **Next**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="50a31-112">Se você quiser criar uma fonte de dados, clique com o botão direito do mouse em **fontes de dados** e clique em **nova fonte de dados** para iniciar o assistente de fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="50a31-112">If you want to create a data source, right-click **Data Sources** and then click **New Data Source** to start the Data Source Wizard.</span></span>  
  
4.  <span data-ttu-id="50a31-113">Na página **selecionar tabelas e exibições** , selecione os seguintes objetos e clique na seta para a direita para incluí-los na nova exibição da fonte de dados:</span><span class="sxs-lookup"><span data-stu-id="50a31-113">On the **Select Tables and Views** page, select the following objects, and then click the right arrow to include them in the new data source view:</span></span>  
  
    -   <span data-ttu-id="50a31-114">**ProspectiveBuyer (dbo)** -tabela de compradores de bicicletas potenciais</span><span class="sxs-lookup"><span data-stu-id="50a31-114">**ProspectiveBuyer (dbo)** - table of prospective bike buyers</span></span>  
  
    -   <span data-ttu-id="50a31-115">**vTargetMail (dbo)** -exibição de dados históricos sobre os compradores de bicicletas anteriores</span><span class="sxs-lookup"><span data-stu-id="50a31-115">**vTargetMail (dbo)** - view of historical data about past bike buyers</span></span>  
  
5.  <span data-ttu-id="50a31-116">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="50a31-116">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="50a31-117">Na página **concluindo o assistente** , por padrão, a exibição da fonte de dados é chamada Adventure Works DW 2012.</span><span class="sxs-lookup"><span data-stu-id="50a31-117">On the **Completing the Wizard** page, by default the data source view is named Adventure Works DW 2012.</span></span> <span data-ttu-id="50a31-118">Altere o nome para `Targeted Mailing` e clique em **concluir**.</span><span class="sxs-lookup"><span data-stu-id="50a31-118">Change the name to `Targeted Mailing`, and then click **Finish**.</span></span>  
  
     <span data-ttu-id="50a31-119">A nova exibição da fonte de dados é aberta na guia **endereçamento direcionado. dsv [Design]** .</span><span class="sxs-lookup"><span data-stu-id="50a31-119">The new data source view opens in the **Targeted Mailing.dsv [Design]** tab.</span></span>  
  
## <a name="previous-task-in-lesson"></a><span data-ttu-id="50a31-120">Tarefa anterior da lição</span><span class="sxs-lookup"><span data-stu-id="50a31-120">Previous Task in Lesson</span></span>  
 [<span data-ttu-id="50a31-121">Criando uma fonte de dados &#40;tutorial de mineração de dados básico&#41;</span><span class="sxs-lookup"><span data-stu-id="50a31-121">Creating a Data Source &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/creating-a-data-source-basic-data-mining-tutorial.md)  
  
## <a name="next-lesson"></a><span data-ttu-id="50a31-122">Próxima lição</span><span class="sxs-lookup"><span data-stu-id="50a31-122">Next Lesson</span></span>  
 [<span data-ttu-id="50a31-123">Lição 2: criando uma estrutura de endereçamento direcionada &#40;tutorial de mineração de dados básico&#41;</span><span class="sxs-lookup"><span data-stu-id="50a31-123">Lesson 2: Building a Targeted Mailing Structure &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-2-building-a-targeted-mailing-structure-basic-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="50a31-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="50a31-124">See Also</span></span>  
 [<span data-ttu-id="50a31-125">Como definir uma exibição da fonte de dados &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="50a31-125">Defining a Data Source View &#40;Analysis Services&#41;</span></span>](https://docs.microsoft.com/analysis-services/multidimensional-models/defining-a-data-source-view-analysis-services)  
  
  
