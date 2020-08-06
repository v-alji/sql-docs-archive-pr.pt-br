---
title: Filtrar eventos com base na hora de término do evento (SQL Server Profiler) | Microsoft Docs | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- event start times [SQL Server]
- filters [SQL Server], traces
- traces [SQL Server], filters
- traces [SQL Server], events
ms.assetid: e965579e-d006-41a3-89ec-cfd5398c67d2
author: stevestein
ms.author: sstein
ms.openlocfilehash: 7f652952ec6706580b876e3e9a20f96e62598f81
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684429"
---
# <a name="filter-events-based-on-the-event-start-time-sql-server-profiler"></a><span data-ttu-id="ff654-102">Filtrar eventos com base na hora de início do evento (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="ff654-102">Filter Events Based on the Event Start Time (SQL Server Profiler)</span></span>
  <span data-ttu-id="ff654-103">Este tópico descreve como filtrar eventos de rastreamento de acordo com a hora de início do evento, usando o [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ff654-103">This topic describes how to filter trace events based on the event start time by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>  
  
### <a name="to-filter-an-event-based-on-the-event-start-time"></a><span data-ttu-id="ff654-104">Para filtrar eventos com base na hora de início do evento</span><span class="sxs-lookup"><span data-stu-id="ff654-104">To filter an event based on the event start time</span></span>  
  
1.  <span data-ttu-id="ff654-105">No menu **Arquivo** , clique em **Novo Rastreamento**e conecte-se a uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ff654-105">On the **File** menu, click **New Trace**, and then connect to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
     <span data-ttu-id="ff654-106">A caixa de diálogo **Propriedades do Rastreamento**é exibida.</span><span class="sxs-lookup"><span data-stu-id="ff654-106">The **Trace Properties**dialog box appears.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ff654-107">Se a opção **Iniciar rastreamento imediatamente após estabelecer a conexão**estiver marcada, a caixa de diálogo **Propriedades do Rastreamento**não será exibida e o rastreamento será iniciado.</span><span class="sxs-lookup"><span data-stu-id="ff654-107">If **Start tracing immediately after making connection**is selected, the **Trace Properties**dialog box fails to appear, and the trace begins instead.</span></span> <span data-ttu-id="ff654-108">Para desabilitar essa configuração, no menu **Ferramentas**, clique em **Opções**e desmarque a caixa de seleção **Iniciar rastreamento imediatamente após estabelecer a conexão** .</span><span class="sxs-lookup"><span data-stu-id="ff654-108">To turn off this setting, on the **Tools**menu, click **Options**, and clear the **Start tracing immediately after making connection** check box.</span></span>  
  
2.  <span data-ttu-id="ff654-109">Na caixa **Nome do rastreamento** , digite um nome para o rastreamento.</span><span class="sxs-lookup"><span data-stu-id="ff654-109">In the **Trace name** box, type a name for the trace.</span></span>  
  
3.  <span data-ttu-id="ff654-110">Na lista de nomes **Usar o modelo**, selecione um modelo de rastreamento.</span><span class="sxs-lookup"><span data-stu-id="ff654-110">In the **Use the template**name list, select a trace template.</span></span>  
  
4.  <span data-ttu-id="ff654-111">Opcionalmente, especifique um destino para os resultados do rastreamento.</span><span class="sxs-lookup"><span data-stu-id="ff654-111">Optionally specify a destination for the trace results.</span></span>  
  
5.  <span data-ttu-id="ff654-112">Na guia **Seleção de Eventos**, clique no título de coluna **StartTime** .</span><span class="sxs-lookup"><span data-stu-id="ff654-112">On the **Events Selection**tab, click the **StartTime** column heading.</span></span> <span data-ttu-id="ff654-113">Você também pode clicar com o botão direito do mouse no título de coluna e clicar em **Editar Filtro de Coluna** para iniciar a caixa de diálogo **Editar Filtro** .</span><span class="sxs-lookup"><span data-stu-id="ff654-113">You can also right-click the column heading, and then click **Edit Column Filter** to launch the **Edit Filter** dialog box.</span></span>  
  
6.  <span data-ttu-id="ff654-114">Expanda **maior que** ou **menor que**e insira um `datetime` valor no campo que aparece abaixo do operador de comparação.</span><span class="sxs-lookup"><span data-stu-id="ff654-114">Expand **Greater than** or **Less than**, and then enter a `datetime` value in the field that appears beneath the comparison operator.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff654-115">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ff654-115">See Also</span></span>  
 [<span data-ttu-id="ff654-116">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="ff654-116">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
