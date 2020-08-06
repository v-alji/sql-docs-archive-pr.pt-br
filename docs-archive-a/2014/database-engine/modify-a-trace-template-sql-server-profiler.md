---
title: Modificar um modelo de rastreamento (SQL Server Profiler) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- templates [SQL Server], traces
- trace templates [SQL Server]
- modifying traces
ms.assetid: b81df2a1-e202-43d8-92b0-0beb145f0116
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 2a93baedb1875ac740e74065ae7188f9b576e083
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570194"
---
# <a name="modify-a-trace-template-sql-server-profiler"></a><span data-ttu-id="c6b51-102">Modificar um modelo de rastreamento (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="c6b51-102">Modify a Trace Template (SQL Server Profiler)</span></span>
  <span data-ttu-id="c6b51-103">Este tópico descreve como modificar um modelo de rastreamento usando o [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c6b51-103">This topic describes how to modify a trace template by using [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)].</span></span>  
  
### <a name="to-modify-a-trace-template"></a><span data-ttu-id="c6b51-104">Para modificar um modelo de rastreamento</span><span class="sxs-lookup"><span data-stu-id="c6b51-104">To modify a trace template</span></span>  
  
1.  <span data-ttu-id="c6b51-105">No menu **Arquivo** , aponte para **Modelos**e clique em **Editar Modelo**.</span><span class="sxs-lookup"><span data-stu-id="c6b51-105">On the **File** menu, point to **Templates**, and then click **Edit Template**.</span></span>  
  
2.  <span data-ttu-id="c6b51-106">Na caixa de diálogo **Propriedades do Modelo de Rastreamento** , na guia **Geral** , você pode modificar o tipo de servidor e o nome do modelo ou optar por usar um modelo padrão para o tipo de servidor.</span><span class="sxs-lookup"><span data-stu-id="c6b51-106">In the **Trace Template Properties** dialog box, on the **General** tab, you can modify the server type and template name, or choose to use a default template for the server type.</span></span>  
  
3.  <span data-ttu-id="c6b51-107">Na guia **seleção de eventos**, use o controle de grade para adicionar ou remover eventos e colunas de dados do arquivo de rastreamento da seguinte maneira.</span><span class="sxs-lookup"><span data-stu-id="c6b51-107">On the **Events Selection**tab, use the grid control to add or remove events and data columns from the trace file as follows.</span></span>  
  
    -   <span data-ttu-id="c6b51-108">Para adicionar um evento, expanda a categoria de evento apropriada na coluna **Eventos** e selecione o nome do evento.</span><span class="sxs-lookup"><span data-stu-id="c6b51-108">To add an event, expand the appropriate event category in the **Events** column, and then select the event name.</span></span>  
  
    -   <span data-ttu-id="c6b51-109">Quando um evento é adicionado, todas as colunas de dados relevantes são incluídas, por padrão.</span><span class="sxs-lookup"><span data-stu-id="c6b51-109">When you add an event, all relevant data columns are included by default.</span></span> <span data-ttu-id="c6b51-110">Para remover uma coluna de dados de um evento do rastreamento, desmarque a caixa de seleção correspondente ao evento na coluna de dados.</span><span class="sxs-lookup"><span data-stu-id="c6b51-110">To remove a data column for an event from a trace, clear the check box in the data column for the event.</span></span>  
  
    -   <span data-ttu-id="c6b51-111">Para adicionar filtros, clique no nome de coluna de dados e especifique os critérios de filtro na caixa de diálogo **Editar Filtro** .</span><span class="sxs-lookup"><span data-stu-id="c6b51-111">To add filters, click the data column name and specify the filter criteria in the **Edit Filter** dialog box.</span></span> <span data-ttu-id="c6b51-112">Você também pode clicar com o botão direito do mouse no nome da coluna de dados e em **Editar Filtro de Coluna** para iniciar a caixa de diálogo **Editar Filtro** .</span><span class="sxs-lookup"><span data-stu-id="c6b51-112">You can also right-click the data column name, and click **Edit Column Filter** to launch the **Edit Filter** dialog box.</span></span> <span data-ttu-id="c6b51-113">Para adicionar o filtro, clique em **OK** .</span><span class="sxs-lookup"><span data-stu-id="c6b51-113">Click **OK** to add the filter.</span></span>  
  
4.  <span data-ttu-id="c6b51-114">Clique em **Salvar**ou em **Salvar Como**para salvar o modelo de rastreamento com outro nome.</span><span class="sxs-lookup"><span data-stu-id="c6b51-114">Click **Save**, or click **Save As**to save the trace template under another name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6b51-115">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c6b51-115">See Also</span></span>  
 <span data-ttu-id="c6b51-116">[Especificar eventos e colunas de dados para um arquivo de rastreamento &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/specify-events-and-data-columns-for-a-trace-file-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="c6b51-116">[Specify Events and Data Columns for a Trace File &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/specify-events-and-data-columns-for-a-trace-file-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="c6b51-117">[Derivar um modelo de um rastreamento em execução &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/derive-a-template-from-a-running-trace-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="c6b51-117">[Derive a Template from a Running Trace &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/derive-a-template-from-a-running-trace-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="c6b51-118">[Derivar um modelo de um arquivo ou de uma tabela de rastreamento &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/derive-a-template-from-a-trace-file-or-trace-table-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="c6b51-118">[Derive a Template from a Trace File or Trace Table &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/derive-a-template-from-a-trace-file-or-trace-table-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="c6b51-119">[Modelos e permissões do SQL Server Profiler](../tools/sql-server-profiler/sql-server-profiler-templates-and-permissions.md) </span><span class="sxs-lookup"><span data-stu-id="c6b51-119">[SQL Server Profiler Templates and Permissions](../tools/sql-server-profiler/sql-server-profiler-templates-and-permissions.md) </span></span>  
 [<span data-ttu-id="c6b51-120">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="c6b51-120">SQL Server Profiler</span></span>](../tools/sql-server-profiler/sql-server-profiler.md)  
  
  
