---
title: Alterar o valor de tempo limite para consultas de mineração de dados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- time-out
ms.assetid: f1add4bc-e882-440a-a98b-333cfa274c3e
author: minewiskan
ms.author: owend
ms.openlocfilehash: 9dcdcdcbb6e2aef48dd8725f10f38180c73f5f6c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575465"
---
# <a name="change-the-time-out-value-for-data-mining-queries"></a><span data-ttu-id="46e46-102">Alterar o valor do tempo limite de consultas de mineração de dados</span><span class="sxs-lookup"><span data-stu-id="46e46-102">Change the Time-out Value for Data Mining Queries</span></span>
  <span data-ttu-id="46e46-103">Às vezes, quando é criado um gráfico de comparação de precisão ou é executada uma consulta de previsão, a geração de todos os dados necessários para a previsão pode demorar.</span><span class="sxs-lookup"><span data-stu-id="46e46-103">When you build a lift chart or execute a prediction query, sometimes it can take a long time to generate all the data required for the prediction.</span></span> <span data-ttu-id="46e46-104">Para evitar que o tempo limite da consulta seja ultrapassado, você pode alterar o valor que controla o tempo em que o servidor [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] permanecerá em espera para concluir uma consulta.</span><span class="sxs-lookup"><span data-stu-id="46e46-104">To prevent the query from timing out, you can change the value that controls how long the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] server waits to complete a query.</span></span>  
  
 <span data-ttu-id="46e46-105">O valor padrão é 15, porém se seus modelos são complexos ou se a fonte de dados for muito grande, este valor poderá ser insuficiente.</span><span class="sxs-lookup"><span data-stu-id="46e46-105">The default value is 15; however, if your models are complex or the data source is large, this might not be enough.</span></span> <span data-ttu-id="46e46-106">Se necessário, você pode aumentar o valor o bastante para permitir tempo suficiente para o processamento.</span><span class="sxs-lookup"><span data-stu-id="46e46-106">If necessary, you can increase the value significantly, to enable enough time for processing.</span></span> <span data-ttu-id="46e46-107">Por exemplo, se você definir o **Tempo Limite da Consulta** como 600, a consulta poderá continuar em execução por até 10 minutos.</span><span class="sxs-lookup"><span data-stu-id="46e46-107">For example, if you set **Query Timeout** to 600, the query could continue to run for up to 10 minutes.</span></span>  
  
 <span data-ttu-id="46e46-108">Para obter mais informações sobre consultas de previsão, consulte [Tarefas e instruções de consulta de Data Mining](data-mining-query-tasks-and-how-tos.md).</span><span class="sxs-lookup"><span data-stu-id="46e46-108">For more information about prediction queries, see [Data Mining Query Tasks and How-tos](data-mining-query-tasks-and-how-tos.md).</span></span>  
  
### <a name="configure-the-time-out-value-for-data-mining-queries"></a><span data-ttu-id="46e46-109">Configure o valor do tempo limite de consultas de mineração de dados</span><span class="sxs-lookup"><span data-stu-id="46e46-109">Configure the time-out value for data mining queries</span></span>  
  
1.  <span data-ttu-id="46e46-110">Em [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], no menu **Ferramentas** , selecione **Opções**.</span><span class="sxs-lookup"><span data-stu-id="46e46-110">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], from the **Tools** menu, selection **Options**.</span></span>  
  
2.  <span data-ttu-id="46e46-111">No painel **Opções** , abra **Designers do Business Intelligence**.</span><span class="sxs-lookup"><span data-stu-id="46e46-111">In the **Options** pane, expand **Business Intelligence Designers**.</span></span>  
  
3.  <span data-ttu-id="46e46-112">Clique na caixa de texto **Tempo Limite da Consulta** e digite um valor para a quantidade de segundos.</span><span class="sxs-lookup"><span data-stu-id="46e46-112">Click the **Query Timeout** text box, and type a value for the number of seconds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46e46-113">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="46e46-113">See Also</span></span>  
 <span data-ttu-id="46e46-114">[Tarefas e instruções de consulta de mineração de dados](data-mining-query-tasks-and-how-tos.md) </span><span class="sxs-lookup"><span data-stu-id="46e46-114">[Data Mining Query Tasks and How-tos](data-mining-query-tasks-and-how-tos.md) </span></span>  
 [<span data-ttu-id="46e46-115">Consultas de mineração de dados</span><span class="sxs-lookup"><span data-stu-id="46e46-115">Data Mining Queries</span></span>](data-mining-queries.md)  
  
  
