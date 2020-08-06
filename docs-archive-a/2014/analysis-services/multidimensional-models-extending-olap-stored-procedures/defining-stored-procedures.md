---
title: Definindo procedimentos armazenados | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- stored procedures [Analysis Services]
- OLAP [Analysis Services], stored procedures
- external routines [Analysis Services]
- stored procedures [Analysis Services], about stored procedures
ms.assetid: f9c57d91-f60f-4f0e-8f7f-d87f4ba97b7c
author: minewiskan
ms.author: owend
ms.openlocfilehash: cc1f028f822d2289ee79702feb2494487040977c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680695"
---
# <a name="defining-stored-procedures"></a><span data-ttu-id="da2eb-102">Definindo procedimentos armazenados</span><span class="sxs-lookup"><span data-stu-id="da2eb-102">Defining Stored Procedures</span></span>
  <span data-ttu-id="da2eb-103">Você pode usar procedimentos armazenados para chamar rotinas externas do [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="da2eb-103">You can use stored procedures to call external routines from [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="da2eb-104">É possível gravar rotinas externas chamadas por um procedimento armazenado em uma linguagem CLR (Common Language Runtime), como C, C++, C#, Visual Basic ou Visual Basic .NET.</span><span class="sxs-lookup"><span data-stu-id="da2eb-104">You can write an external routines called by a stored procedure in any common language runtime (CLR) language, such as C, C++, C#, Visual Basic, or Visual Basic .NET.</span></span> <span data-ttu-id="da2eb-105">Um procedimento armazenado pode ser criado e então chamado a partir de diversos contextos, como outros procedimentos armazenados, medidas calculadas ou aplicativos cliente.</span><span class="sxs-lookup"><span data-stu-id="da2eb-105">A stored procedure can be created once and called from many contexts, such as other stored procedures, calculated measures, or client applications.</span></span> <span data-ttu-id="da2eb-106">Os procedimentos armazenados simplificam o desenvolvimento e a implementação de bancos de dados do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] ao possibilitar que um código comum seja desenvolvido e então armazenado em um único local.</span><span class="sxs-lookup"><span data-stu-id="da2eb-106">Stored procedures simplify [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database development and implementation by allowing common code to be developed once and stored in a single location.</span></span> <span data-ttu-id="da2eb-107">Eles podem ser usados para adicionar a seus aplicativos funcionalidades comerciais que não existem como funcionalidade nativa do MDX.</span><span class="sxs-lookup"><span data-stu-id="da2eb-107">Stored procedures can be used to add business functionality to your applications that is not provided by the native functionality of MDX.</span></span>  
  
 <span data-ttu-id="da2eb-108">Esta seção fornece as informações necessárias para você entender, projetar e implementar procedimentos armazenados.</span><span class="sxs-lookup"><span data-stu-id="da2eb-108">This section provides the information necessary to understand, design, and implement stored procedures.</span></span>  
  
|<span data-ttu-id="da2eb-109">Tópico</span><span class="sxs-lookup"><span data-stu-id="da2eb-109">Topic</span></span>|<span data-ttu-id="da2eb-110">Descrição</span><span class="sxs-lookup"><span data-stu-id="da2eb-110">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="da2eb-111">Projetando procedimentos armazenados</span><span class="sxs-lookup"><span data-stu-id="da2eb-111">Designing Stored Procedures</span></span>](../multidimensional-models-extending-olap-stored-procedures/designing-stored-procedures.md)|<span data-ttu-id="da2eb-112">Descreve como projetar assemblies para uso com o [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="da2eb-112">Describes how to design assemblies for use with [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span>|  
|[<span data-ttu-id="da2eb-113">Criando procedimentos armazenados</span><span class="sxs-lookup"><span data-stu-id="da2eb-113">Creating Stored Procedures</span></span>](creating-stored-procedures.md)|<span data-ttu-id="da2eb-114">Descreve como criar assemblies para o [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="da2eb-114">Describes how to create assemblies for [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span>|  
|[<span data-ttu-id="da2eb-115">Chamando procedimentos armazenados</span><span class="sxs-lookup"><span data-stu-id="da2eb-115">Calling Stored Procedures</span></span>](calling-stored-procedures.md)|<span data-ttu-id="da2eb-116">Fornece informações sobre como usar assemblies no [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="da2eb-116">Provides information on how to use assemblies in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span>|  
|[<span data-ttu-id="da2eb-117">Acessando o contexto de consulta nos procedimentos armazenados</span><span class="sxs-lookup"><span data-stu-id="da2eb-117">Accessing Query Context in Stored Procedures</span></span>](accessing-query-context-in-stored-procedures.md)|<span data-ttu-id="da2eb-118">Descreve como acessar informações de escopo e contexto com assemblies.</span><span class="sxs-lookup"><span data-stu-id="da2eb-118">Describes how to access scope and context information with assemblies.</span></span>|  
|[<span data-ttu-id="da2eb-119">Definindo a segurança para procedimentos armazenados</span><span class="sxs-lookup"><span data-stu-id="da2eb-119">Setting Security for Stored Procedures</span></span>](setting-security-for-stored-procedures.md)|<span data-ttu-id="da2eb-120">Descreve como configurar a segurança de assemblies no [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="da2eb-120">Describes how to configure security for assemblies in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span>|  
|[<span data-ttu-id="da2eb-121">Depurando procedimentos armazenados</span><span class="sxs-lookup"><span data-stu-id="da2eb-121">Debugging Stored Procedures</span></span>](debugging-stored-procedures.md)|<span data-ttu-id="da2eb-122">Descreve como depurar assemblies no [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="da2eb-122">Describes how to debug assemblies in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="da2eb-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="da2eb-123">See Also</span></span>  
 [<span data-ttu-id="da2eb-124">Gerenciamento de assemblies de modelo multidimensional</span><span class="sxs-lookup"><span data-stu-id="da2eb-124">Multidimensional Model Assemblies Management</span></span>](../multidimensional-models/multidimensional-model-assemblies-management.md)  
  
  
