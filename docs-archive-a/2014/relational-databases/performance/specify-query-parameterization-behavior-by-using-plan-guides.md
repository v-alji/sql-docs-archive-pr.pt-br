---
title: Especificar o comportamento de parametrização de consulta usando guias de plano | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- TEMPLATE plan guide
- PARAMETERIZATION FORCED option
- PARAMETERIZATION option
- PARAMETERIZATION SIMPLE option
- parameterization [SQL Server]
- overriding parameterization behavior
- plan guides [SQL Server], parameterization
- parameterized queries [SQL Server]
ms.assetid: f0f738ff-2819-4675-a8c8-1eb6c210a7e6
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f595b9f0e0a6d7bceffc5cb283c60b6f40e025b3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583550"
---
# <a name="specify-query-parameterization-behavior-by-using-plan-guides"></a><span data-ttu-id="af7f1-102">Especificar comportamento de parametrização de consulta usando guias de plano</span><span class="sxs-lookup"><span data-stu-id="af7f1-102">Specify Query Parameterization Behavior by Using Plan Guides</span></span>
  <span data-ttu-id="af7f1-103">Quando a opção de banco de dados PARAMETERIZATION está definida como SIMPLE, o otimizador de consulta do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pode optar por parametrizar as consultas.</span><span class="sxs-lookup"><span data-stu-id="af7f1-103">When the PARAMETERIZATION database option is set to SIMPLE, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] query optimizer may choose to parameterize the queries.</span></span> <span data-ttu-id="af7f1-104">Isso significa que qualquer valor literal contido em uma consulta é substituído por parâmetros.</span><span class="sxs-lookup"><span data-stu-id="af7f1-104">This means that any literal values that are contained in a query are substituted with parameters.</span></span> <span data-ttu-id="af7f1-105">Esse processo é denominado parametrização simples.</span><span class="sxs-lookup"><span data-stu-id="af7f1-105">This process is referred to as simple parameterization.</span></span> <span data-ttu-id="af7f1-106">Quando a parametrização SIMPLE está em vigor, você não pode controlar quais consultas são parametrizadas e quais não são.</span><span class="sxs-lookup"><span data-stu-id="af7f1-106">When SIMPLE parameterization is in effect, you cannot control which queries are parameterized and which queries are not.</span></span> <span data-ttu-id="af7f1-107">No entanto, você pode especificar que todas as consultas em um banco de dados sejam parametrizadas definindo a opção de banco de dados PARAMETERIZATION como FORCED.</span><span class="sxs-lookup"><span data-stu-id="af7f1-107">However, you can specify that all queries in a database be parameterized by setting the PARAMETERIZATION database option to FORCED.</span></span> <span data-ttu-id="af7f1-108">Esse processo é denominado parametrização forçada.</span><span class="sxs-lookup"><span data-stu-id="af7f1-108">This process is referred to as forced parameterization.</span></span>  
  
 <span data-ttu-id="af7f1-109">Você pode substituir o comportamento de parametrização de um banco de dados usando guias de plano das seguintes formas:</span><span class="sxs-lookup"><span data-stu-id="af7f1-109">You can override the parameterization behavior of a database by using plan guides in the following ways:</span></span>  
  
-   <span data-ttu-id="af7f1-110">Quando a opção de banco de dados PARAMETERIZATION está definida como SIMPLE, você pode especificar que haja a tentativa de parametrização forçada em uma determinada classe de consultas.</span><span class="sxs-lookup"><span data-stu-id="af7f1-110">When the PARAMETERIZATION database option is set to SIMPLE, you can specify that forced parameterization is attempted on a certain class of queries.</span></span> <span data-ttu-id="af7f1-111">Você faz isso criando uma guia de plano TEMPLATE no formulário parametrizado da consulta e especificando a dica de consulta PARAMETERIZATION FORCED no procedimento armazenado [sp_create_plan_guide](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="af7f1-111">You do this by creating a TEMPLATE plan guide on the parameterized form of the query, and specifying the PARAMETERIZATION FORCED query hint in the [sp_create_plan_guide](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) stored procedure.</span></span> <span data-ttu-id="af7f1-112">Você pode considerar esse tipo de guia de plano como uma forma de habilitar a parametrização forçada só em certa classe de consultas, em vez de em todas as consultas.</span><span class="sxs-lookup"><span data-stu-id="af7f1-112">You can consider this kind of plan guide as a way to enable forced parameterization only on a certain class of queries, instead of all queries.</span></span>  
  
-   <span data-ttu-id="af7f1-113">Quando a opção de banco de dados PARAMETERIZATION está definida como FORCED, você pode especificar que, para uma determinada classe de consultas, haja somente a tentativa de parametrização simples, não a parametrização forçada.</span><span class="sxs-lookup"><span data-stu-id="af7f1-113">When the PARAMETERIZATION database option is set to FORCED, you can specify that for a certain class of queries, only simple parameterization is attempted, not forced parameterization.</span></span> <span data-ttu-id="af7f1-114">Você faz isso criando uma guia de plano TEMPLATE no formulário parametrizado de forçamento da consulta e especificando a dica de consulta PARAMETERIZATION SIMPLE em **sp_create_plan_guide**.</span><span class="sxs-lookup"><span data-stu-id="af7f1-114">You do this by creating a TEMPLATE plan guide on the force-parameterized form of the query, and specifying the PARAMETERIZATION SIMPLE query hint in **sp_create_plan_guide**.</span></span>  
  
 <span data-ttu-id="af7f1-115">Considere a consulta a seguir no banco de dados [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="af7f1-115">Consider the following query on the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database:</span></span>  
  
```  
SELECT pi.ProductID, SUM(pi.Quantity) AS Total  
FROM Production.ProductModel AS pm   
    INNER JOIN Production.ProductInventory AS pi   
        ON pm.ProductModelID = pi.ProductID   
WHERE pi.ProductID = 101   
GROUP BY pi.ProductID, pi.Quantity HAVING SUM(pi.Quantity) > 50;  
```  
  
 <span data-ttu-id="af7f1-116">Como um administrador de banco de dados, você determinou que não quer habilitar a parametrização forçada em todas as consultas no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="af7f1-116">As a database administrator, you have determined that you do not want to enable forced parameterization on all queries in the database.</span></span> <span data-ttu-id="af7f1-117">Porém, você quer evitar despesas de compilação em todas as consultas que são sintaticamente equivalentes à consulta anterior, mas só diferem em valores literais constantes.</span><span class="sxs-lookup"><span data-stu-id="af7f1-117">However, you do want to avoid compilation costs on all queries that are syntactically equivalent to the previous query, but differ only in their constant literal values.</span></span> <span data-ttu-id="af7f1-118">Em outras palavras, você quer parametrizar a consulta para que um plano de consulta para esse tipo de consulta seja reutilizado.</span><span class="sxs-lookup"><span data-stu-id="af7f1-118">In other words, you want the query to be parameterized so that a query plan for this kind of query is reused.</span></span> <span data-ttu-id="af7f1-119">Nesse caso, complete as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="af7f1-119">In this case, complete the following steps:</span></span>  
  
1.  <span data-ttu-id="af7f1-120">Recupere o formulário parametrizado da consulta.</span><span class="sxs-lookup"><span data-stu-id="af7f1-120">Retrieve the parameterized form of the query.</span></span> <span data-ttu-id="af7f1-121">O único modo seguro de obter esse valor para uso em **sp_create_plan_guide** é usando o procedimento armazenado do sistema [sp_get_query_template](/sql/relational-databases/system-stored-procedures/sp-get-query-template-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="af7f1-121">The only safe way to obtain this value for use in **sp_create_plan_guide** is by using the [sp_get_query_template](/sql/relational-databases/system-stored-procedures/sp-get-query-template-transact-sql) system stored procedure.</span></span>  
  
2.  <span data-ttu-id="af7f1-122">Crie a guia de plano no formulário parametrizado da consulta, especificando a dica de consulta PARAMETERIZATION FORCED.</span><span class="sxs-lookup"><span data-stu-id="af7f1-122">Create the plan guide on the parameterized form of the query, specifying the PARAMETERIZATION FORCED query hint.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="af7f1-123">Como parte da parametrização de uma consulta, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] atribui um tipo de dados aos parâmetros que substituem os valores literais, dependendo do valor e tamanho do literal.</span><span class="sxs-lookup"><span data-stu-id="af7f1-123">As part of parameterizing a query, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] assigns a data type to the parameters that replace the literal values, depending on the value and size of the literal.</span></span> <span data-ttu-id="af7f1-124">O mesmo processo ocorre para o valor dos literais constantes passados para o **@stmt** parâmetro de saída de **sp_get_query_template**.</span><span class="sxs-lookup"><span data-stu-id="af7f1-124">The same process occurs to the value of the constant literals passed to the **@stmt** output parameter of **sp_get_query_template**.</span></span> <span data-ttu-id="af7f1-125">Como o tipo de dados especificado no **@params** argumento de **sp_create_plan_guide** deve corresponder ao da consulta, já que ele é parametrizado pelo [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , talvez seja necessário criar mais de um guia de plano para cobrir o intervalo completo de possíveis valores de parâmetro para a consulta.</span><span class="sxs-lookup"><span data-stu-id="af7f1-125">Because the data type specified in the **@params** argument of **sp_create_plan_guide** must match that of the query as it is parameterized by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], you may have to create more than one plan guide to cover the complete range of possible parameter values for the query.</span></span>  
  
 <span data-ttu-id="af7f1-126">O script a seguir pode ser usado para obter a consulta parametrizada e criar uma guia de plano para ela:</span><span class="sxs-lookup"><span data-stu-id="af7f1-126">The following script can be used both to obtain the parameterized query and then create a plan guide on it:</span></span>  
  
```  
DECLARE @stmt nvarchar(max);  
DECLARE @params nvarchar(max);  
EXEC sp_get_query_template   
    N'SELECT pi.ProductID, SUM(pi.Quantity) AS Total   
      FROM Production.ProductModel AS pm   
      INNER JOIN Production.ProductInventory AS pi ON pm.ProductModelID = pi.ProductID   
      WHERE pi.ProductID = 101   
      GROUP BY pi.ProductID, pi.Quantity   
      HAVING sum(pi.Quantity) > 50',  
    @stmt OUTPUT,   
    @params OUTPUT;  
EXEC sp_create_plan_guide   
    N'TemplateGuide1',   
    @stmt,   
    N'TEMPLATE',   
    NULL,   
    @params,   
    N'OPTION(PARAMETERIZATION FORCED)';  
```  
  
 <span data-ttu-id="af7f1-127">Da mesma forma, em um banco de dados no qual a parametrização forçada já está habilitada, você pode verificar se a consulta de exemplo e outras sintaticamente equivalentes, exceto pelos valores literais constantes, estão parametrizadas de acordo com as regras de parametrização simples.</span><span class="sxs-lookup"><span data-stu-id="af7f1-127">Similarly, in a database in which forced parameterization is already enabled, you can make sure that the sample query, and others that are syntactically equivalent, except for their constant literal values, are parameterized according to the rules of simple parameterization.</span></span> <span data-ttu-id="af7f1-128">Para fazer isso, especifique PARAMETERIZATION SIMPLE em vez de PARAMETERIZATION FORCED na cláusula OPTION.</span><span class="sxs-lookup"><span data-stu-id="af7f1-128">To do this, specify PARAMETERIZATION SIMPLE instead of PARAMETERIZATION FORCED in the OPTION clause.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="af7f1-129">Guias de plano TEMPLATE correspondem a instruções de consultas enviadas em lotes que só consistem em uma única instrução.</span><span class="sxs-lookup"><span data-stu-id="af7f1-129">TEMPLATE plan guides match statements to queries submitted in batches that consist of a single statement only.</span></span> <span data-ttu-id="af7f1-130">Instruções existentes em lotes com várias instruções não são qualificadas para correspondência com guias de plano TEMPLATE.</span><span class="sxs-lookup"><span data-stu-id="af7f1-130">Statements inside multistatement batches are not eligible to be matched by TEMPLATE plan guides.</span></span>  
  
  
