---
title: 'Lição 2: criando uma estrutura de endereçamento direcionada (tutorial de mineração de dados básico) | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 9d0d6ceb-49b5-47c7-9ee6-464da43cc1f6
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 005baa09e802a9ffe98f87239070401f170ddfa9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568968"
---
# <a name="lesson-2-building-a-targeted-mailing-structure-basic-data-mining-tutorial"></a><span data-ttu-id="feb3a-102">Lição 2: Criando uma estrutura de mala direta (Tutorial de mineração de dados básico)</span><span class="sxs-lookup"><span data-stu-id="feb3a-102">Lesson 2: Building a Targeted Mailing Structure (Basic Data Mining Tutorial)</span></span>
  <span data-ttu-id="feb3a-103">O departamento de Marketing da [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] quer aumentar as vendas, tendo como foco clientes específicos para uma campanha de mala direta.</span><span class="sxs-lookup"><span data-stu-id="feb3a-103">The Marketing department of [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] wants to increase sales by targeting specific customers for a mailing campaign.</span></span> <span data-ttu-id="feb3a-104">O banco de dados da empresa contém uma lista de clientes anteriores e uma lista de novos clientes em potencial.</span><span class="sxs-lookup"><span data-stu-id="feb3a-104">The company's database contains a list of past customers and a list of potential new customers.</span></span> <span data-ttu-id="feb3a-105">Investigando os atributos de clientes anteriores, a empresa espera descobrir padrões que possam aplicar em clientes potenciais.</span><span class="sxs-lookup"><span data-stu-id="feb3a-105">By investigating the attributes of previous customers, the company hopes to discover patterns that they can then apply to potential customers.</span></span> <span data-ttu-id="feb3a-106">Por exemplo, eles podem usar as últimas tendências para prever quais clientes potenciais têm mais probabilidade de comprar uma bicicleta [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] ou criar segmentos de clientes para futuras campanhas de marketing.</span><span class="sxs-lookup"><span data-stu-id="feb3a-106">For example, they might use past trends to predict which potential customers are most likely to purchase a bike from [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)], or create customer segments for future marketing campaigns.</span></span>  
  
 <span data-ttu-id="feb3a-107">Nesta lição, você usará o **Assistente de mineração de dados** para criar a estrutura de endereçamento direcionada.</span><span class="sxs-lookup"><span data-stu-id="feb3a-107">In this lesson you will use the **Data Mining Wizard** to create the targeted mailing structure.</span></span> <span data-ttu-id="feb3a-108">Depois de concluir as tarefas nesta lição, você terá uma estrutura de mineração com um único modelo.</span><span class="sxs-lookup"><span data-stu-id="feb3a-108">After you complete the tasks in this lesson, you will have a mining structure with a single model.</span></span> <span data-ttu-id="feb3a-109">Como há muitas etapas e conceitos importantes envolvidos na criação de uma estrutura, dividimos o processo nas três tarefas a seguir:</span><span class="sxs-lookup"><span data-stu-id="feb3a-109">Because there are many steps and important concepts involved in creating a structure, we have separated this process into the following three tasks:</span></span>  
  
 [<span data-ttu-id="feb3a-110">Criando uma estrutura de modelo de mineração de mala direta direcionada &#40;tutorial de mineração de dados básico&#41;</span><span class="sxs-lookup"><span data-stu-id="feb3a-110">Creating a Targeted Mailing Mining Model Structure &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/creating-a-targeted-mailing-mining-model-structure-basic-data-mining-tutorial.md)  
  
 [<span data-ttu-id="feb3a-111">Especificando o tipo de dados e o tipo de conteúdo &#40;tutorial de mineração de dados básico&#41;</span><span class="sxs-lookup"><span data-stu-id="feb3a-111">Specifying the Data Type and Content Type &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/specifying-the-data-type-and-content-type-basic-data-mining-tutorial.md)  
  
 [<span data-ttu-id="feb3a-112">Especificação de um conjunto de dados de teste para a estrutura &#40;tutorial de mineração de dados básico&#41;</span><span class="sxs-lookup"><span data-stu-id="feb3a-112">Specifying a Testing Data Set for the Structure &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/specifying-a-testing-data-set-for-the-structure-basic-data-mining-tutorial.md)  
  
## <a name="first-task-in-lesson"></a><span data-ttu-id="feb3a-113">Primeira tarefa na lição</span><span class="sxs-lookup"><span data-stu-id="feb3a-113">First Task in Lesson</span></span>  
 [<span data-ttu-id="feb3a-114">Criando uma estrutura de modelo de mineração de mala direta direcionada &#40;tutorial de mineração de dados básico&#41;</span><span class="sxs-lookup"><span data-stu-id="feb3a-114">Creating a Targeted Mailing Mining Model Structure &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/creating-a-targeted-mailing-mining-model-structure-basic-data-mining-tutorial.md)  
  
## <a name="previous-lesson"></a><span data-ttu-id="feb3a-115">Lição anterior</span><span class="sxs-lookup"><span data-stu-id="feb3a-115">Previous Lesson</span></span>  
 [<span data-ttu-id="feb3a-116">Lição 1: preparando o Analysis Services de dados &#40;o tutorial básico de Data Mining&#41;</span><span class="sxs-lookup"><span data-stu-id="feb3a-116">Lesson 1: Preparing the Analysis Services Database &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-1-preparing-the-analysis-services-database-basic-data-mining-tutorial.md)  
  
## <a name="next--lesson"></a><span data-ttu-id="feb3a-117">Próxima lição</span><span class="sxs-lookup"><span data-stu-id="feb3a-117">Next  Lesson</span></span>  
 [<span data-ttu-id="feb3a-118">Lição 3: Adicionando e processando modelos</span><span class="sxs-lookup"><span data-stu-id="feb3a-118">Lesson 3: Adding and Processing Models</span></span>](../../2014/tutorials/lesson-3-adding-and-processing-models.md)  
  
## <a name="see-also"></a><span data-ttu-id="feb3a-119">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="feb3a-119">See Also</span></span>  
 <span data-ttu-id="feb3a-120">[Criar a estrutura de mineração de dados &#40;assistente de mineração de dados&#41;](../../2014/analysis-services/create-the-data-mining-structure-data-mining-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="feb3a-120">[Create the Data Mining Structure &#40;Data Mining Wizard&#41;](../../2014/analysis-services/create-the-data-mining-structure-data-mining-wizard.md) </span></span>  
 [<span data-ttu-id="feb3a-121">Criar uma estrutura de mineração relacional</span><span class="sxs-lookup"><span data-stu-id="feb3a-121">Create a Relational Mining Structure</span></span>](../../2014/analysis-services/data-mining/create-a-relational-mining-structure.md)  
  
  
