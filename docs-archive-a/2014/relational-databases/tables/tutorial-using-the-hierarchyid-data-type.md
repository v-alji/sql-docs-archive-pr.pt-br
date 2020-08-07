---
title: 'Tutorial: usando o tipo de dados hierarchyid | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- tutorials [hierarchyid]
- hierarchyid [Database Engine], tutorial
ms.assetid: 5a7f7cfd-7faf-439f-8085-8fd6bf7db355
author: stevestein
ms.author: sstein
ms.openlocfilehash: a735b4c2b51e1c680c8129647733ce1efd9f9984
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571915"
---
# <a name="tutorial-using-the-hierarchyid-data-type"></a><span data-ttu-id="e5c4c-102">Tutorial: Usando o tipo de dados hierarchyid</span><span class="sxs-lookup"><span data-stu-id="e5c4c-102">Tutorial: Using the hierarchyid Data Type</span></span>
  <span data-ttu-id="e5c4c-103">Este tutorial é destinado a usuários com experiência em [!INCLUDE[tsql](../../includes/tsql-md.md)], mas principiantes em tipo de dados `hierarchyid`.</span><span class="sxs-lookup"><span data-stu-id="e5c4c-103">This tutorial is intended for users who are experienced with [!INCLUDE[tsql](../../includes/tsql-md.md)], but are new to the `hierarchyid` data type.</span></span>  
  
## <a name="what-you-will-learn"></a><span data-ttu-id="e5c4c-104">O que você aprenderá</span><span class="sxs-lookup"><span data-stu-id="e5c4c-104">What You Will Learn</span></span>  
 <span data-ttu-id="e5c4c-105">Este tutorial é dividido em duas lições:</span><span class="sxs-lookup"><span data-stu-id="e5c4c-105">This tutorial is divided into two lessons:</span></span>  
  
 [<span data-ttu-id="e5c4c-106">Lição 1: convertendo uma tabela em uma estrutura hierárquica</span><span class="sxs-lookup"><span data-stu-id="e5c4c-106">Lesson 1: Converting a Table to a Hierarchical Structure</span></span>](lesson-1-converting-a-table-to-a-hierarchical-structure.md)  
 <span data-ttu-id="e5c4c-107">Nesta lição, você usa uma tabela de funcionário existente, que foi estruturada como hierarquia pai/filho, e move os dados para uma tabela nova que represente a hierarquia, usando o tipo de dados `hierarchyid`.</span><span class="sxs-lookup"><span data-stu-id="e5c4c-107">In this lesson, you take an existing employee table that is structured as a parent/child hierarchy and move the data into a new table that represents the hierarchy by using the `hierarchyid` data type.</span></span> <span data-ttu-id="e5c4c-108">Esta lição exige o banco de dados de exemplo [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e5c4c-108">This lesson requires the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample database.</span></span>  
  
 [<span data-ttu-id="e5c4c-109">Lição 2: criando e gerenciando dados em uma tabela hierárquica</span><span class="sxs-lookup"><span data-stu-id="e5c4c-109">Lesson 2: Creating and Managing Data in a Hierarchical Table</span></span>](lesson-2-creating-and-managing-data-in-a-hierarchical-table.md)  
 <span data-ttu-id="e5c4c-110">Nesta lição, você cria uma tabela usando o tipo de dados `hierarchyid` para representar a estrutura da hierarquia.</span><span class="sxs-lookup"><span data-stu-id="e5c4c-110">In this lesson, you create a table by using the `hierarchyid` data type to represent the hierarchy structure.</span></span> <span data-ttu-id="e5c4c-111">Em seguida, você manipula os dados da tabela usando os métodos hierárquicos.</span><span class="sxs-lookup"><span data-stu-id="e5c4c-111">Then, you manipulate the data in the table by using the hierarchical methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5c4c-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e5c4c-112">Requirements</span></span>  
 <span data-ttu-id="e5c4c-113">O sistema deverá ter o seguinte instalado:</span><span class="sxs-lookup"><span data-stu-id="e5c4c-113">Your system must have the following installed:</span></span>  
  
-   <span data-ttu-id="e5c4c-114">Qualquer edição do [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] ou posterior.</span><span class="sxs-lookup"><span data-stu-id="e5c4c-114">Any edition of [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] or later.</span></span>  
  
-   <span data-ttu-id="e5c4c-115">O [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] Express.</span><span class="sxs-lookup"><span data-stu-id="e5c4c-115">Either [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] Express.</span></span>  
  
-   <span data-ttu-id="e5c4c-116">Internet Explorer 6 ou versão posterior.</span><span class="sxs-lookup"><span data-stu-id="e5c4c-116">Internet Explorer 6 or a later version.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5c4c-117">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e5c4c-117">See Also</span></span>  
 <span data-ttu-id="e5c4c-118">[Tutorial: Introdução com o Mecanismo de Banco de Dados](../tutorial-getting-started-with-the-database-engine.md) </span><span class="sxs-lookup"><span data-stu-id="e5c4c-118">[Tutorial: Getting Started with the Database Engine](../tutorial-getting-started-with-the-database-engine.md) </span></span>  
 <span data-ttu-id="e5c4c-119">[Tutorial: escrevendo instruções Transact-SQL](../../t-sql/tutorial-writing-transact-sql-statements.md) </span><span class="sxs-lookup"><span data-stu-id="e5c4c-119">[Tutorial: Writing Transact-SQL Statements](../../t-sql/tutorial-writing-transact-sql-statements.md) </span></span>  
 <span data-ttu-id="e5c4c-120">[Referência do método de tipo de dados hierarchyid](/sql/t-sql/data-types/hierarchyid-data-type-method-reference) </span><span class="sxs-lookup"><span data-stu-id="e5c4c-120">[hierarchyid Data Type Method Reference](/sql/t-sql/data-types/hierarchyid-data-type-method-reference) </span></span>  
 <span data-ttu-id="e5c4c-121">[&#40;de dados hierárquicos SQL Server&#41;](../hierarchical-data-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="e5c4c-121">[Hierarchical Data &#40;SQL Server&#41;](../hierarchical-data-sql-server.md) </span></span>  
 [<span data-ttu-id="e5c4c-122">hierarchyid &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e5c4c-122">hierarchyid &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/hierarchyid-data-type-method-reference)  
  
  
