---
title: Página escolher local do item (Report Manager) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 4a53a1a8-d1e1-47ef-b1fc-63352ece7d3c
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 82c044731552033ddd7fc0d8150cf83f300c7d9e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679188"
---
# <a name="choose-item-location-page-report-manager"></a><span data-ttu-id="c2699-102">Página Escolher local do item (Gerenciador de Relatórios)</span><span class="sxs-lookup"><span data-stu-id="c2699-102">Choose Item Location Page (Report Manager)</span></span>
  <span data-ttu-id="c2699-103">Use a página Escolher local do Item para selecionar uma pasta para um novo relatório ou um novo modelo vinculado.</span><span class="sxs-lookup"><span data-stu-id="c2699-103">Use the Choose Item Location page to select a folder for a new linked report or a new model.</span></span> <span data-ttu-id="c2699-104">Se você estiver criando um relatório ou um modelo vinculado para um grupo específico de usuários, coloque o item em uma pasta que contenha outros relatórios e modelos usados por eles.</span><span class="sxs-lookup"><span data-stu-id="c2699-104">If you are creating a linked report or a model for a specific group of users, you may want to place the item in a folder that contains other reports and models they use.</span></span> <span data-ttu-id="c2699-105">Você deve escolher uma pasta que já exista e para a qual você tenha permissão para adicionar conteúdo.</span><span class="sxs-lookup"><span data-stu-id="c2699-105">You must choose a folder that already exists and for which you have permission to add contents.</span></span>  
  
## <a name="navigation"></a><span data-ttu-id="c2699-106">Navegação</span><span class="sxs-lookup"><span data-stu-id="c2699-106">Navigation</span></span>  
 <span data-ttu-id="c2699-107">Use os procedimentos a seguir para navegar para este local na interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="c2699-107">Use the following procedures to navigate to this location in the user interface (UI).</span></span>  
  
###### <a name="to-open-the-choose-item-location-page-for-a-report"></a><span data-ttu-id="c2699-108">Para abrir a página Escolher Local do Item para um relatório</span><span class="sxs-lookup"><span data-stu-id="c2699-108">To open the Choose Item Location page for a report</span></span>  
  
1.  <span data-ttu-id="c2699-109">Abra o Gerenciador de Relatórios e localize o relatório para o qual você deseja adicionar um relatório vinculado.</span><span class="sxs-lookup"><span data-stu-id="c2699-109">Open Report Manager, and locate the report for which you want to add a linked report.</span></span>  
  
2.  <span data-ttu-id="c2699-110">Focalize o relatório e clique na seta do menu suspenso.</span><span class="sxs-lookup"><span data-stu-id="c2699-110">Hover over the report, and click the drop-down arrow.</span></span>  
  
3.  <span data-ttu-id="c2699-111">No menu suspenso, execute uma destas etapas:</span><span class="sxs-lookup"><span data-stu-id="c2699-111">In the drop-down menu, perform one of the following steps:</span></span>  
  
    -   <span data-ttu-id="c2699-112">Clique em **Criar Relatório Vinculado** para abrir a página Novo Relatório Vinculado.</span><span class="sxs-lookup"><span data-stu-id="c2699-112">Click **Create Linked Report** to open the New Linked Report page.</span></span>  
  
    -   <span data-ttu-id="c2699-113">Clique em **Gerenciar** para abrir a página Propriedades gerais do relatório.</span><span class="sxs-lookup"><span data-stu-id="c2699-113">Click **Manage** to open the General properties page for the report.</span></span> <span data-ttu-id="c2699-114">Em seguida, clique em **Criar Relatório Vinculado** para abrir a página Novo Relatório Vinculado.</span><span class="sxs-lookup"><span data-stu-id="c2699-114">Then click **Create Linked Report** to open the New Linked Report page.</span></span>  
  
4.  <span data-ttu-id="c2699-115">Na guia **Geral** , na página de propriedades, clique em **Alterar Local** para abrir a página Escolher Local do Item.</span><span class="sxs-lookup"><span data-stu-id="c2699-115">On the **General** tab, on the properties page, click **Change Location** to open the Choose Item Location page.</span></span>  
  
###### <a name="to-open-the-choose-item-location-page-for-a-model"></a><span data-ttu-id="c2699-116">Para abrir a página Escolher Local do Item de um modelo</span><span class="sxs-lookup"><span data-stu-id="c2699-116">To open the Choose Item Location page for a model</span></span>  
  
1.  <span data-ttu-id="c2699-117">Abra o Gerenciador de Relatórios e localize a fonte de dados para a qual você deseja adicionar um modelo.</span><span class="sxs-lookup"><span data-stu-id="c2699-117">Open Report Manager, and locate the data source for which you want to add a model.</span></span>  
  
2.  <span data-ttu-id="c2699-118">Focalize a fonte de dados e clique na seta para baixo.</span><span class="sxs-lookup"><span data-stu-id="c2699-118">Hover over the data source, and click the drop-down arrow.</span></span>  
  
3.  <span data-ttu-id="c2699-119">No menu suspenso, execute uma destas etapas:</span><span class="sxs-lookup"><span data-stu-id="c2699-119">In the drop-down menu, perform one of the following steps:</span></span>  
  
    -   <span data-ttu-id="c2699-120">Clique em **Gerar Modelo de Relatório** para abrir a página Novo Modelo.</span><span class="sxs-lookup"><span data-stu-id="c2699-120">Click **Generate Report Model** to open the New Model page.</span></span>  
  
    -   <span data-ttu-id="c2699-121">Clique em **Gerenciar** para abrir a página Propriedades gerais da fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="c2699-121">Click **Manage** to open the General properties page for the data source.</span></span> <span data-ttu-id="c2699-122">Em seguida, clique em **Gerar Modelo** para abrir a página Novo Modelo.</span><span class="sxs-lookup"><span data-stu-id="c2699-122">Then click **Generate Model** to open the New Model page.</span></span>  
  
4.  <span data-ttu-id="c2699-123">Na guia **Geral** , na página de propriedades, clique em **Alterar Local** para abrir a página Escolher Local do Item.</span><span class="sxs-lookup"><span data-stu-id="c2699-123">On the **General** tab, on the properties page, click **Change Location** to open the Choose Item Location page.</span></span>  
  
## <a name="options"></a><span data-ttu-id="c2699-124">Opções</span><span class="sxs-lookup"><span data-stu-id="c2699-124">Options</span></span>  
 <span data-ttu-id="c2699-125">**Localidade**</span><span class="sxs-lookup"><span data-stu-id="c2699-125">**Location**</span></span>  
 <span data-ttu-id="c2699-126">Especifique o nome da pasta que deve conter o item que você está criando.</span><span class="sxs-lookup"><span data-stu-id="c2699-126">Specify the name of the folder to contain the item you are creating.</span></span> <span data-ttu-id="c2699-127">É possível digitar o nome completo da pasta ou usar a exibição de árvore para navegar até a pasta desejada.</span><span class="sxs-lookup"><span data-stu-id="c2699-127">You can type the full name or use the tree view to navigate to the folder you want to use.</span></span>  
  
 <span data-ttu-id="c2699-128">**Modo de exibição de árvore**</span><span class="sxs-lookup"><span data-stu-id="c2699-128">**Tree view**</span></span>  
 <span data-ttu-id="c2699-129">Mostra a estrutura de pasta do namespace de servidor de relatórios.</span><span class="sxs-lookup"><span data-stu-id="c2699-129">Shows the folder structure of report server namespace.</span></span> <span data-ttu-id="c2699-130">Clique em um nome de pasta para adicionar o caminho completo até o campo **Local** .</span><span class="sxs-lookup"><span data-stu-id="c2699-130">Click a folder name to add the full path to the **Location** field.</span></span>  
  
 <span data-ttu-id="c2699-131">Clique nos ícones expandir  (+) e recolher (-) na exibição de árvore para abrir e fechar pastas sem adicionar os nomes das pastas ao campo **Local** .</span><span class="sxs-lookup"><span data-stu-id="c2699-131">Click the expand (+) and collapse (-) icons in the tree view to open and close folders without adding the folder names to the **Location** field.</span></span> <span data-ttu-id="c2699-132">Para adicionar um nome de pasta ao campo **Local** , clique no nome da pasta.</span><span class="sxs-lookup"><span data-stu-id="c2699-132">To add a folder name to the **Location** field, click the name of the folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2699-133">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c2699-133">See Also</span></span>  
 <span data-ttu-id="c2699-134">[Nova página de relatório vinculada &#40;Report Manager&#41;](../../2014/reporting-services/new-linked-report-page-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="c2699-134">[New Linked Report Page &#40;Report Manager&#41;](../../2014/reporting-services/new-linked-report-page-report-manager.md) </span></span>  
 <span data-ttu-id="c2699-135">[Nova página de modelo &#40;Report Manager&#41;](../../2014/reporting-services/new-model-page-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="c2699-135">[New Model Page &#40;Report Manager&#41;](../../2014/reporting-services/new-model-page-report-manager.md) </span></span>  
 [<span data-ttu-id="c2699-136">Ajuda F1 do Gerenciador de Relatórios</span><span class="sxs-lookup"><span data-stu-id="c2699-136">Report Manager F1 Help</span></span>](../../2014/reporting-services/report-manager-f1-help.md)  
  
  
