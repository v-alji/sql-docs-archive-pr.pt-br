---
title: Propriedades do SQL Server Agent (página Histórico) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.ag.agent.history.f1
ms.assetid: dc73734c-b3c3-407f-bbd1-8714b4fa47b0
author: stevestein
ms.author: sstein
ms.openlocfilehash: d67ff3da97e11292abcac03958fe1e423b35d7d1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582253"
---
# <a name="sql-server-agent-properties-history-page"></a><span data-ttu-id="42acb-102">Propriedades do SQL Server Agent (página Histórico)</span><span class="sxs-lookup"><span data-stu-id="42acb-102">SQL Server Agent Properties (History Page)</span></span>
  <span data-ttu-id="42acb-103">Use esta página para exibir e modificar as configurações de gerenciamento do [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] log de histórico de serviço do Agent.</span><span class="sxs-lookup"><span data-stu-id="42acb-103">Use this page to view and modify settings for managing the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service history log.</span></span>  
  
## <a name="options"></a><span data-ttu-id="42acb-104">Opções</span><span class="sxs-lookup"><span data-stu-id="42acb-104">Options</span></span>  
 <span data-ttu-id="42acb-105">**Limitar tamanho do log do histórico de trabalho**</span><span class="sxs-lookup"><span data-stu-id="42acb-105">**Limit size of job history log**</span></span>  
 <span data-ttu-id="42acb-106">Define limites para a quantidade de informações do histórico de trabalho que o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent mantém no log.</span><span class="sxs-lookup"><span data-stu-id="42acb-106">Sets limits for the amount of job history information that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent retains in the log.</span></span>  
  
 <span data-ttu-id="42acb-107">**Tamanho máximo (em linhas) do log do histórico de trabalho**</span><span class="sxs-lookup"><span data-stu-id="42acb-107">**Maximum job history log size (in rows)**</span></span>  
 <span data-ttu-id="42acb-108">Define o número máximo de linhas que o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent mantém.</span><span class="sxs-lookup"><span data-stu-id="42acb-108">Sets the maximum number of rows that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent retains.</span></span> <span data-ttu-id="42acb-109">Quando o log aumenta para conter esse número de linhas, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent remove as linhas mais antigas do log à medida que novas linhas forem inseridas.</span><span class="sxs-lookup"><span data-stu-id="42acb-109">When the log grows to contain this number of rows, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent removes the oldest rows in the log as new rows are entered.</span></span>  
  
 <span data-ttu-id="42acb-110">**Máximo de linhas do histórico de trabalho por trabalho**</span><span class="sxs-lookup"><span data-stu-id="42acb-110">**Maximum job history rows per job**</span></span>  
 <span data-ttu-id="42acb-111">Define o número máximo de linhas que o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent mantém por trabalho.</span><span class="sxs-lookup"><span data-stu-id="42acb-111">Sets the maximum number of rows that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent retains per job.</span></span> <span data-ttu-id="42acb-112">Quando o log de um determinado trabalho cresce até conter esse número de linhas, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent remove as linhas mais antigas do log à medida que novas linhas são inseridas.</span><span class="sxs-lookup"><span data-stu-id="42acb-112">When the history for a particular job grows to contain this number of rows, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent removes the oldest rows in the log as new rows are entered.</span></span>  
  
 <span data-ttu-id="42acb-113">**Remover histórico de agente**</span><span class="sxs-lookup"><span data-stu-id="42acb-113">**Remove agent history**</span></span>  
 <span data-ttu-id="42acb-114">Especifica que o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent removerá as entradas presentes no log por mais tempo do que o período especificado.</span><span class="sxs-lookup"><span data-stu-id="42acb-114">Specifies that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent will remove entries that have been in the log longer than a specified length of time.</span></span> <span data-ttu-id="42acb-115">Essa é uma execução de uma vez para remover o histórico.</span><span class="sxs-lookup"><span data-stu-id="42acb-115">This is a one-time execution to remove the history.</span></span> <span data-ttu-id="42acb-116">Se um trabalho recorrente for necessário, crie e agende um plano de manutenção com um trabalho de limpeza.</span><span class="sxs-lookup"><span data-stu-id="42acb-116">If a reoccurring job is needed, create and schedule a maintenance plan with a cleanup job.</span></span>  
  
 <span data-ttu-id="42acb-117">**Com mais de**</span><span class="sxs-lookup"><span data-stu-id="42acb-117">**Older than**</span></span>  
 <span data-ttu-id="42acb-118">Define o período durante o qual o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent manterá entradas.</span><span class="sxs-lookup"><span data-stu-id="42acb-118">Sets the amount of time that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent will retain entries.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42acb-119">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="42acb-119">See Also</span></span>  
 [<span data-ttu-id="42acb-120">Log de erros do SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="42acb-120">SQL Server Agent Error Log</span></span>](sql-server-agent-error-log.md)  
  
  
