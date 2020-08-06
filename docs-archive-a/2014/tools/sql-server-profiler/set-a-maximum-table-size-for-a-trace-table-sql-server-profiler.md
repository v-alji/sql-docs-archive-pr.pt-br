---
title: Definir um tamanho máximo para uma tabela de rastreamento (SQL Server Profiler) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- size [SQL Server], trace tables
- maximum table size for traces
ms.assetid: d0ae83e5-1c88-4a2e-be05-2c341280b978
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5f48efbe02e300e06faf857ed0fb36ae340ad979
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678395"
---
# <a name="set-a-maximum-table-size-for-a-trace-table-sql-server-profiler"></a><span data-ttu-id="1d750-102">Definir um tamanho máximo para uma tabela de rastreamento (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="1d750-102">Set a Maximum Table Size for a Trace Table (SQL Server Profiler)</span></span>
  <span data-ttu-id="1d750-103">Este tópico descreve como definir um tamanho máximo para tabelas de rastreamento usando o [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1d750-103">This topic describes how to set a maximum table size for trace tables by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>  
  
### <a name="to-set-a-maximum-table-size-for-a-trace-table"></a><span data-ttu-id="1d750-104">Para definir um tamanho máximo para uma tabela de rastreamento</span><span class="sxs-lookup"><span data-stu-id="1d750-104">To set a maximum table size for a trace table</span></span>  
  
1.  <span data-ttu-id="1d750-105">No menu **Arquivo** , clique em **Novo Rastreamento**e conecte a uma instância do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="1d750-105">On the **File** menu, click **New Trace**, and then connect to an instance of SQL Server.</span></span>  
  
     <span data-ttu-id="1d750-106">A caixa de diálogo **Propriedades do Rastreamento**é exibida.</span><span class="sxs-lookup"><span data-stu-id="1d750-106">The **Trace Properties**dialog box appears.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1d750-107">Se **Iniciar rastreamento imediatamente após estabelecer a conexão**estiver selecionado, a caixa de diálogo **Propriedades do Rastreamento**não será exibida e o rastreamento será iniciado.</span><span class="sxs-lookup"><span data-stu-id="1d750-107">If **Start tracing immediately after making connection**is selected, the **Trace Properties**dialog box fails to appear and the trace begins instead.</span></span> <span data-ttu-id="1d750-108">Para desabilitar essa configuração, no menu **Ferramentas**, clique em **Opções**e desmarque a caixa de seleção **Iniciar rastreamento imediatamente após estabelecer a conexão** .</span><span class="sxs-lookup"><span data-stu-id="1d750-108">To turn off this setting, on the **Tools**menu, click **Options**, and clear the **Start tracing immediately after making connection** check box.</span></span>  
  
2.  <span data-ttu-id="1d750-109">Na caixa **Nome do rastreamento** , digite um nome para o rastreamento.</span><span class="sxs-lookup"><span data-stu-id="1d750-109">In the **Trace name** box, type a name for the trace.</span></span>  
  
3.  <span data-ttu-id="1d750-110">Na lista **Nome do modelo**, selecione um modelo de rastreamento.</span><span class="sxs-lookup"><span data-stu-id="1d750-110">In the **Template name**list, select a trace template.</span></span>  
  
4.  <span data-ttu-id="1d750-111">Marque a caixa de seleção **Salvar em tabela**.</span><span class="sxs-lookup"><span data-stu-id="1d750-111">Select the **Save to table**check box.</span></span>  
  
5.  <span data-ttu-id="1d750-112">Conecte-se ao servidor em que deseja armazenar o rastreamento.</span><span class="sxs-lookup"><span data-stu-id="1d750-112">Connect to the server on which you want the trace to be stored.</span></span>  
  
     <span data-ttu-id="1d750-113">A caixa de diálogo **Tabela de Destino** é exibida.</span><span class="sxs-lookup"><span data-stu-id="1d750-113">The **Destination Table** dialog box appears.</span></span>  
  
6.  <span data-ttu-id="1d750-114">Selecione um banco de dados para o rastreamento na lista **Banco de Dados** .</span><span class="sxs-lookup"><span data-stu-id="1d750-114">Select a database for the trace from the **Database** list.</span></span>  
  
7.  <span data-ttu-id="1d750-115">Na caixa **Tabela** , digite ou selecione um nome de tabela.</span><span class="sxs-lookup"><span data-stu-id="1d750-115">In the **Table** box, type or select a table name.</span></span>  
  
8.  <span data-ttu-id="1d750-116">Marque a caixa de seleção **Definir máximo de linhas** e especifique um número máximo de linhas para a tabela de rastreamento.</span><span class="sxs-lookup"><span data-stu-id="1d750-116">Select the **Set maximum rows** check box, and specify a maximum number of rows for the trace table.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1d750-117">Quando o número de linhas na tabela exceder o máximo especificado, os eventos do rastreamento deixarão de ser registrados.</span><span class="sxs-lookup"><span data-stu-id="1d750-117">When the number of rows in the table exceeds the maximum that you have specified, the trace events are no longer recorded.</span></span> <span data-ttu-id="1d750-118">O rastreamento, porém, continuará.</span><span class="sxs-lookup"><span data-stu-id="1d750-118">However, tracing continues.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d750-119">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="1d750-119">See Also</span></span>  
 <span data-ttu-id="1d750-120">[SQL Server Profiler](sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="1d750-120">[SQL Server Profiler](sql-server-profiler.md) </span></span>  
 [<span data-ttu-id="1d750-121">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="1d750-121">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
