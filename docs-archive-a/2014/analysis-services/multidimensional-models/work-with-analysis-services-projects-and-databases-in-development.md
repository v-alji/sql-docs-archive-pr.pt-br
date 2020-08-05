---
title: Trabalhando com projetos de Analysis Services e bancos de dados durante a fase de desenvolvimento | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Analysis Services, projects
ms.assetid: 39cf9166-fa92-40fe-9962-210a52461257
author: minewiskan
ms.author: owend
ms.openlocfilehash: 762ea6f33a94f65e7dd6895cd038d4a52d40d43e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574353"
---
# <a name="working-with-analysis-services-projects-and-databases-during-the-development-phase"></a><span data-ttu-id="ffc02-102">Trabalhando com projetos e bancos de dados do Analysis Services durante a fase de desenvolvimento</span><span class="sxs-lookup"><span data-stu-id="ffc02-102">Working with Analysis Services Projects and Databases During the Development Phase</span></span>
  <span data-ttu-id="ffc02-103">Você pode desenvolver um banco de dados do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] usando o [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] em modo de projeto ou online.</span><span class="sxs-lookup"><span data-stu-id="ffc02-103">You can develop an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database by using [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] in either project mode or online mode.</span></span>  
  
## <a name="single-developer"></a><span data-ttu-id="ffc02-104">Único desenvolvedor</span><span class="sxs-lookup"><span data-stu-id="ffc02-104">Single Developer</span></span>  
 <span data-ttu-id="ffc02-105">Quando apenas um desenvolvedor estiver desenvolvendo o banco de dados inteiro do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] e todos os seus objetos constituintes, o desenvolvedor pode usar o [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] em modo de projeto ou online a qualquer momento durante o ciclo de vida da solução de business intelligence.</span><span class="sxs-lookup"><span data-stu-id="ffc02-105">When only a single developer is developing the entire [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database and all of its constituent objects, the developer can use [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] in either project mode or online mode at any time during the lifecycle of the business intelligence solution.</span></span> <span data-ttu-id="ffc02-106">No caso de um único desenvolvedor, a escolha dos modos não é imprescindível.</span><span class="sxs-lookup"><span data-stu-id="ffc02-106">In the case of a single developer, the choice of modes is not particularly critical.</span></span> <span data-ttu-id="ffc02-107">A manutenção de um arquivo de projeto offline integrado ao sistema de controle de código-fonte apresenta muitas vantagens, como arquivamento e reversão.</span><span class="sxs-lookup"><span data-stu-id="ffc02-107">The maintenance of an offline project file integrated with a source control system has many benefits, such as archiving and rollback.</span></span> <span data-ttu-id="ffc02-108">No entanto, havendo um único desenvolvedor, não haverá problema de comunicar alterações a outro desenvolvedor.</span><span class="sxs-lookup"><span data-stu-id="ffc02-108">However, with a single developer you will not have the problem of communicating changes with another developer.</span></span>  
  
## <a name="multiple-developers"></a><span data-ttu-id="ffc02-109">Vários desenvolvedores</span><span class="sxs-lookup"><span data-stu-id="ffc02-109">Multiple Developers</span></span>  
 <span data-ttu-id="ffc02-110">Se houver vários desenvolvedores trabalhando em uma solução de business intelligence, surgirão problemas se eles não utilizarem o modo de projeto com o controle de código-fonte na maior parte do tempo, senão integralmente.</span><span class="sxs-lookup"><span data-stu-id="ffc02-110">When multiple developers are working on a business intelligence solution, problems will arise if the developers do not work in project mode with source control under most, if not all circumstances.</span></span> <span data-ttu-id="ffc02-111">O controle de código-fonte evita que dois desenvolvedores alterem ao mesmo tempo o mesmo objeto.</span><span class="sxs-lookup"><span data-stu-id="ffc02-111">Source control ensures that two developers are not making changes to the same object at the same time.</span></span>  
  
 <span data-ttu-id="ffc02-112">Por exemplo, suponhamos que um desenvolvedor esteja trabalhando em modo de projeto e alterando os objetos selecionados.</span><span class="sxs-lookup"><span data-stu-id="ffc02-112">For example, suppose a developer is working in project mode and making changes to selected objects.</span></span> <span data-ttu-id="ffc02-113">Enquanto ele faz essas alterações, outro desenvolvedor altera o banco de dados implantado em modo online.</span><span class="sxs-lookup"><span data-stu-id="ffc02-113">While the developer is making these changes, suppose that another developer makes a change to the deployed database in online mode.</span></span> <span data-ttu-id="ffc02-114">Um problema surgirá quando o primeiro desenvolvedor tentar implantar seu projeto do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] modificado.</span><span class="sxs-lookup"><span data-stu-id="ffc02-114">A problem will arise when the first developer attempts to deploy his or her modified [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project.</span></span> <span data-ttu-id="ffc02-115">Ou seja, o [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] detectará que os objetos mudaram no banco de dados implantado e pedirá que o desenvolvedor substitua todo o banco de dados, o que eliminará as alterações feitas pelo segundo desenvolvedor.</span><span class="sxs-lookup"><span data-stu-id="ffc02-115">Namely, [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] will detect that objects have changed within the deployed database and prompt the developer to overwrite the entire database, overwriting the changes of the second developer.</span></span> <span data-ttu-id="ffc02-116">Como o [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] não tem como resolver as alterações entre a instância do banco de dados do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] e os objetos do projeto que estão prestes a serem substituídos, a única opção real do primeiro desenvolvedor será descartar suas alterações e iniciar um novo projeto com base na versão atual do banco de dados do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ffc02-116">Since [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] has no means of resolving the changes between the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database instance and the objects in the project about to be overwritten, the only real choice the first developer has is to discard all of his or her changes and starting anew from a new project based on the current version of the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database.</span></span>  
  
  