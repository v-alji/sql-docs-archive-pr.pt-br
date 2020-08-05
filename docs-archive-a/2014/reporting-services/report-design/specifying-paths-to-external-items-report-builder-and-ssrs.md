---
title: Especificando caminhos para itens externos (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 4fe513da-f3c5-479c-9fec-8662b91a0d6d
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 097a3566f914e7810039ee07bc3d3bf3185d7f06
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569068"
---
# <a name="specifying-paths-to-external-items-report-builder-and-ssrs"></a><span data-ttu-id="8f77d-102">Especificando caminhos para itens externos (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="8f77d-102">Specifying Paths to External Items (Report Builder and SSRS)</span></span>
  <span data-ttu-id="8f77d-103">Você especifica caminhos nas propriedades de item de relatório para referenciar itens, como relatórios detalhados, sub-relatórios e arquivos de imagem, que são externos ao arquivo de definição de relatório e armazenados em um servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="8f77d-103">You specify paths in report item properties to reference items such as drillthrough reports, subreports, and image files that are external to the report definition file and are stored on a report server.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
> [!NOTE]  
>  <span data-ttu-id="8f77d-104">No Construtor de Relatórios, os caminhos para itens devem especificar itens em um servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="8f77d-104">In Report Builder, paths to items must specify items on a report server.</span></span> <span data-ttu-id="8f77d-105">Não há suporte para caminhos para itens em um sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="8f77d-105">Paths to items on a file system are not supported.</span></span> <span data-ttu-id="8f77d-106">Você somente poderá visualizar um relatório que usa esses itens se estiver conectado ao servidor de relatório em que os itens estão localizados.</span><span class="sxs-lookup"><span data-stu-id="8f77d-106">You can preview a report that uses these items only if you are connected to the report server where the items are located.</span></span>  
  
 <span data-ttu-id="8f77d-107">Quando você especifica um caminho para um item externo em uma caixa de diálogo para ações, sub-relatórios ou imagens, pode navegar diretamente até o servidor de relatório e selecionar esse item.</span><span class="sxs-lookup"><span data-stu-id="8f77d-107">When you specify a path for an external item in a dialog box for actions, subreports, or images, you can browse directly to the report server and select the item.</span></span> <span data-ttu-id="8f77d-108">Navegar até o item e selecioná-lo diretamente é a maneira recomendada de especificar um relatório detalhado ou sub-relatório.</span><span class="sxs-lookup"><span data-stu-id="8f77d-108">Browsing to an item and selecting it directly is the recommended way to specify a drillthrough report or subreport.</span></span> <span data-ttu-id="8f77d-109">Dessa forma, os nomes de parâmetro corretos estarão disponíveis em uma lista suspensa quando você especificar parâmetros de relatório ou sub-relatório.</span><span class="sxs-lookup"><span data-stu-id="8f77d-109">That way the correct parameter names will be available in a drop-down list when you specify report or subreport parameters.</span></span> <span data-ttu-id="8f77d-110">Ao alterar o caminho de um item para apontar para um item diferente, você deverá atualizar manualmente os nomes de parâmetro corretos e valores conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="8f77d-110">When you change an item path to point to a different item, you must manually update the correct parameter names and values as needed.</span></span>  
  
 <span data-ttu-id="8f77d-111">Em um servidor de relatório configurado no modo nativo, especifique um nome de relatório detalhado sem a extensão de arquivo .rdl.</span><span class="sxs-lookup"><span data-stu-id="8f77d-111">On a report server configured in native mode, specify a drillthrough report name without the file extension .rdl.</span></span>  
  
 <span data-ttu-id="8f77d-112">Em um servidor de relatório configurado no modo integrado do SharePoint, você deve incluir a extensão de arquivo .rdl.</span><span class="sxs-lookup"><span data-stu-id="8f77d-112">On a report server configured in SharePoint integrated mode, you must include the file extension .rdl.</span></span> <span data-ttu-id="8f77d-113">O caminho pode ser um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="8f77d-113">The path can be one of the following:</span></span>  
  
-   <span data-ttu-id="8f77d-114">**Um caminho relativo para o item do relatório principal.**</span><span class="sxs-lookup"><span data-stu-id="8f77d-114">**A relative path to the item from the main report.**</span></span> <span data-ttu-id="8f77d-115">Por exemplo, ../AllSubreports/Subreport1.</span><span class="sxs-lookup"><span data-stu-id="8f77d-115">For example, ../AllSubreports/Subreport1.</span></span> <span data-ttu-id="8f77d-116">Neste exemplo, o **..**</span><span class="sxs-lookup"><span data-stu-id="8f77d-116">In this example, the **..**</span></span> <span data-ttu-id="8f77d-117">indica a pasta acima da pasta em que o relatório principal está localizado.</span><span class="sxs-lookup"><span data-stu-id="8f77d-117">indicates the folder above the folder where the main report is located.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8f77d-118">Caminhos relativos não são suportados quando o relatório é executado dentro de Construtor de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="8f77d-118">Relative paths are not supported when the report is run inside Report Builder.</span></span> <span data-ttu-id="8f77d-119">Para exibir um relatório que use caminhos relativos a itens externos, salve o relatório no servidor de relatório e execute o relatório de lá</span><span class="sxs-lookup"><span data-stu-id="8f77d-119">To view a report that uses relative paths to external items, save the report to the report server, and run the report from there</span></span>  
  
-   <span data-ttu-id="8f77d-120">**Um caminho completo para o item.**</span><span class="sxs-lookup"><span data-stu-id="8f77d-120">**A full path to the item.**</span></span>  
  
    -   <span data-ttu-id="8f77d-121">**Em um servidor de relatório:** o caminho começa com **/** , a pasta Base.</span><span class="sxs-lookup"><span data-stu-id="8f77d-121">**On a report server:** The path starts from **/**, the Home folder.</span></span> <span data-ttu-id="8f77d-122">Por exemplo, ../Reports/AllSubreports/Subreport1.</span><span class="sxs-lookup"><span data-stu-id="8f77d-122">For example, /Reports/AllSubreports/Subreport1.</span></span>  
  
    -   <span data-ttu-id="8f77d-123">**Em um site do SharePoint:** você deve especificar o nome do relatório em uma expressão, com a URL completa do item e a extensão de arquivo .rdl.</span><span class="sxs-lookup"><span data-stu-id="8f77d-123">**On a SharePoint site:** You must specify the report name in an expression, with the full URL of the item and the file extension .rdl.</span></span> <span data-ttu-id="8f77d-124">Por exemplo, `="http://server/site/library/folder/Report1.rdl"`.</span><span class="sxs-lookup"><span data-stu-id="8f77d-124">For example, `="http://server/site/library/folder/Report1.rdl"`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f77d-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8f77d-125">See Also</span></span>  
 <span data-ttu-id="8f77d-126">[Adicionar uma imagem externa &#40;Construtor de Relatórios e SSRS&#41;](add-an-external-image-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="8f77d-126">[Add an External Image &#40;Report Builder and SSRS&#41;](add-an-external-image-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="8f77d-127">[Adicionar um sub-relatório e parâmetros &#40;Construtor de Relatórios e SSRS&#41;](add-a-subreport-and-parameters-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="8f77d-127">[Add a Subreport and Parameters &#40;Report Builder and SSRS&#41;](add-a-subreport-and-parameters-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="8f77d-128">Adicionar uma ação de detalhamento a um relatório &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="8f77d-128">Add a Drillthrough Action on a Report &#40;Report Builder and SSRS&#41;</span></span>](add-a-drillthrough-action-on-a-report-report-builder-and-ssrs.md)  
  
  
