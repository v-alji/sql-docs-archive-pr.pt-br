---
title: Página itens dependentes (Report Manager) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 4dcfb311-e9c3-4c5d-b2e0-018d79f37d2e
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 488b10d7d7985972274340897ee3975618a12639
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570536"
---
# <a name="dependent-items-page-report-manager"></a><span data-ttu-id="fe0a9-102">Página Itens Dependentes (Gerenciador de Relatórios)</span><span class="sxs-lookup"><span data-stu-id="fe0a9-102">Dependent Items Page (Report Manager)</span></span>
  <span data-ttu-id="fe0a9-103">Use a página Itens Dependentes para exibir uma lista de relatórios e modelos que referenciam uma fonte de dados compartilhada.</span><span class="sxs-lookup"><span data-stu-id="fe0a9-103">Use the Dependent Items page to view a list of reports and models that reference a shared data source.</span></span> <span data-ttu-id="fe0a9-104">O ícone para cada tipo de item indica se é um relatório ou um modelo.</span><span class="sxs-lookup"><span data-stu-id="fe0a9-104">The icon for each item type indicates whether it is a report or a model.</span></span> <span data-ttu-id="fe0a9-105">Essa página pode ser exibida em exibição de lista ou exibição de detalhes.</span><span class="sxs-lookup"><span data-stu-id="fe0a9-105">This page can be viewed in list view or details view.</span></span> <span data-ttu-id="fe0a9-106">Use exibição de detalhes para mostrar mais informações sobre cada item.</span><span class="sxs-lookup"><span data-stu-id="fe0a9-106">Use details view to show more information about each item.</span></span> <span data-ttu-id="fe0a9-107">Opções adicionais de página estão disponíveis na exibição de detalhes.</span><span class="sxs-lookup"><span data-stu-id="fe0a9-107">Additional page options are available in details view.</span></span> <span data-ttu-id="fe0a9-108">Para ajudar a gerenciar a fonte de dados compartilhada, essa página fornece links para relatórios e modelos que usam a fonte de dados, métricas de quando o relatório ou modelo foi executado ou modificado pela última vez e botões Excluir e Mover para que você possa facilmente remover relatórios e modelos que não são mais usados ou movê-los para um local diferente enquanto determina se eles ainda serão necessários.</span><span class="sxs-lookup"><span data-stu-id="fe0a9-108">To help you manage the shared data source, this page provides links to reports and models that use the data source, metrics on when the report or model was last run or modified, and Delete and Move buttons so that you can easily remove reports and models that are no longer used, or move them to a different location while you determine whether they are still needed.</span></span>  
  
## <a name="navigation"></a><span data-ttu-id="fe0a9-109">Navegação</span><span class="sxs-lookup"><span data-stu-id="fe0a9-109">Navigation</span></span>  
 <span data-ttu-id="fe0a9-110">Use o procedimento a seguir para navegar para este local na interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="fe0a9-110">Use the following procedure to navigate to this location in the user interface (UI).</span></span>  
  
###### <a name="to-open-the-dependent-items-page"></a><span data-ttu-id="fe0a9-111">Para abrir a página Itens Dependentes</span><span class="sxs-lookup"><span data-stu-id="fe0a9-111">To open the Dependent Items page</span></span>  
  
1.  <span data-ttu-id="fe0a9-112">Abra o Gerenciador de Relatórios e localize a fonte de dados compartilhada cujos itens dependentes você deseja exibir.</span><span class="sxs-lookup"><span data-stu-id="fe0a9-112">Open Report Manager, and locate the shared data source for which you want to view dependent items.</span></span>  
  
2.  <span data-ttu-id="fe0a9-113">Focalize o item e clique na seta do menu suspenso.</span><span class="sxs-lookup"><span data-stu-id="fe0a9-113">Hover over the item, and click the drop-down arrow.</span></span>  
  
3.  <span data-ttu-id="fe0a9-114">No menu suspenso, clique em **Gerenciar**.</span><span class="sxs-lookup"><span data-stu-id="fe0a9-114">In the drop-down menu, click **Manage**.</span></span> <span data-ttu-id="fe0a9-115">Esse procedimento abre a página Propriedades gerais da fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="fe0a9-115">This opens the General properties page for the data source.</span></span>  
  
4.  <span data-ttu-id="fe0a9-116">Selecione a guia **Itens Dependentes** .</span><span class="sxs-lookup"><span data-stu-id="fe0a9-116">Select the **Dependent Items** tab.</span></span>  
  
## <a name="options"></a><span data-ttu-id="fe0a9-117">Opções</span><span class="sxs-lookup"><span data-stu-id="fe0a9-117">Options</span></span>  
 <span data-ttu-id="fe0a9-118">**Nome**</span><span class="sxs-lookup"><span data-stu-id="fe0a9-118">**Name**</span></span>  
 <span data-ttu-id="fe0a9-119">Mostra o nome do relatório ou modelo.</span><span class="sxs-lookup"><span data-stu-id="fe0a9-119">Shows the name of the report or model.</span></span> <span data-ttu-id="fe0a9-120">Clique no nome do relatório para abri-lo.</span><span class="sxs-lookup"><span data-stu-id="fe0a9-120">Click the name of the report to open it.</span></span> <span data-ttu-id="fe0a9-121">Clique no nome do modelo para abrir suas páginas de propriedades.</span><span class="sxs-lookup"><span data-stu-id="fe0a9-121">Click the name of the model to open its property pages.</span></span>  
  
 <span data-ttu-id="fe0a9-122">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="fe0a9-122">**Description**</span></span>  
 <span data-ttu-id="fe0a9-123">Exibe a descrição do relatório ou modelo.</span><span class="sxs-lookup"><span data-stu-id="fe0a9-123">Shows the description of the report or model.</span></span>  
  
 <span data-ttu-id="fe0a9-124">**Excluir**</span><span class="sxs-lookup"><span data-stu-id="fe0a9-124">**Delete**</span></span>  
 <span data-ttu-id="fe0a9-125">Clique para excluir o relatório ou o modelo do banco de dados do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="fe0a9-125">Click to delete the report or model from the report server database.</span></span> <span data-ttu-id="fe0a9-126">Antes de clicar em **Excluir**, marque a caixa de seleção ao lado de cada item que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="fe0a9-126">Before clicking **Delete**, select the check box next to each item that you want to delete.</span></span>  
  
 <span data-ttu-id="fe0a9-127">**Mover**</span><span class="sxs-lookup"><span data-stu-id="fe0a9-127">**Move**</span></span>  
 <span data-ttu-id="fe0a9-128">Clique para realocar um relatório ou modelo dentro da hierarquia de pasta.</span><span class="sxs-lookup"><span data-stu-id="fe0a9-128">Click to relocate a report or model within the folder hierarchy.</span></span> <span data-ttu-id="fe0a9-129">Antes de clicar em **Mover**, marque a caixa de seleção próximo a cada item que você deseja mover.</span><span class="sxs-lookup"><span data-stu-id="fe0a9-129">Before clicking **Move**, select the check box next to each item that you want to move.</span></span> <span data-ttu-id="fe0a9-130">Isso abre a página Mover Itens, onde você pode navegar pelas pastas para selecionar um local novo.</span><span class="sxs-lookup"><span data-stu-id="fe0a9-130">This opens the Move Items page, where you can browse through folders to select a new location.</span></span>  
  
 <span data-ttu-id="fe0a9-131">**Editar**</span><span class="sxs-lookup"><span data-stu-id="fe0a9-131">**Edit**</span></span>  
 <span data-ttu-id="fe0a9-132">Clique no ícone Propriedade para acessar as páginas de propriedades de um relatório ou modelo.</span><span class="sxs-lookup"><span data-stu-id="fe0a9-132">Click the Property icon to access the property pages of a report, or model.</span></span>  
  
 <span data-ttu-id="fe0a9-133">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="fe0a9-133">**Type**</span></span>  
 <span data-ttu-id="fe0a9-134">Exibe o ícone do tipo de item.</span><span class="sxs-lookup"><span data-stu-id="fe0a9-134">Shows the icon of the item type.</span></span>  
  
 <span data-ttu-id="fe0a9-135">**Data de Modificação**</span><span class="sxs-lookup"><span data-stu-id="fe0a9-135">**Modified Date**</span></span>  
 <span data-ttu-id="fe0a9-136">Exibe a data e hora em que o relatório ou modelo foram modificados pela última vez.</span><span class="sxs-lookup"><span data-stu-id="fe0a9-136">Shows the date and time when the report or model was last modified.</span></span>  
  
 <span data-ttu-id="fe0a9-137">**Modificado por**</span><span class="sxs-lookup"><span data-stu-id="fe0a9-137">**Modified By**</span></span>  
 <span data-ttu-id="fe0a9-138">Mostra o nome do usuário que modificou por último as propriedades do item.</span><span class="sxs-lookup"><span data-stu-id="fe0a9-138">Shows the name of the user who last modified the item properties.</span></span>  
  
 <span data-ttu-id="fe0a9-139">**Quando Executado**</span><span class="sxs-lookup"><span data-stu-id="fe0a9-139">**When Run**</span></span>  
 <span data-ttu-id="fe0a9-140">Para relatórios executados como instantâneos de execução de relatório, exibe a data e hora da última atualização do relatório.</span><span class="sxs-lookup"><span data-stu-id="fe0a9-140">For reports that run as report execution snapshots, displays the date and time at which the report was last refreshed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe0a9-141">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="fe0a9-141">See Also</span></span>  
 <span data-ttu-id="fe0a9-142">[Ajuda F1 Report Manager](../../2014/reporting-services/report-manager-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="fe0a9-142">[Report Manager F1 Help](../../2014/reporting-services/report-manager-f1-help.md) </span></span>  
 <span data-ttu-id="fe0a9-143">[Gerenciador de Relatórios &#40;Modo Nativo do SSRS&#41;](../../2014/reporting-services/report-manager-ssrs-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="fe0a9-143">[Report Manager  &#40;SSRS Native Mode&#41;](../../2014/reporting-services/report-manager-ssrs-native-mode.md) </span></span>  
 <span data-ttu-id="fe0a9-144">[Página de conteúdo &#40;Report Manager&#41;](../../2014/reporting-services/contents-page-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="fe0a9-144">[Contents Page &#40;Report Manager&#41;](../../2014/reporting-services/contents-page-report-manager.md) </span></span>  
 [<span data-ttu-id="fe0a9-145">Ajuda F1 do Gerenciador de Relatórios</span><span class="sxs-lookup"><span data-stu-id="fe0a9-145">Report Manager F1 Help</span></span>](../../2014/reporting-services/report-manager-f1-help.md)  
  
  
