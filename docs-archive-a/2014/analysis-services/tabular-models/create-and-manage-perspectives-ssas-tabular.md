---
title: Criar e gerenciar perspectivas (SSAS tabular) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.perspectivedb.f1
ms.assetid: 2a411c2b-2820-4086-ad7f-ce6a941fefc7
author: minewiskan
ms.author: owend
ms.openlocfilehash: 6d0029ff61aa05e2e83f34833c3d0af17ddb3beb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570301"
---
# <a name="create-and-manage-perspectives-ssas-tabular"></a><span data-ttu-id="51879-102">Criar e Gerenciar Perspectivas (SSAS tabular)</span><span class="sxs-lookup"><span data-stu-id="51879-102">Create and Manage Perspectives (SSAS Tabular)</span></span>
  <span data-ttu-id="51879-103">As perspectivas definem subconjuntos visíveis de um modelo que fornece pontos de vista concentrados, específicos à empresa ou específicos ao aplicativo.</span><span class="sxs-lookup"><span data-stu-id="51879-103">Perspectives define viewable subsets of a model that provide focused, business-specific, or application-specific viewpoints of the model.</span></span> <span data-ttu-id="51879-104">As tarefas neste tópico descrevem como criar e gerenciar perspectivas usando a caixa de diálogo **Perspectivas** no designer modelo.</span><span class="sxs-lookup"><span data-stu-id="51879-104">The tasks in this topic describe how to create and manage perspectives by using the **Perspectives** dialog box in the model designer.</span></span>  
  
 <span data-ttu-id="51879-105">Este tópico inclui as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="51879-105">This topic includes the following tasks:</span></span>  
  
-   [<span data-ttu-id="51879-106">Para adicionar uma perspectiva</span><span class="sxs-lookup"><span data-stu-id="51879-106">To add a perspective</span></span>](#bkmk_add)  
  
-   [<span data-ttu-id="51879-107">Para editar uma perspectiva</span><span class="sxs-lookup"><span data-stu-id="51879-107">To edit a perspective</span></span>](#bkmk_edit)  
  
-   [<span data-ttu-id="51879-108">Para renomear uma perspectiva</span><span class="sxs-lookup"><span data-stu-id="51879-108">To rename a perspective</span></span>](#bkmk_rename)  
  
-   [<span data-ttu-id="51879-109">Para excluir uma perspectiva</span><span class="sxs-lookup"><span data-stu-id="51879-109">To delete a perspective</span></span>](#bkmk_delete)  
  
-   [<span data-ttu-id="51879-110">Para copiar uma perspectiva</span><span class="sxs-lookup"><span data-stu-id="51879-110">To copy a perspective</span></span>](#bkmk_copy)  
  
## <a name="tasks"></a><span data-ttu-id="51879-111">Tarefas</span><span class="sxs-lookup"><span data-stu-id="51879-111">Tasks</span></span>  
 <span data-ttu-id="51879-112">Para criar perspectivas, você usará a caixa de diálogo **Criar e Gerenciar Perspectivas** , onde você pode adicionar, editar, excluir, copiar e exibir perspectivas.</span><span class="sxs-lookup"><span data-stu-id="51879-112">To create perspectives, you will use the **Perspectives** dialog box, where you can add, edit, delete, copy, and view perspectives.</span></span> <span data-ttu-id="51879-113">Para exibir a caixa de diálogo **Perspectivas** , no [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], clique no menu **Modelo** e clique em **Perspectivas**.</span><span class="sxs-lookup"><span data-stu-id="51879-113">To view the **Perspectives** dialog box, in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], click on the **Model** menu, and then click **Perspectives**.</span></span>  
  
###  <a name="to-add-a-perspective"></a><a name="bkmk_add"></a> <span data-ttu-id="51879-114">Para adicionar uma perspectiva</span><span class="sxs-lookup"><span data-stu-id="51879-114">To add a perspective</span></span>  
  
-   <span data-ttu-id="51879-115">Para adicionar uma nova perspectiva, clique em **Nova Perspectiva**.</span><span class="sxs-lookup"><span data-stu-id="51879-115">To add a new perspective, click **New Perspective**.</span></span> <span data-ttu-id="51879-116">É possível marcar e desmarcar os objetos de campo a serem incluídos e fornecer um nome à nova perspectiva.</span><span class="sxs-lookup"><span data-stu-id="51879-116">You can then check and uncheck field objects to be included and provide a name for the new perspective.</span></span>  
  
     <span data-ttu-id="51879-117">Se você criar uma perspectiva vazia com todos os campos de objeto, um usuário que usa essa perspectiva verá uma Lista de Campos vazia.</span><span class="sxs-lookup"><span data-stu-id="51879-117">If you create an empty perspective with all of the field object fields, then a user using this perspective will see an empty Field List.</span></span> <span data-ttu-id="51879-118">Perspectivas devem conter pelo menos uma tabela e coluna.</span><span class="sxs-lookup"><span data-stu-id="51879-118">Perspectives should contain at least one table and column.</span></span>  
  
###  <a name="to-edit-a-perspective"></a><a name="bkmk_edit"></a><span data-ttu-id="51879-119">Para editar uma perspectiva</span><span class="sxs-lookup"><span data-stu-id="51879-119">To edit a perspective</span></span>  
  
-   <span data-ttu-id="51879-120">Para modificar uma perspectiva, marque e desmarque os campos na coluna da perspectiva, que adiciona e remove objetos de campo da perspectiva.</span><span class="sxs-lookup"><span data-stu-id="51879-120">To modify a perspective, check and uncheck fields in the perspective's column, which adds and removes field objects from the perspective.</span></span>  
  
###  <a name="to-rename-a-perspective"></a><a name="bkmk_rename"></a><span data-ttu-id="51879-121">Para renomear uma perspectiva</span><span class="sxs-lookup"><span data-stu-id="51879-121">To rename a perspective</span></span>  
  
-   <span data-ttu-id="51879-122">Quando você passa o mouse sobre o cabeçalho da coluna de uma perspectiva (o nome da perspectiva), o botão **renomear** é exibido.</span><span class="sxs-lookup"><span data-stu-id="51879-122">When you hover over a perspective's column header (the name of the perspective), the **Rename** button appears.</span></span> <span data-ttu-id="51879-123">Para renomear a perspectiva, clique em **Renomear**e insira um novo nome ou edite o nome existente.</span><span class="sxs-lookup"><span data-stu-id="51879-123">To rename the perspective, click **Rename**, and then enter a new name or edit the existing name.</span></span>  
  
###  <a name="to-delete-a-perspective"></a><a name="bkmk_delete"></a><span data-ttu-id="51879-124">Para excluir uma perspectiva</span><span class="sxs-lookup"><span data-stu-id="51879-124">To delete a perspective</span></span>  
  
-   <span data-ttu-id="51879-125">Quando você passa o mouse sobre o cabeçalho da coluna de uma perspectiva (o nome da perspectiva), o botão **excluir** é exibido.</span><span class="sxs-lookup"><span data-stu-id="51879-125">When you hover over a perspective's column header (the name of the perspective), the **Delete** button appears.</span></span> <span data-ttu-id="51879-126">Para excluir a perspectiva, clique no botão **Excluir** e clique em **Sim** na janela de confirmação.</span><span class="sxs-lookup"><span data-stu-id="51879-126">To delete the perspective, click the **Delete** button, and then click **Yes** in the confirmation window.</span></span>  
  
###  <a name="to-copy-a-perspective"></a><a name="bkmk_copy"></a><span data-ttu-id="51879-127">Para copiar uma perspectiva</span><span class="sxs-lookup"><span data-stu-id="51879-127">To copy a perspective</span></span>  
  
-   <span data-ttu-id="51879-128">Quando você passa o mouse sobre o cabeçalho da coluna de uma perspectiva, o botão **copiar** é exibido.</span><span class="sxs-lookup"><span data-stu-id="51879-128">When you hover over a perspective's column header, the **Copy** button appears.</span></span> <span data-ttu-id="51879-129">Para criar uma cópia dessa perspectiva, clique no botão **Copiar** .</span><span class="sxs-lookup"><span data-stu-id="51879-129">To create a copy of that perspective, click the **Copy** button.</span></span> <span data-ttu-id="51879-130">Uma cópia da perspectiva selecionada é adicionada como uma nova perspectiva à direita das perspectivas existentes.</span><span class="sxs-lookup"><span data-stu-id="51879-130">A copy of the selected perspective is added as a new perspective to the right of existing perspectives.</span></span> <span data-ttu-id="51879-131">A nova perspectiva herda o nome da perspectiva copiada e uma anotação *- Copiar* é acrescentada ao final do nome.</span><span class="sxs-lookup"><span data-stu-id="51879-131">The new perspective inherits the name of the copied perspective and a *- Copy* annotation is appended to the end of the name.</span></span> <span data-ttu-id="51879-132">Por exemplo, se uma cópia da perspectiva de *vendas* for criada, a nova perspectiva será chamada de *cópia de vendas*.</span><span class="sxs-lookup"><span data-stu-id="51879-132">For example, if a copy of the *Sales* perspective is created, the new perspective is called *Sales - Copy*.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51879-133">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="51879-133">See Also</span></span>  
 <span data-ttu-id="51879-134">[Perspectivas &#40;SSAS de tabela&#41;](perspectives-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="51879-134">[Perspectives &#40;SSAS Tabular&#41;](perspectives-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="51879-135">Hierarquias &#40;SSAS de Tabela&#41;</span><span class="sxs-lookup"><span data-stu-id="51879-135">Hierarchies &#40;SSAS Tabular&#41;</span></span>](hierarchies-ssas-tabular.md)  
  
  
