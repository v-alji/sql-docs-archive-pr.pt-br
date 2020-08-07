---
title: Criando objetos de banco de dados com integração CLR (Common Language Runtime) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- routines [CLR integration]
- database objects [CLR integration], building
- common language runtime [SQL Server], building database objects
- managed code [SQL Server], database objects
- building database objects [CLR integration]
- .NET Framework routines [SQL Server]
ms.assetid: ce34132c-bfa3-447b-9131-b6e17c672efe
author: rothja
ms.author: jroth
ms.openlocfilehash: 3c849c095a3be1c590e6fcb3ce87a0725eb795c4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575164"
---
# <a name="building-database-objects-with-common-language-runtime-clr-integration"></a><span data-ttu-id="0e19e-102">Criando objetos de banco de dados com integração CLR (Common Language Runtime)</span><span class="sxs-lookup"><span data-stu-id="0e19e-102">Building Database Objects with Common Language Runtime (CLR) Integration</span></span>
  <span data-ttu-id="0e19e-103">Você pode criar objetos de banco de dados usando o [!INCLUDE[ssNoVersion](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] é chamado de "rotina CLR".</span><span class="sxs-lookup"><span data-stu-id="0e19e-103">You can build database objects using the [!INCLUDE[ssNoVersion](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] is referred to as a "CLR routine."</span></span> <span data-ttu-id="0e19e-104">Essas rotinas incluem:</span><span class="sxs-lookup"><span data-stu-id="0e19e-104">These routines include:</span></span>  
  
-   <span data-ttu-id="0e19e-105">Funções definidas pelo usuário com valor escalar (UDFs escalares)</span><span class="sxs-lookup"><span data-stu-id="0e19e-105">Scalar-valued user-defined functions (scalar UDFs)</span></span>  
  
-   <span data-ttu-id="0e19e-106">Funções definidas pelo usuário com valor de tabela (TVFs)</span><span class="sxs-lookup"><span data-stu-id="0e19e-106">Table-valued user-defined functions (TVFs)</span></span>  
  
-   <span data-ttu-id="0e19e-107">Procedimentos definidos pelo usuário (UDPs)</span><span class="sxs-lookup"><span data-stu-id="0e19e-107">User-defined procedures (UDPs)</span></span>  
  
-   <span data-ttu-id="0e19e-108">Gatilhos definidos pelo usuário</span><span class="sxs-lookup"><span data-stu-id="0e19e-108">User-defined triggers</span></span>  
  
 <span data-ttu-id="0e19e-109">As rotinas CLR têm a mesma estrutura no código gerenciado.</span><span class="sxs-lookup"><span data-stu-id="0e19e-109">CLR routines have the same structure in managed code.</span></span> <span data-ttu-id="0e19e-110">Elas são mapeadas para métodos públicos e estáticos (compartilhados no [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic .NET) de uma classe.</span><span class="sxs-lookup"><span data-stu-id="0e19e-110">They are mapped to public, static (shared in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic .NET) methods of a class.</span></span> <span data-ttu-id="0e19e-111">Além das rotinas, também podem ser definidos UDTs (tipos definidos pelo usuário) e funções de agregação definida pelo usuário usando o .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="0e19e-111">In addition to routines, user-defined types (UDTs) and user-defined aggregate functions can also be defined using the .NET Framework.</span></span> <span data-ttu-id="0e19e-112">Os UDTs e as agregações definidas pelo usuário são mapeados para classes inteiras do .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="0e19e-112">UDTs and user-defined aggregates are mapped to entire .NET Framework classes.</span></span>  
  
 <span data-ttu-id="0e19e-113">Cada tipo de rotina de .NET Framework tem um [!INCLUDE[tsql](../../../includes/ssnoversion-md.md)] que o [!INCLUDE[tsql](../../../includes/tsql-md.md)] equivalente pode ser usado.</span><span class="sxs-lookup"><span data-stu-id="0e19e-113">Each type of .NET Framework routine has a [!INCLUDE[tsql](../../../includes/ssnoversion-md.md)] that the [!INCLUDE[tsql](../../../includes/tsql-md.md)] equivalent can be used.</span></span> <span data-ttu-id="0e19e-114">Por exemplo, UDFs escalares podem ser usados em qualquer expressão escalar.</span><span class="sxs-lookup"><span data-stu-id="0e19e-114">For instance, scalar UDFs can be used in any scalar expression.</span></span> <span data-ttu-id="0e19e-115">Uma TVF pode ser usada em qualquer cláusula FROM.</span><span class="sxs-lookup"><span data-stu-id="0e19e-115">A TVF can be used in any FROM clause.</span></span> <span data-ttu-id="0e19e-116">Um procedimento pode ser invocado em uma instrução EXEC ou de um aplicativo cliente.</span><span class="sxs-lookup"><span data-stu-id="0e19e-116">A procedure can be invoked in an EXEC statement or invoked from a client application.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0e19e-117">A execução de um objeto CLR (função definida pelo usuário, tipo definido pelo usuário ou gatilho) no Common Language Runtime poderá acontecer em vários threads (plano paralelo), se o otimizador de consulta achar que isso é benéfico.</span><span class="sxs-lookup"><span data-stu-id="0e19e-117">Execution of a CLR object (user-defined function, user-defined type, or trigger) on the common language runtime can take place on multiple threads (parallel plan), if the query optimizer decides it is beneficial.</span></span> <span data-ttu-id="0e19e-118">No entanto, se uma função definida pelo usuário acessar dados, a execução estará em um plano serial.</span><span class="sxs-lookup"><span data-stu-id="0e19e-118">However, if a user-defined function accesses data, execution will be  on a serial plan.</span></span> <span data-ttu-id="0e19e-119">Quando executado em uma versão de servidor antes do [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)], se uma função definida pelo usuário contiver parâmetros LOB ou valores de retorno, execução também deverá estar em um plano serial.</span><span class="sxs-lookup"><span data-stu-id="0e19e-119">When executed on a server version prior to [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)], if a user-defined function contains LOB parameters or return values, execution also must be on a serial plan.</span></span>  
  
 <span data-ttu-id="0e19e-120">A tabela a seguir lista os tópicos abordados nesta seção.</span><span class="sxs-lookup"><span data-stu-id="0e19e-120">The following table lists the topics covered in this section.</span></span>  
  
 [<span data-ttu-id="0e19e-121">Introdução à integração CLR</span><span class="sxs-lookup"><span data-stu-id="0e19e-121">Getting Started with CLR Integration</span></span>](getting-started-with-clr-integration.md)  
 <span data-ttu-id="0e19e-122">Fornece uma visão geral breve das bibliotecas e namespaces necessários para compilar um objeto usando a integração CLR com o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0e19e-122">Provides a brief overview of the libraries and namespaces required to compile object using CLR integration with [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="0e19e-123">Inclui o exemplo de procedimento armazenado CLR "Hello World".</span><span class="sxs-lookup"><span data-stu-id="0e19e-123">Includes an example "Hello World" CLR stored procedure.</span></span>  
  
 [<span data-ttu-id="0e19e-124">Bibliotecas do .NET Framework compatíveis</span><span class="sxs-lookup"><span data-stu-id="0e19e-124">Supported .NET Framework Libraries</span></span>](supported-net-framework-libraries.md)  
 <span data-ttu-id="0e19e-125">Fornece informações sobre as bibliotecas do .NET Framework suportadas pela integração CLR.</span><span class="sxs-lookup"><span data-stu-id="0e19e-125">Provides information on the .NET Framework libraries supported by CLR integration.</span></span>  
  
 [<span data-ttu-id="0e19e-126">Restrições do modelo de programação da Integração CLR</span><span class="sxs-lookup"><span data-stu-id="0e19e-126">CLR Integration Programming Model Restrictions</span></span>](clr-integration-programming-model-restrictions.md)  
 <span data-ttu-id="0e19e-127">Fornece informações sobre restrições de modelo de programação de integração CLR.</span><span class="sxs-lookup"><span data-stu-id="0e19e-127">Provides information about CLR integration programming model restrictions.</span></span>  
  
 [<span data-ttu-id="0e19e-128">Tipos de dados do SQL Server no .NET Framework</span><span class="sxs-lookup"><span data-stu-id="0e19e-128">SQL Server Data Types in the .NET Framework</span></span>](../../clr-integration-database-objects-types-net-framework/sql-server-data-types-in-the-net-framework.md)  
 <span data-ttu-id="0e19e-129">Uma visão geral dos tipos de dados do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] e seus equivalentes do .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="0e19e-129">An overview of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] data types and their .NET Framework equivalents.</span></span>  
  
 [<span data-ttu-id="0e19e-130">Visão geral dos atributos personalizados da integração CLR</span><span class="sxs-lookup"><span data-stu-id="0e19e-130">Overview of CLR Integration Custom Attributes</span></span>](../../../database-engine/dev-guide/overview-of-clr-integration-custom-attributes.md)  
 <span data-ttu-id="0e19e-131">Fornece informações sobre atributos personalizados de integração CLR.</span><span class="sxs-lookup"><span data-stu-id="0e19e-131">Provides information about CLR integration custom attributes.</span></span>  
  
 [<span data-ttu-id="0e19e-132">Funções do CLR definidas pelo usuário</span><span class="sxs-lookup"><span data-stu-id="0e19e-132">CLR User-Defined Functions</span></span>](../../clr-integration-database-objects-user-defined-functions/clr-user-defined-functions.md)  
 <span data-ttu-id="0e19e-133">Descreve como implementar e usar os vários tipos de funções CLR: com valor de tabela, escalares e funções de agregação definida pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="0e19e-133">Describes how to implement and use the various types of CLR functions: table-valued, scalar, and user-defined aggregate functions.</span></span>  
  
 [<span data-ttu-id="0e19e-134">Tipos definido pelo usuário CLR</span><span class="sxs-lookup"><span data-stu-id="0e19e-134">CLR User-Defined Types</span></span>](../../clr-integration-database-objects-user-defined-types/clr-user-defined-types.md)  
 <span data-ttu-id="0e19e-135">Descreve como implementar e usar tipos definidos pelo usuário CLR.</span><span class="sxs-lookup"><span data-stu-id="0e19e-135">Describes how to implement and use CLR user-defined types.</span></span>  
  
 [<span data-ttu-id="0e19e-136">Procedimentos armazenados CLR</span><span class="sxs-lookup"><span data-stu-id="0e19e-136">CLR Stored Procedures</span></span>](../../../database-engine/dev-guide/clr-stored-procedures.md)  
 <span data-ttu-id="0e19e-137">Descreve como implementar e usar procedimentos armazenados CLR.</span><span class="sxs-lookup"><span data-stu-id="0e19e-137">Describes how to implement and use CLR stored procedures.</span></span>  
  
 [<span data-ttu-id="0e19e-138">Gatilhos de CLR</span><span class="sxs-lookup"><span data-stu-id="0e19e-138">CLR Triggers</span></span>](../../../database-engine/dev-guide/clr-triggers.md)  
 <span data-ttu-id="0e19e-139">Descreve como implementar e usar gatilhos CLR.</span><span class="sxs-lookup"><span data-stu-id="0e19e-139">Describes how to implement and use CLR triggers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e19e-140">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0e19e-140">See Also</span></span>  
 [<span data-ttu-id="0e19e-141">Visão geral da integração do CLR&#41; &#40;Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="0e19e-141">Common Language Runtime &#40;CLR&#41; Integration Overview</span></span>](../common-language-runtime-integration-overview.md)  
  
  
