---
title: Warnings (Database Designer) (Analysis Services-dados multidimensionais) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.databasedesigner.warnings.f1
ms.assetid: 13f58b4d-f345-4fbc-ae2d-b3c8290a797d
author: minewiskan
ms.author: owend
ms.openlocfilehash: bf635460187fe56f4811de5090cada002ea8ca3b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572195"
---
# <a name="warnings-database-designer-analysis-services---multidimensional-data"></a><span data-ttu-id="51698-102">Avisos (Designer de Banco de Dados) (Analysis Services - Dados multidimensionais)</span><span class="sxs-lookup"><span data-stu-id="51698-102">Warnings (Database Designer) (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="51698-103">Use a guia **Avisos** para exibir e ignorar regras globalmente e para exibir e reabilitar instâncias específicas de avisos ignorados.</span><span class="sxs-lookup"><span data-stu-id="51698-103">Use the **Warnings** tab to view and dismiss rules globally, and to view and re-enable specific instances of dismissed warnings.</span></span> <span data-ttu-id="51698-104">A guia **Avisos** exibe duas grades: **Regras de Aviso de Design** e **Avisos Ignorados**.</span><span class="sxs-lookup"><span data-stu-id="51698-104">The **Warnings** tab displays two grids: **Design Warning Rules** and **Dismissed Warnings**.</span></span>  
  
 <span data-ttu-id="51698-105">**Para exibir a guia Avisos**</span><span class="sxs-lookup"><span data-stu-id="51698-105">**To display the Warnings tab**</span></span>  
  
1.  <span data-ttu-id="51698-106">No [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], abra um projeto do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="51698-106">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project.</span></span>  
  
2.  <span data-ttu-id="51698-107">No **Gerenciador de Soluções**, clique com o botão direito do mouse no projeto do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , clique em **Editar Banco de Dados**e então clique na guia **Avisos** .</span><span class="sxs-lookup"><span data-stu-id="51698-107">In **Solution Explorer**, right-click the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project, click **Edit Database**, and then click the **Warnings** tab.</span></span>  
  
## <a name="design-warning-rules-grid"></a><span data-ttu-id="51698-108">Grade de Regras de Aviso de Design</span><span class="sxs-lookup"><span data-stu-id="51698-108">Design Warning Rules Grid</span></span>  
 <span data-ttu-id="51698-109">A grade de **Regras de Aviso de Design** exibe todas as regras de aviso de design.</span><span class="sxs-lookup"><span data-stu-id="51698-109">The **Design Warning Rules** grid displays all the design warning rules.</span></span> <span data-ttu-id="51698-110">Esta grade também controla as regras que são habilitadas para o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="51698-110">This grid also controls which rules are enabled for the database.</span></span> <span data-ttu-id="51698-111">Para habilitar ou desabilitar uma regra de aviso, selecione ou desmarque sua caixa de seleção.</span><span class="sxs-lookup"><span data-stu-id="51698-111">To enable or disable a warning rule, select or clear its check box.</span></span>  
  
 <span data-ttu-id="51698-112">A grade **Regras de Aviso de Design** tem as seguintes colunas:</span><span class="sxs-lookup"><span data-stu-id="51698-112">The **Design Warning Rules** grid has the following columns:</span></span>  
  
 <span data-ttu-id="51698-113">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="51698-113">**Description**</span></span>  
 <span data-ttu-id="51698-114">Exibe o nome da regra.</span><span class="sxs-lookup"><span data-stu-id="51698-114">Displays the name of the rule.</span></span> <span data-ttu-id="51698-115">As regras são agrupadas por categoria.</span><span class="sxs-lookup"><span data-stu-id="51698-115">Rules are grouped by category.</span></span>  
  
 <span data-ttu-id="51698-116">**Importância**</span><span class="sxs-lookup"><span data-stu-id="51698-116">**Importance**</span></span>  
 <span data-ttu-id="51698-117">Exibe a importância atribuída à regra.</span><span class="sxs-lookup"><span data-stu-id="51698-117">Displays the importance assigned to the rule.</span></span>  
  
 <span data-ttu-id="51698-118">**Comentários**</span><span class="sxs-lookup"><span data-stu-id="51698-118">**Comments**</span></span>  
 <span data-ttu-id="51698-119">(Opcional) Permite ao usuário digitar um comentário que explica por que você está ignorando o aviso.</span><span class="sxs-lookup"><span data-stu-id="51698-119">(Optional) Allows the user to type a comment that explains why you are dismissing the warning.</span></span>  
  
## <a name="dismissed-warnings-grid"></a><span data-ttu-id="51698-120">Grade Avisos Ignorados</span><span class="sxs-lookup"><span data-stu-id="51698-120">Dismissed Warnings Grid</span></span>  
 <span data-ttu-id="51698-121">A grade **Avisos Ignorados** exibe todas as ocorrências de avisos específicos que foram ignorados na **Lista de Erros**.</span><span class="sxs-lookup"><span data-stu-id="51698-121">The **Dismissed Warnings** grid displays all specific warning occurrences that have been dismissed from the **Error List**.</span></span> <span data-ttu-id="51698-122">Para reabilitar um aviso, selecione-o na grade e clique em **Reabilitar**.</span><span class="sxs-lookup"><span data-stu-id="51698-122">To re-enable a warning, select it in the grid, and then click **Re-enable**.</span></span>  
  
 <span data-ttu-id="51698-123">A grade **Avisos Ignorados** tem o seguinte conteúdo:</span><span class="sxs-lookup"><span data-stu-id="51698-123">The **Dismissed Warnings** grid has the following :</span></span>  
  
 <span data-ttu-id="51698-124">**Objeto**</span><span class="sxs-lookup"><span data-stu-id="51698-124">**Object**</span></span>  
 <span data-ttu-id="51698-125">Exibe um ícone que representa o tipo de objeto e o nome do objeto.</span><span class="sxs-lookup"><span data-stu-id="51698-125">Displays an icon that represents the object type and the object name.</span></span>  
  
 <span data-ttu-id="51698-126">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="51698-126">**Type**</span></span>  
 <span data-ttu-id="51698-127">Exibe o tipo de objeto.</span><span class="sxs-lookup"><span data-stu-id="51698-127">Displays the object type.</span></span>  
  
 <span data-ttu-id="51698-128">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="51698-128">**Description**</span></span>  
 <span data-ttu-id="51698-129">Exibe o nome da regra.</span><span class="sxs-lookup"><span data-stu-id="51698-129">Displays the name of the rule.</span></span>  
  
 <span data-ttu-id="51698-130">**Importância**</span><span class="sxs-lookup"><span data-stu-id="51698-130">**Importance**</span></span>  
 <span data-ttu-id="51698-131">Exibe a importância atribuída à regra.</span><span class="sxs-lookup"><span data-stu-id="51698-131">Displays the importance assigned to the rule.</span></span>  
  
 <span data-ttu-id="51698-132">**Comentários**</span><span class="sxs-lookup"><span data-stu-id="51698-132">**Comments**</span></span>  
 <span data-ttu-id="51698-133">Exibe o comentário que foi digitado quando o aviso foi ignorado.</span><span class="sxs-lookup"><span data-stu-id="51698-133">Displays the comment that was entered when the warning was dismissed.</span></span> <span data-ttu-id="51698-134">Você pode adicionar ou modificar um comentário aqui.</span><span class="sxs-lookup"><span data-stu-id="51698-134">You can add or modify a comment here.</span></span>  
  
 <span data-ttu-id="51698-135">**Reabilitar**</span><span class="sxs-lookup"><span data-stu-id="51698-135">**Re-enable**</span></span>  
 <span data-ttu-id="51698-136">Reabilita os avisos selecionados.</span><span class="sxs-lookup"><span data-stu-id="51698-136">Re-enables the selected warnings.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="51698-137">Se um objeto tiver um aviso, mas o objeto estiver em um estado inválido ou tiver sido manualmente removido do projeto, um ícone de erro aparecerá próximo ao aviso na lista.</span><span class="sxs-lookup"><span data-stu-id="51698-137">If an object has a warning, but the object is in an invalid state or was manually removed from the project, an error icon appears next to the warning in the list.</span></span> <span data-ttu-id="51698-138">Para ignorar o aviso, selecione-o e clique em **Reabilitar**.</span><span class="sxs-lookup"><span data-stu-id="51698-138">To dismiss the warning, select it and then click **Re-enable**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51698-139">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="51698-139">See Also</span></span>  
 <span data-ttu-id="51698-140">[Caixa de diálogo ignorar aviso &#40;Analysis Services de dados multidimensionais&#41;](dismiss-warning-dialog-box-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="51698-140">[Dismiss Warning Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](dismiss-warning-dialog-box-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="51698-141">Geral &#40;designer de banco de dados&#41; &#40;Analysis Services-dados multidimensionais&#41;</span><span class="sxs-lookup"><span data-stu-id="51698-141">General &#40;Database Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;</span></span>](general-database-designer-analysis-services-multidimensional-data.md)  
  
  
