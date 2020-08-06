---
title: Caixa de diálogo Propriedades do relatório, referências (Construtor de Relatórios) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- "10082"
ms.assetid: 3414c857-8ea6-4fc4-a6d5-b4883c039efa
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2c28e9053a1c13f8d0e0b7b44f3b1a037976c318
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681401"
---
# <a name="report-properties-dialog-box-references-report-builder"></a><span data-ttu-id="4f6ee-102">Caixa de diálogo Propriedades do Relatório, Referências (Construtor de Relatórios)</span><span class="sxs-lookup"><span data-stu-id="4f6ee-102">Report Properties Dialog Box, References (Report Builder)</span></span>
  <span data-ttu-id="4f6ee-103">Selecione **Referências** na caixa de diálogo **Propriedades do Relatório** para adicionar ou remover as referências para assemblies personalizados ou outros assemblies externos e instâncias de classe personalizada usadas pelas expressões na definição do relatório.</span><span class="sxs-lookup"><span data-stu-id="4f6ee-103">Select **References** on the **Report Properties** dialog box to add or remove references to custom or other external assemblies and custom class instances that are used by expressions in the report definition.</span></span> <span data-ttu-id="4f6ee-104">Assemblies personalizados não têm suporte no modo local no Construtor de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="4f6ee-104">Custom assemblies are not supported in local mode in Report Builder.</span></span> <span data-ttu-id="4f6ee-105">Para criar relatórios que usam assemblies personalizados, use Report Designer no [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4f6ee-105">To author reports that use custom assemblies, use Report Designer in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
## <a name="options"></a><span data-ttu-id="4f6ee-106">Opções</span><span class="sxs-lookup"><span data-stu-id="4f6ee-106">Options</span></span>  
 <span data-ttu-id="4f6ee-107">**Adicionar ou remover assemblies**</span><span class="sxs-lookup"><span data-stu-id="4f6ee-107">**Add or remove assemblies**</span></span>  
 <span data-ttu-id="4f6ee-108">Lista os assemblies aos quais o relatório faz referência.</span><span class="sxs-lookup"><span data-stu-id="4f6ee-108">Lists the assemblies that the report references.</span></span> <span data-ttu-id="4f6ee-109">O assembly deve estar disponível no computador no qual a ferramenta que você usando para criar o relatório está instalada e no servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="4f6ee-109">The assembly must be available on the computer on which the tool you are using to design the report is installed and on the report server.</span></span> <span data-ttu-id="4f6ee-110">O nome da referência deve corresponder exatamente ao conteúdo das **\<CodeModule>** marcas no arquivo de linguagem de definição de relatório (. RDL).</span><span class="sxs-lookup"><span data-stu-id="4f6ee-110">The name of the reference must match the contents of **\<CodeModule>** tags in the Report Definition Language (.rdl) file exactly.</span></span>  
  
 <span data-ttu-id="4f6ee-111">**Adicionar**</span><span class="sxs-lookup"><span data-stu-id="4f6ee-111">**Add**</span></span>  
 <span data-ttu-id="4f6ee-112">Clique para adicionar um assembly.</span><span class="sxs-lookup"><span data-stu-id="4f6ee-112">Click to add an assembly.</span></span> <span data-ttu-id="4f6ee-113">Clique no botão de reticências (...) para abrir a caixa de diálogo **abrir** e selecione os assemblies necessários para concluir o processamento do relatório e a avaliação da expressão.</span><span class="sxs-lookup"><span data-stu-id="4f6ee-113">Click the ellipsis (...) button to open the **Open** dialog box and select the assemblies necessary to complete report processing and expression evaluation.</span></span>  
  
 <span data-ttu-id="4f6ee-114">**Remover**</span><span class="sxs-lookup"><span data-stu-id="4f6ee-114">**Remove**</span></span>  
 <span data-ttu-id="4f6ee-115">Para remover uma referência de assembly da lista, selecione o nome do assembly e clique no botão **Remover** .</span><span class="sxs-lookup"><span data-stu-id="4f6ee-115">To remove an assembly reference from the list, select the assembly name and click the **Remove** button.</span></span>  
  
 <span data-ttu-id="4f6ee-116">**Adicionar ou remover classes**</span><span class="sxs-lookup"><span data-stu-id="4f6ee-116">**Add or remove classes**</span></span>  
 <span data-ttu-id="4f6ee-117">Lista as instâncias de classe usadas pelo relatório.</span><span class="sxs-lookup"><span data-stu-id="4f6ee-117">Lists the class instances that are used by the report.</span></span> <span data-ttu-id="4f6ee-118">A lista de classe só é usada por membros baseados em instância, não membros estáticos.</span><span class="sxs-lookup"><span data-stu-id="4f6ee-118">The class list is used only by instance-based members, not static members.</span></span>  
  
 <span data-ttu-id="4f6ee-119">**Adicionar**</span><span class="sxs-lookup"><span data-stu-id="4f6ee-119">**Add**</span></span>  
 <span data-ttu-id="4f6ee-120">Clique para adicionar uma referência de classe.</span><span class="sxs-lookup"><span data-stu-id="4f6ee-120">Click to add a class reference.</span></span> <span data-ttu-id="4f6ee-121">Clique no botão de reticências (...) para abrir a caixa de diálogo **abrir** e selecione as classes necessárias para concluir o processamento do relatório e a avaliação da expressão.</span><span class="sxs-lookup"><span data-stu-id="4f6ee-121">Click the ellipsis (...) button to open the **Open** dialog box and select the classes necessary to complete report processing and expression evaluation.</span></span>  
  
 <span data-ttu-id="4f6ee-122">**Remover**</span><span class="sxs-lookup"><span data-stu-id="4f6ee-122">**Remove**</span></span>  
 <span data-ttu-id="4f6ee-123">Para excluir a instância de classe, selecione-a e clique no botão **Remover** .</span><span class="sxs-lookup"><span data-stu-id="4f6ee-123">To delete the class instance, select it and click the **Remove** button.</span></span>  
  
 <span data-ttu-id="4f6ee-124">**Limpeza**</span><span class="sxs-lookup"><span data-stu-id="4f6ee-124">**Up**</span></span>  
 <span data-ttu-id="4f6ee-125">Para classes que têm dependências, você pode mover esta referência mais para cima na lista.</span><span class="sxs-lookup"><span data-stu-id="4f6ee-125">For classes that have dependencies, you can move this reference higher in the list.</span></span>  
  
 <span data-ttu-id="4f6ee-126">**Down**</span><span class="sxs-lookup"><span data-stu-id="4f6ee-126">**Down**</span></span>  
 <span data-ttu-id="4f6ee-127">Para classes que têm dependências, você pode mover esta referência mais para baixo na lista.</span><span class="sxs-lookup"><span data-stu-id="4f6ee-127">For classes that have dependencies, you can move this reference lower in the list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f6ee-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="4f6ee-128">See Also</span></span>  
 <span data-ttu-id="4f6ee-129">[Construtor de Relatórios ajuda para caixas de diálogo, painéis e assistentes](../../2014/reporting-services/report-builder-help-for-dialog-boxes-panes-and-wizards.md) </span><span class="sxs-lookup"><span data-stu-id="4f6ee-129">[Report Builder Help for Dialog Boxes, Panes, and Wizards](../../2014/reporting-services/report-builder-help-for-dialog-boxes-panes-and-wizards.md) </span></span>  
 [<span data-ttu-id="4f6ee-130">Expressões &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="4f6ee-130">Expressions &#40;Report Builder and SSRS&#41;</span></span>](report-design/expressions-report-builder-and-ssrs.md)  
  
  
