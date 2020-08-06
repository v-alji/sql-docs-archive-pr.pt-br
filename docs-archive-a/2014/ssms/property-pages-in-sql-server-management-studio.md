---
title: Páginas de propriedades no SQL Server Management Studio | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- property pages [SQL Server Management Studio]
ms.assetid: 719282c3-e9cc-4e0e-9a83-7fb8b8b17f67
author: stevestein
ms.author: sstein
ms.openlocfilehash: 3fae6a07fbaa2a259fcca5c3807094b31e0d52d2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683891"
---
# <a name="property-pages-in-sql-server-management-studio"></a><span data-ttu-id="8e8d9-102">Páginas de propriedades no SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8e8d9-102">Property Pages in SQL Server Management Studio</span></span>
  <span data-ttu-id="8e8d9-103">As caixas de diálogo de página de propriedades no [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] usam um formato comum que exibe informações com categorias que podem ser expandidas e recolhidas.</span><span class="sxs-lookup"><span data-stu-id="8e8d9-103">Property page dialog boxes in [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] all use a common format displaying information with expanding and collapsing categories.</span></span> <span data-ttu-id="8e8d9-104">Os campos mostrados dependem da propriedade em particular.</span><span class="sxs-lookup"><span data-stu-id="8e8d9-104">The fields shown depend on the particular property.</span></span> <span data-ttu-id="8e8d9-105">As propriedades mostradas em cinza são somente leitura.</span><span class="sxs-lookup"><span data-stu-id="8e8d9-105">Properties shown in gray are read-only.</span></span> <span data-ttu-id="8e8d9-106">Os botões Categorizado e Alfabético estão na parte superior de cada página de propriedades.</span><span class="sxs-lookup"><span data-stu-id="8e8d9-106">Categorized and Alphabetic buttons are near the top of each property page.</span></span>  
  
 <span data-ttu-id="8e8d9-107">A tabela a seguir descreve os elementos comuns das caixas de diálogo das páginas de propriedades do [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8e8d9-107">The following table describes the common elements of [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] property page dialog boxes.</span></span>  
  
|<span data-ttu-id="8e8d9-108">Elemento</span><span class="sxs-lookup"><span data-stu-id="8e8d9-108">Element</span></span>|<span data-ttu-id="8e8d9-109">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="8e8d9-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8e8d9-110">**Categorizado**</span><span class="sxs-lookup"><span data-stu-id="8e8d9-110">**Categorized**</span></span>|<span data-ttu-id="8e8d9-111">Relaciona todas as propriedades e valores de propriedade do objeto selecionado, classificado por categoria.</span><span class="sxs-lookup"><span data-stu-id="8e8d9-111">Lists all properties and property values for the selected object, sorted by category.</span></span> <span data-ttu-id="8e8d9-112">Em uma exibição por categoria, você pode recolher uma categoria para reduzir o número de propriedades visíveis.</span><span class="sxs-lookup"><span data-stu-id="8e8d9-112">In category view, you can collapse a category to reduce the number of visible properties.</span></span> <span data-ttu-id="8e8d9-113">Quando você expande ou recolhe uma categoria, você vê um sinal de mais (+) ou menos (-) à esquerda do nome da categoria.</span><span class="sxs-lookup"><span data-stu-id="8e8d9-113">When you expand or collapse a category, you see a plus sign (+) or minus sign (-) to the left of the category name.</span></span> <span data-ttu-id="8e8d9-114">As categorias são listadas em ordem alfabética.</span><span class="sxs-lookup"><span data-stu-id="8e8d9-114">Categories are listed alphabetically.</span></span>|  
|<span data-ttu-id="8e8d9-115">**Alfabético**</span><span class="sxs-lookup"><span data-stu-id="8e8d9-115">**Alphabetic**</span></span>|<span data-ttu-id="8e8d9-116">Relaciona todas as propriedades e valores de propriedade do objeto selecionado, classificado por ordem alfabética.</span><span class="sxs-lookup"><span data-stu-id="8e8d9-116">Lists all properties and property values for the selected object, sorted alphabetically.</span></span>|  
|<span data-ttu-id="8e8d9-117">Nome da propriedade</span><span class="sxs-lookup"><span data-stu-id="8e8d9-117">Property name</span></span>|<span data-ttu-id="8e8d9-118">A primeira coluna da grade relaciona os nomes das propriedades.</span><span class="sxs-lookup"><span data-stu-id="8e8d9-118">The first column in the grid lists the property names.</span></span>|  
|<span data-ttu-id="8e8d9-119">Propriedades</span><span class="sxs-lookup"><span data-stu-id="8e8d9-119">Properties</span></span>|<span data-ttu-id="8e8d9-120">A segunda coluna da grade relaciona os valores das propriedades.</span><span class="sxs-lookup"><span data-stu-id="8e8d9-120">The second column in the grid lists the property values.</span></span>|  
|<span data-ttu-id="8e8d9-121">Painel de descrição</span><span class="sxs-lookup"><span data-stu-id="8e8d9-121">Description pane</span></span>|<span data-ttu-id="8e8d9-122">O painel de descrição é exibido na parte inferior da página e mostra o tipo de propriedade e uma descrição curta da propriedade.</span><span class="sxs-lookup"><span data-stu-id="8e8d9-122">The description pane appears at the bottom of the page and shows the property type and a short description of the property.</span></span> <span data-ttu-id="8e8d9-123">Você pode ativar e desativar a descrição da propriedade usando o comando **Descrição** no menu de atalho.</span><span class="sxs-lookup"><span data-stu-id="8e8d9-123">You can turn the description of the property off and on using the **Description** command on the shortcut menu.</span></span>|  
  
  
