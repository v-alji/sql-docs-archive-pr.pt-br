---
title: Página de pesquisa (Report Manager) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 51ffdc07-e1b9-4ed7-acb3-dd98d7cce273
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2528133f5b2ecc4bed4c16fdd476591b3bab52d2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574492"
---
# <a name="search-page-report-manager"></a><span data-ttu-id="832cc-102">Página Pesquisa (Gerenciador de Relatórios)</span><span class="sxs-lookup"><span data-stu-id="832cc-102">Search Page (Report Manager)</span></span>
  <span data-ttu-id="832cc-103">Use a página Resultados da Pesquisa para exibir os resultados de uma operação de pesquisa especificada para um relatório, relatório vinculado, modelo de relatório, fonte de dados compartilhada, pasta ou recurso.</span><span class="sxs-lookup"><span data-stu-id="832cc-103">Use the Search Results page to view the results of a search operation specified for a report, linked report, report model, shared data source, folder, or resource.</span></span> <span data-ttu-id="832cc-104">Os resultados da pesquisa são listados em ordem alfabética.</span><span class="sxs-lookup"><span data-stu-id="832cc-104">Search results are listed alphabetically.</span></span> <span data-ttu-id="832cc-105">Você pode classificar por tipo, nome ou descrição.</span><span class="sxs-lookup"><span data-stu-id="832cc-105">You can sort by type, name, or description.</span></span>  
  
 <span data-ttu-id="832cc-106">Os itens a seguir são excluídos de uma operação de pesquisa: instantâneos de relatório contidos em histórico de relatório, assinatura e agendas compartilhadas.</span><span class="sxs-lookup"><span data-stu-id="832cc-106">The following items are excluded from a search operation: report snapshots contained in report history, subscriptions, and shared schedules.</span></span> <span data-ttu-id="832cc-107">Da mesma forma, permissão não adequada para exibir uma pasta ou um relatório exclui aquele item de uma pesquisa.</span><span class="sxs-lookup"><span data-stu-id="832cc-107">Similarly, insufficient permission to view a folder or report excludes that item from a search.</span></span>  
  
 <span data-ttu-id="832cc-108">Você não pode procurar texto dentro de um relatório ou modelo.</span><span class="sxs-lookup"><span data-stu-id="832cc-108">You cannot search for text within a report or model.</span></span> <span data-ttu-id="832cc-109">Para procurar um texto específico em um relatório, use a barra de ferramentas na parte superior do relatório.</span><span class="sxs-lookup"><span data-stu-id="832cc-109">To search for specific text within a report, use the toolbar at the top of the report.</span></span>  
  
## <a name="navigation"></a><span data-ttu-id="832cc-110">Navegação</span><span class="sxs-lookup"><span data-stu-id="832cc-110">Navigation</span></span>  
 <span data-ttu-id="832cc-111">Use o procedimento a seguir para navegar para este local na interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="832cc-111">Use the following procedure to navigate to this location in the user interface (UI).</span></span>  
  
###### <a name="to-open-the-search-results-page"></a><span data-ttu-id="832cc-112">Para abrir a página Resultados da Pesquisa</span><span class="sxs-lookup"><span data-stu-id="832cc-112">To open the Search Results page</span></span>  
  
1.  <span data-ttu-id="832cc-113">Abra o Gerenciador de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="832cc-113">Open Report Manager.</span></span>  
  
2.  <span data-ttu-id="832cc-114">Na parte superior da página, digite os critérios de pesquisa na caixa **Pesquisar**.</span><span class="sxs-lookup"><span data-stu-id="832cc-114">At the top of the page, type your search criteria in the **Search** box.</span></span> <span data-ttu-id="832cc-115">Em seguida, pressione Enter ou clique na seta Pesquisar.</span><span class="sxs-lookup"><span data-stu-id="832cc-115">Then press Enter or click the Search arrow.</span></span>  
  
## <a name="options"></a><span data-ttu-id="832cc-116">Opções</span><span class="sxs-lookup"><span data-stu-id="832cc-116">Options</span></span>  
 <span data-ttu-id="832cc-117">**Excluir**</span><span class="sxs-lookup"><span data-stu-id="832cc-117">**Delete**</span></span>  
 <span data-ttu-id="832cc-118">Clique para remover um item de um banco de dados do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="832cc-118">Click to remove an item from a report server database.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="832cc-119">Este botão só está disponível em **Exibição de Detalhes**.</span><span class="sxs-lookup"><span data-stu-id="832cc-119">This button is available only in **Details View**.</span></span> <span data-ttu-id="832cc-120">Porém, você pode focalizar um item e usar o menu para acessar a funcionalidade de exclusão em **Exibição de Detalhes** ou em **Exibição de Lista**.</span><span class="sxs-lookup"><span data-stu-id="832cc-120">However, you can hover over an item and use the menu to access the delete functionality in either **Details View** or in **List View**.</span></span>  
  
 <span data-ttu-id="832cc-121">**Mover**</span><span class="sxs-lookup"><span data-stu-id="832cc-121">**Move**</span></span>  
 <span data-ttu-id="832cc-122">Clique para realocar um item.</span><span class="sxs-lookup"><span data-stu-id="832cc-122">Click to relocate an item.</span></span> <span data-ttu-id="832cc-123">Isso abre a página Mover Itens, onde você pode selecionar um local de pasta diferente.</span><span class="sxs-lookup"><span data-stu-id="832cc-123">This opens the Move Items page, where you can select a different folder location.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="832cc-124">Este botão só está disponível em **Exibição de Detalhes**.</span><span class="sxs-lookup"><span data-stu-id="832cc-124">This button is available only in **Details View**.</span></span> <span data-ttu-id="832cc-125">Porém, você pode focalizar um item e usar o menu para acessar a funcionalidade de movimentação em **Exibição de Detalhes** ou em **Exibição de Lista**.</span><span class="sxs-lookup"><span data-stu-id="832cc-125">However, you can hover over an item and use the menu to access the move functionality in either **Details View** or in **List View**.</span></span>  
  
 <span data-ttu-id="832cc-126">Caixa de pesquisa</span><span class="sxs-lookup"><span data-stu-id="832cc-126">Search box</span></span>  
 <span data-ttu-id="832cc-127">Digite todo ou parte do nome de um item que você deseja localizar e clique em **Ir** para iniciar a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="832cc-127">Type all or part of the name of an item that you want to locate, and then click **Go** to start the search.</span></span> <span data-ttu-id="832cc-128">A cadeia de caracteres mais longa que você pode pesquisar é de 128 caracteres.</span><span class="sxs-lookup"><span data-stu-id="832cc-128">The longest string you can search for is 128 characters.</span></span>  
  
 <span data-ttu-id="832cc-129">Nomes de itens ou descrições que contêm toda a cadeia de caracteres da pesquisa em qualquer lugar do valor de texto serão incluídos nos resultados da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="832cc-129">Item names or descriptions that contain the entire search string anywhere in the text value are included in the search results.</span></span>  
  
 <span data-ttu-id="832cc-130">Os operadores boolianos como o caractere de adição (+) não têm suporte.</span><span class="sxs-lookup"><span data-stu-id="832cc-130">Boolean operators such as the plus character (+) are not supported.</span></span>  
  
 <span data-ttu-id="832cc-131">**Exibição de detalhes**</span><span class="sxs-lookup"><span data-stu-id="832cc-131">**Details View**</span></span>  
 <span data-ttu-id="832cc-132">Clique para exibir a página Resultados da Pesquisa em uma lista que contém informações adicionais sobre os itens, como o tipo de item, o nome, a descrição, a pasta na qual o item está localizado e quando ele foi executado pela última vez.</span><span class="sxs-lookup"><span data-stu-id="832cc-132">Click to display the Search Results page in a list that contains additional information about items, such as the item type, name, description, the folder in which the item is located, and when it was last run.</span></span> <span data-ttu-id="832cc-133">Em **Exibição de Detalhes**, é possível usar os botões **Excluir** e **Mover** para remover e realocar itens na pasta.</span><span class="sxs-lookup"><span data-stu-id="832cc-133">In **Details View**, you can use **Delete** and **Move** buttons to remove and relocate items in the folder.</span></span>  
  
 <span data-ttu-id="832cc-134">Focalize um item e clique na seta do menu suspenso para abri-lo e acessar e configurar as propriedades do item selecionado.</span><span class="sxs-lookup"><span data-stu-id="832cc-134">Hover over an item and click the drop-down arrow to open the drop-down menu from which you can access and configure properties of the selected item.</span></span>  
  
 <span data-ttu-id="832cc-135">**Exibição de lista**</span><span class="sxs-lookup"><span data-stu-id="832cc-135">**List View**</span></span>  
 <span data-ttu-id="832cc-136">Clique para exibir a página Resultados da Pesquisa sem os detalhes da **Exibição de Detalhes**.</span><span class="sxs-lookup"><span data-stu-id="832cc-136">Click to display the Search Results page without details as in **Details View**.</span></span> <span data-ttu-id="832cc-137">Exibição de Lista é a exibição padrão quando a página Resultados da Pesquisa é exibida.</span><span class="sxs-lookup"><span data-stu-id="832cc-137">List View is the default view when the Search Results page opens.</span></span>  
  
 <span data-ttu-id="832cc-138">Focalize um item e clique na seta do menu suspenso para abri-lo e acessar e configurar as propriedades do item selecionado.</span><span class="sxs-lookup"><span data-stu-id="832cc-138">Hover over an item and click the drop-down arrow to open the drop-down menu from which you can access and configure properties of the selected item.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="832cc-139">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="832cc-139">See Also</span></span>  
 <span data-ttu-id="832cc-140">[Gerenciador de Relatórios &#40;Modo Nativo do SSRS&#41;](../../2014/reporting-services/report-manager-ssrs-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="832cc-140">[Report Manager  &#40;SSRS Native Mode&#41;](../../2014/reporting-services/report-manager-ssrs-native-mode.md) </span></span>  
 [<span data-ttu-id="832cc-141">Ajuda F1 do Gerenciador de Relatórios</span><span class="sxs-lookup"><span data-stu-id="832cc-141">Report Manager F1 Help</span></span>](../../2014/reporting-services/report-manager-f1-help.md)  
  
  
