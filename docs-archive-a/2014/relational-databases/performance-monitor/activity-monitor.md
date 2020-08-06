---
title: Monitor de Atividade | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Activity Monitor [SQL Server]
ms.assetid: 1e6c430d-3a2a-468e-a3d5-ef5459c36c15
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 71fd0d1172b4fcd5739a3af1a60246cc7dce3b93
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684673"
---
# <a name="activity-monitor"></a><span data-ttu-id="ce805-102">Monitor de Atividade</span><span class="sxs-lookup"><span data-stu-id="ce805-102">Activity Monitor</span></span>
  <span data-ttu-id="ce805-103">O Monitor de Atividade exibe informações sobre os processos do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e como esses processos afetam a instância atual do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ce805-103">Activity Monitor displays information about [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] processes and how these processes affect the current instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="benefits-of-activity-monitor"></a><span data-ttu-id="ce805-104">Benefícios do Monitor de Atividade</span><span class="sxs-lookup"><span data-stu-id="ce805-104">Benefits of Activity Monitor</span></span>  
 <span data-ttu-id="ce805-105">O monitor de atividade é uma janela de documento com guias que tem os seguintes painéis expansíveis e recolhíveis: **visão geral**, **tarefas de usuário ativas**, **esperas de recursos**, e **/s de arquivo de dados**e **consultas caras recentes**.</span><span class="sxs-lookup"><span data-stu-id="ce805-105">Activity Monitor is a tabbed document window that has the following expandable and collapsible panes: **Overview**, **Active User Tasks**, **Resource Waits**, **Data File I/O**, and **Recent Expensive Queries**.</span></span> <span data-ttu-id="ce805-106">Quando qualquer painel é expandido, o Monitor de Atividade consulta a instância para obter informações.</span><span class="sxs-lookup"><span data-stu-id="ce805-106">When any pane is expanded, Activity Monitor queries the instance for information.</span></span> <span data-ttu-id="ce805-107">Quando um painel é recolhido, todas as atividades de consulta são interrompidas para esse painel.</span><span class="sxs-lookup"><span data-stu-id="ce805-107">When a pane is collapsed, all querying activity stops for that pane.</span></span> <span data-ttu-id="ce805-108">Também é possível expandir um ou mais painéis ao mesmo tempo para exibir diferentes tipos de atividades na instância.</span><span class="sxs-lookup"><span data-stu-id="ce805-108">You can also expand one or more panes at the same time to view different kinds of activity on the instance.</span></span>  
  
 <span data-ttu-id="ce805-109">Para as colunas incluídas nas painéis tarefas do **usuário ativo**, **esperas de recursos**, e **/s de arquivo de dados**e **consultas caras recentes** , você pode personalizar a exibição das seguintes maneiras:</span><span class="sxs-lookup"><span data-stu-id="ce805-109">For the columns that are included in the **Active User Tasks**, **Resource Waits**, **Data File I/O**, and **Recent Expensive Queries** panes, you can customize the display in the following ways:</span></span>  
  
1.  <span data-ttu-id="ce805-110">Para reorganizar a ordem das colunas, clique no título da coluna e arraste-o para outro local na faixa de opções de título.</span><span class="sxs-lookup"><span data-stu-id="ce805-110">To rearrange the order of the columns, click the column heading and drag it to another location in the heading ribbon.</span></span>  
  
2.  <span data-ttu-id="ce805-111">Para classificar uma coluna, clique no nome da coluna.</span><span class="sxs-lookup"><span data-stu-id="ce805-111">To sort a column, click the column name.</span></span>  
  
3.  <span data-ttu-id="ce805-112">Para filtrar uma ou mais colunas, clique na seta suspensa no título da coluna e selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="ce805-112">To filter on one or more columns, click the drop-down arrow in the column heading, and then select a value.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="ce805-113">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="ce805-113">Related Tasks</span></span>  
 <span data-ttu-id="ce805-114">Use as tarefas a seguir para começar a usar o Monitor de Atividade:</span><span class="sxs-lookup"><span data-stu-id="ce805-114">Use the following tasks to get started with Activity Monitor:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ce805-115">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="ce805-115">**Description**</span></span>|<span data-ttu-id="ce805-116">**Tópico**</span><span class="sxs-lookup"><span data-stu-id="ce805-116">**Topic**</span></span>|  
|<span data-ttu-id="ce805-117">Descreve como abrir o Monitor de Atividade e como definir o intervalo de atualização do Monitor de Atividade.</span><span class="sxs-lookup"><span data-stu-id="ce805-117">Describes how to open Activity Monitor and how to set the Activity Monitor refresh interval.</span></span>|[<span data-ttu-id="ce805-118">Abrir o Monitor de Atividade &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="ce805-118">Open Activity Monitor &#40;SQL Server Management Studio&#41;</span></span>](../performance-monitor/open-activity-monitor-sql-server-management-studio.md)|  
|<span data-ttu-id="ce805-119">Vincula-se a tópicos sobre monitoramento de atividade e desempenho do servidor.</span><span class="sxs-lookup"><span data-stu-id="ce805-119">Links to topics for server performance and activity monitoring.</span></span>|[<span data-ttu-id="ce805-120">Monitoramento de desempenho e atividade de servidor</span><span class="sxs-lookup"><span data-stu-id="ce805-120">Server Performance and Activity Monitoring</span></span>](../performance/server-performance-and-activity-monitoring.md)|  
  
  
