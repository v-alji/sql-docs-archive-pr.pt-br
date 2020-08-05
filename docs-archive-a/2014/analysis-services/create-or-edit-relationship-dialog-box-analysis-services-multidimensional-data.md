---
title: Caixa de diálogo criar ou editar relação (Analysis Services-dados multidimensionais) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.dsvdesigner.createrelationship.f1
helpviewer_keywords:
- Create Relationship dialog box
ms.assetid: da3c7074-623e-4ddf-a707-d3276a47cf1c
author: minewiskan
ms.author: owend
ms.openlocfilehash: 4edae3f78ac6b764d91e1be97787fe59d49421db
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572281"
---
# <a name="create-or-edit-relationship-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="244b6-102">Caixa de diálogo Criar ou Editar Relação (Analysis Services - Dados Multidimensionais)</span><span class="sxs-lookup"><span data-stu-id="244b6-102">Create or Edit Relationship Dialog Box (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="244b6-103">Use a caixa de diálogo **Criar/Editar Relação** no [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] para definir ou modificar uma relação em uma exibição da fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="244b6-103">Use the **Create/Edit Relationship** dialog box in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] to define or modify a relationship in a data source view.</span></span> <span data-ttu-id="244b6-104">É possível exibir a caixa de diálogo **Criar/Editar Relação** das seguintes maneiras:</span><span class="sxs-lookup"><span data-stu-id="244b6-104">You can display the **Create/Edit Relationship** dialog box by:</span></span>  
  
-   <span data-ttu-id="244b6-105">Clicando em **Nova Relação** no painel **Barra de Ferramentas** do **Designer de Exibição da Fonte de Dados**.</span><span class="sxs-lookup"><span data-stu-id="244b6-105">Clicking **New Relationship** in the **Toolbar** pane of **Data Source View Designer**.</span></span>  
  
-   <span data-ttu-id="244b6-106">Clicando com o botão direito do mouse em uma tabela no painel **Tabelas** ou **Diagrama** do **Designer de Exibição da Fonte de Dados** e selecionando **Nova Relação**.</span><span class="sxs-lookup"><span data-stu-id="244b6-106">Right-clicking a table in either the **Tables** or **Diagram** pane of **Data Source View Designer** and selecting **New Relationship**.</span></span>  
  
-   <span data-ttu-id="244b6-107">Clicando com o botão direito do mouse em uma relação no painel **Diagrama** do **Designer de Exibição da Fonte de Dados** e selecionando **Explorar Relação**.</span><span class="sxs-lookup"><span data-stu-id="244b6-107">Right-clicking a relationship in the **Diagram** pane of **Data Source View Designer** and selecting **Edit Relationship**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="244b6-108">Você pode criar relações no **Designer de exibição da fonte de dados** que não existem na fonte de dados subjacente e remover relações criadas pelo **Designer de exibição da fonte de dados** de relações de chave estrangeira existentes na fonte de dados subjacente.</span><span class="sxs-lookup"><span data-stu-id="244b6-108">You can create relationships in **Data Source View Designer** that do not exist in the underlying data source, and remove relationships created by **Data Source View Designer** from existing foreign key relationships in the underlying data source.</span></span>  
  
## <a name="options"></a><span data-ttu-id="244b6-109">Opções</span><span class="sxs-lookup"><span data-stu-id="244b6-109">Options</span></span>  
 <span data-ttu-id="244b6-110">**Tabela de origem (chave estrangeira)**</span><span class="sxs-lookup"><span data-stu-id="244b6-110">**Source (foreign key) table**</span></span>  
 <span data-ttu-id="244b6-111">Selecione a tabela ou consulta nomeada que contém a referência a uma ou mais colunas na tabela de destino.</span><span class="sxs-lookup"><span data-stu-id="244b6-111">Select the table or named query that contains the reference to one or more columns in the destination table.</span></span>  
  
 <span data-ttu-id="244b6-112">**Tabela de destino (chave primária)**</span><span class="sxs-lookup"><span data-stu-id="244b6-112">**Destination (primary key) table**</span></span>  
 <span data-ttu-id="244b6-113">Selecione a tabela que contém uma ou mais colunas referenciadas pela tabela de origem.</span><span class="sxs-lookup"><span data-stu-id="244b6-113">Select the table that contains one or more columns referenced by the source table.</span></span> <span data-ttu-id="244b6-114">Para autojunções, selecione a mesma tabela selecionada em **Tabela de origem (chave estrangeira)**.</span><span class="sxs-lookup"><span data-stu-id="244b6-114">For self-joins, select the same table selected in **Source (foreign key) table**.</span></span>  
  
 <span data-ttu-id="244b6-115">**Colunas de origem**</span><span class="sxs-lookup"><span data-stu-id="244b6-115">**Source columns**</span></span>  
 <span data-ttu-id="244b6-116">Selecione as colunas que referenciam colunas na tabela de dimensões.</span><span class="sxs-lookup"><span data-stu-id="244b6-116">Select the columns that reference columns in the destination table.</span></span>  
  
 <span data-ttu-id="244b6-117">**Colunas de destino**</span><span class="sxs-lookup"><span data-stu-id="244b6-117">**Destination columns**</span></span>  
 <span data-ttu-id="244b6-118">Selecione as colunas que são referenciadas pelas colunas na tabela de origem.</span><span class="sxs-lookup"><span data-stu-id="244b6-118">Select the columns that are referenced by columns in the source table.</span></span>  
  
 <span data-ttu-id="244b6-119">**Ordem**</span><span class="sxs-lookup"><span data-stu-id="244b6-119">**Reverse**</span></span>  
 <span data-ttu-id="244b6-120">Clique para inverter a direção da relação.</span><span class="sxs-lookup"><span data-stu-id="244b6-120">Click to reverse the direction of the relationship.</span></span>  
  
 <span data-ttu-id="244b6-121">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="244b6-121">**Description**</span></span>  
 <span data-ttu-id="244b6-122">Digite uma descrição opcional para a relação.</span><span class="sxs-lookup"><span data-stu-id="244b6-122">Type an optional description for the relationship.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="244b6-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="244b6-123">See Also</span></span>  
 <span data-ttu-id="244b6-124">[Analysis Services designers e caixas de diálogo &#40;dados multidimensionais&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="244b6-124">[Analysis Services Designers and Dialog Boxes &#40;Multidimensional Data&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="244b6-125">Designer de Exibição da Fonte de Dados &#40;Analysis Services – Dados multidimensionais&#41;</span><span class="sxs-lookup"><span data-stu-id="244b6-125">Data Source View Designer &#40;Analysis Services - Multidimensional Data&#41;</span></span>](data-source-view-designer-analysis-services-multidimensional-data.md)  
  
  
