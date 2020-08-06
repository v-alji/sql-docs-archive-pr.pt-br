---
title: Recursos modificados (banco de dados independente) | Microsoft Docs
ms.custom: ''
ms.date: 07/17/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- contained database, modifications to DBs
ms.assetid: a2942509-39a2-4903-b504-ae80a300a9de
author: stevestein
ms.author: sstein
ms.openlocfilehash: bc52821deeb879022881f838c61823b23c0c10c8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685725"
---
# <a name="modified-features-contained-database"></a><span data-ttu-id="62fb2-102">Recursos modificados (banco de dados independente)</span><span class="sxs-lookup"><span data-stu-id="62fb2-102">Modified Features (Contained Database)</span></span>
  <span data-ttu-id="62fb2-103">Os recursos a seguir foram modificados para serem suportados por um banco de dados independente parcialmente.</span><span class="sxs-lookup"><span data-stu-id="62fb2-103">The following features have been modified to be supported by a partially contained database.</span></span> <span data-ttu-id="62fb2-104">Normalmente, eles são modificados para que não ultrapassem o limite de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="62fb2-104">Features are usually modified so they do not cross the database boundary.</span></span>  
  
 <span data-ttu-id="62fb2-105">Para obter mais informações, veja [Bancos de dados independentes](contained-databases.md).</span><span class="sxs-lookup"><span data-stu-id="62fb2-105">For more information, see [Contained Databases](contained-databases.md).</span></span>  
  
## <a name="alter-database"></a><span data-ttu-id="62fb2-106">ALTER DATABASE</span><span class="sxs-lookup"><span data-stu-id="62fb2-106">ALTER DATABASE</span></span>  
  
### <a name="application-level"></a><span data-ttu-id="62fb2-107">Nível de aplicativo</span><span class="sxs-lookup"><span data-stu-id="62fb2-107">Application Level</span></span>  
 <span data-ttu-id="62fb2-108">Ao usar a instrução ALTER DATABASE de dentro de um banco de dados independente, a sintaxe irá diferir da que é usada para um banco de dados dependente.</span><span class="sxs-lookup"><span data-stu-id="62fb2-108">When using the ALTER DATABASE statement from inside of a contained database, the syntax differs from that used for a non-contained database.</span></span> <span data-ttu-id="62fb2-109">Essa diferença inclui restrições de elementos da instrução que se estendem além do banco de dados para a instância.</span><span class="sxs-lookup"><span data-stu-id="62fb2-109">This difference includes restrictions of elements of the statement that extend beyond the database to the instance.</span></span> <span data-ttu-id="62fb2-110">Para obter mais informações, veja [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="62fb2-110">For more information, see [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql).</span></span>  
  
### <a name="instance-level"></a><span data-ttu-id="62fb2-111">Nível de instância</span><span class="sxs-lookup"><span data-stu-id="62fb2-111">Instance Level</span></span>  
 <span data-ttu-id="62fb2-112">A sintaxe para a instrução ALTER DATABASE, quando usada fora de um banco de dados independente, irá diferir da que é usada para bancos de dados dependentes.</span><span class="sxs-lookup"><span data-stu-id="62fb2-112">The syntax for the ALTER DATABASE when used outside of a contained database differs from that used for non-contained databases.</span></span> <span data-ttu-id="62fb2-113">Estas alterações impedem o cruzamento do limite de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="62fb2-113">These changes prevent crossing the database boundary.</span></span> <span data-ttu-id="62fb2-114">Para obter mais informações, veja [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="62fb2-114">For more information, see [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql).</span></span>  
  
## <a name="create-database"></a><span data-ttu-id="62fb2-115">CREATE DATABASE</span><span class="sxs-lookup"><span data-stu-id="62fb2-115">CREATE DATABASE</span></span>  
 <span data-ttu-id="62fb2-116">A sintaxe CREATE DATABASE para um banco de dados independente difere da que é usada em um banco de dados dependente.</span><span class="sxs-lookup"><span data-stu-id="62fb2-116">The CREATE DATABASE syntax for a contained database differs from that for a non-contained database.</span></span> <span data-ttu-id="62fb2-117">Veja [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) para obter informações sobre novos requisitos de sintaxe e concessões.</span><span class="sxs-lookup"><span data-stu-id="62fb2-117">See [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql)for information about new syntax requirements and allowances.</span></span>  
  
## <a name="temporary-tables"></a><span data-ttu-id="62fb2-118">Tabelas temporárias</span><span class="sxs-lookup"><span data-stu-id="62fb2-118">Temporary Tables</span></span>  
 <span data-ttu-id="62fb2-119">São permitidas tabelas temporárias locais dentro de um banco de dados independente, mas o comportamento delas difere das usadas em bancos de dados dependentes.</span><span class="sxs-lookup"><span data-stu-id="62fb2-119">Local temporary tables are permitted within a contained database, but their behavior differs from those in non-contained databases.</span></span> <span data-ttu-id="62fb2-120">Em bancos de dados dependentes, os dados de tabelas temporárias são agrupados na ordenação de **tempdb**.</span><span class="sxs-lookup"><span data-stu-id="62fb2-120">In non-contained databases, temporary table data is collated in the collation of **tempdb**.</span></span> <span data-ttu-id="62fb2-121">Em um banco de dados independente, os dados de tabelas temporárias são agrupados na ordenação do banco de dados independente.</span><span class="sxs-lookup"><span data-stu-id="62fb2-121">In a contained database temporary table data is collated in the collation of the contained database.</span></span>  
  
 <span data-ttu-id="62fb2-122">Todo os metadados associados a tabelas temporárias (por exemplo, nomes de tabelas e de colunas, índices, etc.) estarão na ordenação de catálogo.</span><span class="sxs-lookup"><span data-stu-id="62fb2-122">All metadata associated with temporary tables (for example, table and column names, indexes, and so on) will be in the catalog collation.</span></span>  
  
 <span data-ttu-id="62fb2-123">Podem não ser usadas restrições nomeadas em tabelas temporárias.</span><span class="sxs-lookup"><span data-stu-id="62fb2-123">Named constraints may not be used in temporary tables.</span></span>  
  
 <span data-ttu-id="62fb2-124">Tabelas temporárias podem não recorrer a tipos definidos pelo usuário, coleções de esquemas XML ou funções definidas pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="62fb2-124">Temporary tables may not refer to user-defined types, XML schema collections, or user-defined functions.</span></span>  
  
## <a name="collation"></a><span data-ttu-id="62fb2-125">Collation</span><span class="sxs-lookup"><span data-stu-id="62fb2-125">Collation</span></span>  
 <span data-ttu-id="62fb2-126">No modelo de banco de dados dependente, há três tipos separados de ordenação: ordenação de banco de dados, ordenação de Instância e ordenação de tempdb.</span><span class="sxs-lookup"><span data-stu-id="62fb2-126">In the non-contained database model, there are three separate types of collation: Database collation, Instance collation, and tempdb collation.</span></span> <span data-ttu-id="62fb2-127">Bancos de dados independentes usam apenas duas ordenações, ordenação de banco de dados e a nova ordenação de catálogo.</span><span class="sxs-lookup"><span data-stu-id="62fb2-127">Contained databases use only two collations, database collation and the new catalog collation.</span></span> <span data-ttu-id="62fb2-128">Veja [Ordenações de banco de dados independentes](contained-database-collations.md) para obter mais detalhes sobre a ordenação de banco de dados independente.</span><span class="sxs-lookup"><span data-stu-id="62fb2-128">See [Contained Database Collations](contained-database-collations.md) for more details on contained database collation.</span></span>  
  
## <a name="user-options"></a><span data-ttu-id="62fb2-129">Opções de usuário</span><span class="sxs-lookup"><span data-stu-id="62fb2-129">User Options</span></span>  
 <span data-ttu-id="62fb2-130">Ao habilitar bancos de dados independentes, é preciso definir a [Opção user options](../../database-engine/configure-windows/configure-the-user-options-server-configuration-option.md) como 0 para a instância de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="62fb2-130">When enabling contained databases, the [user options Option](../../database-engine/configure-windows/configure-the-user-options-server-configuration-option.md) must be set to 0 for the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62fb2-131">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="62fb2-131">See Also</span></span>  
 <span data-ttu-id="62fb2-132">[Ordenações de banco de dados independentes](contained-database-collations.md) </span><span class="sxs-lookup"><span data-stu-id="62fb2-132">[Contained Database Collations](contained-database-collations.md) </span></span>  
 [<span data-ttu-id="62fb2-133">Bancos de dados independentes</span><span class="sxs-lookup"><span data-stu-id="62fb2-133">Contained Databases</span></span>](contained-databases.md)  
  
  
