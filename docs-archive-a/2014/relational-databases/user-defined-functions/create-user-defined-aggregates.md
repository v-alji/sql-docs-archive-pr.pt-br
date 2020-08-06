---
title: Criar agregações definidas pelo usuário | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- aggregate functions [SQL Server], user-defined
- user-defined functions [CLR integration]
ms.assetid: c278b746-6323-4b32-b460-239915acc067
author: rothja
ms.author: jroth
ms.openlocfilehash: c91179cb194bbfb79e8e7a8476e9725877b88afa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685037"
---
# <a name="create-user-defined-aggregates"></a><span data-ttu-id="95b8b-102">Criar agregações definidas pelo usuário</span><span class="sxs-lookup"><span data-stu-id="95b8b-102">Create User-defined Aggregates</span></span>
  <span data-ttu-id="95b8b-103">Você pode criar um objeto de banco de dados dentro do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que é programado em um assembly CLR.</span><span class="sxs-lookup"><span data-stu-id="95b8b-103">You can create a database object inside [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that is programmed in a CLR assembly.</span></span> <span data-ttu-id="95b8b-104">Os objetos do banco de dados que podem alavancar o modelo de programação avançado fornecido pelo CLR incluem gatilhos, procedimentos armazenados, funções, funções de agregação e tipos.</span><span class="sxs-lookup"><span data-stu-id="95b8b-104">Database objects that can leverage the rich programming model provided by the CLR include triggers, stored procedures, functions, aggregate functions, and types.</span></span>  
  
 <span data-ttu-id="95b8b-105">Assim como as funções de agregação internas fornecidas em [!INCLUDE[tsql](../../includes/tsql-md.md)], as funções de agregação definidas pelo usuário executam o cálculo de um conjunto de valores e retornam um único valor.</span><span class="sxs-lookup"><span data-stu-id="95b8b-105">Like the built-in aggregate functions provided in [!INCLUDE[tsql](../../includes/tsql-md.md)], user-defined aggregate functions perform a calculation on a set of values and return a single value.</span></span>  
  
 <span data-ttu-id="95b8b-106">Criar uma função de agregação definida pelo usuário em [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] envolve as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="95b8b-106">Creating a user-defined aggregate function in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] involves the following steps:</span></span>  
  
-   <span data-ttu-id="95b8b-107">Definir a função de agregação definida pelo usuário como uma classe em uma linguagem [!INCLUDE[msCoName](../../includes/msconame-md.md)] suportada por .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="95b8b-107">Define the user-defined aggregate function as a class in a [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework-supported language.</span></span> <span data-ttu-id="95b8b-108">Para obter mais informações sobre como programar agregações definidas pelo usuário em CLR, veja [Agregações CLR definidas pelo usuário](../clr-integration-database-objects-user-defined-functions/clr-user-defined-aggregates.md).</span><span class="sxs-lookup"><span data-stu-id="95b8b-108">For more information about how to program user-defined aggregates in the CLR, see [CLR User-Defined Aggregates](../clr-integration-database-objects-user-defined-functions/clr-user-defined-aggregates.md).</span></span> <span data-ttu-id="95b8b-109">Compile essa classe para criar um assembly CLR que usa o compilador de linguagem apropriado.</span><span class="sxs-lookup"><span data-stu-id="95b8b-109">Compile this class to build a CLR assembly using the appropriate language compiler.</span></span>  
  
-   <span data-ttu-id="95b8b-110">Registrar o assembly no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usando a instrução CREATE ASSEMBLY.</span><span class="sxs-lookup"><span data-stu-id="95b8b-110">Register the assembly in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] using the CREATE ASSEMBLY statement.</span></span> <span data-ttu-id="95b8b-111">Para obter mais informações sobre assemblies no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], veja [Assemblies &#40;Mecanismo de Banco de Dados&#41;](../clr-integration/assemblies-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="95b8b-111">For more information about assemblies in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [Assemblies &#40;Database Engine&#41;](../clr-integration/assemblies-database-engine.md).</span></span>  
  
-   <span data-ttu-id="95b8b-112">Criar a agregação definida pelo usuário que referencia o assembly registrado que usa a instrução CREATE AGGREGATE.</span><span class="sxs-lookup"><span data-stu-id="95b8b-112">Create the user-defined aggregate that references the registered assembly using the CREATE AGGREGATE statement.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="95b8b-113">A implantação de um projeto SQL Server no [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] registra um assembly no banco de dados especificado para o projeto.</span><span class="sxs-lookup"><span data-stu-id="95b8b-113">Deploying a SQL Server Project in [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] registers an assembly in the database that was specified for the project.</span></span> <span data-ttu-id="95b8b-114">Implantar um projeto também cria uma agregação definida pelo usuário no banco de dados para todas as definições de classe anotadas pelo atributo `SqlUserDefinedAggregate`.</span><span class="sxs-lookup"><span data-stu-id="95b8b-114">Deploying the project also creates a user-defined aggregate in the database for all class definitions annotated with the `SqlUserDefinedAggregate` attribute.</span></span> <span data-ttu-id="95b8b-115">Para obter mais informações, consulte [Deploying CLR Database Objects](../clr-integration/deploying-clr-database-objects.md).</span><span class="sxs-lookup"><span data-stu-id="95b8b-115">For more information, see [Deploying CLR Database Objects](../clr-integration/deploying-clr-database-objects.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="95b8b-116">A capacidade do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de executar o código CLR, por padrão, está desativada.</span><span class="sxs-lookup"><span data-stu-id="95b8b-116">The ability of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to execute CLR code is off by default.</span></span> <span data-ttu-id="95b8b-117">É possível criar, alterar e remover objetos do banco de dados que fazem referência aos módulos de código gerenciados, mas essas referências não serão executadas no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , a menos que a [Opção clr enabled](../../database-engine/configure-windows/clr-enabled-server-configuration-option.md) tenha sido habilitada com [sp_configure (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="95b8b-117">You can create, alter and drop database objects that reference managed code modules, but these references will not execute in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] unless the [clr enabled Option](../../database-engine/configure-windows/clr-enabled-server-configuration-option.md) is enabled using [sp_configure (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql).</span></span>  
  
 <span data-ttu-id="95b8b-118">**Para criar, modificar ou descartar um assembly**</span><span class="sxs-lookup"><span data-stu-id="95b8b-118">**To create, modify, or drop an assembly**</span></span>  
  
-   [<span data-ttu-id="95b8b-119">CREATE ASSEMBLY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="95b8b-119">CREATE ASSEMBLY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-assembly-transact-sql)  
  
-   [<span data-ttu-id="95b8b-120">ALTER ASSEMBLY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="95b8b-120">ALTER ASSEMBLY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-assembly-transact-sql)  
  
-   [<span data-ttu-id="95b8b-121">DROP ASSEMBLY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="95b8b-121">DROP ASSEMBLY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/drop-assembly-transact-sql)  
  
 <span data-ttu-id="95b8b-122">**Para criar uma agregação definida pelo usuário**</span><span class="sxs-lookup"><span data-stu-id="95b8b-122">**To create a user-defined aggregate**</span></span>  
  
-   [<span data-ttu-id="95b8b-123">CREATE AGGREGATE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="95b8b-123">CREATE AGGREGATE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-aggregate-transact-sql)  
  
## <a name="see-also"></a><span data-ttu-id="95b8b-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="95b8b-124">See Also</span></span>  
 [<span data-ttu-id="95b8b-125">Conceitos de programação da Integração CLR &#40;Common Language Runtime&#41;</span><span class="sxs-lookup"><span data-stu-id="95b8b-125">Common Language Runtime &#40;CLR&#41; Integration Programming Concepts</span></span>](../clr-integration/common-language-runtime-clr-integration-programming-concepts.md)  
  
  
