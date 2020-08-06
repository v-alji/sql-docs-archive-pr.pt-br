---
title: Assemblies (Mecanismo de Banco de Dados) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- assemblies [CLR integration]
- assemblies [CLR integration], about assemblies
- managed code [SQL Server], assemblies
ms.assetid: 4b146437-3061-47f6-9e8c-26eeea10b54e
author: rothja
ms.author: jroth
ms.openlocfilehash: 7edb18ccfa9954fe52093f87948f956c2eacc1b1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87682297"
---
# <a name="assemblies-database-engine"></a><span data-ttu-id="7dd29-102">Assemblies (Mecanismo de Banco de Dados)</span><span class="sxs-lookup"><span data-stu-id="7dd29-102">Assemblies (Database Engine)</span></span>
  <span data-ttu-id="7dd29-103">Os tópicos desta seção fornecem informações para ajudá-lo a entender, projetar e implementar assemblies.</span><span class="sxs-lookup"><span data-stu-id="7dd29-103">The topics in this section provide information to help you understand, design, and implement assemblies.</span></span>  
  
 <span data-ttu-id="7dd29-104">Os assemblies são arquivos DLL usados em uma instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] para implantar funções, procedimentos armazenados, gatilhos, agregações definidas pelo usuário e tipos definidos pelo usuário que são escritos em uma das linguagens de código gerenciado hospedadas pelo [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] Common Language Runtime (CLR), em vez de em [!INCLUDE[tsql](../../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7dd29-104">Assemblies are DLL files used in an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to deploy functions, stored procedures, triggers, user-defined aggregates, and user-defined types that are written in one of the managed code languages hosted by the [!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] common language runtime (CLR), instead of in [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="7dd29-105">Um assembly no [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] é um objeto que faz referência a um módulo de aplicativo gerenciado (arquivo .dll) criado em CLR do [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7dd29-105">An assembly in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] is an object that references a managed application module (.dll file) that was created in the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] common language runtime.</span></span> <span data-ttu-id="7dd29-106">Um assembly contém metadados de classe e código gerenciado.</span><span class="sxs-lookup"><span data-stu-id="7dd29-106">An assembly contains class metadata and managed code.</span></span> <span data-ttu-id="7dd29-107">Carregar um assembly para uma instância do SQL Server é a primeira etapa da criação de qualquer um dos objetos de banco de dados a seguir:</span><span class="sxs-lookup"><span data-stu-id="7dd29-107">Uploading an assembly to an instance of SQL Server is the first step toward creating any of the following database objects:</span></span>  
  
-   <span data-ttu-id="7dd29-108">Funções CLR.</span><span class="sxs-lookup"><span data-stu-id="7dd29-108">CLR functions.</span></span> <span data-ttu-id="7dd29-109">Para obter mais informações, consulte [Create CLR Functions](../user-defined-functions/create-clr-functions.md).</span><span class="sxs-lookup"><span data-stu-id="7dd29-109">For more information, see [Create CLR Functions](../user-defined-functions/create-clr-functions.md).</span></span>  
  
-   <span data-ttu-id="7dd29-110">Procedimentos armazenados CLR</span><span class="sxs-lookup"><span data-stu-id="7dd29-110">CLR stored procedures.</span></span> <span data-ttu-id="7dd29-111">Para obter mais informações, consulte [procedimentos armazenados CLR](../../database-engine/dev-guide/clr-stored-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="7dd29-111">For more information, see [CLR Stored Procedures](../../database-engine/dev-guide/clr-stored-procedures.md).</span></span>  
  
-   <span data-ttu-id="7dd29-112">Gatilhos CLR.</span><span class="sxs-lookup"><span data-stu-id="7dd29-112">CLR triggers.</span></span> <span data-ttu-id="7dd29-113">Para obter mais informações, consulte [criar gatilhos CLR](../triggers/create-clr-triggers.md).</span><span class="sxs-lookup"><span data-stu-id="7dd29-113">For more information, see [Create CLR Triggers](../triggers/create-clr-triggers.md).</span></span>  
  
-   <span data-ttu-id="7dd29-114">Funções de agregação definidas pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="7dd29-114">User-defined aggregate functions.</span></span> <span data-ttu-id="7dd29-115">Para obter mais informações, consulte [criar agregações definidas pelo usuário](../user-defined-functions/create-user-defined-aggregates.md).</span><span class="sxs-lookup"><span data-stu-id="7dd29-115">For more information, see [Create User-defined Aggregates](../user-defined-functions/create-user-defined-aggregates.md).</span></span>  
  
-   <span data-ttu-id="7dd29-116">Tipos definidos pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="7dd29-116">User-defined types.</span></span> <span data-ttu-id="7dd29-117">Para obter mais informações, confira [Usando tipos definidos pelo usuário](../native-client/features/using-user-defined-types.md).</span><span class="sxs-lookup"><span data-stu-id="7dd29-117">For more information, see [Using User-Defined Types](../native-client/features/using-user-defined-types.md).</span></span>  
  
 <span data-ttu-id="7dd29-118">Os assemblies executam as funções a seguir no [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="7dd29-118">Assemblies perform the following functions in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="7dd29-119">Contêm o código gerenciado que executa a funcionalidade de um ou mais dos objetos de banco de dados CLR listados anteriormente.</span><span class="sxs-lookup"><span data-stu-id="7dd29-119">Contain the managed code that runs the functionality of one or more of the CLR database objects previously listed.</span></span>  
  
-   <span data-ttu-id="7dd29-120">Contêm metadados que incluem o número de versão e cultura do assembly, uma chave pública opcional que identifica exclusivamente a lista de classes do assembly, os métodos definidos no assembly e a arquitetura do processador do assembly.</span><span class="sxs-lookup"><span data-stu-id="7dd29-120">Contain metadata that includes the version number and culture of the assembly, an optional public key that uniquely identifies the list of classes of the assembly, the methods that are defined in the assembly, and the processor architecture of the assembly.</span></span>  
  
-   <span data-ttu-id="7dd29-121">Gerenciam nível de acesso do código gerenciado a recursos externos, regulando permissões de acesso a código.</span><span class="sxs-lookup"><span data-stu-id="7dd29-121">Manage the degree to which managed code can access outside resources by regulating code access permissions.</span></span>  
  
-   <span data-ttu-id="7dd29-122">Contêm metadados sobre dependências em outros assemblies referenciados pelo assembly.</span><span class="sxs-lookup"><span data-stu-id="7dd29-122">Contain metadata about dependencies on other assemblies that are referenced by the assembly.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7dd29-123">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="7dd29-123">In This Section</span></span>  
  
|<span data-ttu-id="7dd29-124">Tópico</span><span class="sxs-lookup"><span data-stu-id="7dd29-124">Topic</span></span>|<span data-ttu-id="7dd29-125">Descrição</span><span class="sxs-lookup"><span data-stu-id="7dd29-125">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="7dd29-126">Criação de Assemblies</span><span class="sxs-lookup"><span data-stu-id="7dd29-126">Designing Assemblies</span></span>](assemblies-designing.md)|<span data-ttu-id="7dd29-127">Explica o que levar em consideração antes de criar um assembly.</span><span class="sxs-lookup"><span data-stu-id="7dd29-127">Explains what you have to consider before creating an assembly.</span></span> <span data-ttu-id="7dd29-128">Inclui assemblies de empacotamento, permissões de acesso a código e outras restrições.</span><span class="sxs-lookup"><span data-stu-id="7dd29-128">This includes packaging assemblies, code access permissions, and other restrictions.</span></span>|  
|[<span data-ttu-id="7dd29-129">Implementando assemblies</span><span class="sxs-lookup"><span data-stu-id="7dd29-129">Implementing Assemblies</span></span>](assemblies-implementing.md)|<span data-ttu-id="7dd29-130">Explica como criar e eliminar assemblies, como e quando modificar assemblies e como recuperar metadados sobre assemblies.</span><span class="sxs-lookup"><span data-stu-id="7dd29-130">Explains how to create and drop assemblies, how and when to modify assemblies, and how to retrieve metadata about assemblies.</span></span>|  
|[<span data-ttu-id="7dd29-131">Obtendo informações sobre assemblies</span><span class="sxs-lookup"><span data-stu-id="7dd29-131">Getting Information About Assemblies</span></span>](assemblies-getting-information.md)|<span data-ttu-id="7dd29-132">Lista as exibições do catálogo e funções que podem ser consultadas para metadados sobre assemblies.</span><span class="sxs-lookup"><span data-stu-id="7dd29-132">Lists the catalog views and functions that can be queried for metadata about assemblies.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7dd29-133">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7dd29-133">See Also</span></span>  
 [<span data-ttu-id="7dd29-134">Conceitos de programação da Integração CLR &#40;Common Language Runtime&#41;</span><span class="sxs-lookup"><span data-stu-id="7dd29-134">Common Language Runtime &#40;CLR&#41; Integration Programming Concepts</span></span>](common-language-runtime-clr-integration-programming-concepts.md)  
  
  
