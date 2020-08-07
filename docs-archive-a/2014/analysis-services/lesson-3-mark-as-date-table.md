---
title: 'Lição 4: marcar como tabela de data | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: c32cc336-b7d8-4122-9d62-4936344d2315
author: minewiskan
ms.author: owend
ms.openlocfilehash: c3ccc57d770d954e9523196d2393fa9dc2ada5b7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575433"
---
# <a name="lesson-4-mark-as-date-table"></a><span data-ttu-id="767c9-102">Lição 4: Marcar como Tabela de Data</span><span class="sxs-lookup"><span data-stu-id="767c9-102">Lesson 4: Mark as Date Table</span></span>
  <span data-ttu-id="767c9-103">Na lição 2: Adicionar Dados, você importou uma tabela de dimensão chamada DimDate.</span><span class="sxs-lookup"><span data-stu-id="767c9-103">In Lesson 2: Add Data, you imported a dimension table named DimDate.</span></span> <span data-ttu-id="767c9-104">Você renomeou a tabela DimDate, na Lição 3: Renomear Colunas, como simplesmente Data.</span><span class="sxs-lookup"><span data-stu-id="767c9-104">You then renamed the DimDate table, in Lesson 3: Rename Columns, to simply, Date.</span></span> <span data-ttu-id="767c9-105">Em seu modelo, essa tabela agora é chamada Date; ela também pode ser conhecida como uma *tabela Data*, pois contém dados de data e hora.</span><span class="sxs-lookup"><span data-stu-id="767c9-105">While in your model this table is now named Date, it can also be known as a *Date table*, in that it contains date and time data.</span></span>  
  
 <span data-ttu-id="767c9-106">Sempre que você usar funções de Inteligência de Dados Temporais em cálculos, como fará quando criar medidas mais adiante, especifique as propriedades da tabela de data, que inclui uma *tabela de Data* e uma *coluna de Data* de identificador exclusivo nessa tabela.</span><span class="sxs-lookup"><span data-stu-id="767c9-106">Whenever you use Time Intelligence functions in calculations, as you will do when you create measures a little later, you must specify date table properties, which include a *Date table* and a unique identifier *Date column* in that table.</span></span> <span data-ttu-id="767c9-107">Você pode criar relações válidas entre outras tabelas e a tabela de Data; necessário para cálculos que usam funções de inteligência de tempo DAX.</span><span class="sxs-lookup"><span data-stu-id="767c9-107">You can then create valid relationships between other tables and the Date table; necessary for calculations using DAX time intelligence functions.</span></span>  
  
 <span data-ttu-id="767c9-108">Nesta lição, você aprenderá a marcar a tabela de Data importada e renomeada como a *tabela de Data* e a coluna de Data (na tabela de Data) como a *coluna de Data* (identificador exclusivo).</span><span class="sxs-lookup"><span data-stu-id="767c9-108">In this lesson, you will mark the imported and renamed Date table as the *Date table* and the Date column (in the Date table) as the *Date column* (unique identifier).</span></span> <span data-ttu-id="767c9-109">Todo o uso da data de nome pode ser confuso, mas logo você terá a ideia.</span><span class="sxs-lookup"><span data-stu-id="767c9-109">All the use of the name Date can get kind of confusing, but you'll soon get the idea.</span></span>  
  
 <span data-ttu-id="767c9-110">Tempo estimado para concluir esta lição: **3 minutos**</span><span class="sxs-lookup"><span data-stu-id="767c9-110">Estimated time to complete this lesson: **3 minutes**</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="767c9-111">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="767c9-111">Prerequisites</span></span>  
 <span data-ttu-id="767c9-112">Este tópico faz parte de um tutorial de modelagem tabular, que deve ser concluído na devida ordem.</span><span class="sxs-lookup"><span data-stu-id="767c9-112">This topic is part of a tabular modeling tutorial, which should be completed in order.</span></span> <span data-ttu-id="767c9-113">Antes de executar as tarefas desta lição, você deverá ter concluído a lição anterior: [Lição 3: Renomear colunas](rename-columns.md).</span><span class="sxs-lookup"><span data-stu-id="767c9-113">Before performing the tasks in this lesson, you should have completed the previous lesson: [Lesson 3: Rename Columns](rename-columns.md).</span></span>  
  
### <a name="to-set-mark-as-date-table"></a><span data-ttu-id="767c9-114">Para definir Marcar Como Tabela de Data</span><span class="sxs-lookup"><span data-stu-id="767c9-114">To set Mark as Date Table</span></span>  
  
1.  <span data-ttu-id="767c9-115">No designer de modelos, clique na tabela **Data** (guia).</span><span class="sxs-lookup"><span data-stu-id="767c9-115">In the model designer, click the **Date** table (tab).</span></span>  
  
2.  <span data-ttu-id="767c9-116">Clique no menu **tabela** , clique em **Data**e, em seguida, clique em **Marcar como tabela de data**.</span><span class="sxs-lookup"><span data-stu-id="767c9-116">Click the **Table** menu, then click **Date**, and then click **Mark as Date Table**.</span></span>  
  
3.  <span data-ttu-id="767c9-117">Na caixa de diálogo **Marcar como Tabela de Data** , na caixa de listagem **Data** , selecione a coluna **Data** como o identificador exclusivo.</span><span class="sxs-lookup"><span data-stu-id="767c9-117">In the **Mark as Date Table** dialog box, in the **Date** listbox, select the **Date** column as the unique identifier.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="767c9-118">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="767c9-118">Next Steps</span></span>  
 <span data-ttu-id="767c9-119">Para continuar este tutorial, vá para a próxima lição: [Lição 5: Criar relações](lesson-4-create-relationships.md).</span><span class="sxs-lookup"><span data-stu-id="767c9-119">To continue this tutorial, go to the next lesson: [Lesson 5: Create Relationships](lesson-4-create-relationships.md).</span></span>  
  
  
