---
title: Exibir o plano de execução estimado | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- zoom [SQL Server]
- estimated execution plan [SQL Server]
- displaying execution plans
- viewing execution plans
- execution plans [SQL Server], displaying
- customizing execution plan display [SQL Server]
- modifying execution plan display
- custom zoom [SQL Server]
ms.assetid: e94aa576-4c0c-4c54-ad05-6c3432cc615b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 79c0972661d40eb9e359cf43f7a1f0b1b2ae4b0c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679882"
---
# <a name="display-the-estimated-execution-plan"></a><span data-ttu-id="14ab7-102">Exibir o plano de execução estimado</span><span class="sxs-lookup"><span data-stu-id="14ab7-102">Display the Estimated Execution Plan</span></span>
  <span data-ttu-id="14ab7-103">Este tópico descreve como gerar planos de execução gráfica estimados usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="14ab7-103">This topic describes how to generate graphical estimated execution plans by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="14ab7-104">Quando são gerados planos de execução estimados, as consultas ou lotes [!INCLUDE[tsql](../../includes/tsql-md.md)] não são executadas.</span><span class="sxs-lookup"><span data-stu-id="14ab7-104">When estimated execution plans are generated, the [!INCLUDE[tsql](../../includes/tsql-md.md)] queries or batches do not execute.</span></span> <span data-ttu-id="14ab7-105">Ao invés disso, o plano de execução gerado exibe o plano de execução de consulta que o [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] teria maior probabilidade de usar se fossem executadas consultas.</span><span class="sxs-lookup"><span data-stu-id="14ab7-105">Instead, the execution plan that is generated displays the query execution plan that [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] would most probably use if the queries were actually executed.</span></span>  
  
 <span data-ttu-id="14ab7-106">Para usar esse recurso, os usuários devem ter as permissões apropriadas para executar a consulta [!INCLUDE[tsql](../../includes/tsql-md.md)] para as quais está sendo gerado um plano de execução gráfica e devem ter permissão SHOWPLAN para todos os bancos de dados incluídos na consulta.</span><span class="sxs-lookup"><span data-stu-id="14ab7-106">To use this feature, users must have the appropriate permissions to execute the [!INCLUDE[tsql](../../includes/tsql-md.md)] query for which a graphical execution plan is being generated, and they must be granted the SHOWPLAN permission for all databases referenced by the query.</span></span>  
  
### <a name="to-display-the-estimated-execution-plan-for-a-query"></a><span data-ttu-id="14ab7-107">Para exibir o plano de execução estimado para uma consulta</span><span class="sxs-lookup"><span data-stu-id="14ab7-107">To display the estimated execution plan for a query</span></span>  
  
1.  <span data-ttu-id="14ab7-108">Na barra de ferramentas, clique em **Consulta do Mecanismo de Banco de Dados**.</span><span class="sxs-lookup"><span data-stu-id="14ab7-108">On the toolbar, click **Database Engine Query**.</span></span> <span data-ttu-id="14ab7-109">Você também pode abrir uma consulta existente e exibir o plano de execução estimado clicando no botão de barra de ferramentas **Abrir Arquivo** e localizando a consulta existente.</span><span class="sxs-lookup"><span data-stu-id="14ab7-109">You can also open an existing query and display the estimated execution plan by clicking the **Open File** toolbar button and locating the existing query.</span></span>  
  
2.  <span data-ttu-id="14ab7-110">Insira a consulta para a qual você deseja exibir o plano de execução estimado.</span><span class="sxs-lookup"><span data-stu-id="14ab7-110">Enter the query for which you would like to display the estimated execution plan.</span></span>  
  
3.  <span data-ttu-id="14ab7-111">No menu **Consulta** , clique em **Exibir Plano de Execução Estimado** ou clique no botão de barra de ferramentas **Exibir Plano de Execução Estimado** .</span><span class="sxs-lookup"><span data-stu-id="14ab7-111">On the **Query** menu, click **Display Estimated Execution Plan** or click the **Display Estimated Execution Plan** toolbar button.</span></span> <span data-ttu-id="14ab7-112">O plano de execução estimado é exibido na guia **Plano de execução** no painel de resultados.</span><span class="sxs-lookup"><span data-stu-id="14ab7-112">The estimated execution plan is displayed on the **Execution Plan** tab in the results pane.</span></span> <span data-ttu-id="14ab7-113">Para exibir mais informações, mantenha o mouse sobre os ícones dos operadores lógicos e físicos e exiba a dica de tela com a descrição e as propriedades do operador.</span><span class="sxs-lookup"><span data-stu-id="14ab7-113">To view additional information, pause the mouse over the logical and physical operator icons and view the description and properties of the operator in the displayed ToolTip.</span></span> <span data-ttu-id="14ab7-114">Você também pode exibir propriedades do operador na janela Propriedades.</span><span class="sxs-lookup"><span data-stu-id="14ab7-114">Alternatively, you can view operator properties in the Properties window.</span></span> <span data-ttu-id="14ab7-115">Se a janela Propriedades não estiver visível, clique com o botão direito do mouse em um operador e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="14ab7-115">If Properties is not visible, right-click an operator and click **Properties**.</span></span> <span data-ttu-id="14ab7-116">Selecione um operador cujas propriedades exibir.</span><span class="sxs-lookup"><span data-stu-id="14ab7-116">Select an operator to view its properties.</span></span>  
  
4.  <span data-ttu-id="14ab7-117">Para alterar a exibição do plano de execução, clique com o botão direito do mouse no plano de execução e selecione **Ampliar**, **Reduzir**, **Zoom Personalizado**ou **Ajustar Nível de Zoom**.</span><span class="sxs-lookup"><span data-stu-id="14ab7-117">To alter the display of the execution plan, right-click the execution plan and select **Zoom In**, **Zoom Out**, **Custom Zoom**, or **Zoom to Fit**.</span></span> <span data-ttu-id="14ab7-118">**Ampliar** e **Reduzir** permitem ampliar ou reduzir o plano de execução com valores fixos.</span><span class="sxs-lookup"><span data-stu-id="14ab7-118">**Zoom In** and **Zoom Out** allow you to magnify or reduce the execution plan by fixed amounts.</span></span> <span data-ttu-id="14ab7-119">**Zoom personalizado** permite que você defina sua própria ampliação da exibição, como ampliar em 80 por cento.</span><span class="sxs-lookup"><span data-stu-id="14ab7-119">**Custom Zoom** allows you to define your own display magnification, such as zooming at 80 percent.</span></span> <span data-ttu-id="14ab7-120">**Ajustar Nível de Zoom** aumenta o plano de execução para se ajustar ao painel de resultados.</span><span class="sxs-lookup"><span data-stu-id="14ab7-120">**Zoom to Fit** magnifies the execution plan to fit the result pane.</span></span>  
  
  
