---
title: Salvar resultados de rastreamento em uma tabela (SQL Server Profiler) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- saving traces
- traces [SQL Server], saving
ms.assetid: edbecf74-683b-4e43-a1ef-7a3d5f5e27f6
author: stevestein
ms.author: sstein
ms.openlocfilehash: 08acfb4e7136f8b28d1c990d508b8578f96a57b8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683816"
---
# <a name="save-trace-results-to-a-table-sql-server-profiler"></a><span data-ttu-id="6d3e4-102">Salvar resultados de rastreamento em uma tabela (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="6d3e4-102">Save Trace Results to a Table (SQL Server Profiler)</span></span>
  <span data-ttu-id="6d3e4-103">Este tópico descreve como salvar resultados de rastreamento em uma tabela do banco de dados, usando o [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6d3e4-103">This topic describes how to save trace results to a database table by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>  
  
### <a name="to-save-trace-results-to-a-table"></a><span data-ttu-id="6d3e4-104">Para salvar resultados de rastreamento em uma tabela</span><span class="sxs-lookup"><span data-stu-id="6d3e4-104">To save trace results to a table</span></span>  
  
1.  <span data-ttu-id="6d3e4-105">No menu **Arquivo** , clique em **Novo Rastreamento**e conecte-se a uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6d3e4-105">On the **File** menu, click **New Trace**, and then connect to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
     <span data-ttu-id="6d3e4-106">A caixa de diálogo **Propriedades do Rastreamento**é exibida.</span><span class="sxs-lookup"><span data-stu-id="6d3e4-106">The **Trace Properties**dialog box appears.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="6d3e4-107">Se **Iniciar rastreamento imediatamente após estabelecer a conexão**estiver selecionado, a caixa de diálogo **Propriedades do Rastreamento**não será exibida e o rastreamento será iniciado.</span><span class="sxs-lookup"><span data-stu-id="6d3e4-107">If **Start tracing immediately after making connection**is selected, the **Trace Properties**dialog box fails to appear and the trace begins instead.</span></span> <span data-ttu-id="6d3e4-108">Para desabilitar essa configuração, no menu **Ferramentas**, clique em **Opções**e desmarque a caixa de seleção **Iniciar rastreamento imediatamente após estabelecer a conexão** .</span><span class="sxs-lookup"><span data-stu-id="6d3e4-108">To turn off this setting, on the **Tools**menu, click **Options**, and clear the **Start tracing immediately after making connection** check box.</span></span>  
  
2.  <span data-ttu-id="6d3e4-109">Na caixa de diálogo **Nome do rastreamento** , digite um nome para o rastreamento e clique em **Salvar em tabela**.</span><span class="sxs-lookup"><span data-stu-id="6d3e4-109">In the **Trace name** box, type a name for the trace, and then click **Save to table**.</span></span>  
  
3.  <span data-ttu-id="6d3e4-110">Na caixa de diálogo **Conectar ao Servidor** , conecte-se ao banco de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que conterá a tabela de rastreamento.</span><span class="sxs-lookup"><span data-stu-id="6d3e4-110">In the **Connect to server** dialog box, connect to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database that will contain the trace table.</span></span>  
  
4.  <span data-ttu-id="6d3e4-111">Na caixa de diálogo **Tabela de Destino** , selecione um banco de dados na lista **Banco de Dados**.</span><span class="sxs-lookup"><span data-stu-id="6d3e4-111">In the **Destination Table** dialog box, select a database from the **Database**list.</span></span>  
  
5.  <span data-ttu-id="6d3e4-112">Na lista **Proprietário** , selecione o proprietário do rastreamento.</span><span class="sxs-lookup"><span data-stu-id="6d3e4-112">In the **Owner** list, select the owner for the trace.</span></span>  
  
6.  <span data-ttu-id="6d3e4-113">Na lista **Tabela** , digite ou selecione o nome da tabela a conter os resultados do rastreamento.</span><span class="sxs-lookup"><span data-stu-id="6d3e4-113">In the **Table** list, type or select the table name for the trace results.</span></span> <span data-ttu-id="6d3e4-114">Clique em **OK.**</span><span class="sxs-lookup"><span data-stu-id="6d3e4-114">Click **OK.**</span></span>  
  
7.  <span data-ttu-id="6d3e4-115">Na caixa de diálogo **Propriedades do rastreamento** , marque a caixa de seleção **Definir máximo de linhas (em milhares)** para especificar o número máximo de linhas a serem salvas.</span><span class="sxs-lookup"><span data-stu-id="6d3e4-115">In the **Trace Properties** dialog box, select the **Set maximum rows (in thousands)** check box to specify the maximum number of rows to save.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d3e4-116">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6d3e4-116">See Also</span></span>  
 [<span data-ttu-id="6d3e4-117">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="6d3e4-117">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
