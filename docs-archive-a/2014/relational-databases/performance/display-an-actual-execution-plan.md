---
title: Exibir um plano de execução real | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- displaying execution plans
- actual execution plans
- viewing execution plans
- execution plans [SQL Server], displaying
ms.assetid: 9e583a18-5f4a-4054-bfe1-4b2a76630db6
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f384e2d2752b7601fbb46b8ee7f7b56a2615651c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679888"
---
# <a name="display-an-actual-execution-plan"></a><span data-ttu-id="5eb1d-102">Exibir um plano de execução real</span><span class="sxs-lookup"><span data-stu-id="5eb1d-102">Display an Actual Execution Plan</span></span>
  <span data-ttu-id="5eb1d-103">Este tópico descreve como gerar planos de execução gráfica reais usando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5eb1d-103">This topic describes how to generate actual graphical execution plans by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="5eb1d-104">Quando planos de execução reais são gerados, as consultas ou lotes [!INCLUDE[tsql](../../includes/tsql-md.md)] são executados.</span><span class="sxs-lookup"><span data-stu-id="5eb1d-104">When actual execution plans are generated, the [!INCLUDE[tsql](../../includes/tsql-md.md)] queries or batches execute.</span></span> <span data-ttu-id="5eb1d-105">O plano de execução gerado exibe o plano de execução de consulta real que o [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] usa para executar as consultas.</span><span class="sxs-lookup"><span data-stu-id="5eb1d-105">The execution plan that is generated displays the actual query execution plan that the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] uses to execute the queries.</span></span>  
  
 <span data-ttu-id="5eb1d-106">Para usar esse recurso, os usuários devem ter as permissões apropriadas para executar as consultas [!INCLUDE[tsql](../../includes/tsql-md.md)] para as quais um plano de execução gráfica está sendo gerado e eles devem ter a permissão SHOWPLAN para todos os bancos de dados referenciados pela consulta.</span><span class="sxs-lookup"><span data-stu-id="5eb1d-106">To use this feature, users must have the appropriate permissions to execute the [!INCLUDE[tsql](../../includes/tsql-md.md)] queries for which a graphical execution plan is being generated, and they must be granted the SHOWPLAN permission for all databases referenced by the query.</span></span>  
  
### <a name="to-include-an-execution-plan-for-a-query-during-execution"></a><span data-ttu-id="5eb1d-107">Para incluir um plano de execução para uma consulta durante a execução</span><span class="sxs-lookup"><span data-stu-id="5eb1d-107">To include an execution plan for a query during execution</span></span>  
  
1.  <span data-ttu-id="5eb1d-108">Na barra de ferramentas do [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , clique em **Consulta do Mecanismo de Banco de Dados**.</span><span class="sxs-lookup"><span data-stu-id="5eb1d-108">On the [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] toolbar, click **Database Engine Query**.</span></span> <span data-ttu-id="5eb1d-109">Você também pode abrir uma consulta existente e exibir o plano de execução estimado clicando no botão de barra de ferramentas **Abrir Arquivo** e localizando a consulta existente.</span><span class="sxs-lookup"><span data-stu-id="5eb1d-109">You can also open an existing query and display the estimated execution plan by clicking the **Open File** toolbar button and locating the existing query.</span></span>  
  
2.  <span data-ttu-id="5eb1d-110">Insira a consulta para a qual você deseja exibir o plano de execução real.</span><span class="sxs-lookup"><span data-stu-id="5eb1d-110">Enter the query for which you would like to display the actual execution plan.</span></span>  
  
3.  <span data-ttu-id="5eb1d-111">No menu **consulta** , clique em **incluir plano de execução real** ou clique no botão de barra de ferramentas **incluir plano de execução real**</span><span class="sxs-lookup"><span data-stu-id="5eb1d-111">On the **Query** menu, click **Include Actual Execution Plan** or click the **Include Actual Execution Plan** toolbar button</span></span>  
  
4.  <span data-ttu-id="5eb1d-112">Execute a consulta clicando no botão de barra de ferramentas **Executar** .</span><span class="sxs-lookup"><span data-stu-id="5eb1d-112">Execute the query by clicking the **Execute** toolbar button.</span></span> <span data-ttu-id="5eb1d-113">O plano usado pelo otimizador de consulta é exibido na guia **Plano de Execução** no painel de resultados.</span><span class="sxs-lookup"><span data-stu-id="5eb1d-113">The plan used by the query optimizer is displayed on the **Execution Plan** tab in the results pane.</span></span> <span data-ttu-id="5eb1d-114">Movimente o mouse sobre os operadores lógicos e físicos para exibir a descrição e propriedades dos operadores na dica de tela exibida.</span><span class="sxs-lookup"><span data-stu-id="5eb1d-114">Pause the mouse over the logical and physical operators to view the description and properties of the operators in the displayed ToolTip.</span></span>  
  
     <span data-ttu-id="5eb1d-115">Você também pode exibir propriedades do operador na janela Propriedades.</span><span class="sxs-lookup"><span data-stu-id="5eb1d-115">Alternatively, you can view operator properties in the Properties window.</span></span> <span data-ttu-id="5eb1d-116">Se a janela Propriedades não estiver visível, clique com o botão direito do mouse em um operador e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="5eb1d-116">If Properties is not visible, right-click an operator and select **Properties**.</span></span> <span data-ttu-id="5eb1d-117">Selecione um operador cujas propriedades exibir.</span><span class="sxs-lookup"><span data-stu-id="5eb1d-117">Select an operator to view its properties.</span></span>  
  
5.  <span data-ttu-id="5eb1d-118">Você pode alterar a exibição do plano de execução clicando com o botão direito no plano de execução e selecionando **Ampliar**, **Reduzir**, **Zoom Personalizado**ou **Ajustar Nível de Zoom**.</span><span class="sxs-lookup"><span data-stu-id="5eb1d-118">You can alter the display of the execution plan by right-clicking the execution plan and selecting **Zoom In**, **Zoom Out**, **Custom Zoom**, or **Zoom to Fit**.</span></span> <span data-ttu-id="5eb1d-119">**Ampliar** e **Reduzir** permitem ampliar ou reduzir o plano de execução, enquanto **Zoom Personalizado** permite definir seu próprio zoom, como ampliar em 80 por cento.</span><span class="sxs-lookup"><span data-stu-id="5eb1d-119">**Zoom In** and **Zoom Out** allow you to zoom in or out on the execution plan, while **Custom Zoom** allows you to define your own zoom, such as zooming at 80 percent.</span></span> <span data-ttu-id="5eb1d-120">**Ajustar Nível de Zoom** aumenta o plano de execução para se ajustar ao painel de resultados.</span><span class="sxs-lookup"><span data-stu-id="5eb1d-120">**Zoom to Fit** magnifies the execution plan to fit the result pane.</span></span>  
  
  
