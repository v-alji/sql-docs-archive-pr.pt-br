---
title: Adicionar ou excluir um grupo de um gráfico (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 0445b0ac-acae-4462-80fb-fe9735ac66db
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2ac558ccbd8855018877228b2b38debf769f1573
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684535"
---
# <a name="add-or-delete-a-group-in-a-chart-report-builder-and-ssrs"></a><span data-ttu-id="ce355-102">Adicionar ou excluir um grupo em um gráfico (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="ce355-102">Add or Delete a Group in a Chart (Report Builder and SSRS)</span></span>
  <span data-ttu-id="ce355-103">Clique na região de dados do gráfico para exibir o painel **dados do gráfico** .</span><span class="sxs-lookup"><span data-stu-id="ce355-103">Click in the chart data region to display the **Chart Data** pane.</span></span> <span data-ttu-id="ce355-104">Crie grupos arrastando campos de conjuntos de dados para as áreas **Grupos de Categorias** e **Grupos de Séries** .</span><span class="sxs-lookup"><span data-stu-id="ce355-104">Create groups by dragging dataset fields to the **Category Groups** and **Series Groups** areas.</span></span> <span data-ttu-id="ce355-105">Para adicionar grupos aninhados, adicione vários campos à área.</span><span class="sxs-lookup"><span data-stu-id="ce355-105">To add nested groups, add multiple fields to the area.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-parent-or-child-group-to-a-chart"></a><span data-ttu-id="ce355-106">Para adicionar um grupo pai ou filho a um gráfico</span><span class="sxs-lookup"><span data-stu-id="ce355-106">To add a parent or child group to a chart</span></span>  
  
1.  <span data-ttu-id="ce355-107">Na superfície de design de relatório, clique em qualquer lugar no gráfico para selecioná-lo.</span><span class="sxs-lookup"><span data-stu-id="ce355-107">On the report design surface, click anywhere in the chart to select it.</span></span> <span data-ttu-id="ce355-108">O painel **Dados do Gráfico** é exibido.</span><span class="sxs-lookup"><span data-stu-id="ce355-108">The **Chart Data** pane appears.</span></span>  
  
2.  <span data-ttu-id="ce355-109">Arraste um campo na janela **Dados do Relatório** para a área **Grupos de Categorias** ou **Grupos de Séries** .</span><span class="sxs-lookup"><span data-stu-id="ce355-109">Drag a field from the **Report Data** window to the **Category Groups** or **Series Groups** area.</span></span> <span data-ttu-id="ce355-110">Para adicionar um grupo pai, posicione o cursor na frente de um grupo existente.</span><span class="sxs-lookup"><span data-stu-id="ce355-110">To add a parent group, position the cursor in front of an existing group.</span></span> <span data-ttu-id="ce355-111">Para adicionar um grupo filho, posicione o cursor depois de um grupo existente.</span><span class="sxs-lookup"><span data-stu-id="ce355-111">To add a child group, position the cursor after an existing group.</span></span>  
  
### <a name="to-edit-a-category-group-on-a-chart"></a><span data-ttu-id="ce355-112">Para editar um grupo de categorias em um gráfico</span><span class="sxs-lookup"><span data-stu-id="ce355-112">To edit a category group on a chart</span></span>  
  
1.  <span data-ttu-id="ce355-113">Na superfície de design de relatório, clique em qualquer lugar no gráfico para selecioná-lo.</span><span class="sxs-lookup"><span data-stu-id="ce355-113">On the report design surface, click anywhere in the chart to select it.</span></span> <span data-ttu-id="ce355-114">O painel **Dados do Gráfico** é exibido.</span><span class="sxs-lookup"><span data-stu-id="ce355-114">The **Chart Data** pane appears.</span></span>  
  
2.  <span data-ttu-id="ce355-115">Clique com o botão direito do mouse no grupo na área **Grupos de Categorias** e clique em **Propriedades de Grupo de Categorias**.</span><span class="sxs-lookup"><span data-stu-id="ce355-115">Right-click the group in the **Category Groups** area, and then click **Category Group Properties**.</span></span>  
  
3.  <span data-ttu-id="ce355-116">Adicione ou remova expressões de grupo, filtros, expressões de classificação e variáveis de grupo.</span><span class="sxs-lookup"><span data-stu-id="ce355-116">Add or remove group expressions, filters, sort expressions, and group variables.</span></span>  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-edit-a-series-group-on-a-chart"></a><span data-ttu-id="ce355-117">Para editar um grupo de séries em um gráfico</span><span class="sxs-lookup"><span data-stu-id="ce355-117">To edit a series group on a chart</span></span>  
  
1.  <span data-ttu-id="ce355-118">Na superfície de design de relatório, clique em qualquer lugar no gráfico para selecioná-lo.</span><span class="sxs-lookup"><span data-stu-id="ce355-118">On the report design surface, click anywhere in the chart to select it.</span></span> <span data-ttu-id="ce355-119">O painel **Dados do Gráfico** é exibido.</span><span class="sxs-lookup"><span data-stu-id="ce355-119">The **Chart Data** pane appears.</span></span>  
  
2.  <span data-ttu-id="ce355-120">Clique com o botão direito do mouse na área **Grupos de Séries** e clique em **Propriedades do Grupo de Séries**.</span><span class="sxs-lookup"><span data-stu-id="ce355-120">Right-click the group in the **Series Groups** area, and then click **Series Group Properties**.</span></span>  
  
3.  <span data-ttu-id="ce355-121">Adicione ou remova expressões de grupo, filtros, expressões de classificação e variáveis de grupo.</span><span class="sxs-lookup"><span data-stu-id="ce355-121">Add or remove group expressions, filters, sort expressions, and group variables.</span></span>  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-delete-a-group-from-a-chart"></a><span data-ttu-id="ce355-122">Para excluir um grupo de um gráfico</span><span class="sxs-lookup"><span data-stu-id="ce355-122">To delete a group from a chart</span></span>  
  
1.  <span data-ttu-id="ce355-123">Na superfície de design de relatório, clique em qualquer lugar no gráfico para selecioná-lo.</span><span class="sxs-lookup"><span data-stu-id="ce355-123">On the report design surface, click anywhere in the chart to select it.</span></span> <span data-ttu-id="ce355-124">O painel **Dados do Gráfico** é exibido.</span><span class="sxs-lookup"><span data-stu-id="ce355-124">The **Chart Data** pane appears.</span></span>  
  
2.  <span data-ttu-id="ce355-125">Clique com o botão direito do mouse no grupo na área **Grupos de Categorias** ou **Grupos de Séries** e clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="ce355-125">Right-click the group in the **Category Groups** or **Series Groups** area, and then click **Delete**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce355-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ce355-126">See Also</span></span>  
 [<span data-ttu-id="ce355-127">Gráficos &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="ce355-127">Charts &#40;Report Builder and SSRS&#41;</span></span>](charts-report-builder-and-ssrs.md)  
  
  
