---
title: Vincular um relatório a um modelo como um relatório de clickthrough | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- customizing clickthrough reports
- clickthrough reports, customizing
- clickthrough reports, templates
ms.assetid: 3af42de3-67ef-41c2-bc8a-7045baec6f63
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: cb84f8036dbe5a1694628144f0b948452261ca75
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570505"
---
# <a name="link-a-report-to-a-model-as-a-clickthrough-report"></a><span data-ttu-id="4373a-102">Vincular um relatório a um modelo como um relatório de clickthrough</span><span class="sxs-lookup"><span data-stu-id="4373a-102">Link a Report to a Model as a Clickthrough Report</span></span>
  <span data-ttu-id="4373a-103">Em vez de usar os modelos de relatório de clickthrough padrão, você pode criar um relatório Construtor de Relatórios e vinculá-lo a uma entidade específica no modelo de relatório.</span><span class="sxs-lookup"><span data-stu-id="4373a-103">Instead of using the default clickthrough report templates, you can create a Report Builder report and then link it to a specific entity in the report model.</span></span> <span data-ttu-id="4373a-104">Quando a pessoa que está exibindo o relatório clica nos dados interativos do relatório principal, esse relatório é exibido como relatório de clickthrough.</span><span class="sxs-lookup"><span data-stu-id="4373a-104">When the person viewing the report clicks the interactive data in the main report, this report is displayed as a clickthrough report.</span></span> <span data-ttu-id="4373a-105">Para vincular um relatório a uma entidade, use o Gerenciador de Relatórios [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4373a-105">To link a report to an entity, use [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] Report Manager.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="4373a-106">A entidade principal, ou básica, usada no relatório deve ser igual à entidade a qual o relatório está vinculado.</span><span class="sxs-lookup"><span data-stu-id="4373a-106">The primary, or base, entity that is used in the report must to be the same entity to which the report is linked.</span></span>  
  
### <a name="to-start-report-manager-from-a-browser"></a><span data-ttu-id="4373a-107">Para iniciar o Gerenciador de Relatórios em um navegador</span><span class="sxs-lookup"><span data-stu-id="4373a-107">To start Report Manager from a browser</span></span>  
  
1.  <span data-ttu-id="4373a-108">Abra o [!INCLUDE[msCoName](../includes/msconame-md.md)] Internet Explorer 6.0 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="4373a-108">Open [!INCLUDE[msCoName](../includes/msconame-md.md)] Internet Explorer 6.0 or later.</span></span>  
  
2.  <span data-ttu-id="4373a-109">Na barra de endereço do navegador da Web, digite a URL do Gerenciador de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="4373a-109">In the address bar of the Web browser, type the Report Manager URL.</span></span> <span data-ttu-id="4373a-110">Por padrão, a URL é http:// \<*ComputerName*> /reports.</span><span class="sxs-lookup"><span data-stu-id="4373a-110">By default, the URL is http://\<*ComputerName*>/reports.</span></span>  
  
### <a name="to-create-a-customized-clickthrough-report"></a><span data-ttu-id="4373a-111">Para criar um relatório de clickthrough personalizado</span><span class="sxs-lookup"><span data-stu-id="4373a-111">To create a customized clickthrough report</span></span>  
  
1.  <span data-ttu-id="4373a-112">Navegue até o modelo de relatório para o qual você quer adicionar o relatório de clickthrough personalizado.</span><span class="sxs-lookup"><span data-stu-id="4373a-112">Navigate to the report model to which you want to add the customized clickthrough report.</span></span>  
  
2.  <span data-ttu-id="4373a-113">Clique duas vezes no modelo de relatório.</span><span class="sxs-lookup"><span data-stu-id="4373a-113">Double-click the report model.</span></span>  
  
3.  <span data-ttu-id="4373a-114">Clique em **Clickthrough**.</span><span class="sxs-lookup"><span data-stu-id="4373a-114">Click **Clickthrough**.</span></span>  
  
4.  <span data-ttu-id="4373a-115">Selecione a entidade para a qual você deseja anexar o relatório de clickthrough personalizado.</span><span class="sxs-lookup"><span data-stu-id="4373a-115">Select the entity to which you want to attach the customized clickthrough report.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="4373a-116">Esta entidade deve ser igual à entidade básica do relatório de clickthrough personalizado.</span><span class="sxs-lookup"><span data-stu-id="4373a-116">This entity must be the same as the base entity of the customized clickthrough report.</span></span>  
  
5.  <span data-ttu-id="4373a-117">Para exibir um relatório personalizado quando uma instância única da entidade selecionada é clicada, clique no botão **Procurar** do relatório de instância única.</span><span class="sxs-lookup"><span data-stu-id="4373a-117">To display the customized report when a single instance of the selected entity is clicked, click the Single instance report **Browse** button.</span></span>  
  
     <span data-ttu-id="4373a-118">- ou -</span><span class="sxs-lookup"><span data-stu-id="4373a-118">-or-</span></span>  
  
     <span data-ttu-id="4373a-119">Para exibir um relatório personalizado quando uma instância múltipla da entidade selecionada é clicada, clique no botão **Procurar** do relatório de instância múltipla.</span><span class="sxs-lookup"><span data-stu-id="4373a-119">To display the customized report when a multiple instance of the selected entity is clicked, click the Multiple instance report **Browse** button.</span></span>  
  
6.  <span data-ttu-id="4373a-120">Selecione o relatório e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4373a-120">Select the report and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="4373a-121">Clique em **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="4373a-121">Click **Apply**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4373a-122">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="4373a-122">See Also</span></span>  
 [<span data-ttu-id="4373a-123">Relatórios de clickthrough &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="4373a-123">Clickthrough Reports &#40;SSRS&#41;</span></span>](reports/clickthrough-reports-ssrs.md)  
  
  
