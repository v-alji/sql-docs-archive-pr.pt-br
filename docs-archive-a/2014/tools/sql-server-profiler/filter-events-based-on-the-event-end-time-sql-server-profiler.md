---
title: Filtrar eventos com base na hora de término do evento (SQL Server Profiler) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- event end times [SQL Server]
- filters [SQL Server], traces
- traces [SQL Server], filters
- traces [SQL Server], events
ms.assetid: 74628f9e-2d39-496a-a443-0a3887db223d
author: stevestein
ms.author: sstein
ms.openlocfilehash: d25d8e1adbd95f48d88fd1516c48dcc0f8374a7c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685391"
---
# <a name="filter-events-based-on-the-event-end-time-sql-server-profiler"></a><span data-ttu-id="26e01-102">Filtrar eventos com base na hora de término do evento (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="26e01-102">Filter Events Based on the Event End Time (SQL Server Profiler)</span></span>
  <span data-ttu-id="26e01-103">Este tópico descreve como filtrar eventos de rastreamento de acordo com a hora de término do evento, usando o [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="26e01-103">This topic describes how to filter trace events based on the event ending time by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>  
  
### <a name="to-filter-events-based-on-the-event-end-time"></a><span data-ttu-id="26e01-104">Para filtrar eventos com base na hora de término do evento</span><span class="sxs-lookup"><span data-stu-id="26e01-104">To filter events based on the event end time</span></span>  
  
1.  <span data-ttu-id="26e01-105">No menu **Arquivo** , clique em **Novo Rastreamento**e conecte-se a uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="26e01-105">On the **File** menu, click **New Trace**, and then connect to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
     <span data-ttu-id="26e01-106">A caixa de diálogo **Propriedades do Rastreamento**é exibida.</span><span class="sxs-lookup"><span data-stu-id="26e01-106">The **Trace Properties**dialog box appears.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="26e01-107">Se **Iniciar rastreamento imediatamente após estabelecer a conexão**estiver selecionado, a caixa de diálogo **Propriedades do Rastreamento**não será exibida e o rastreamento será iniciado.</span><span class="sxs-lookup"><span data-stu-id="26e01-107">If **Start tracing immediately after making connection**is selected, the **Trace Properties**dialog box fails to appear and the trace begins instead.</span></span> <span data-ttu-id="26e01-108">Para desabilitar essa configuração, no menu **Ferramentas**, clique em **Opções**e desmarque a caixa de seleção **Iniciar rastreamento imediatamente após estabelecer a conexão** .</span><span class="sxs-lookup"><span data-stu-id="26e01-108">To turn off this setting, on the **Tools**menu, click **Options**, and clear the **Start tracing immediately after making connection** check box.</span></span>  
  
2.  <span data-ttu-id="26e01-109">Na caixa de diálogo **Propriedades do Rastreamento** , verifique se a guia **Geral** está marcada e insira um nome na caixa de texto **TraceName** .</span><span class="sxs-lookup"><span data-stu-id="26e01-109">In the **Trace Properties** dialog box, make sure the **General** tab is selected, and enter a name in the **TraceName** text box.</span></span>  
  
3.  <span data-ttu-id="26e01-110">Na lista **Usar o modelo**, selecione um modelo de rastreamento.</span><span class="sxs-lookup"><span data-stu-id="26e01-110">From the **Use the template**list, select a trace template.</span></span>  
  
4.  <span data-ttu-id="26e01-111">Opcionalmente, especifique um arquivo ou tabela de destino onde os resultados do rastreamento serão salvos.</span><span class="sxs-lookup"><span data-stu-id="26e01-111">Optionally, specify a destination file or table in which to save the trace results.</span></span>  
  
5.  <span data-ttu-id="26e01-112">Na guia **Seleção de Eventos**, clique na coluna de dados **EndTime** para iniciar a caixa de diálogo **Editar Filtro** .</span><span class="sxs-lookup"><span data-stu-id="26e01-112">On the **Events Selection**tab, click the **EndTime** data column to launch the **Edit Filter** dialog box.</span></span> <span data-ttu-id="26e01-113">Você também pode clicar com o botão direito do mouse no título de coluna e selecionar **Editar Filtro de Coluna**.</span><span class="sxs-lookup"><span data-stu-id="26e01-113">You can also right-click the column heading, and select **Edit Column Filter**.</span></span>  
  
6.  <span data-ttu-id="26e01-114">Expanda **maior que** ou **menor que**e insira um `datetime` valor no campo que aparece abaixo do operador de comparação.</span><span class="sxs-lookup"><span data-stu-id="26e01-114">Expand **Greater than** or **Less than**, and enter a `datetime`value in the field that appears beneath the comparison operator.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26e01-115">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="26e01-115">See Also</span></span>  
 <span data-ttu-id="26e01-116">[SQL Server Profiler](sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="26e01-116">[SQL Server Profiler](sql-server-profiler.md) </span></span>  
 [<span data-ttu-id="26e01-117">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="26e01-117">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
