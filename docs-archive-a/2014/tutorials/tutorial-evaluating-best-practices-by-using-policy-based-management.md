---
title: 'Tutorial: avaliando as práticas recomendadas usando o gerenciamento baseado em políticas | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- best practices analyzer
- Policy-Based Management, best practices policies
- Best Practices [Database Engine]
- Policy-Based Management, evaluating policies
- BPA
- tutorials [Policy-Based Management]
- Policy-Based Management, tutorials
ms.assetid: c7867f9b-7acc-4fae-bde1-63808c403ebc
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 42e6b505c71abecce7b56b5cb2544b4e9f4e8f71
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681285"
---
# <a name="tutorial-evaluating-best-practices-by-using-policy-based-management"></a><span data-ttu-id="ebbe9-102">Tutorial: Como avaliar práticas recomendadas usando o Gerenciamento Baseado em Políticas</span><span class="sxs-lookup"><span data-stu-id="ebbe9-102">Tutorial: Evaluating Best Practices by Using Policy-Based Management</span></span>
  <span data-ttu-id="ebbe9-103">Bem-vindo ao tutorial Avaliando práticas recomendadas usando o Gerenciamento Baseado em Políticas.</span><span class="sxs-lookup"><span data-stu-id="ebbe9-103">Welcome to the Evaluating Best Practices by Using Policy-Based Management tutorial.</span></span> <span data-ttu-id="ebbe9-104">O tutorial é destinado a usuários familiarizados com o [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], mas que não conhecem o Gerenciamento Baseado em Políticas.</span><span class="sxs-lookup"><span data-stu-id="ebbe9-104">This tutorial is intended for users who are familiar with [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], but new to Policy-Based Management.</span></span> <span data-ttu-id="ebbe9-105">O gerenciamento baseado em políticas é um sistema que define as políticas que podem ser usadas para impor padrões de administração de sites.</span><span class="sxs-lookup"><span data-stu-id="ebbe9-105">Policy-Based Management is a system for defining policies that can be used enforce site administration standards.</span></span> <span data-ttu-id="ebbe9-106">O gerenciamento baseado em políticas inclui um conjunto de práticas recomendadas que você pode usar para analisar uma instância do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] e determinar se a instância atende às diretrizes de práticas recomendadas e recomendações.</span><span class="sxs-lookup"><span data-stu-id="ebbe9-106">Policy-Based Management includes a set of best practices policies that you can use to analyze an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] to determine whether the instance meets best practices guidelines and recommendations.</span></span>  
  
## <a name="what-you-will-learn"></a><span data-ttu-id="ebbe9-107">O que você aprenderá</span><span class="sxs-lookup"><span data-stu-id="ebbe9-107">What You Will Learn</span></span>  
 <span data-ttu-id="ebbe9-108">Neste tutorial, você aprenderá a avaliar políticas de práticas recomendadas para o [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)] de acordo com a demanda (ou "ad hoc"), ou de forma agendada.</span><span class="sxs-lookup"><span data-stu-id="ebbe9-108">In this tutorial, you will learn how to evaluate best practices policies for the [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)] on an on-demand (or "ad hoc") basis, or on a scheduled basis.</span></span>  
  
 <span data-ttu-id="ebbe9-109">Este tutorial é dividido em duas lições:</span><span class="sxs-lookup"><span data-stu-id="ebbe9-109">This tutorial is divided into two lessons:</span></span>  
  
 [<span data-ttu-id="ebbe9-110">Lição 1: Avaliar práticas recomendadas sob demanda</span><span class="sxs-lookup"><span data-stu-id="ebbe9-110">Lesson 1: Evaluate Best Practices on an On-Demand Basis</span></span>](../../2014/tutorials/lesson-1-evaluate-best-practices-on-an-on-demand-basis.md)  
 <span data-ttu-id="ebbe9-111">Nesta lição, você realizará uma avaliação sob demanda das políticas de práticas recomendadas em relação a uma ou mais instâncias do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ebbe9-111">In this lesson, you perform an on-demand evaluation of the policies against one or more instances of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="ebbe9-112">Lição 2: Avaliar políticas de melhores práticas de forma agendada</span><span class="sxs-lookup"><span data-stu-id="ebbe9-112">Lesson 2: Evaluate Best Practices Policies on a Scheduled Basis</span></span>](../../2014/tutorials/lesson-2-evaluate-best-practices-policies-on-a-scheduled-basis.md)  
 <span data-ttu-id="ebbe9-113">Nesta lição, você configura políticas de práticas recomendadas para serem executadas de forma agendada.</span><span class="sxs-lookup"><span data-stu-id="ebbe9-113">In this lesson, you configure best practices policies to run on a scheduled basis.</span></span> <span data-ttu-id="ebbe9-114">A lição mostra como configurar políticas agendadas em uma única instância, e como implantar políticas agendadas de um local central para várias instâncias do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ebbe9-114">The lesson shows how to configure scheduled policies on a single instance, and how to deploy scheduled policies from a central location to multiple instances of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ebbe9-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ebbe9-115">Requirements</span></span>  
 <span data-ttu-id="ebbe9-116">Esta lição requer conhecimento básico em banco de dados e uma compreensão básica do [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ebbe9-116">This lesson requires basic database knowledge and a basic understanding of [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="ebbe9-117">Para usar este tutorial, o servidor deve ter o [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] instalado.</span><span class="sxs-lookup"><span data-stu-id="ebbe9-117">To use this tutorial, the server must have [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] installed.</span></span>  
  
## <a name="start-the-tutorial"></a><span data-ttu-id="ebbe9-118">Inicie o tutorial</span><span class="sxs-lookup"><span data-stu-id="ebbe9-118">Start the Tutorial</span></span>  
 [<span data-ttu-id="ebbe9-119">Lição 1: Avaliar práticas recomendadas sob demanda</span><span class="sxs-lookup"><span data-stu-id="ebbe9-119">Lesson 1: Evaluate Best Practices on an On-Demand Basis</span></span>](../../2014/tutorials/lesson-1-evaluate-best-practices-on-an-on-demand-basis.md)  
  
## <a name="see-also"></a><span data-ttu-id="ebbe9-120">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ebbe9-120">See Also</span></span>  
 [<span data-ttu-id="ebbe9-121">Administrar servidores com Gerenciamento Baseado em Políticas</span><span class="sxs-lookup"><span data-stu-id="ebbe9-121">Administer Servers by Using Policy-Based Management</span></span>](../relational-databases/policy-based-management/administer-servers-by-using-policy-based-management.md)  
  
  
