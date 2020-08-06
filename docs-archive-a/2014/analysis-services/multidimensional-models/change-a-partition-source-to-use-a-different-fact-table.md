---
title: Alterar uma origem de partição para usar uma tabela de fatos diferente | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- fact tables [Analysis Services]
- partitions [Analysis Services], fact tables
ms.assetid: 5508312f-8e46-4802-9362-6688ca03d098
author: minewiskan
ms.author: owend
ms.openlocfilehash: 0063a6023d769dc6dccd616655d10e0bd3c65a98
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683805"
---
# <a name="change-a-partition-source-to-use-a-different-fact-table"></a><span data-ttu-id="e2d6d-102">Alterar uma origem de partição para usar uma tabela de fatos diferente</span><span class="sxs-lookup"><span data-stu-id="e2d6d-102">Change a partition source to use a different fact table</span></span>
  <span data-ttu-id="e2d6d-103">Ao criar uma partição para um cubo, você pode optar por usar uma tabela de fatos diferente.</span><span class="sxs-lookup"><span data-stu-id="e2d6d-103">When you create a partition for a cube, you can choose to use a different fact table.</span></span> <span data-ttu-id="e2d6d-104">Tabelas diferentes podem ser derivadas de uma única exibição da fonte de dados, de exibições diferentes da fonte de dados ou de fontes de dados diferentes.</span><span class="sxs-lookup"><span data-stu-id="e2d6d-104">Different tables may be from a single data source view, from different data source views, or from different data sources.</span></span> <span data-ttu-id="e2d6d-105">Uma exibição da fonte de dados também pode conter tabelas diferentes de mais de uma fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="e2d6d-105">A data source view may also contain different tables from more than one data source.</span></span>  
  
 <span data-ttu-id="e2d6d-106">Todas as tabelas de fatos e dimensões das partições de um cubo devem ter a mesma estrutura da tabela de fatos e das dimensões do cubo.</span><span class="sxs-lookup"><span data-stu-id="e2d6d-106">All fact tables and dimensions for a cube's partitions must have the same structure as the fact table and dimensions of the cube.</span></span> <span data-ttu-id="e2d6d-107">Por exemplo, tabelas de fatos diferentes podem ter a mesma estrutura, mas conter dados de diferentes anos ou linhas de produtos.</span><span class="sxs-lookup"><span data-stu-id="e2d6d-107">For example, different fact tables can have the same structure but contain data for different years or different product lines.</span></span>  
  
 <span data-ttu-id="e2d6d-108">Especifique uma tabela de fatos na página **Especificar Informações sobre a Origem** do Assistente para Partições.</span><span class="sxs-lookup"><span data-stu-id="e2d6d-108">You specify a fact table on the **Specify Source Information** page of the Partition Wizard.</span></span> <span data-ttu-id="e2d6d-109">Nessa página, no grupo Origem da Partição próximo a **Examinar**, especifique uma fonte de dados ou a exibição da fonte de dados que deve ser examinada.</span><span class="sxs-lookup"><span data-stu-id="e2d6d-109">On this page, in the Partition Source group next to **Look in**, specify a data source or data source view in which to look.</span></span> <span data-ttu-id="e2d6d-110">Em seguida, clique em **Localizar Tabelas**e, em **Tabelas Disponíveis**, selecione a tabela que deseja usar.</span><span class="sxs-lookup"><span data-stu-id="e2d6d-110">Next, click **Find Tables**, and then, under **Available Tables**, select the table you want to use.</span></span>  
  
 <span data-ttu-id="e2d6d-111">Ao usar tabelas de fatos diferentes, verifique se nenhum dado está duplicado entre as partições.</span><span class="sxs-lookup"><span data-stu-id="e2d6d-111">When you use different fact tables, ensure that no data is duplicated among the partitions.</span></span> <span data-ttu-id="e2d6d-112">Por exemplo, se uma tabela de fatos contém apenas as transações de 2012 e outra tabela de fatos contém apenas as transações de 2013, essas tabelas contêm dados independentes.</span><span class="sxs-lookup"><span data-stu-id="e2d6d-112">For example, if one fact table contains transactions for 2012 only, and another fact table contains transactions for 2013 only, these tables contain independent data.</span></span> <span data-ttu-id="e2d6d-113">Do mesmo modo, tabelas de fatos para linhas de produtos ou áreas geográficas diferentes são independentes.</span><span class="sxs-lookup"><span data-stu-id="e2d6d-113">Similarly, fact tables for distinct product lines or distinct geographical areas are independent.</span></span>  
  
 <span data-ttu-id="e2d6d-114">É possível, mas não recomendado, usar tabelas de fatos diferentes que contêm dados duplicados.</span><span class="sxs-lookup"><span data-stu-id="e2d6d-114">It is possible, but not recommended, to use different fact tables that contain duplicated data.</span></span> <span data-ttu-id="e2d6d-115">Nesse caso, é necessário usar filtros nas partições para assegurar que os dados usados por uma partição não sejam usados por nenhuma outra.</span><span class="sxs-lookup"><span data-stu-id="e2d6d-115">In this case, you must use filters in the partitions to ensure that data used by one partition is not used by any other partition.</span></span> <span data-ttu-id="e2d6d-116">Para obter mais informações, consulte [Criar e gerenciar uma partição local &#40;Analysis Services&#41;](create-and-manage-a-local-partition-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="e2d6d-116">For more information, see [Create and Manage a Local Partition &#40;Analysis Services&#41;](create-and-manage-a-local-partition-analysis-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2d6d-117">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e2d6d-117">See Also</span></span>  
 [<span data-ttu-id="e2d6d-118">Criar e gerenciar uma partição local &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="e2d6d-118">Create and Manage a Local Partition &#40;Analysis Services&#41;</span></span>](create-and-manage-a-local-partition-analysis-services.md)  
  
  
