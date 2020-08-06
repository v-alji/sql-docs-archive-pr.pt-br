---
title: Exibir o XML para um projeto Analysis Services (SSDT) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- projects [Analysis Services], viewing XML
ms.assetid: dd1a4bc6-57b5-47df-8619-09f921aa6351
author: minewiskan
ms.author: owend
ms.openlocfilehash: 1c320145be2073c741498bed0f10732ac8d528e9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684924"
---
# <a name="view-the-xml-for-an-analysis-services-project-ssdt"></a><span data-ttu-id="77254-102">Exibir o XML de um projeto do Analysis Services (SSDT)</span><span class="sxs-lookup"><span data-stu-id="77254-102">View the XML for an Analysis Services Project (SSDT)</span></span>
  <span data-ttu-id="77254-103">Quando você trabalha com um banco de dados do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] no modo de projeto, o [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] cria uma definição XML para cada objeto da pasta de projeto.</span><span class="sxs-lookup"><span data-stu-id="77254-103">When you are working with an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database in project mode, [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] creates an XML definition for each object within the project folder.</span></span> <span data-ttu-id="77254-104">Você pode exibir o conteúdo do arquivo XML de cada objeto do [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="77254-104">You can view the contents of the XML file for each object within [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="77254-105">Pode também editar o arquivo XML diretamente; contudo, isso não é recomendável na maioria das vezes, pois você pode fazer alterações que inviabilizarão a leitura do XML pelo [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="77254-105">You can also edit the XML file directly; however, this is not recommended in most circumstances as you may make changes that make the XML unreadable by [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="77254-106">Não é possível exibir o código xml do projeto inteiro, mas sim o código de cada objeto, pois existe um arquivo separado para cada um deles.</span><span class="sxs-lookup"><span data-stu-id="77254-106">You cannot view the xml code for an entire project, but rather you view the code for each object because a separate file exists for each object.</span></span> <span data-ttu-id="77254-107">A única maneira de exibir o código de um projeto inteiro é criar o projeto e exibir o código ASSL no \<project name> arquivo. asdatabase.</span><span class="sxs-lookup"><span data-stu-id="77254-107">The only way to view the code for an entire project is to build the project and view the ASSL code in the \<project name>.asdatabase file.</span></span>  
  
### <a name="to-view-the-xml-code-for-an-object"></a><span data-ttu-id="77254-108">Exibir o código de XML de um objeto</span><span class="sxs-lookup"><span data-stu-id="77254-108">To view the XML code for an object</span></span>  
  
1.  <span data-ttu-id="77254-109">Abra o projeto do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] no [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="77254-109">Open the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="77254-110">No Gerenciador de Soluções, clique com o botão direito do mouse no objeto e clique em **Exibir Código**.</span><span class="sxs-lookup"><span data-stu-id="77254-110">Right-click the object in Solution Explorer and then click **View Code**.</span></span>  
  
     <span data-ttu-id="77254-111">O código XML do objeto aparece no [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="77254-111">The XML code for the object appears in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77254-112">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="77254-112">See Also</span></span>  
 [<span data-ttu-id="77254-113">Criar projetos do Analysis Services &#40;SSDT&#41;</span><span class="sxs-lookup"><span data-stu-id="77254-113">Build Analysis Services Projects &#40;SSDT&#41;</span></span>](build-analysis-services-projects-ssdt.md)  
  
  
