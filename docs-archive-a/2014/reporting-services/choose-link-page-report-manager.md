---
title: Página escolher link (Report Manager) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: a89a555d-efa3-45d6-951e-db78ec6a2c8e
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: bc40fe726555babee8d9940e198a93577bd6a09f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571869"
---
# <a name="choose-link-page-report-manager"></a><span data-ttu-id="c3e6f-102">Página Escolher Link (Gerenciador de Relatórios)</span><span class="sxs-lookup"><span data-stu-id="c3e6f-102">Choose Link Page (Report Manager)</span></span>
  <span data-ttu-id="c3e6f-103">Use a página Escolher Link para escolher um relatório diferente no qual basear o relatório vinculado atualmente selecionado.</span><span class="sxs-lookup"><span data-stu-id="c3e6f-103">Use the Choose Link page to choose a different report upon which to base the currently selected linked report.</span></span> <span data-ttu-id="c3e6f-104">Relatórios vinculados são baseados em outros relatórios já publicados em um servidor de relatórios.</span><span class="sxs-lookup"><span data-stu-id="c3e6f-104">Linked reports are based on other reports already published to a report server.</span></span> <span data-ttu-id="c3e6f-105">Um relatório vinculado usa o layout e os dados de um relatório base, mas tem páginas de propriedades separadas para que você possa personalizar propriedades de parâmetros, configurações de segurança, nome, descrição e local.</span><span class="sxs-lookup"><span data-stu-id="c3e6f-105">A linked report uses the layout and data of the base report, but has separate property pages so that you can customize parameter properties, security settings, name, description, and location.</span></span>  
  
 <span data-ttu-id="c3e6f-106">Na página Escolher Link, você pode escolher um relatório diferente publicado para usar com o relatório vinculado.</span><span class="sxs-lookup"><span data-stu-id="c3e6f-106">Through the Choose Link page, you can choose a different published report to use with the linked report.</span></span> <span data-ttu-id="c3e6f-107">Outras configurações do relatório vinculado (como configurações de segurança e parâmetro) não são afetadas por alterações nas informações do link.</span><span class="sxs-lookup"><span data-stu-id="c3e6f-107">Other settings of the linked report (such as security and parameter settings) are unaffected by changes to the link information.</span></span> <span data-ttu-id="c3e6f-108">O servidor de relatório não validará a sua seleção; portanto, escolha um relatório que tenha os mesmos parâmetros que os especificados no relatório vinculado.</span><span class="sxs-lookup"><span data-stu-id="c3e6f-108">The report server will not validate your selection, so be sure to choose a report that has the same parameters as those you specified on the linked report.</span></span>  
  
## <a name="navigation"></a><span data-ttu-id="c3e6f-109">Navegação</span><span class="sxs-lookup"><span data-stu-id="c3e6f-109">Navigation</span></span>  
 <span data-ttu-id="c3e6f-110">Use o procedimento a seguir para navegar para este local na interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="c3e6f-110">Use the following procedure to navigate to this location in the user interface (UI).</span></span>  
  
###### <a name="to-open-the-choose-link-page"></a><span data-ttu-id="c3e6f-111">Para abrir a página Escolha Link</span><span class="sxs-lookup"><span data-stu-id="c3e6f-111">To open the Choose Link page</span></span>  
  
1.  <span data-ttu-id="c3e6f-112">Abra o Gerenciador de Relatórios e localize o relatório vinculado que você deseja alterar.</span><span class="sxs-lookup"><span data-stu-id="c3e6f-112">Open Report Manager, and locate the linked report you want to change.</span></span>  
  
2.  <span data-ttu-id="c3e6f-113">Focalize o relatório vinculado e clique na seta do menu suspenso.</span><span class="sxs-lookup"><span data-stu-id="c3e6f-113">Hover over the linked report, and click the drop-down arrow.</span></span>  
  
3.  <span data-ttu-id="c3e6f-114">No menu suspenso, clique em **Gerenciar**.</span><span class="sxs-lookup"><span data-stu-id="c3e6f-114">In the drop-down menu, click **Manage**.</span></span> <span data-ttu-id="c3e6f-115">Esse procedimento abre a página de propriedades **Geral** do relatório vinculado.</span><span class="sxs-lookup"><span data-stu-id="c3e6f-115">This opens the **General** properties page for the linked report.</span></span>  
  
4.  <span data-ttu-id="c3e6f-116">Na guia **Geral** , na página de propriedades, clique em **Alterar Link**.</span><span class="sxs-lookup"><span data-stu-id="c3e6f-116">On the **General** tab, on the properties page, click **Change Link**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="c3e6f-117">Opções</span><span class="sxs-lookup"><span data-stu-id="c3e6f-117">Options</span></span>  
 <span data-ttu-id="c3e6f-118">**Localidade**</span><span class="sxs-lookup"><span data-stu-id="c3e6f-118">**Location**</span></span>  
 <span data-ttu-id="c3e6f-119">Especifique o nome completo do relatório publicado, incluindo o caminho da pasta e o nome do relatório.</span><span class="sxs-lookup"><span data-stu-id="c3e6f-119">Specify the full name of the published report, including the folder path and report name.</span></span> <span data-ttu-id="c3e6f-120">É possível digitar o nome completo do relatório ou usar a exibição de árvore para navegar até o relatório desejado.</span><span class="sxs-lookup"><span data-stu-id="c3e6f-120">You can type the full name of the report or use the tree view to navigate to the report you want to use.</span></span>  
  
 <span data-ttu-id="c3e6f-121">**Modo de exibição de árvore**</span><span class="sxs-lookup"><span data-stu-id="c3e6f-121">**Tree view**</span></span>  
 <span data-ttu-id="c3e6f-122">Exibe todas as pastas na hierarquia de pastas do servidor de relatórios.</span><span class="sxs-lookup"><span data-stu-id="c3e6f-122">Shows all of the folders in the report server folder hierarchy.</span></span> <span data-ttu-id="c3e6f-123">Para usar a exibição de árvore para preencher o campo **Local** , clique no nome do relatório.</span><span class="sxs-lookup"><span data-stu-id="c3e6f-123">To use the tree view to fill in the **Location** field, click the name of the report.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3e6f-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c3e6f-124">See Also</span></span>  
 <span data-ttu-id="c3e6f-125">[Página Propriedades gerais, relatórios &#40;Report Manager&#41;](../../2014/reporting-services/general-properties-page-reports-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="c3e6f-125">[General Properties Page, Reports &#40;Report Manager&#41;](../../2014/reporting-services/general-properties-page-reports-report-manager.md) </span></span>  
 <span data-ttu-id="c3e6f-126">[Nova página de relatório vinculada &#40;Report Manager&#41;](../../2014/reporting-services/new-linked-report-page-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="c3e6f-126">[New Linked Report Page &#40;Report Manager&#41;](../../2014/reporting-services/new-linked-report-page-report-manager.md) </span></span>  
 [<span data-ttu-id="c3e6f-127">Ajuda F1 do Gerenciador de Relatórios</span><span class="sxs-lookup"><span data-stu-id="c3e6f-127">Report Manager F1 Help</span></span>](../../2014/reporting-services/report-manager-f1-help.md)  
  
  
