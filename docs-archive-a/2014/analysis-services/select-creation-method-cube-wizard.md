---
title: Selecionar método de criação (Assistente para cubos) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.cubewizard.cubedefinition.f1
ms.assetid: 985d3b5b-7891-465b-862d-f7e75431b342
author: minewiskan
ms.author: owend
ms.openlocfilehash: c8c4d611e00a2b3f5d115ea5749b1e494a44bf57
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582139"
---
# <a name="select-creation-method-cube-wizard"></a><span data-ttu-id="d86da-102">Selecionar Método de Criação (Assistente para Cubos)</span><span class="sxs-lookup"><span data-stu-id="d86da-102">Select Creation Method (Cube Wizard)</span></span>
  <span data-ttu-id="d86da-103">Use a página **Selecionar Método de Criação** para especificar como criar o cubo.</span><span class="sxs-lookup"><span data-stu-id="d86da-103">Use the **Select Creation Method** page to specify how to create the cube.</span></span>  
  
## <a name="options"></a><span data-ttu-id="d86da-104">Opções</span><span class="sxs-lookup"><span data-stu-id="d86da-104">Options</span></span>  
 <span data-ttu-id="d86da-105">**Usar tabelas existentes**</span><span class="sxs-lookup"><span data-stu-id="d86da-105">**Use existing tables**</span></span>  
 <span data-ttu-id="d86da-106">Selecione para criar um cubo usando tabelas existentes em uma fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="d86da-106">Select to create a cube by using existing tables in a data source.</span></span> <span data-ttu-id="d86da-107">O assistente guiará você pelo processo de seleção e definição de grupos de medidas e dimensões com base nas tabelas existentes para criar seu novo cubo.</span><span class="sxs-lookup"><span data-stu-id="d86da-107">The wizard will guide you through the process of selecting and defining measure groups and dimensions based on existing tables to build your new cube.</span></span>  
  
 <span data-ttu-id="d86da-108">**Criar um cubo vazio**</span><span class="sxs-lookup"><span data-stu-id="d86da-108">**Create an empty cube**</span></span>  
 <span data-ttu-id="d86da-109">Selecione para criar um cubo vazio.</span><span class="sxs-lookup"><span data-stu-id="d86da-109">Select to create an empty cube.</span></span> <span data-ttu-id="d86da-110">Essa opção será útil quando você desejar criar tudo manualmente ou quando todos os grupos de medidas no cubo forem grupos de medidas vinculados.</span><span class="sxs-lookup"><span data-stu-id="d86da-110">This option is useful when you want to create everything manually, or when all measure groups in the cube are linked measure groups.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d86da-111">Essa opção só estará disponível quando você estiver trabalhando com um projeto do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] e não quando você estiver conectado diretamente com um banco de dados do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d86da-111">This option is only available when you are working with an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project and not when you are connected directly to an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database.</span></span>  
  
 <span data-ttu-id="d86da-112">**Gerar tabelas na fonte de dados**</span><span class="sxs-lookup"><span data-stu-id="d86da-112">**Generate tables in the data source**</span></span>  
 <span data-ttu-id="d86da-113">Selecione para criar um cubo primeiro e, em seguida, gerar novas tabelas na fonte de dados com base na definição do cubo.</span><span class="sxs-lookup"><span data-stu-id="d86da-113">Select to create a cube first and then generate new tables in the data source based on the cube definition.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d86da-114">Para usar esta opção, você deve ter permissão para criar objetos na fonte de dados subjacente.</span><span class="sxs-lookup"><span data-stu-id="d86da-114">To use this option, you must have permission to create objects in the underlying data source.</span></span>  
  
 <span data-ttu-id="d86da-115">Selecionar essa opção tornará a opção **Modelo** disponível.</span><span class="sxs-lookup"><span data-stu-id="d86da-115">Selecting this option will make the **Template** option available.</span></span>  
  
 <span data-ttu-id="d86da-116">**Modelo**</span><span class="sxs-lookup"><span data-stu-id="d86da-116">**Template**</span></span>  
 <span data-ttu-id="d86da-117">Selecione o modelo que deseja usar para criar o cubo.</span><span class="sxs-lookup"><span data-stu-id="d86da-117">Select the template that you want to use to create the cube.</span></span> <span data-ttu-id="d86da-118">Os modelos oferecem um conjunto de definições orientado para um propósito de negócio específico.</span><span class="sxs-lookup"><span data-stu-id="d86da-118">Templates provide a set of definitions oriented towards a specific business purpose.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d86da-119">Essa opção só estará disponível quando a opção **Gerar tabelas na fonte de dados** for selecionada.</span><span class="sxs-lookup"><span data-stu-id="d86da-119">This option is only available when the **Generate tables in the data source** option has been selected.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d86da-120">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d86da-120">See Also</span></span>  
 <span data-ttu-id="d86da-121">[Objetos de cubo &#40;Analysis Services de dados multidimensionais&#41;](multidimensional-models-olap-logical-cube-objects/cube-objects-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="d86da-121">[Cube Objects &#40;Analysis Services - Multidimensional Data&#41;](multidimensional-models-olap-logical-cube-objects/cube-objects-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="d86da-122">[Cubos em modelos multidimensionais](multidimensional-models/cubes-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="d86da-122">[Cubes in Multidimensional Models](multidimensional-models/cubes-in-multidimensional-models.md) </span></span>  
 [<span data-ttu-id="d86da-123">Dimensões em modelos multidimensionais</span><span class="sxs-lookup"><span data-stu-id="d86da-123">Dimensions in Multidimensional Models</span></span>](multidimensional-models/dimensions-in-multidimensional-models.md)  
  
  
