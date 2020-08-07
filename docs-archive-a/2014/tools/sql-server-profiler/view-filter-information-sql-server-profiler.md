---
title: Exibir informações de filtro (SQL Server Profiler) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- displaying filter information
- filters [SQL Server], viewing
- filters [SQL Server], traces
- traces [SQL Server], filters
- viewing filter information
ms.assetid: 8d002dea-376a-452c-b3ca-3e93656ed75f
author: stevestein
ms.author: sstein
ms.openlocfilehash: 931b83f8087d446cfc7b08d9582cbad5b02cf671
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571740"
---
# <a name="view-filter-information-sql-server-profiler"></a><span data-ttu-id="39f72-102">Exibir informações de filtro (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="39f72-102">View Filter Information (SQL Server Profiler)</span></span>
  <span data-ttu-id="39f72-103">Este tópico descreve como exibir filtros em colunas de dados de classes de evento, usando o [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="39f72-103">This topic describes how to view filters on data columns for event classes by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>  
  
### <a name="to-view-filter-information"></a><span data-ttu-id="39f72-104">Para exibir informações de filtro</span><span class="sxs-lookup"><span data-stu-id="39f72-104">To view filter information</span></span>  
  
1.  <span data-ttu-id="39f72-105">Abra um arquivo de rastreamento, tabela de rastreamento ou um script SQL e, no menu **Arquivo** , clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="39f72-105">Open a trace file, trace table, or SQL script, and on the **File** menu, click **Properties**.</span></span> <span data-ttu-id="39f72-106">Se você estiver editando um modelo de rastreamento ou criando um rastreamento novo, ignore esta etapa.</span><span class="sxs-lookup"><span data-stu-id="39f72-106">If you are editing a trace template or creating a new trace, skip this step.</span></span>  
  
2.  <span data-ttu-id="39f72-107">Na guia **Seleção de Eventos** , clique com o botão direito do mouse no nome da coluna de dados do filtro que deseja exibir e clique em **Editar Filtro de Coluna**.</span><span class="sxs-lookup"><span data-stu-id="39f72-107">On the **Events Selection** tab, right-click the data column name for the filter you want to view, and click **Edit Column Filter**.</span></span>  
  
3.  <span data-ttu-id="39f72-108">Na caixa de diálogo **Editar Filtro** , expanda os operadores de comparação de filtro para consultar o valor atribuído ao critério especificado.</span><span class="sxs-lookup"><span data-stu-id="39f72-108">In the **Edit Filter** dialog box, expand the filter comparison operators to see the assigned value for the specified criterion.</span></span> <span data-ttu-id="39f72-109">Repita as Etapas 2 e 3 para todas as colunas cujas informações de filtro quiser visualizar.</span><span class="sxs-lookup"><span data-stu-id="39f72-109">Repeat Steps 2 and 3 for all columns for which you want to view filter information.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="39f72-110">Operadores de comparação que já têm valores atribuídos são formatados em negrito.</span><span class="sxs-lookup"><span data-stu-id="39f72-110">Comparison operators with assigned values are formatted bold.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39f72-111">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="39f72-111">See Also</span></span>  
 [<span data-ttu-id="39f72-112">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="39f72-112">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
