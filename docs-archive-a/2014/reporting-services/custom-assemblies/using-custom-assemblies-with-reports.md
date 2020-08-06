---
title: Usando assemblies personalizados com relatórios | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- custom assemblies [Reporting Services]
- assemblies [Reporting Services], custom
- custom assemblies [Reporting Services], about custom assemblies
ms.assetid: 53d141d0-2185-466a-84dc-7b90d284da3d
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f77b9da44ebb57617bd45e43d1e1e847e9074662
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679726"
---
# <a name="using-custom-assemblies-with-reports"></a><span data-ttu-id="372d2-102">Usando assemblies personalizados com relatórios</span><span class="sxs-lookup"><span data-stu-id="372d2-102">Using Custom Assemblies with Reports</span></span>
  <span data-ttu-id="372d2-103">No [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], você pode escrever código personalizado para valores de item de relatório, estilos e formatação.</span><span class="sxs-lookup"><span data-stu-id="372d2-103">In [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], you can write custom code for report item values, styles, and formatting.</span></span> <span data-ttu-id="372d2-104">Por exemplo, você pode usar código personalizado para formatar moedas com base na localidade, sinalizar certos valores com formatação especial ou aplicar outras regras comerciais que sejam praticadas por sua empresa.</span><span class="sxs-lookup"><span data-stu-id="372d2-104">For example, you can use custom code to format currencies based on locale, flag certain values with special formatting, or apply other business rules that are in practice for your company.</span></span> <span data-ttu-id="372d2-105">Uma maneira de incluir esse código em seus relatórios é criar um assembly de código personalizado usando o [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] que você pode referenciar em seus arquivos de definição de relatório.</span><span class="sxs-lookup"><span data-stu-id="372d2-105">One way to include this code in your reports is to create a custom code assembly using the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] that you can reference from within your report definition files.</span></span> <span data-ttu-id="372d2-106">O servidor chama as funções em seus assemblies personalizados quando um relatório é executado.</span><span class="sxs-lookup"><span data-stu-id="372d2-106">The server calls the functions in your custom assemblies when a report is run.</span></span> <span data-ttu-id="372d2-107">Os assemblies personalizados podem ser usados para recuperar funções especializadas que você planeja usar em seus relatórios.</span><span class="sxs-lookup"><span data-stu-id="372d2-107">Custom assemblies can be used to retrieve specialized functions that you plan to use in your reports.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="372d2-108">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="372d2-108">In This Section</span></span>  
 [<span data-ttu-id="372d2-109">Referenciando assemblies em um arquivo RDL</span><span class="sxs-lookup"><span data-stu-id="372d2-109">Referencing Assemblies in an RDL File</span></span>](referencing-assemblies-in-an-rdl-file.md)  
 <span data-ttu-id="372d2-110">Descreve como referenciar seus assemblies personalizados em um arquivo de linguagem de definição de relatório.</span><span class="sxs-lookup"><span data-stu-id="372d2-110">Describes how to reference your custom assemblies in a report definition language file.</span></span>  
  
 [<span data-ttu-id="372d2-111">Implantando um assembly personalizado</span><span class="sxs-lookup"><span data-stu-id="372d2-111">Deploying a Custom Assembly</span></span>](deploying-a-custom-assembly.md)  
 <span data-ttu-id="372d2-112">Descreve como implantar um assembly personalizado para o Designer de Relatórios e para o servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="372d2-112">Describes how to deploy a custom assembly to Report Designer and the report server.</span></span>  
  
 [<span data-ttu-id="372d2-113">Usando assemblies de nome forte personalizados</span><span class="sxs-lookup"><span data-stu-id="372d2-113">Using Strong-Named Custom Assemblies</span></span>](using-strong-named-custom-assemblies.md)  
 <span data-ttu-id="372d2-114">Descreve como usar assemblies personalizados com nomes fortes.</span><span class="sxs-lookup"><span data-stu-id="372d2-114">Describes how to use custom assemblies with strong names.</span></span>  
  
 [<span data-ttu-id="372d2-115">Declarando permissões em assemblies personalizados</span><span class="sxs-lookup"><span data-stu-id="372d2-115">Asserting Permissions in Custom Assemblies</span></span>](asserting-permissions-in-custom-assemblies.md)  
 <span data-ttu-id="372d2-116">Descreve como implantar assemblies personalizados com permissões limitadas e específicas e como declarar essas permissões em código.</span><span class="sxs-lookup"><span data-stu-id="372d2-116">Describes how to deploy custom assemblies with limited and specific permissions and how to assert those permissions in code.</span></span>  
  
 [<span data-ttu-id="372d2-117">Acessando assemblies personalizados por meio de expressões</span><span class="sxs-lookup"><span data-stu-id="372d2-117">Accessing Custom Assemblies Through Expressions</span></span>](accessing-custom-assemblies-through-expressions.md)  
 <span data-ttu-id="372d2-118">Descreve como chamar métodos de assembly personalizados como expressões de relatório em suas definições de relatório.</span><span class="sxs-lookup"><span data-stu-id="372d2-118">Describes how to call custom assembly methods as report expressions in your report definitions.</span></span>  
  
 [<span data-ttu-id="372d2-119">Inicializando objetos assembly personalizados</span><span class="sxs-lookup"><span data-stu-id="372d2-119">Initializing Custom Assembly Objects</span></span>](initializing-custom-assembly-objects.md)  
 <span data-ttu-id="372d2-120">Descreve como inicializar valores para objetos de assembly personalizados chamados de um relatório.</span><span class="sxs-lookup"><span data-stu-id="372d2-120">Describes how to initialize values for custom assembly objects called from a report.</span></span>  
  
 [<span data-ttu-id="372d2-121">Como fazer: Depurar assemblies personalizados</span><span class="sxs-lookup"><span data-stu-id="372d2-121">How to: Debug Custom Assemblies</span></span>](how-to-debug-custom-assemblies.md)  
 <span data-ttu-id="372d2-122">Descreve como depurar seu código de assembly personalizado.</span><span class="sxs-lookup"><span data-stu-id="372d2-122">Describes how to debug your custom assembly code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="372d2-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="372d2-123">See Also</span></span>  
 [<span data-ttu-id="372d2-124">Linguagem RDL &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="372d2-124">Report Definition Language &#40;SSRS&#41;</span></span>](../reports/report-definition-language-ssrs.md)  
  
  
