---
title: Especificar informações de origem (Assistente para dimensões) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.dimensionwizard.dimensionmaintable.f1
ms.assetid: 0538b490-5185-49e1-a783-4ce3539a0de5
author: minewiskan
ms.author: owend
ms.openlocfilehash: 99bbaac0bdf24a18dcde455e779f056b98106dc4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581495"
---
# <a name="specify-source-information-dimension-wizard"></a><span data-ttu-id="a52bb-102">Especificar Informações sobre a Origem (Assistente de Dimensão)</span><span class="sxs-lookup"><span data-stu-id="a52bb-102">Specify Source Information (Dimension Wizard)</span></span>
  <span data-ttu-id="a52bb-103">Use a página **Selecionar a Tabela de Dimensões Principal** para selecionar a exibição da fonte de dados, a tabela de dimensões principal, as colunas de chave e a coluna de nome de membro para a dimensão a ser criada.</span><span class="sxs-lookup"><span data-stu-id="a52bb-103">Use the **Select the Main Dimension Table** page to select the data source view, main dimension table, key columns, and member name column for the dimension to be created.</span></span>  
  
 <span data-ttu-id="a52bb-104">**Para abrir o Assistente para Dimensões**</span><span class="sxs-lookup"><span data-stu-id="a52bb-104">**To open the Dimension Wizard**</span></span>  
  
-   <span data-ttu-id="a52bb-105">No [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], no **Gerenciador de Soluções**, clique com o botão direito do mouse na pasta **Dimensões** de um projeto do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] e clique em **Nova Dimensão**.</span><span class="sxs-lookup"><span data-stu-id="a52bb-105">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], in **Solution Explorer**, right-click the **Dimensions** folder for an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project, and then click **New Dimension**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="a52bb-106">Opções</span><span class="sxs-lookup"><span data-stu-id="a52bb-106">Options</span></span>  
 <span data-ttu-id="a52bb-107">**Exibição da fonte de dados**</span><span class="sxs-lookup"><span data-stu-id="a52bb-107">**Data source view**</span></span>  
 <span data-ttu-id="a52bb-108">Selecione uma exibição da fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="a52bb-108">Select a data source view.</span></span>  
  
 <span data-ttu-id="a52bb-109">**Tabela principal**</span><span class="sxs-lookup"><span data-stu-id="a52bb-109">**Main table**</span></span>  
 <span data-ttu-id="a52bb-110">Selecione uma tabela da exibição da fonte de dados selecionada para usar como tabela principal para a dimensão.</span><span class="sxs-lookup"><span data-stu-id="a52bb-110">Select a table from the selected data source view to use as the main table for the dimension.</span></span>  
  
 <span data-ttu-id="a52bb-111">**Colunas de chave**</span><span class="sxs-lookup"><span data-stu-id="a52bb-111">**Key columns**</span></span>  
 <span data-ttu-id="a52bb-112">Selecione as colunas de chave da tabela especificada na **Tabela Principal** para o atributo de chave da dimensão.</span><span class="sxs-lookup"><span data-stu-id="a52bb-112">Select the key columns from the table specified in **Main table** for the key attribute of the dimension.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a52bb-113">Mais de uma coluna pode ser selecionada.</span><span class="sxs-lookup"><span data-stu-id="a52bb-113">More than one column can be selected.</span></span> <span data-ttu-id="a52bb-114">Se a tabela contiver uma chave primária composta, selecione todas as colunas incluídas na chave primária composta.</span><span class="sxs-lookup"><span data-stu-id="a52bb-114">If the table contains a composite primary key, select all the columns included in the composite primary key.</span></span> <span data-ttu-id="a52bb-115">A ordem das colunas de chave é importante.</span><span class="sxs-lookup"><span data-stu-id="a52bb-115">The order of the key columns is important.</span></span>  
  
 <span data-ttu-id="a52bb-116">**Coluna de Nome**</span><span class="sxs-lookup"><span data-stu-id="a52bb-116">**Name column**</span></span>  
 <span data-ttu-id="a52bb-117">Selecione a coluna da tabela especificada na **Tabela Principal** que oferece os nomes de membros para a dimensão.</span><span class="sxs-lookup"><span data-stu-id="a52bb-117">Select the column from the table specified in **Main table** that provides the member names for the dimension.</span></span> <span data-ttu-id="a52bb-118">Uma coluna de nomes deve ser especificada quando uma chave composta for usada.</span><span class="sxs-lookup"><span data-stu-id="a52bb-118">A name column must be specified when a composite key is used.</span></span> <span data-ttu-id="a52bb-119">Para criar uma coluna de nomes para uma chave composta, recomendamos criar um cálculo nomeado na exibição da fonte de dados que concatene as colunas de chave especificadas.</span><span class="sxs-lookup"><span data-stu-id="a52bb-119">To create a name column for a composite key, we recommend that you create a named calculation in the data source view that concatenates the specified key columns.</span></span> <span data-ttu-id="a52bb-120">Quando uma única chave for usada, a coluna de nome é opcional.</span><span class="sxs-lookup"><span data-stu-id="a52bb-120">When a single key is used, the name column is optional.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a52bb-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a52bb-121">See Also</span></span>  
 <span data-ttu-id="a52bb-122">[Ajuda F1 do assistente para dimensões](dimension-wizard-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="a52bb-122">[Dimension Wizard F1 Help](dimension-wizard-f1-help.md) </span></span>  
 <span data-ttu-id="a52bb-123">[Dimensões &#40;Analysis Services de dados multidimensionais&#41;](multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="a52bb-123">[Dimensions &#40;Analysis Services - Multidimensional Data&#41;](multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="a52bb-124">Dimensões em modelos multidimensionais</span><span class="sxs-lookup"><span data-stu-id="a52bb-124">Dimensions in Multidimensional Models</span></span>](multidimensional-models/dimensions-in-multidimensional-models.md)  
  
  
