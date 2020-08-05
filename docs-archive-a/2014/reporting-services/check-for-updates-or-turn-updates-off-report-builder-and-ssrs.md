---
title: Verificar se há atualizações ou desativar atualizações (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 9c69792d-d7c4-453b-ae2f-6d2d071d8606
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 088d41e71d770f746367f2760cff8ff67b15623c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573800"
---
# <a name="check-for-updates-or-turn-updates-off-report-builder-and-ssrs"></a><span data-ttu-id="9e31b-102">Verificar ou desativar atualizações (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="9e31b-102">Check for Updates or Turn Updates Off (Report Builder and SSRS)</span></span>
  <span data-ttu-id="9e31b-103">Sempre que você abre um relatório, o Construtor de Relatórios verifica se as instâncias publicadas das partes de relatório no relatório foram atualizadas no servidor de relatório ou no site do SharePoint integrado com o servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="9e31b-103">Every time you open a report, Report Builder checks to see if the published instances of report parts in that report have been updated on the report server or SharePoint site integrated with a report server.</span></span> <span data-ttu-id="9e31b-104">Também procura alterações nos itens dependentes das partes de relatório, como o conjunto de dados e os parâmetros.</span><span class="sxs-lookup"><span data-stu-id="9e31b-104">It also checks for changes in the report parts' dependent items, such as the dataset and parameters.</span></span> <span data-ttu-id="9e31b-105">Se as partes de relatório ou suas dependências foram atualizados no site ou servidor, uma barra de informações no relatório exibe o número de partes atualizadas.</span><span class="sxs-lookup"><span data-stu-id="9e31b-105">If any report parts or their dependencies have been updated on the site or server, an information bar in your report displays the number of updated parts.</span></span> <span data-ttu-id="9e31b-106">Você pode optar por exibir e aceitar ou rejeitar as atualizações ou descartar a barra de informações.</span><span class="sxs-lookup"><span data-stu-id="9e31b-106">You can choose to view and accept or reject the updates, or dismiss the information bar.</span></span>  
  
 <span data-ttu-id="9e31b-107">Você também pode desabilitar a barra de informações e não ser informado se as instâncias publicadas das partes de relatório foram alteradas.</span><span class="sxs-lookup"><span data-stu-id="9e31b-107">You can also disable the information bar and not be informed if published instances of report parts have changed.</span></span> <span data-ttu-id="9e31b-108">Essa é uma configuração de usuário; ela será desabilitada para todos os relatórios que você abrir.</span><span class="sxs-lookup"><span data-stu-id="9e31b-108">This is a user setting; it will be disabled for all reports that you open.</span></span> <span data-ttu-id="9e31b-109">Mesmo que você tenha desabilitado a barra de informações, ainda poderá procurar atualizações.</span><span class="sxs-lookup"><span data-stu-id="9e31b-109">Even if you have disabled the information bar, you can still check for updates.</span></span>  
  
### <a name="to-turn-on-and-off-report-part-updates"></a><span data-ttu-id="9e31b-110">Para ligar e desligar as atualizações de parte de relatório</span><span class="sxs-lookup"><span data-stu-id="9e31b-110">To turn on and off report part updates</span></span>  
  
1.  <span data-ttu-id="9e31b-111">Clique no botão Construtor de Relatórios e clique em **Opções**.</span><span class="sxs-lookup"><span data-stu-id="9e31b-111">Click the Report Builder button, and then click **Options**.</span></span>  
  
2.  <span data-ttu-id="9e31b-112">Na caixa de diálogo **Opções** , na guia **recursos** , marque ou desmarque a caixa de seleção **Mostrar atualizações em partes de relatório em meus relatórios** .</span><span class="sxs-lookup"><span data-stu-id="9e31b-112">In the **Options** dialog box, on the **Resources** tab, select or clear the **Show updates to report parts in my reports** check box.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9e31b-113">Esta é uma configuração de usuário.</span><span class="sxs-lookup"><span data-stu-id="9e31b-113">This is a user setting.</span></span> <span data-ttu-id="9e31b-114">Ela será desabilitada para todos os relatórios que você abrir.</span><span class="sxs-lookup"><span data-stu-id="9e31b-114">It will be disabled for all reports that you open.</span></span>  
  
### <a name="to-check-for-updates"></a><span data-ttu-id="9e31b-115">Para verificar atualizações</span><span class="sxs-lookup"><span data-stu-id="9e31b-115">To check for updates</span></span>  
  
-   <span data-ttu-id="9e31b-116">Clique com o botão direito do mouse na superfície de design fora do relatório ou no corpo do relatório e clique em **verificar se há atualizações**.</span><span class="sxs-lookup"><span data-stu-id="9e31b-116">Right-click the design surface outside the report, or in the report body, and click **Check for Updates**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e31b-117">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9e31b-117">See Also</span></span>  
 <span data-ttu-id="9e31b-118">[Partes de relatório &#40;Construtor de Relatórios e SSRS&#41;](report-parts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="9e31b-118">[Report Parts &#40;Report Builder and SSRS&#41;](report-parts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="9e31b-119">[Publicar e republicar partes de relatório &#40;Construtor de Relatórios e SSRS&#41;](report-design/publish-and-republish-report-parts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="9e31b-119">[Publish and Republish Report Parts &#40;Report Builder and SSRS&#41;](report-design/publish-and-republish-report-parts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="9e31b-120">[Procurar partes de relatório e definir uma pasta padrão &#40;Construtor de Relatórios e SSRS&#41;](report-design/browse-for-report-parts-and-set-a-default-folder-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="9e31b-120">[Browse for Report Parts and Set a Default Folder &#40;Report Builder and SSRS&#41;](report-design/browse-for-report-parts-and-set-a-default-folder-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="9e31b-121">[Solucionar problemas de partes de relatório &#40;Construtor de Relatórios e SSRS&#41;](../../2014/reporting-services/troubleshoot-report-parts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="9e31b-121">[Troubleshoot Report Parts &#40;Report Builder and SSRS&#41;](../../2014/reporting-services/troubleshoot-report-parts-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="9e31b-122">Partes de relatório e conjuntos de dados no Construtor de Relatórios</span><span class="sxs-lookup"><span data-stu-id="9e31b-122">Report Parts and Datasets in Report Builder</span></span>](report-data/report-parts-and-datasets-in-report-builder.md)  
  
  
