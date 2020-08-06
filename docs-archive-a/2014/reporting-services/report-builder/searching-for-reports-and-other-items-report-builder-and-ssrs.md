---
title: Pesquisando relatórios e outros itens (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 6a586659-5c2b-453b-8f40-a3a469277b17
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: a964cbdbc674fb3d29e18b5e5075695f0033801e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569151"
---
# <a name="searching-for-reports-and-other-items-report-builder--and-ssrs"></a><span data-ttu-id="97e14-102">Pesquisando relatórios e outros itens (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="97e14-102">Searching for Reports and Other Items (Report Builder  and SSRS)</span></span>
  <span data-ttu-id="97e14-103">Você pode usar o Gerenciador de Relatórios para pesquisar um servidor de relatório à procura de itens específicos por nome ou descrição.</span><span class="sxs-lookup"><span data-stu-id="97e14-103">You can use Report Manager to search a report server for specific items by name or description.</span></span> <span data-ttu-id="97e14-104">Você pode procurar por relatórios publicados, modelos de relatório, pastas, fontes de dados compartilhadas e recursos.</span><span class="sxs-lookup"><span data-stu-id="97e14-104">You can search for published reports, report models, folders, shared data sources, and resources.</span></span> <span data-ttu-id="97e14-105">Você não pode procurar por agendas, proprietários, atribuições de função, instantâneos específicos no histórico de relatório ou assinaturas.</span><span class="sxs-lookup"><span data-stu-id="97e14-105">You cannot search for schedules, owners, role assignments, specific snapshots in report history, or subscriptions.</span></span> <span data-ttu-id="97e14-106">A pesquisa é executada no banco de dados do servidor de relatórios no qual os itens estão armazenados.</span><span class="sxs-lookup"><span data-stu-id="97e14-106">The search is performed on the report server database where the items are stored.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="97e14-107">A execução de uma pesquisa do sistema de arquivos não retornará resultados da pesquisa para itens gerenciados por um servidor de relatórios.</span><span class="sxs-lookup"><span data-stu-id="97e14-107">Performing a file system search will not return search results for items managed by a report server.</span></span>  
  
-   <span data-ttu-id="97e14-108">Para procurar por itens no Gerenciador de Relatórios, digite uma cadeia de caracteres de pesquisa na caixa de texto **Pesquisar** na parte superior da página.</span><span class="sxs-lookup"><span data-stu-id="97e14-108">To search for items in Report Manager, type a search string in the **Search for** text box at the top of the page.</span></span> <span data-ttu-id="97e14-109">As pesquisas começam no nó superior na hierarquia da pasta e continua até cada ramificação.</span><span class="sxs-lookup"><span data-stu-id="97e14-109">Searches begin at the top node in the folder hierarchy and then proceed through every branch.</span></span> <span data-ttu-id="97e14-110">Se você não tiver permissão para acessar uma ramificação específica, essa ramificação será ignorada.</span><span class="sxs-lookup"><span data-stu-id="97e14-110">If you do not have permission to access a specific branch, that branch is skipped.</span></span> <span data-ttu-id="97e14-111">Isso se aplica às pastas Meus Relatórios que pertencem a outros usuários e a outras pastas que geralmente não estão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="97e14-111">This applies to My Reports folders that belong to other users, and to other folders that are not generally available.</span></span> <span data-ttu-id="97e14-112">Somente os relatórios e itens para os quais você tem permissão para exibir são incluídos nos resultados da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="97e14-112">Only reports and items that you have permission to view are included in the search results.</span></span>  
  
-   <span data-ttu-id="97e14-113">Para procurar por um item por nome ou descrição, especifique toda ou parte do texto que deseja coincidir.</span><span class="sxs-lookup"><span data-stu-id="97e14-113">To search for an item by name or description, specify all or part of the text that you want to match.</span></span> <span data-ttu-id="97e14-114">A cadeia de caracteres de pesquisa não faz distinção entre maiúsculas e minúsculas.</span><span class="sxs-lookup"><span data-stu-id="97e14-114">The search string is not case-sensitive.</span></span> <span data-ttu-id="97e14-115">Você não pode usar os operadores de pesquisa, como símbolos de mais (+) ou menos (-), para exigir ou excluir critérios de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="97e14-115">You cannot use search operators such as plus (+) or minus (-) symbols to require or exclude search criteria.</span></span>  
  
-   <span data-ttu-id="97e14-116">Para procurar um texto específico em um relatório, use a barra de ferramentas na parte superior do relatório.</span><span class="sxs-lookup"><span data-stu-id="97e14-116">To search for specific text within a report, use the toolbar at the top of the report.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="97e14-117">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="97e14-117">See Also</span></span>  
 <span data-ttu-id="97e14-118">[Localizando e exibindo relatórios no Report Manager &#40;Construtor de Relatórios e SSRS&#41;](finding-and-viewing-reports-in-the-web-portal-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="97e14-118">[Finding and Viewing Reports in Report Manager &#40;Report Builder and SSRS&#41;](finding-and-viewing-reports-in-the-web-portal-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="97e14-119">[Usando meus relatórios &#40;Construtor de Relatórios e SSRS&#41;](using-my-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="97e14-119">[Using My Reports &#40;Report Builder and SSRS&#41;](using-my-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="97e14-120">[Localizando, exibindo e gerenciando relatórios &#40;Construtor de Relatórios e SSRS &#41;](finding-viewing-and-managing-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="97e14-120">[Finding, Viewing, and Managing Reports &#40;Report Builder and SSRS &#41;](finding-viewing-and-managing-reports-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="97e14-121">Abrir e fechar um relatório &#40;Gerenciador de Relatórios&#41;</span><span class="sxs-lookup"><span data-stu-id="97e14-121">Open and Close a Report &#40;Report Manager&#41;</span></span>](../reports/open-and-close-a-report-report-manager.md)  
  
  
