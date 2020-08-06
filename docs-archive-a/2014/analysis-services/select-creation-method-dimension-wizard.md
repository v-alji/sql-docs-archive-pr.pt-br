---
title: Selecionar método de criação (Assistente para dimensões) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.dimensionwizard.dimensiondefinition.f1
ms.assetid: 291b0b2d-a03a-4df6-82f7-90ad92d4d1cf
author: minewiskan
ms.author: owend
ms.openlocfilehash: 6338a0bde7865482fb7a98d7ec36ba5a71feb806
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679042"
---
# <a name="select-creation-method-dimension-wizard"></a><span data-ttu-id="9b4eb-102">Selecionar Método de Criação (Assistente para Dimensões)</span><span class="sxs-lookup"><span data-stu-id="9b4eb-102">Select Creation Method (Dimension Wizard)</span></span>
  <span data-ttu-id="9b4eb-103">Use a página **Selecionar Método de Criação** para selecionar como criar a dimensão.</span><span class="sxs-lookup"><span data-stu-id="9b4eb-103">Use the **Select Creation Method** page to select how to create the dimension.</span></span>  
  
 <span data-ttu-id="9b4eb-104">**Para abrir o Assistente para Dimensões**</span><span class="sxs-lookup"><span data-stu-id="9b4eb-104">**To open the Dimension Wizard**</span></span>  
  
-   <span data-ttu-id="9b4eb-105">No [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], no **Gerenciador de Soluções**, clique com o botão direito do mouse na pasta **Dimensões** de um projeto do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] e clique em **Nova Dimensão**.</span><span class="sxs-lookup"><span data-stu-id="9b4eb-105">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], in **Solution Explorer**, right-click the **Dimensions** folder for an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project, and then click **New Dimension**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="9b4eb-106">Opções</span><span class="sxs-lookup"><span data-stu-id="9b4eb-106">Options</span></span>  
 <span data-ttu-id="9b4eb-107">**Usar uma tabela existente**</span><span class="sxs-lookup"><span data-stu-id="9b4eb-107">**Use an existing table**</span></span>  
 <span data-ttu-id="9b4eb-108">Crie uma dimensão a partir de uma ou mais tabelas em uma fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="9b4eb-108">Create a dimension from one or more tables in a data source.</span></span> <span data-ttu-id="9b4eb-109">Os atributos que estão disponíveis para a dimensão dependerão da estrutura dos dados na tabela.</span><span class="sxs-lookup"><span data-stu-id="9b4eb-109">The attributes that are available for the dimension will depend on the structure of the data in the table.</span></span>  
  
 <span data-ttu-id="9b4eb-110">Para obter mais informações, consulte [Criar uma dimensão usando uma tabela existente](multidimensional-models/create-a-dimension-by-using-an-existing-table.md).</span><span class="sxs-lookup"><span data-stu-id="9b4eb-110">For more information, see [Create a Dimension by Using an Existing Table](multidimensional-models/create-a-dimension-by-using-an-existing-table.md).</span></span>  
  
 <span data-ttu-id="9b4eb-111">**Gerar uma tabela de tempo na fonte de dados**</span><span class="sxs-lookup"><span data-stu-id="9b4eb-111">**Generate a time table in the data source**</span></span>  
 <span data-ttu-id="9b4eb-112">Crie uma tabela de tempo na fonte de dados subjacente e então use essa tabela para criar uma dimensão de tempo.</span><span class="sxs-lookup"><span data-stu-id="9b4eb-112">Create a time table in the underlying data source and then use that table to create a time dimension.</span></span> <span data-ttu-id="9b4eb-113">Use esta opção quando nenhuma tabela dessas existir e você não quiser usar um script para criar uma.</span><span class="sxs-lookup"><span data-stu-id="9b4eb-113">Use this option when no such table exists and you do not want to use a script to create one.</span></span> <span data-ttu-id="9b4eb-114">A nova tabela de tempo conterá dados para o intervalo de datas, atributos e calendários que você especificar no assistente.</span><span class="sxs-lookup"><span data-stu-id="9b4eb-114">The new time table will contain data for the date range, attributes, and calendars that you specify in the wizard.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9b4eb-115">Para usar esta opção, você deve ter permissão para criar objetos na fonte de dados subjacente.</span><span class="sxs-lookup"><span data-stu-id="9b4eb-115">To use this option, you must have permission to create objects in the underlying data source.</span></span> <span data-ttu-id="9b4eb-116">Se você não tiver permissão para criar objetos na fonte de dados, tente em vez disso usar a opção **Gerar uma tabela de tempo no servidor** .</span><span class="sxs-lookup"><span data-stu-id="9b4eb-116">If you do not have permission to create objects on the data source, try to use the **Generate a time table on the server** option instead.</span></span>  
  
 <span data-ttu-id="9b4eb-117">Para obter mais informações, consulte [Criar uma dimensão temporal gerando uma tabela de tempo](multidimensional-models/create-a-time-dimension-by-generating-a-time-table.md).</span><span class="sxs-lookup"><span data-stu-id="9b4eb-117">For more information, see [Create a Time Dimension by Generating a Time Table](multidimensional-models/create-a-time-dimension-by-generating-a-time-table.md).</span></span>  
  
 <span data-ttu-id="9b4eb-118">**Gerar uma tabela de tempo no servidor**</span><span class="sxs-lookup"><span data-stu-id="9b4eb-118">**Generate a time table on the server**</span></span>  
 <span data-ttu-id="9b4eb-119">Crie uma tabela de tempo diretamente no servidor e então use essa tabela para criar uma dimensão de tempo.</span><span class="sxs-lookup"><span data-stu-id="9b4eb-119">Create a time table directly on the server and then use that table to create a time dimension.</span></span> <span data-ttu-id="9b4eb-120">Use esta opção se você não tem permissão para criar objetos na fonte de dados subjacente.</span><span class="sxs-lookup"><span data-stu-id="9b4eb-120">Use this option if you do not have permission to create objects in the underlying data source.</span></span> <span data-ttu-id="9b4eb-121">A nova dimensão de tempo conterá dados para o intervalo de datas, atributos e calendários que você especificar no assistente.</span><span class="sxs-lookup"><span data-stu-id="9b4eb-121">The new time dimension will contain data for the date range, attributes, and calendars that you specify in the wizard.</span></span>  
  
 <span data-ttu-id="9b4eb-122">Para obter mais informações, consulte [Criar uma dimensão temporal gerando uma tabela de tempo](multidimensional-models/create-a-time-dimension-by-generating-a-time-table.md).</span><span class="sxs-lookup"><span data-stu-id="9b4eb-122">For more information, see [Create a Time Dimension by Generating a Time Table](multidimensional-models/create-a-time-dimension-by-generating-a-time-table.md).</span></span>  
  
 <span data-ttu-id="9b4eb-123">**Gerar uma tabela que não seja de tempo na fonte de dados**</span><span class="sxs-lookup"><span data-stu-id="9b4eb-123">**Generate a non-time table in the data source**</span></span>  
 <span data-ttu-id="9b4eb-124">Crie a dimensão sem uma fonte de dados relacional subjacente e então gere o esquema necessário para a fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="9b4eb-124">Design the dimension without an underlying relational data source, and then generate the necessary schema for the data source.</span></span> <span data-ttu-id="9b4eb-125">Esta abordagem é conhecida como modelagem de cima para baixo.</span><span class="sxs-lookup"><span data-stu-id="9b4eb-125">This approach is known as top-down modeling.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9b4eb-126">Para usar esta opção, você deve ter permissão para criar objetos na fonte de dados subjacente.</span><span class="sxs-lookup"><span data-stu-id="9b4eb-126">To use this option, you must have permission to create objects in the underlying data source.</span></span>  
  
 <span data-ttu-id="9b4eb-127">Você pode construir a dimensão com ou sem um modelo.</span><span class="sxs-lookup"><span data-stu-id="9b4eb-127">You can build the dimension with or without a template.</span></span> <span data-ttu-id="9b4eb-128">Para construir a dimensão com um modelo, selecione o modelo da lista **Modelo** .</span><span class="sxs-lookup"><span data-stu-id="9b4eb-128">To build the dimension with a template, select the template from the **Template** list.</span></span>  
  
 <span data-ttu-id="9b4eb-129">Para obter mais informações, consulte [Criar uma dimensão gerando uma tabela que não seja de tempo na fonte de dados](multidimensional-models/create-a-dimension-by-generating-a-non-time-table-in-the-data-source.md).</span><span class="sxs-lookup"><span data-stu-id="9b4eb-129">For more information, see [Create a Dimension by Generating a Non-Time Table in the Data Source](multidimensional-models/create-a-dimension-by-generating-a-non-time-table-in-the-data-source.md).</span></span>  
  
 <span data-ttu-id="9b4eb-130">**Modelo**</span><span class="sxs-lookup"><span data-stu-id="9b4eb-130">**Template**</span></span>  
 <span data-ttu-id="9b4eb-131">Selecione o modelo que deseja usar para criar a dimensão.</span><span class="sxs-lookup"><span data-stu-id="9b4eb-131">Select the template that you want to use to create the dimension.</span></span> <span data-ttu-id="9b4eb-132">Os modelos oferecem um conjunto completo de atributos e definições de hierarquia orientado a um propósito empresarial específico.</span><span class="sxs-lookup"><span data-stu-id="9b4eb-132">Templates provide a complete set of attribute and hierarchy definitions oriented towards a specific business purpose.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9b4eb-133">Esta opção só está disponível quando a opção **Gerar uma tabela que não seja de tempo na fonte de dados** tiver sido marcada.</span><span class="sxs-lookup"><span data-stu-id="9b4eb-133">This option is only available when the **Generate a non-time table in the data source** option has been selected.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b4eb-134">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9b4eb-134">See Also</span></span>  
 <span data-ttu-id="9b4eb-135">[Ajuda F1 do assistente para dimensões](dimension-wizard-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="9b4eb-135">[Dimension Wizard F1 Help](dimension-wizard-f1-help.md) </span></span>  
 <span data-ttu-id="9b4eb-136">[Dimensões &#40;Analysis Services de dados multidimensionais&#41;](multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="9b4eb-136">[Dimensions &#40;Analysis Services - Multidimensional Data&#41;](multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="9b4eb-137">Dimensões em modelos multidimensionais</span><span class="sxs-lookup"><span data-stu-id="9b4eb-137">Dimensions in Multidimensional Models</span></span>](multidimensional-models/dimensions-in-multidimensional-models.md)  
  
  
