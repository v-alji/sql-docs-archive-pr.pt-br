---
title: Execução direta | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- ODBC applications, statements
- direct execution [ODBC]
- SQLExecDirect function
- statements [ODBC], direct execution
ms.assetid: fa36e1af-ed98-4abc-97c1-c4cc5d227b29
author: rothja
ms.author: jroth
ms.openlocfilehash: 29153f3e4e9265e87feb0e23ba9ae97118691e95
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569415"
---
# <a name="direct-execution"></a><span data-ttu-id="a4a44-102">Execução direta</span><span class="sxs-lookup"><span data-stu-id="a4a44-102">Direct Execution</span></span>
  <span data-ttu-id="a4a44-103">A execução direta é o modo mais básico de executar uma instrução.</span><span class="sxs-lookup"><span data-stu-id="a4a44-103">Direct execution is the most basic way to execute a statement.</span></span> <span data-ttu-id="a4a44-104">Um aplicativo cria uma cadeia de caracteres que contém uma [!INCLUDE[tsql](../../../includes/tsql-md.md)] instrução e a envia para execução usando a função **SQLExecDirect** .</span><span class="sxs-lookup"><span data-stu-id="a4a44-104">An application builds a character string containing a [!INCLUDE[tsql](../../../includes/tsql-md.md)] statement and submits it for execution using the **SQLExecDirect** function.</span></span> <span data-ttu-id="a4a44-105">Quando a instrução alcança o servidor, o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] a compila em um plano de execução e executa esse plano imediatamente.</span><span class="sxs-lookup"><span data-stu-id="a4a44-105">When the statement reaches the server, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] compiles it into an execution plan and then immediately runs the execution plan.</span></span>  
  
 <span data-ttu-id="a4a44-106">A execução direta normalmente é usada por aplicativos que compilam e executam instruções no tempo de execução e é o método mais eficiente para instruções que serão executadas de uma só vez.</span><span class="sxs-lookup"><span data-stu-id="a4a44-106">Direct execution is commonly used by applications that build and execute statements at run time and is the most efficient method for statements that will be executed a single time.</span></span> <span data-ttu-id="a4a44-107">O problema com muitos bancos de dados é que a instrução SQL deve ser analisada e compilada sempre que é executada, o que adiciona sobrecarga se a instrução for executada várias vezes.</span><span class="sxs-lookup"><span data-stu-id="a4a44-107">Its drawback with many databases is that the SQL statement must be parsed and compiled each time it is executed, which adds overhead if the statement is executed multiple times.</span></span>  
  
 <span data-ttu-id="a4a44-108">O [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] aprimora significativamente o desempenho da execução direta de instruções executadas comumente em ambientes de vários usuários, e o uso de SQLExecDirect com marcadores de parâmetro para instruções SQL usadas normalmente pode abordar a eficiência da execução preparada.</span><span class="sxs-lookup"><span data-stu-id="a4a44-108">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] significantly improves the performance of direct execution of commonly executed statements in multiuser environments and using SQLExecDirect with parameter markers for commonly executed SQL statements can approach the efficiency of prepared execution.</span></span>  
  
 <span data-ttu-id="a4a44-109">Quando conectado a uma instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] driver ODBC do Native Client usa [sp_executesql](/sql/relational-databases/system-stored-procedures/sp-executesql-transact-sql) para transmitir a instrução SQL ou o lote especificado em **SQLExecDirect**.</span><span class="sxs-lookup"><span data-stu-id="a4a44-109">When connected to an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver uses [sp_executesql](/sql/relational-databases/system-stored-procedures/sp-executesql-transact-sql) to transmit the SQL statement or batch specified on **SQLExecDirect**.</span></span> [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]<span data-ttu-id="a4a44-110">tem a lógica para determinar rapidamente se uma instrução SQL ou um lote executado com **sp_executesql** corresponde à instrução ou ao lote que gerou um plano de execução que já existe na memória.</span><span class="sxs-lookup"><span data-stu-id="a4a44-110">has logic to quickly determine if an SQL statement or batch executed with **sp_executesql** matches the statement or batch that generated an execution plan that already exists in memory.</span></span> <span data-ttu-id="a4a44-111">Se houver correspondência, o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] simplesmente reutilizará o plano existente, em vez de compilar um novo plano.</span><span class="sxs-lookup"><span data-stu-id="a4a44-111">If a match is made, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] simply reuses the existing plan rather than compile a new plan.</span></span> <span data-ttu-id="a4a44-112">Isso significa que as instruções SQL comumente executadas executadas com **SQLExecDirect** em um sistema com muitos usuários se beneficiarão de muitos benefícios de reutilização de plano que só estavam disponíveis para procedimentos armazenados em versões anteriores do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a4a44-112">This means that commonly executed SQL statements executed with **SQLExecDirect** in a system with many users will benefit from many of the plan-reuse benefits that were only available to stored procedures in earlier versions of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="a4a44-113">Esse benefício de reutilizar planos de execução só funciona quando vários usuários estiverem executando a mesma instrução ou lote SQL.</span><span class="sxs-lookup"><span data-stu-id="a4a44-113">This benefit of reusing execution plans only works when several users are executing the same SQL statement or batch.</span></span> <span data-ttu-id="a4a44-114">Siga estas convenções de codificação para aumentar a probabilidade de as instruções SQL executadas por clientes diferentes serem semelhantes a ponto de permitirem a reutilização de planos de execução:</span><span class="sxs-lookup"><span data-stu-id="a4a44-114">Follow these coding conventions to increase the probability that the SQL statements executed by different clients are similar enough to be able to reuse execution plans:</span></span>  
  
-   <span data-ttu-id="a4a44-115">Não inclua constantes de dados nas instruções SQL; em vez disso, use marcadores de parâmetro associados para programar variáveis.</span><span class="sxs-lookup"><span data-stu-id="a4a44-115">Do not include data constants in the SQL statements; instead use parameter markers bound to program variables.</span></span> <span data-ttu-id="a4a44-116">Para obter mais informações, consulte [usando parâmetros de instrução](../using-statement-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="a4a44-116">For more information, see [Using Statement Parameters](../using-statement-parameters.md).</span></span>  
  
-   <span data-ttu-id="a4a44-117">Use nomes de objeto totalmente qualificados.</span><span class="sxs-lookup"><span data-stu-id="a4a44-117">Use fully qualified object names.</span></span> <span data-ttu-id="a4a44-118">Os planos de execução não serão reutilizados se os nomes de objeto não forem totalmente qualificados.</span><span class="sxs-lookup"><span data-stu-id="a4a44-118">Execution plans are not reused if object names are not qualified.</span></span>  
  
-   <span data-ttu-id="a4a44-119">Faça com que as conexões de aplicativo usem, na medida do possível, um conjunto comum de opções de conexão e instrução.</span><span class="sxs-lookup"><span data-stu-id="a4a44-119">Have application connections as possible use a common set of connection and statement options.</span></span> <span data-ttu-id="a4a44-120">Os planos de execução gerados para uma conexão com um conjunto de opções (como ANSI_NULLS) não são reutilizados para uma conexão que tenha outro conjunto de opções.</span><span class="sxs-lookup"><span data-stu-id="a4a44-120">Execution plans generated for a connection with one set of options (such as ANSI_NULLS) are not reused for a connection having another set of options.</span></span> <span data-ttu-id="a4a44-121">O driver ODBC do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client e o provedor OLE DB do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client têm as mesmas configurações padrão para essas opções.</span><span class="sxs-lookup"><span data-stu-id="a4a44-121">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver and the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider both have the same default settings for these options.</span></span>  
  
 <span data-ttu-id="a4a44-122">Se todas as instruções executadas com **SQLExecDirect** forem codificadas usando essas convenções, o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] poderá reutilizar planos de execução quando a oportunidade surgir.</span><span class="sxs-lookup"><span data-stu-id="a4a44-122">If all statements executed with **SQLExecDirect** are coded using these conventions, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] can reuse execution plans when the opportunity arises.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4a44-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a4a44-123">See Also</span></span>  
 [<span data-ttu-id="a4a44-124">Executando instruções &#40;&#41;ODBC</span><span class="sxs-lookup"><span data-stu-id="a4a44-124">Executing Statements &#40;ODBC&#41;</span></span>](executing-statements-odbc.md)  
  
  