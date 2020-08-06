---
title: Definir dimensões de banco de dados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- dimensions [Analysis Services], defining
ms.assetid: fe84588b-66a3-4100-a1cf-59b21b7adf01
author: minewiskan
ms.author: owend
ms.openlocfilehash: ad5334e71b0f133f80933a7d1702d8ada7565501
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679059"
---
# <a name="define-database-dimensions"></a><span data-ttu-id="44524-102">Definir as dimensões do banco de dados</span><span class="sxs-lookup"><span data-stu-id="44524-102">Define Database Dimensions</span></span>
  <span data-ttu-id="44524-103">Use o designer de dimensão no [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] para configurar uma dimensão de banco de dados existente em um [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] projeto ou banco de dados.</span><span class="sxs-lookup"><span data-stu-id="44524-103">Use Dimension Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] to configure an existing database dimension in a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project or database.</span></span> <span data-ttu-id="44524-104">Você pode usar o Designer de Dimensão para fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="44524-104">You can use Dimension Designer to do the following:</span></span>  
  
-   <span data-ttu-id="44524-105">Configurar as propriedades do nível de dimensão.</span><span class="sxs-lookup"><span data-stu-id="44524-105">Configure the dimension-level properties.</span></span>  
  
-   <span data-ttu-id="44524-106">Adicionar e configurar os atributos de dimensão.</span><span class="sxs-lookup"><span data-stu-id="44524-106">Add and configure dimension attributes.</span></span>  
  
-   <span data-ttu-id="44524-107">Definir e configurar hierarquias definidas pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="44524-107">Define and configure user-defined hierarchies.</span></span>  
  
-   <span data-ttu-id="44524-108">Definir e configurar relações entre atributos.</span><span class="sxs-lookup"><span data-stu-id="44524-108">Define and configure relationships between attributes.</span></span>  
  
-   <span data-ttu-id="44524-109">Definir conversões de dimensão.</span><span class="sxs-lookup"><span data-stu-id="44524-109">Define dimension translations.</span></span>  
  
-   <span data-ttu-id="44524-110">Para dimensões processadas, você pode procurar na estrutura de dimensão e exibir dados.</span><span class="sxs-lookup"><span data-stu-id="44524-110">For processed dimensions, you can browse the dimension structure and view data.</span></span>  
  
 <span data-ttu-id="44524-111">Depois que você modificar uma dimensão, um atributo ou uma hierarquia, é necessário processar a dimensão em questão para exibir as mudanças.</span><span class="sxs-lookup"><span data-stu-id="44524-111">After you modify a dimension, attribute, or hierarchy, you must process that dimension to view the changes.</span></span> <span data-ttu-id="44524-112">Ao trabalhar em modo de projeto, você implanta as alterações na instância do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] antes do processamento.</span><span class="sxs-lookup"><span data-stu-id="44524-112">When working in project mode, you deploy the changes to the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance before processing.</span></span>  
  
 <span data-ttu-id="44524-113">Para obter mais informações sobre como abrir uma dimensão no Designer de Dimensões, consulte [Modificar ou excluir uma dimensão de banco de dados no Gerenciador de Soluções](database-dimensions-modify-or-delete-a-database-dimension-in-solution-explorer.md).</span><span class="sxs-lookup"><span data-stu-id="44524-113">For more information about how to open a dimension in Dimension Designer, see [Modify or Delete a Database Dimension in Solution Explorer](database-dimensions-modify-or-delete-a-database-dimension-in-solution-explorer.md).</span></span>  
  
 <span data-ttu-id="44524-114">O Designer de Dimensão tem três guias diferentes que são descritas na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="44524-114">Dimension Designer has three different tabs, which are described in the following table.</span></span>  
  
|<span data-ttu-id="44524-115">Tab</span><span class="sxs-lookup"><span data-stu-id="44524-115">Tab</span></span>|<span data-ttu-id="44524-116">Descrição</span><span class="sxs-lookup"><span data-stu-id="44524-116">Description</span></span>|  
|---------|-----------------|  
|<span data-ttu-id="44524-117">**Estrutura da Dimensão**</span><span class="sxs-lookup"><span data-stu-id="44524-117">**Dimension Structure**</span></span>|<span data-ttu-id="44524-118">Use esta guia para trabalhar com a estrutura de uma dimensão-para examinar ou criar o esquema de exibição da fonte de dados para uma dimensão, para trabalhar com atributos e para organizar atributos em hierarquias definidas pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="44524-118">Use this tab to work with the structure of a dimension-to examine or create the data source view schema for a dimension, to work with attributes, and to organize attributes in user-defined hierarchies.</span></span>|  
|<span data-ttu-id="44524-119">**Relações de Atributo**</span><span class="sxs-lookup"><span data-stu-id="44524-119">**Attribute Relationships**</span></span>|<span data-ttu-id="44524-120">Use essa guia para criar, modificar ou excluir as relações de atributo de uma dimensão.</span><span class="sxs-lookup"><span data-stu-id="44524-120">Use this tab to create, modify, or delete the attribute relationships of a dimension.</span></span>|  
|<span data-ttu-id="44524-121">**Translations**</span><span class="sxs-lookup"><span data-stu-id="44524-121">**Translations**</span></span>|<span data-ttu-id="44524-122">Use essa guia para adicionar e editar conversões de metadados de dimensão em linguagens diferentes.</span><span class="sxs-lookup"><span data-stu-id="44524-122">Use this tab to add and edit translations of dimension metadata in different languages.</span></span>|  
|<span data-ttu-id="44524-123">**Navegador**</span><span class="sxs-lookup"><span data-stu-id="44524-123">**Browser**</span></span>|<span data-ttu-id="44524-124">Use essa guia para examinar os membros de uma dimensão processada e para revisar as conversões de metadados de dimensão.</span><span class="sxs-lookup"><span data-stu-id="44524-124">Use this tab to examine the members of a processed dimension and to review translations of dimension metadata.</span></span>|  
  
 <span data-ttu-id="44524-125">Os tópicos a seguir descrevem as tarefas que você pode executar no Designer de Dimensão.</span><span class="sxs-lookup"><span data-stu-id="44524-125">The following topics describe the tasks that you can perform in Dimension Designer.</span></span>  
  
 [<span data-ttu-id="44524-126">Referência de propriedades de atributo de dimensão</span><span class="sxs-lookup"><span data-stu-id="44524-126">Dimension Attribute Properties Reference</span></span>](dimension-attribute-properties-reference.md)  
 <span data-ttu-id="44524-127">Descreve como definir e configurar um atributo de dimensão.</span><span class="sxs-lookup"><span data-stu-id="44524-127">Describes how to define and configure a dimension attribute.</span></span>  
  
 [<span data-ttu-id="44524-128">Criar hierarquias definidas pelo usuário</span><span class="sxs-lookup"><span data-stu-id="44524-128">Create User-Defined Hierarchies</span></span>](user-defined-hierarchies-create.md)  
 <span data-ttu-id="44524-129">Descreve como definir e configurar uma hierarquia definida pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="44524-129">Describes how to define and configure a user-defined hierarchy.</span></span>  
  
 [<span data-ttu-id="44524-130">Definir relações de atributo</span><span class="sxs-lookup"><span data-stu-id="44524-130">Define Attribute Relationships</span></span>](attribute-relationships-define.md)  
 <span data-ttu-id="44524-131">Descreve como definir e configurar uma relação de atributo.</span><span class="sxs-lookup"><span data-stu-id="44524-131">Describes how to define and configure an attribute relationship.</span></span>  
  
 [<span data-ttu-id="44524-132">Usar o Assistente de Business Intelligence para aprimorar dimensões</span><span class="sxs-lookup"><span data-stu-id="44524-132">Use the Business Intelligence Wizard to Enhance Dimensions</span></span>](../use-the-business-intelligence-wizard-to-enhance-dimensions.md)  
 <span data-ttu-id="44524-133">Descreve como usar o Business Intelligence Wizard para aprimorar uma dimensão.</span><span class="sxs-lookup"><span data-stu-id="44524-133">Describes how to use the Business Intelligence Wizard to enhance a dimension.</span></span>  
  
  
