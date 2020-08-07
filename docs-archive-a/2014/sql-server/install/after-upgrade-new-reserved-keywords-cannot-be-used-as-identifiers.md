---
title: Após a atualização, novas palavras-chave reservadas não podem ser usadas como identificadores | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- keywords [SQL Server], after upgrade
- keywords [SQL Server], reserved
- keywords [SQL Server]
ms.assetid: cb242081-54f8-4273-a8ef-52f3751c25ef
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 36f7f8cadcba5e114feee4a3c42de6f40070ce72
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573541"
---
# <a name="after-upgrade-new-reserved-keywords-cannot-be-used-as-identifiers"></a><span data-ttu-id="7289c-102">Depois de atualização, novas palavras-chave reservadas não poderão ser usadas como identificadores</span><span class="sxs-lookup"><span data-stu-id="7289c-102">After upgrade, new reserved keywords cannot be used as identifiers</span></span>
  <span data-ttu-id="7289c-103">O Supervisor de Atualização detectou o uso de palavras que são palavras-chave reservadas.</span><span class="sxs-lookup"><span data-stu-id="7289c-103">Upgrade Advisor detected the use of words that are reserved keywords.</span></span> <span data-ttu-id="7289c-104">Uma palavra-chave reservada não pode ser usada como um identificador ou nome de objeto a menos que o nome seja delimitado.</span><span class="sxs-lookup"><span data-stu-id="7289c-104">A reserved keyword cannot be used as an identifier or object name unless the name is delimited.</span></span>  
  
## <a name="component"></a><span data-ttu-id="7289c-105">Componente</span><span class="sxs-lookup"><span data-stu-id="7289c-105">Component</span></span>  
 <span data-ttu-id="7289c-106">Mecanismo de Banco de Dados</span><span class="sxs-lookup"><span data-stu-id="7289c-106">Database Engine</span></span>  
  
## <a name="description"></a><span data-ttu-id="7289c-107">Descrição</span><span class="sxs-lookup"><span data-stu-id="7289c-107">Description</span></span>  
 <span data-ttu-id="7289c-108">No nível de compatibilidade 90 ou inferior, as seguintes palavras não são palavras-chave reservadas e podem ser usadas como identificadores ou nomes de objeto em scripts [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7289c-108">At compatibility level 90 or lower, the following words are not reserved keywords and can be used as identifiers or object names in [!INCLUDE[tsql](../../includes/tsql-md.md)] scripts.</span></span> <span data-ttu-id="7289c-109">No nível de compatibilidade 100, estas palavras são palavras-chave totalmente reservadas e não devem ser usadas como identificadores ou nomes de objeto.</span><span class="sxs-lookup"><span data-stu-id="7289c-109">At compatibility level 100, these words are fully reserved keywords and should not be used as identifiers or object names.</span></span>  
  
-   <span data-ttu-id="7289c-110">EXTERNAL</span><span class="sxs-lookup"><span data-stu-id="7289c-110">EXTERNAL</span></span>  
  
-   <span data-ttu-id="7289c-111">MESCLAR</span><span class="sxs-lookup"><span data-stu-id="7289c-111">MERGE</span></span>  
  
-   <span data-ttu-id="7289c-112">PIVOT</span><span class="sxs-lookup"><span data-stu-id="7289c-112">PIVOT</span></span>  
  
-   <span data-ttu-id="7289c-113">REVERT</span><span class="sxs-lookup"><span data-stu-id="7289c-113">REVERT</span></span>  
  
-   <span data-ttu-id="7289c-114">STOPLIST</span><span class="sxs-lookup"><span data-stu-id="7289c-114">STOPLIST</span></span>  
  
-   <span data-ttu-id="7289c-115">TABLESAMPLE</span><span class="sxs-lookup"><span data-stu-id="7289c-115">TABLESAMPLE</span></span>  
  
-   <span data-ttu-id="7289c-116">UNPIVOT</span><span class="sxs-lookup"><span data-stu-id="7289c-116">UNPIVOT</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="7289c-117">Ação corretiva</span><span class="sxs-lookup"><span data-stu-id="7289c-117">Corrective Action</span></span>  
 <span data-ttu-id="7289c-118">É recomendável renomear o objeto.</span><span class="sxs-lookup"><span data-stu-id="7289c-118">We recommend that you rename the object.</span></span> <span data-ttu-id="7289c-119">Se isso não puder ser feito antes da atualização, use um dos seguintes métodos até o nome ser alterado:</span><span class="sxs-lookup"><span data-stu-id="7289c-119">If that cannot be done before upgrading, use one of the following methods until the name can be changed:</span></span>  
  
-   <span data-ttu-id="7289c-120">Mantenha a configuração do nível de compatibilidade do banco de dados como 90 ou inferior.</span><span class="sxs-lookup"><span data-stu-id="7289c-120">Retain the database compatibility level setting of 90 or lower.</span></span>  
  
-   <span data-ttu-id="7289c-121">Faça referência ao objeto usando identificadores delimitados.</span><span class="sxs-lookup"><span data-stu-id="7289c-121">Refer to the object by using delimited identifiers.</span></span> <span data-ttu-id="7289c-122">Por exemplo, a instrução `CREATE TABLE [MERGE] ([MERGE] int);` usa colchetes para delimitar a mesclagem de nome de objeto.</span><span class="sxs-lookup"><span data-stu-id="7289c-122">For example, the statement `CREATE TABLE [MERGE] ([MERGE] int);` uses brackets to delimit the object name MERGE.</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="7289c-123">Recursos externos</span><span class="sxs-lookup"><span data-stu-id="7289c-123">External Resources</span></span>  
 [<span data-ttu-id="7289c-124">Palavras-chave reservadas &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="7289c-124">Reserved Keywords &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/language-elements/reserved-keywords-transact-sql)  
  
 [<span data-ttu-id="7289c-125">MERGE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="7289c-125">MERGE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/merge-transact-sql)  
  
 [<span data-ttu-id="7289c-126">Identificadores delimitados (Mecanismo de Banco de Dados)</span><span class="sxs-lookup"><span data-stu-id="7289c-126">Delimited Identifiers (Database Engine)</span></span>](https://go.microsoft.com/fwlink/?LinkId=112509)  
  
 [<span data-ttu-id="7289c-127">Nível de compatibilidade de ALTER DATABASE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="7289c-127">ALTER DATABASE Compatibility Level &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-database-transact-sql-compatibility-level)  
  
  
