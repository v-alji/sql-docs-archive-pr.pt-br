---
title: Caixa de diálogo Propriedades do relatório, referências | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- "10530"
- sql12.rtp.rptdesigner.reportproperties.references.f1
ms.assetid: 4639d368-9918-4bb1-9953-7a724ca78dea
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 4b28ea0865d37bdc56054d6b23dc8c82d9279b08
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681398"
---
# <a name="report-properties-dialog-box-references"></a><span data-ttu-id="d164b-102">Caixa de diálogo Propriedades do Relatório, Referências</span><span class="sxs-lookup"><span data-stu-id="d164b-102">Report Properties Dialog Box, References</span></span>
  <span data-ttu-id="d164b-103">Selecione **Referências** na caixa de diálogo **Propriedades do Relatório** para adicionar ou remover as referências para assemblies personalizados ou outros assemblies externos e instâncias de classe personalizada usadas pelas expressões na definição do relatório.</span><span class="sxs-lookup"><span data-stu-id="d164b-103">Select **References** on the **Report Properties** dialog box to add or remove references to custom or other external assemblies and custom class instances that are used by expressions in the report definition.</span></span>  
  
## <a name="options"></a><span data-ttu-id="d164b-104">Opções</span><span class="sxs-lookup"><span data-stu-id="d164b-104">Options</span></span>  
 <span data-ttu-id="d164b-105">**Adicionar ou remover assemblies**</span><span class="sxs-lookup"><span data-stu-id="d164b-105">**Add or remove assemblies**</span></span>  
 <span data-ttu-id="d164b-106">Lista os assemblies aos quais o relatório faz referência.</span><span class="sxs-lookup"><span data-stu-id="d164b-106">Lists the assemblies that the report references.</span></span> <span data-ttu-id="d164b-107">O assembly deve estar disponível no computador no qual a ferramenta que você usando para criar o relatório está instalada e no servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="d164b-107">The assembly must be available on the computer on which the tool you are using to design the report is installed and on the report server.</span></span> <span data-ttu-id="d164b-108">O nome da referência deve corresponder exatamente ao conteúdo das **\<CodeModule>** marcas no arquivo de linguagem de definição de relatório (. RDL).</span><span class="sxs-lookup"><span data-stu-id="d164b-108">The name of the reference must match the contents of **\<CodeModule>** tags in the Report Definition Language (.rdl) file exactly.</span></span>  
  
 <span data-ttu-id="d164b-109">**Adicionar**</span><span class="sxs-lookup"><span data-stu-id="d164b-109">**Add**</span></span>  
 <span data-ttu-id="d164b-110">Clique para adicionar um assembly.</span><span class="sxs-lookup"><span data-stu-id="d164b-110">Click to add an assembly.</span></span> <span data-ttu-id="d164b-111">Clique no botão de reticências (...) para abrir a caixa de diálogo **abrir** e selecione os assemblies necessários para concluir o processamento do relatório e a avaliação da expressão.</span><span class="sxs-lookup"><span data-stu-id="d164b-111">Click the ellipsis (...) button to open the **Open** dialog box and select the assemblies necessary to complete report processing and expression evaluation.</span></span>  
  
 <span data-ttu-id="d164b-112">**Excluir**</span><span class="sxs-lookup"><span data-stu-id="d164b-112">**Delete**</span></span>  
 <span data-ttu-id="d164b-113">Para remover uma referência de assembly da lista, selecione o nome do assembly e clique no botão **Remover** .</span><span class="sxs-lookup"><span data-stu-id="d164b-113">To remove an assembly reference from the list, select the assembly name and click the **Remove** button.</span></span>  
  
 <span data-ttu-id="d164b-114">**Adicionar ou remover classes**</span><span class="sxs-lookup"><span data-stu-id="d164b-114">**Add or remove classes**</span></span>  
 <span data-ttu-id="d164b-115">Lista as instâncias de classe usadas pelo relatório.</span><span class="sxs-lookup"><span data-stu-id="d164b-115">Lists the class instances that are used by the report.</span></span> <span data-ttu-id="d164b-116">A lista de classe só é usada por membros baseados em instância, não membros estáticos.</span><span class="sxs-lookup"><span data-stu-id="d164b-116">The class list is used only by instance-based members, not static members.</span></span>  
  
 <span data-ttu-id="d164b-117">**Adicionar**</span><span class="sxs-lookup"><span data-stu-id="d164b-117">**Add**</span></span>  
 <span data-ttu-id="d164b-118">Clique para adicionar uma referência de classe.</span><span class="sxs-lookup"><span data-stu-id="d164b-118">Click to add a class reference.</span></span> <span data-ttu-id="d164b-119">Clique no botão de reticências (...) para abrir a caixa de diálogo **abrir** e selecione as classes necessárias para concluir o processamento do relatório e a avaliação da expressão.</span><span class="sxs-lookup"><span data-stu-id="d164b-119">Click the ellipsis (...) button to open the **Open** dialog box and select the classes necessary to complete report processing and expression evaluation.</span></span>  
  
 <span data-ttu-id="d164b-120">**Excluir**</span><span class="sxs-lookup"><span data-stu-id="d164b-120">**Delete**</span></span>  
 <span data-ttu-id="d164b-121">Para excluir a instância de classe, selecione-a e clique no botão **Remover** .</span><span class="sxs-lookup"><span data-stu-id="d164b-121">To delete the class instance, select it and click the **Remove** button.</span></span>  
  
 <span data-ttu-id="d164b-122">**Limpeza**</span><span class="sxs-lookup"><span data-stu-id="d164b-122">**Up**</span></span>  
 <span data-ttu-id="d164b-123">Para classes que têm dependências, você pode mover esta referência mais para cima na lista.</span><span class="sxs-lookup"><span data-stu-id="d164b-123">For classes that have dependencies, you can move this reference higher in the list.</span></span>  
  
 <span data-ttu-id="d164b-124">**Down**</span><span class="sxs-lookup"><span data-stu-id="d164b-124">**Down**</span></span>  
 <span data-ttu-id="d164b-125">Para classes que têm dependências, você pode mover esta referência mais para baixo na lista.</span><span class="sxs-lookup"><span data-stu-id="d164b-125">For classes that have dependencies, you can move this reference lower in the list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d164b-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d164b-126">See Also</span></span>  
 <span data-ttu-id="d164b-127">[Referências a código personalizado e assemblies em expressões no Designer de Relatórios &#40;SSRS&#41;](report-design/custom-code-and-assembly-references-in-expressions-in-report-designer-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="d164b-127">[Custom Code and Assembly References in Expressions in Report Designer &#40;SSRS&#41;](report-design/custom-code-and-assembly-references-in-expressions-in-report-designer-ssrs.md) </span></span>  
 <span data-ttu-id="d164b-128">[As coleções de variáveis de grupo e de relatório fazem referência &#40;Construtor de Relatórios e SSRS&#41;](report-design/built-in-collections-report-and-group-variables-references-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="d164b-128">[Report and Group Variables Collections References &#40;Report Builder and SSRS&#41;](report-design/built-in-collections-report-and-group-variables-references-report-builder.md) </span></span>  
 [<span data-ttu-id="d164b-129">Exemplos de expressões &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="d164b-129">Expression Examples &#40;Report Builder and SSRS&#41;</span></span>](report-design/expression-examples-report-builder-and-ssrs.md)  
  
  
