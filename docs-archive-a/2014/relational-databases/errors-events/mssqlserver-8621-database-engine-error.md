---
title: MSSQLSERVER_8621 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 8621 (Database Engine error)
ms.assetid: 67f59865-becd-4999-8bb0-90aedd7effbf
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 48c36cf936475e3deea37a172c7dc59f88d0a31a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575861"
---
# <a name="mssqlserver_8621"></a><span data-ttu-id="930f0-102">MSSQLSERVER_8621</span><span class="sxs-lookup"><span data-stu-id="930f0-102">MSSQLSERVER_8621</span></span>
    
## <a name="details"></a><span data-ttu-id="930f0-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="930f0-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="930f0-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="930f0-104">Product Name</span></span>|<span data-ttu-id="930f0-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="930f0-105">SQL Server</span></span>|  
|<span data-ttu-id="930f0-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="930f0-106">Event ID</span></span>|<span data-ttu-id="930f0-107">8621</span><span class="sxs-lookup"><span data-stu-id="930f0-107">8621</span></span>|  
|<span data-ttu-id="930f0-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="930f0-108">Event Source</span></span>|<span data-ttu-id="930f0-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="930f0-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="930f0-110">Componente</span><span class="sxs-lookup"><span data-stu-id="930f0-110">Component</span></span>|<span data-ttu-id="930f0-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="930f0-111">SQLEngine</span></span>|  
|<span data-ttu-id="930f0-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="930f0-112">Symbolic Name</span></span>|<span data-ttu-id="930f0-113">OPTIMIZER_STACK_OVERFLOW_ERR</span><span class="sxs-lookup"><span data-stu-id="930f0-113">OPTIMIZER_STACK_OVERFLOW_ERR</span></span>|  
|<span data-ttu-id="930f0-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="930f0-114">Message Text</span></span>|<span data-ttu-id="930f0-115">O processador de consultas ficou sem espaço de pilha suficiente durante a otimização da consulta.</span><span class="sxs-lookup"><span data-stu-id="930f0-115">The query processor ran out of stack space during query optimization.</span></span> <span data-ttu-id="930f0-116">Simplifique a consulta.</span><span class="sxs-lookup"><span data-stu-id="930f0-116">Please simplify the query.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="930f0-117">Explicação</span><span class="sxs-lookup"><span data-stu-id="930f0-117">Explanation</span></span>  
 <span data-ttu-id="930f0-118">É provável que a causa do erro seja o tamanho da consulta expandida.</span><span class="sxs-lookup"><span data-stu-id="930f0-118">The size of the expanded query is the most likely cause of the error.</span></span> <span data-ttu-id="930f0-119">A consulta expandida substitui na consulta original as definições de cada uma das exibições, colunas computadas, funções [!INCLUDE[tsql](../../includes/tsql-md.md)] e expressões de tabela comuns a que faz referência, além de ações em cascata, como atualizar índices secundários, exibições e gatilhos.</span><span class="sxs-lookup"><span data-stu-id="930f0-119">The expanded query substitutes into the original query the definitions of each of the views, computed columns, [!INCLUDE[tsql](../../includes/tsql-md.md)] functions, and common table expressions it references, as well as cascading actions like updating secondary indexes, views, and triggers.</span></span>  
  
 <span data-ttu-id="930f0-120">É provável que a consulta seja grande em alguma dimensão; por exemplo, o número de tabelas referenciadas por definições de exibição ou uma expressão escalar muito grande.</span><span class="sxs-lookup"><span data-stu-id="930f0-120">Most likely the query is large in some dimension; for example, the number of tables referenced by view definitions, or a very large scalar expression.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="930f0-121">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="930f0-121">User Action</span></span>  
 <span data-ttu-id="930f0-122">Simplifique a consulta dividindo-a em várias consultas na dimensão maior.</span><span class="sxs-lookup"><span data-stu-id="930f0-122">Simplify the query by breaking the query into multiple queries along the largest dimension.</span></span> <span data-ttu-id="930f0-123">Primeiro remova todos os elementos da consulta que não são de fato necessários e, depois, tente adicionar uma tabela temporária e dividir a consulta em duas.</span><span class="sxs-lookup"><span data-stu-id="930f0-123">First remove any query elements that are not really necessary, then try adding a temp table and splitting the query in two.</span></span>  <span data-ttu-id="930f0-124">Apenas mover uma parte da consulta para uma subconsulta, função ou expressão de tabela comum não é suficiente, porque elas são recombinadas pelo compilador [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="930f0-124">Merely moving a part of the query to a subquery, function, or common table expression is insufficient because they get recombined by the [!INCLUDE[tsql](../../includes/tsql-md.md)] compiler.</span></span>  
  
  
