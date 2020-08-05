---
title: Desenvolvendo com ASSL (linguagem de script de Analysis Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- Analysis Services Scripting Language
- ASSL
ms.assetid: ce9aca4d-b7ad-451e-bb7f-20c2b0c03f29
author: minewiskan
ms.author: owend
ms.openlocfilehash: fbb64c120e67d5b4ac12e7bd77f0e0c4e5736757
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574359"
---
# <a name="developing-with-analysis-services-scripting-language-assl"></a><span data-ttu-id="b832e-102">Desenvolvendo com ASSL (linguagem de script do Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="b832e-102">Developing with Analysis Services Scripting Language (ASSL)</span></span>
  <span data-ttu-id="b832e-103">ASSL (Linguagem de scripts do Analysis Services) é uma extensão ao XMLA que adiciona uma linguagem de definição de objeto e linguagem de comandos para criar e gerenciar as estruturas do Analysis Services diretamente no servidor.</span><span class="sxs-lookup"><span data-stu-id="b832e-103">Analysis Services Scripting Language (ASSL) is an extension to XMLA that adds an object definition language and command language for creating and managing Analysis Services structures directly on the server.</span></span> <span data-ttu-id="b832e-104">Você pode usar o ASSL em um aplicativo personalizado para comunicar-se com o Analysis Services em um protocolo XMLA.</span><span class="sxs-lookup"><span data-stu-id="b832e-104">You can use ASSL in custom application to communicate with Analysis Services over the XMLA protocol.</span></span> <span data-ttu-id="b832e-105">O ASSL é composto de duas partes:</span><span class="sxs-lookup"><span data-stu-id="b832e-105">ASSL is made up of two parts:</span></span>  
  
-   <span data-ttu-id="b832e-106">Uma DDL (Linguagem de Definição de Dados), ou linguagem de definição de objeto, define e descreve uma instância do [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)], além de bancos de dados e de objetos de banco de dados contidos na instância.</span><span class="sxs-lookup"><span data-stu-id="b832e-106">A Data Definition Language (DDL), or object definition language, defines and describes an instance of [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)], as well as the databases and database objects that the instance contains.</span></span>  
  
-   <span data-ttu-id="b832e-107">Uma linguagem de comandos que envia comandos de ação, como `Create`, `Alter`ou `Process`, para uma instância do Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="b832e-107">A command language that sends action commands, such as `Create`, `Alter`, or `Process`, to an instance of Analysis Services.</span></span> <span data-ttu-id="b832e-108">Esse idioma de comando é discutido no [XML for Analysis &#40;referência de&#41; XMLA](https://docs.microsoft.com/bi-reference/xmla/xml-for-analysis-xmla-reference).</span><span class="sxs-lookup"><span data-stu-id="b832e-108">This command language is discussed in the [XML for Analysis  &#40;XMLA&#41; Reference](https://docs.microsoft.com/bi-reference/xmla/xml-for-analysis-xmla-reference).</span></span>  
  
 <span data-ttu-id="b832e-109">Para exibir o ASSL que descreve uma solução multidimensional no [!INCLUDE[ssBIDevStudio](../../../includes/ssbidevstudio-md.md)], você pode usar o comando de Código de Exibição no nível do projeto.</span><span class="sxs-lookup"><span data-stu-id="b832e-109">To view the ASSL that describes a multidimensional solution in [!INCLUDE[ssBIDevStudio](../../../includes/ssbidevstudio-md.md)], you can use the View Code command at the project level.</span></span> <span data-ttu-id="b832e-110">Ainda é possível criar ou editar script ASSL no [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)] usando o editor de consultas XMLA.</span><span class="sxs-lookup"><span data-stu-id="b832e-110">You can also create or edit ASSL script in [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)] using the XMLA query editor.</span></span> <span data-ttu-id="b832e-111">Os scripts que você cria podem ser usados para gerenciar objetos ou executar comandos no servidor.</span><span class="sxs-lookup"><span data-stu-id="b832e-111">The scripts you build can be used to manage objects or run commands on the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b832e-112">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b832e-112">See Also</span></span>  
 <span data-ttu-id="b832e-113">[Objetos ASSL e características de objeto](assl-objects-and-object-characteristics.md) </span><span class="sxs-lookup"><span data-stu-id="b832e-113">[ASSL Objects and Object Characteristics](assl-objects-and-object-characteristics.md) </span></span>  
 <span data-ttu-id="b832e-114">[Convenções XML ASSL](assl-xml-conventions.md) </span><span class="sxs-lookup"><span data-stu-id="b832e-114">[ASSL XML Conventions](assl-xml-conventions.md) </span></span>  
 [<span data-ttu-id="b832e-115">Fontes de dados e associações &#40;SSAS multidimensional&#41;</span><span class="sxs-lookup"><span data-stu-id="b832e-115">Data Sources and Bindings &#40;SSAS Multidimensional&#41;</span></span>](../data-sources-and-bindings-ssas-multidimensional.md)  
  
  
