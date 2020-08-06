---
title: Especificar um filtro de ponto de interrupção
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Transact-SQL debugger, breakpoint filter
ms.assetid: 7bf1dddd-7b0b-4c47-8a7b-28a5569b4fa5
author: rothja
ms.author: jroth
ms.openlocfilehash: 9fc320397da1bddc0d28191c359c4d311b23e044
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574624"
---
# <a name="specify-a-breakpoint-filter"></a><span data-ttu-id="c9666-102">Especificar um filtro de ponto de interrupção</span><span class="sxs-lookup"><span data-stu-id="c9666-102">Specify a Breakpoint Filter</span></span>
  <span data-ttu-id="c9666-103">Um filtro de ponto de interrupção limita o ponto de interrupção para atuar somente em computadores, sistemas operacionais, processos e threads especificados.</span><span class="sxs-lookup"><span data-stu-id="c9666-103">A breakpoint filter limits the breakpoint to acting only on specified computers, operating system processes, and threads.</span></span> <span data-ttu-id="c9666-104">Filtros de ponto de interrupção são normalmente usados ao depurar aplicativos paralelos.</span><span class="sxs-lookup"><span data-stu-id="c9666-104">Breakpoint filters are typically used when debugging parallel applications.</span></span>  
  
##  <a name="filter-considerations"></a><a name="BKMK_ActionConsiderations"></a> <span data-ttu-id="c9666-105">Considerações sobre filtros</span><span class="sxs-lookup"><span data-stu-id="c9666-105">Filter Considerations</span></span>  
 <span data-ttu-id="c9666-106">Filtros de ponto de interrupção não são normalmente usados com o depurador [!INCLUDE[tsql](../../includes/tsql-md.md)] porque os scripts [!INCLUDE[tsql](../../includes/tsql-md.md)] e os procedimentos armazenados não são aplicativos paralelos.</span><span class="sxs-lookup"><span data-stu-id="c9666-106">Breakpoint filters are not typically used with the [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger because [!INCLUDE[tsql](../../includes/tsql-md.md)] scripts and stored procedures are not parallel applications.</span></span>  
  
#### <a name="to-specify-a-breakpoint-filter"></a><span data-ttu-id="c9666-107">Para especificar um filtro de ponto de interrupção</span><span class="sxs-lookup"><span data-stu-id="c9666-107">To Specify a Breakpoint Filter</span></span>  
  
1.  <span data-ttu-id="c9666-108">Na janela do editor, clique com o botão direito do mouse no glifo do ponto de interrupção e clique em **Filtro** no menu de atalho.</span><span class="sxs-lookup"><span data-stu-id="c9666-108">In the editor window, right-click the breakpoint glyph, and then click **Filter** on the shortcut menu.</span></span>  
  
     <span data-ttu-id="c9666-109">-ou-</span><span class="sxs-lookup"><span data-stu-id="c9666-109">-or-</span></span>  
  
     <span data-ttu-id="c9666-110">Na janela **Pontos de Interrupção** , clique com o botão direito do mouse no glifo do ponto de interrupção e clique em **Filtro** no menu de atalho.</span><span class="sxs-lookup"><span data-stu-id="c9666-110">In the **Breakpoints** window, right-click the breakpoint glyph, and then click **Filter** on the shortcut menu.</span></span>  
  
2.  <span data-ttu-id="c9666-111">Na caixa de diálogo **Filtros de Ponto de Interrupção** , use a caixa **Filtro** para especificar computadores por nome ou processos e threads do sistema operacional por nome ou número da ID:</span><span class="sxs-lookup"><span data-stu-id="c9666-111">In the **Breakpoint Filters** dialog box, use the **Filter** box to specify computers by name, or operating system processes and threads by either name or ID number:</span></span>  
  
    -   <span data-ttu-id="c9666-112">`MachineName` é o computador que está executando a instância do Mecanismo de Banco de Dados.</span><span class="sxs-lookup"><span data-stu-id="c9666-112">`MachineName` is the computer running the instance of the Database Engine.</span></span>  
  
    -   <span data-ttu-id="c9666-113">`ProcessID` e `ProcessName` são o processo do sistema operacional que executa a instância do Mecanismo de Banco de Dados.</span><span class="sxs-lookup"><span data-stu-id="c9666-113">`ProcessID`, and `ProcessName` are the operating system process running the instance of the Database Engine.</span></span>  
  
    -   <span data-ttu-id="c9666-114">`ThreadID` e `ThreadName` são o thread do sistema operacional que executa o lote [!INCLUDE[tsql](../../includes/tsql-md.md)], procedimento ou função na instância do Mecanismo de Banco de Dados.</span><span class="sxs-lookup"><span data-stu-id="c9666-114">`ThreadID` and `ThreadName` are the operating system thread running the [!INCLUDE[tsql](../../includes/tsql-md.md)] batch, procedure, or function in the instance of the Database Engine.</span></span>  
  
3.  <span data-ttu-id="c9666-115">Clique em **OK** para implementar as alterações ou em **Cancelar** para sair sem aplicar as alterações.</span><span class="sxs-lookup"><span data-stu-id="c9666-115">Click **OK** to implement the changes, or **Cancel** to exit without applying the changes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9666-116">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c9666-116">See Also</span></span>  
 <span data-ttu-id="c9666-117">[Especificar uma condição de ponto de interrupção](specify-a-breakpoint-condition.md) </span><span class="sxs-lookup"><span data-stu-id="c9666-117">[Specify a Breakpoint Condition](specify-a-breakpoint-condition.md) </span></span>  
 <span data-ttu-id="c9666-118">[Especificar uma contagem de ocorrências](specify-a-hit-count.md) </span><span class="sxs-lookup"><span data-stu-id="c9666-118">[Specify a Hit Count](specify-a-hit-count.md) </span></span>  
 [<span data-ttu-id="c9666-119">Especificar uma ação de ponto de interrupção</span><span class="sxs-lookup"><span data-stu-id="c9666-119">Specify a Breakpoint Action</span></span>](specify-a-breakpoint-action.md)  
