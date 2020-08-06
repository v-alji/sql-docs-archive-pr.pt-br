---
title: Filtrar SPIDs (IDs de processo do servidor) em um rastreamento (SQL Server Profiler) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- filters [SQL Server], traces
- filters [SQL Server], SPIDs
- traces [SQL Server], filters
ms.assetid: f5945c39-be6b-4632-91cb-92066c80e188
author: stevestein
ms.author: sstein
ms.openlocfilehash: 99ae7eac6f19bd942a04f97b0a7da580eadc9dbf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684427"
---
# <a name="filter-server-process-ids-spids-in-a-trace-sql-server-profiler"></a><span data-ttu-id="da460-102">Filtrar IDs de processo de servidor em um rastreamento (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="da460-102">Filter Server Process IDs (SPIDs) in a Trace (SQL Server Profiler)</span></span>
  <span data-ttu-id="da460-103">Este tópico descreve como filtrar identificadores de processo de servidor (SPIDs) em um rastreamento, usando o [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="da460-103">This topic describes how to filter server process identifiers (SPIDs) in a trace by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>  
  
### <a name="to-filter-system-ids-in-a-trace"></a><span data-ttu-id="da460-104">Para filtrar IDs de sistema em um rastreamento</span><span class="sxs-lookup"><span data-stu-id="da460-104">To filter system IDs in a trace</span></span>  
  
1.  <span data-ttu-id="da460-105">No menu **Arquivo** , clique em **Novo Rastreamento**e conecte a uma instância do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="da460-105">On the **File** menu, click **New Trace**, and then connect to an instance of SQL Server.</span></span>  
  
     <span data-ttu-id="da460-106">A caixa de diálogo **Propriedades do Rastreamento**é exibida.</span><span class="sxs-lookup"><span data-stu-id="da460-106">The **Trace Properties**dialog box appears.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="da460-107">Se **Iniciar rastreamento imediatamente após estabelecer a conexão**for selecionado, a caixa de diálogo **Propriedades do rastreamento**não será exibida e o rastreamento será iniciado em vez disso.</span><span class="sxs-lookup"><span data-stu-id="da460-107">if **Start tracing immediately after making connection**is selected, the **Trace Properties**dialog box fails to appear, and the trace begins instead.</span></span> <span data-ttu-id="da460-108">Para desabilitar essa configuração, no menu **Ferramentas**, clique em **Opções**e desmarque a caixa de seleção **Iniciar rastreamento imediatamente após estabelecer a conexão** .</span><span class="sxs-lookup"><span data-stu-id="da460-108">To turn off this setting, on the **Tools**menu, click **Options**, and clear the **Start tracing immediately after making connection** check box.</span></span>  
  
2.  <span data-ttu-id="da460-109">Na caixa **Nome do rastreamento** , digite um nome para o rastreamento.</span><span class="sxs-lookup"><span data-stu-id="da460-109">In the **Trace name** box, type a name for the trace.</span></span>  
  
3.  <span data-ttu-id="da460-110">Na lista de nomes **Usar o modelo**, selecione um modelo de rastreamento.</span><span class="sxs-lookup"><span data-stu-id="da460-110">In the **Use the template**name list, select a trace template.</span></span>  
  
4.  <span data-ttu-id="da460-111">Opcionalmente, especifique um arquivo ou tabela de destino onde os resultados do rastreamento serão salvos.</span><span class="sxs-lookup"><span data-stu-id="da460-111">Optionally, specify a destination file or table in which to save the trace results.</span></span>  
  
5.  <span data-ttu-id="da460-112">Na guia **Seleção de Eventos**, clique no título da coluna **SPID**para iniciar a caixa de diálogo **Editar Filtro** .</span><span class="sxs-lookup"><span data-stu-id="da460-112">On the **Events Selection**tab, click the **SPID**column heading to launch the **Edit Filter** dialog box.</span></span> <span data-ttu-id="da460-113">Você também pode clicar com o botão direito do mouse no título de coluna e selecionar **Editar Filtro de Coluna**.</span><span class="sxs-lookup"><span data-stu-id="da460-113">You can also right-click the column heading and choose **Edit Column Filter**.</span></span> <span data-ttu-id="da460-114">Se a coluna **SPID** não aparecer, marque a caixa **Mostrar todas as colunas** .</span><span class="sxs-lookup"><span data-stu-id="da460-114">If the **SPID** column does not appear, check the **Show all columns** box.</span></span>  
  
6.  <span data-ttu-id="da460-115">Na caixa de diálogo **Editar Filtro** , expanda o operador de comparação apropriado e insira um SPID como valor de comparação.</span><span class="sxs-lookup"><span data-stu-id="da460-115">In the **Edit Filter** dialog box, expand the appropriate comparison operator, and enter a SPID as a value for the comparison.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da460-116">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="da460-116">See Also</span></span>  
 [<span data-ttu-id="da460-117">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="da460-117">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
