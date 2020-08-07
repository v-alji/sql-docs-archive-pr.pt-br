---
title: Ocultar ou excluir níveis em uma hierarquia derivada (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- derived hierarchies, hiding levels
- derived hierarchies, deleting levels
ms.assetid: e00582b9-9415-4b66-b4a7-9f590d83875f
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 039b05633bcd1fdc69d226e565b3dc5211e9734f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575187"
---
# <a name="hide-or-delete-levels-in-a-derived-hierarchy-master-data-services"></a><span data-ttu-id="a21f4-102">Ocultar ou excluir níveis em uma hierarquia derivada (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="a21f4-102">Hide or Delete Levels in a Derived Hierarchy (Master Data Services)</span></span>
  <span data-ttu-id="a21f4-103">No [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], oculte um nível em uma hierarquia derivada quando você precisar agrupar o nível, mas não for necessário mostrar o nível.</span><span class="sxs-lookup"><span data-stu-id="a21f4-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], hide a level in a derived hierarchy when you require the level for grouping but you do not need to show the level.</span></span> <span data-ttu-id="a21f4-104">Exclua um nível quando você não quiser usá-lo para agrupamento.</span><span class="sxs-lookup"><span data-stu-id="a21f4-104">Delete a level when you do not want to use it for grouping.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="a21f4-105">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="a21f4-105">Prerequisites</span></span>  
 <span data-ttu-id="a21f4-106">Para executar esse procedimento:</span><span class="sxs-lookup"><span data-stu-id="a21f4-106">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="a21f4-107">Você deve ter permissão para acessar a área funcional **Administração do sistema** .</span><span class="sxs-lookup"><span data-stu-id="a21f4-107">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="a21f4-108">Você deve ser um administrador de modelo.</span><span class="sxs-lookup"><span data-stu-id="a21f4-108">You must be a model administrator.</span></span> <span data-ttu-id="a21f4-109">Para obter mais informações, consulte [administradores &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="a21f4-109">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-hide-or-delete-levels-in-a-derived-hierarchy"></a><span data-ttu-id="a21f4-110">Para ocultar ou excluir níveis em uma hierarquia derivada</span><span class="sxs-lookup"><span data-stu-id="a21f4-110">To hide or delete levels in a derived hierarchy</span></span>  
  
1.  <span data-ttu-id="a21f4-111">No [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], clique em **Administração do Sistema**.</span><span class="sxs-lookup"><span data-stu-id="a21f4-111">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="a21f4-112">Na página **exibição de modelo** , na barra de menus, aponte para **gerenciar** e clique em **hierarquias derivadas**.</span><span class="sxs-lookup"><span data-stu-id="a21f4-112">On the **Model View** page, from the menu bar, point to **Manage** and click **Derived Hierarchies**.</span></span>  
  
3.  <span data-ttu-id="a21f4-113">Na página **Manutenção da Hierarquia Derivada** , na lista **Modelo** , selecione um modelo.</span><span class="sxs-lookup"><span data-stu-id="a21f4-113">On the **Derived Hierarchy Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="a21f4-114">Selecione a linha da hierarquia derivada que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="a21f4-114">Select the row for the derived hierarchy you want to edit.</span></span>  
  
5.  <span data-ttu-id="a21f4-115">Clique em **Editar hierarquia derivada selecionada**.</span><span class="sxs-lookup"><span data-stu-id="a21f4-115">Click **Edit selected derived hierarchy**.</span></span>  
  
6.  <span data-ttu-id="a21f4-116">No painel **Níveis Atuais** :</span><span class="sxs-lookup"><span data-stu-id="a21f4-116">In the **Current Levels** pane:</span></span>  
  
    -   <span data-ttu-id="a21f4-117">Para ocultar um nível, clique em um nível sem ser o superior ou o inferior.</span><span class="sxs-lookup"><span data-stu-id="a21f4-117">To hide a level, click a level other than the top or bottom.</span></span> <span data-ttu-id="a21f4-118">Na lista **Visível** , selecione **Não**.</span><span class="sxs-lookup"><span data-stu-id="a21f4-118">From the **Visible** list, select **No**.</span></span> <span data-ttu-id="a21f4-119">Em seguida, clique em **Salvar item de hierarquia selecionado**.</span><span class="sxs-lookup"><span data-stu-id="a21f4-119">Then click **Save selected hierarchy item**.</span></span>  
  
    -   <span data-ttu-id="a21f4-120">Para excluir o nível superior, clique em **Excluir item de hierarquia selecionado**.</span><span class="sxs-lookup"><span data-stu-id="a21f4-120">To delete the top level, click **Delete selected hierarchy item**.</span></span> <span data-ttu-id="a21f4-121">Na caixa de diálogo de confirmação, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="a21f4-121">In the confirmation dialog box, click **OK**.</span></span> <span data-ttu-id="a21f4-122">Somente é possível excluir o nível superior.</span><span class="sxs-lookup"><span data-stu-id="a21f4-122">You can delete the top level only.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a21f4-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a21f4-123">See Also</span></span>  
 <span data-ttu-id="a21f4-124">[Mover membros dentro de uma hierarquia &#40;Master Data Services&#41;](../../2014/master-data-services/move-members-within-a-hierarchy-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="a21f4-124">[Move Members within a Hierarchy &#40;Master Data Services&#41;](../../2014/master-data-services/move-members-within-a-hierarchy-master-data-services.md) </span></span>  
 [<span data-ttu-id="a21f4-125">Hierarquias derivadas &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="a21f4-125">Derived Hierarchies &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/derived-hierarchies-master-data-services.md)  
  
  
