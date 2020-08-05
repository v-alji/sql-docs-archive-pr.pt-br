---
title: Análise de fluxo de dados | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 5654cb30-cad2-470c-97b3-59cb331033e5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 184b53d3e982cd80d7c9c0909538a751585ae21d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571532"
---
# <a name="analysis-of-data-flow"></a><span data-ttu-id="8a36b-102">Análise do Fluxo de Dados</span><span class="sxs-lookup"><span data-stu-id="8a36b-102">Analysis of Data Flow</span></span>
  <span data-ttu-id="8a36b-103">Você pode usar o modo de exibição de banco de dados [catalog.execution_data_statistics](../relational-databases/statistics/statistics.md) `SSISDB` para analisar o fluxo de dado dos pacotes.</span><span class="sxs-lookup"><span data-stu-id="8a36b-103">You can use the [catalog.execution_data_statistics](../relational-databases/statistics/statistics.md)`SSISDB` database view to analyze the data flow of packages.</span></span> <span data-ttu-id="8a36b-104">Esta exibição exibe uma linha a cada vez que um componente de fluxo de dados envia dados a um componente downstream.</span><span class="sxs-lookup"><span data-stu-id="8a36b-104">This view displays a row each time a data flow component sends data to a downstream component.</span></span> <span data-ttu-id="8a36b-105">As informações podem ser usadas para obter um entendimento mais profundo das linhas que são enviadas para cada componente.</span><span class="sxs-lookup"><span data-stu-id="8a36b-105">The information can be used to gain a deeper understanding of the rows that are sent to each component.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8a36b-106">O nível de log deve ser definido para **Detalhado** para capturar as informações com a exibição de catalog.execution_data_statistics.</span><span class="sxs-lookup"><span data-stu-id="8a36b-106">The logging level must be set to **Verbose** in order to capture information with the catalog.execution_data_statistics view.</span></span>  
  
 <span data-ttu-id="8a36b-107">O exemplo a seguir exibe o número de linhas enviadas entre componentes de um pacote.</span><span class="sxs-lookup"><span data-stu-id="8a36b-107">The following example displays the number of rows sent between components of a package.</span></span>  
  
```  
use SSISDB  
select package_name, task_name, source_component_name, destination_component_name, rows_sent  
from catalog.execution_data_statistics  
where execution_id = 132  
order by source_component_name, destination_component_name  
  
```  
  
 <span data-ttu-id="8a36b-108">O exemplo a seguir calcula o número de linhas por milissegundo enviadas por cada componente para uma execução específica.</span><span class="sxs-lookup"><span data-stu-id="8a36b-108">The following example calculates the number of rows per millisecond sent by each component for a specific execution.</span></span> <span data-ttu-id="8a36b-109">Os valores calculados são:</span><span class="sxs-lookup"><span data-stu-id="8a36b-109">The calculated values are:</span></span>  
  
-   <span data-ttu-id="8a36b-110">**total_rows** – a soma de todas as linhas enviadas pelo componente</span><span class="sxs-lookup"><span data-stu-id="8a36b-110">**total_rows** - the sum of all the rows sent by the component</span></span>  
  
-   <span data-ttu-id="8a36b-111">**wall_clock_time_ms** – o tempo de execução decorrido total, em milissegundos, para cada componente</span><span class="sxs-lookup"><span data-stu-id="8a36b-111">**wall_clock_time_ms** - the total elapsed execution time, in milliseconds, for each component</span></span>  
  
-   <span data-ttu-id="8a36b-112">**num_rows_per_millisecond** – o número de linhas por milissegundo enviadas por cada componente</span><span class="sxs-lookup"><span data-stu-id="8a36b-112">**num_rows_per_millisecond** - the number of rows per millisecond sent by each component</span></span>  
  
 <span data-ttu-id="8a36b-113">A `HAVING` cláusula é usada para evitar um erro de divisão por zero nos cálculos.</span><span class="sxs-lookup"><span data-stu-id="8a36b-113">The `HAVING` clause is used to prevent a divide-by-zero error in the calculations.</span></span>  
  
```  
use SSISDB  
select source_component_name, destination_component_name,  
    sum(rows_sent) as total_rows,  
    DATEDIFF(ms,min(created_time),max(created_time)) as wall_clock_time_ms,  
    ((0.0+sum(rows_sent)) / (datediff(ms,min(created_time),max(created_time)))) as [num_rows_per_millisecond]  
from [catalog].[execution_data_statistics]  
where execution_id = 132  
group by source_component_name, destination_component_name  
having (datediff(ms,min(created_time),max(created_time))) > 0  
order by source_component_name desc  
  
```  
  
## <a name="related-tasks"></a><span data-ttu-id="8a36b-114">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="8a36b-114">Related Tasks</span></span>  
 [<span data-ttu-id="8a36b-115">Depurar o fluxo de dados</span><span class="sxs-lookup"><span data-stu-id="8a36b-115">Debugging Data Flow</span></span>](troubleshooting/debugging-data-flow.md)  
  
 [<span data-ttu-id="8a36b-116">Ferramentas de solução de problemas de execução de pacote</span><span class="sxs-lookup"><span data-stu-id="8a36b-116">Troubleshooting Tools for Package Execution</span></span>](troubleshooting/troubleshooting-tools-for-package-execution.md)  
  
## <a name="see-also"></a><span data-ttu-id="8a36b-117">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8a36b-117">See Also</span></span>  
 [<span data-ttu-id="8a36b-118">Dados em fluxos de dados</span><span class="sxs-lookup"><span data-stu-id="8a36b-118">Data in Data Flows</span></span>](data-flow/data-in-data-flows.md)  
  
  
