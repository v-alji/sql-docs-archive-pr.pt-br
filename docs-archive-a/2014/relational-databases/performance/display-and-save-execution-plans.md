---
title: Exibir e salvar planos de execução | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Showplan results
- execution plans [SQL Server]
- queries [SQL Server], tuning
- execution plans [SQL Server], how-to topics
- SQL Server Management Studio [SQL Server], execution plans
- tuning queries [SQL Server]
ms.assetid: bcd6f094-c613-4835-ae19-4caaadb4bb17
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: e236ed2a298bc8fc9a829948a864f6f5c27a2ba2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679891"
---
# <a name="display-and-save-execution-plans"></a><span data-ttu-id="39c68-102">Exibir e salvar planos de execução</span><span class="sxs-lookup"><span data-stu-id="39c68-102">Display and Save Execution Plans</span></span>
  <span data-ttu-id="39c68-103">Esta seção explica como exibir planos de execução e como salvá-los em um arquivo no formato XML usando o Microsoft [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="39c68-103">This section explains how to display execution plans and how to save execution plans to a file in XML format by using Microsoft [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="39c68-104">Planos de execução exibem graficamente os métodos de recuperação de dados escolhidos pelo otimizador de consulta do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="39c68-104">Execution plans graphically display the data retrieval methods chosen by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] query optimizer.</span></span> <span data-ttu-id="39c68-105">Planos de execução representam o custo de execução de instruções e consultas específicas no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usando ícones em vez da representação tabular produzida pelas instruções SET SHOWPLAN_ALL ou SET SHOWPLAN_TEXT.</span><span class="sxs-lookup"><span data-stu-id="39c68-105">Execution plans represent the execution cost of specific statements and queries in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] using icons rather than the tabular representation produced by the SET SHOWPLAN_ALL or SET SHOWPLAN_TEXT statements.</span></span> <span data-ttu-id="39c68-106">Essa abordagem gráfica é muito útil para entender as características de desempenho de uma consulta.</span><span class="sxs-lookup"><span data-stu-id="39c68-106">This graphical approach is very useful for understanding the performance characteristics of a query.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="39c68-107">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="39c68-107">In This Section</span></span>  
  
-   [<span data-ttu-id="39c68-108">Exibir o plano de execução estimado</span><span class="sxs-lookup"><span data-stu-id="39c68-108">Display the Estimated Execution Plan</span></span>](display-the-estimated-execution-plan.md)  
  
-   [<span data-ttu-id="39c68-109">Exibir um plano de execução real</span><span class="sxs-lookup"><span data-stu-id="39c68-109">Display an Actual Execution Plan</span></span>](display-an-actual-execution-plan.md)  
  
-   [<span data-ttu-id="39c68-110">Salvar um plano de execução em formato XML</span><span class="sxs-lookup"><span data-stu-id="39c68-110">Save an Execution Plan in XML Format</span></span>](save-an-execution-plan-in-xml-format.md)  
  
  
