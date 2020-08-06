---
title: Exibições | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- views [SQL Server], about views
ms.assetid: ada83c28-e8b7-45d9-b53c-b3d67c8820c8
author: stevestein
ms.author: sstein
ms.openlocfilehash: c7332506666b11e96255c2b903d70b232ae4efa6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568395"
---
# <a name="views"></a><span data-ttu-id="0f65c-102">Exibições</span><span class="sxs-lookup"><span data-stu-id="0f65c-102">Views</span></span>
  <span data-ttu-id="0f65c-103">Uma exibição é uma tabela virtual cujos conteúdos são definidos por uma consulta.</span><span class="sxs-lookup"><span data-stu-id="0f65c-103">A view is a virtual table whose contents are defined by a query.</span></span> <span data-ttu-id="0f65c-104">Como uma tabela, uma exibição consiste em um conjunto de colunas nomeadas e linhas de dados.</span><span class="sxs-lookup"><span data-stu-id="0f65c-104">Like a table, a view consists of a set of named columns and rows of data.</span></span> <span data-ttu-id="0f65c-105">Exceto se indexada, uma exibição não existe como um conjunto armazenado de valores de dados em um banco de dados.</span><span class="sxs-lookup"><span data-stu-id="0f65c-105">Unless indexed, a view does not exist as a stored set of data values in a database.</span></span> <span data-ttu-id="0f65c-106">As linhas e colunas dos dados vêm de tabelas referidas em consultas que definem a exibição e são produzidas, dinamicamente, quando a exibição é referenciada.</span><span class="sxs-lookup"><span data-stu-id="0f65c-106">The rows and columns of data come from tables referenced in the query defining the view and are produced dynamically when the view is referenced.</span></span>  
  
 <span data-ttu-id="0f65c-107">Uma exibição atua como um filtro nas tabelas subjacentes na exibição.</span><span class="sxs-lookup"><span data-stu-id="0f65c-107">A view acts as a filter on the underlying tables referenced in the view.</span></span> <span data-ttu-id="0f65c-108">A consulta que define a exibição pode ser de uma ou mais tabelas ou de outras exibições dos bancos de dados atuais ou outros.</span><span class="sxs-lookup"><span data-stu-id="0f65c-108">The query that defines the view can be from one or more tables or from other views in the current or other databases.</span></span> <span data-ttu-id="0f65c-109">As consultas distribuídas podem também ser usadas para definir as exibições que usam os dados de diversas fontes heterogêneas.</span><span class="sxs-lookup"><span data-stu-id="0f65c-109">Distributed queries can also be used to define views that use data from multiple heterogeneous sources.</span></span> <span data-ttu-id="0f65c-110">Isso é útil, por exemplo, se você deseja combinar dados estruturados de forma semelhante de diferentes servidores, cada um dos quais armazena dados para uma região diferente de sua organização.</span><span class="sxs-lookup"><span data-stu-id="0f65c-110">This is useful, for example, if you want to combine similarly structured data from different servers, each of which stores data for a different region of your organization.</span></span>  
  
 <span data-ttu-id="0f65c-111">As exibições são geralmente usadas para focalizar, simplificar e personalizar a percepção que cada usuário tem do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="0f65c-111">Views are generally used to focus, simplify, and customize the perception each user has of the database.</span></span> <span data-ttu-id="0f65c-112">As exibições podem ser usadas como mecanismos de segurança para permitir que usuários acessem dados por meio da exibição, sem conceder-lhes permissões para acessarem diretamente as tabelas base subjacentes da exibição.</span><span class="sxs-lookup"><span data-stu-id="0f65c-112">Views can be used as security mechanisms by letting users access data through the view, without granting the users permissions to directly access the underlying base tables of the view.</span></span> <span data-ttu-id="0f65c-113">As exibições podem ser usadas para fornecer uma interface compatível com versões anteriores para emular uma tabela que costumava existir, mas cujo esquema foi alterado.</span><span class="sxs-lookup"><span data-stu-id="0f65c-113">Views can be used to provide a backward compatible interface to emulate a table that used to exist but whose schema has changed.</span></span> <span data-ttu-id="0f65c-114">As exibições também podem ser usadas quando você copia dados para e de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para melhorar o desempenho e particionar dados.</span><span class="sxs-lookup"><span data-stu-id="0f65c-114">Views can also be used when you copy data to and from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to improve performance and to partition data.</span></span>  
  
## <a name="types-of-views"></a><span data-ttu-id="0f65c-115">Tipos de exibições</span><span class="sxs-lookup"><span data-stu-id="0f65c-115">Types of Views</span></span>  
 <span data-ttu-id="0f65c-116">Além da função padrão de exibições básicas definidas pelo usuário, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fornece os seguintes tipos de exibições que servem para propósitos especiais em um banco de dados:</span><span class="sxs-lookup"><span data-stu-id="0f65c-116">Besides the standard role of basic user-defined views, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provides the following types of views that serve special purposes in a database.</span></span>  
  
 <span data-ttu-id="0f65c-117">Exibições indexadas</span><span class="sxs-lookup"><span data-stu-id="0f65c-117">Indexed Views</span></span>  
 <span data-ttu-id="0f65c-118">Uma exibição indexada é uma exibição que foi materializada.</span><span class="sxs-lookup"><span data-stu-id="0f65c-118">An indexed view is a view that has been materialized.</span></span> <span data-ttu-id="0f65c-119">Isto significa que a definição de exibição foi computada e os dados resultantes foram armazenaram como uma tabela.</span><span class="sxs-lookup"><span data-stu-id="0f65c-119">This means the view definition has been computed and the resulting data stored just like a table.</span></span> <span data-ttu-id="0f65c-120">Você indexa uma exibição criando um índice com cluster exclusivo nela.</span><span class="sxs-lookup"><span data-stu-id="0f65c-120">You index a view by creating a unique clustered index on it.</span></span> <span data-ttu-id="0f65c-121">As exibições indexadas podem melhorar sensivelmente o desempenho de alguns tipos de consultas.</span><span class="sxs-lookup"><span data-stu-id="0f65c-121">Indexed views can dramatically improve the performance of some types of queries.</span></span> <span data-ttu-id="0f65c-122">As exibições indexadas funcionam melhor para consultas que agregam muitas linhas.</span><span class="sxs-lookup"><span data-stu-id="0f65c-122">Indexed views work best for queries that aggregate many rows.</span></span> <span data-ttu-id="0f65c-123">Eles não são muito apropriadas para conjuntos de dados subjacentes atualizados com frequência.</span><span class="sxs-lookup"><span data-stu-id="0f65c-123">They are not well-suited for underlying data sets that are frequently updated.</span></span>  
  
 <span data-ttu-id="0f65c-124">Exibições particionadas</span><span class="sxs-lookup"><span data-stu-id="0f65c-124">Partitioned Views</span></span>  
 <span data-ttu-id="0f65c-125">Uma exibição particionada associa dados particionados horizontalmente de um conjunto de tabelas membro em um ou mais servidores.</span><span class="sxs-lookup"><span data-stu-id="0f65c-125">A partitioned view joins horizontally partitioned data from a set of member tables across one or more servers.</span></span> <span data-ttu-id="0f65c-126">Isso faz com que os dados pareçam ser provenientes de uma tabela.</span><span class="sxs-lookup"><span data-stu-id="0f65c-126">This makes the data appear as if from one table.</span></span> <span data-ttu-id="0f65c-127">Uma exibição que associa tabelas membro na mesma instância de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] é uma exibição particionada local.</span><span class="sxs-lookup"><span data-stu-id="0f65c-127">A view that joins member tables on the same instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is a local partitioned view.</span></span>  
  
 <span data-ttu-id="0f65c-128">Exibições do sistema</span><span class="sxs-lookup"><span data-stu-id="0f65c-128">System Views</span></span>  
 <span data-ttu-id="0f65c-129">Exibições do sistema expõem metadados de catálogo.</span><span class="sxs-lookup"><span data-stu-id="0f65c-129">System views expose catalog metadata.</span></span> <span data-ttu-id="0f65c-130">Você pode usar exibições do sistema para retornar informações sobre a instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ou os objetos definidos na instância.</span><span class="sxs-lookup"><span data-stu-id="0f65c-130">You can use system views to return information about the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or the objects defined in the instance.</span></span> <span data-ttu-id="0f65c-131">Por exemplo, você pode consultar a exibição de catálogo de sys.databases para retornar informações sobre os bancos de dados definidos pelo usuário disponível na instância.</span><span class="sxs-lookup"><span data-stu-id="0f65c-131">For example, you can query the sys.databases catalog view to return information about the user-defined databases available in the instance.</span></span> <span data-ttu-id="0f65c-132">Para obter mais informações, veja [Exibições do sistema &#40;Transact-SQL&#41;](/sql/t-sql/language-reference)</span><span class="sxs-lookup"><span data-stu-id="0f65c-132">For more information, see [System Views &#40;Transact-SQL&#41;](/sql/t-sql/language-reference)</span></span>  
  
## <a name="common-view-tasks"></a><span data-ttu-id="0f65c-133">Tarefas de exibição comuns</span><span class="sxs-lookup"><span data-stu-id="0f65c-133">Common View Tasks</span></span>  
 <span data-ttu-id="0f65c-134">A tabela a seguir fornece links a tarefas comuns associadas à criação ou modificação de uma exibição.</span><span class="sxs-lookup"><span data-stu-id="0f65c-134">The following table provides links to common tasks associated with creating or modifying a view.</span></span>  
  
|<span data-ttu-id="0f65c-135">Tarefas de exibição</span><span class="sxs-lookup"><span data-stu-id="0f65c-135">View Tasks</span></span>|<span data-ttu-id="0f65c-136">Tópico</span><span class="sxs-lookup"><span data-stu-id="0f65c-136">Topic</span></span>|  
|----------------|-----------|  
|<span data-ttu-id="0f65c-137">Descreve como criar uma exibição.</span><span class="sxs-lookup"><span data-stu-id="0f65c-137">Describes how to create a view.</span></span>|[<span data-ttu-id="0f65c-138">Criar exibições</span><span class="sxs-lookup"><span data-stu-id="0f65c-138">Create Views</span></span>](../views/views.md)|  
|<span data-ttu-id="0f65c-139">Descreve como criar uma exibição indexada.</span><span class="sxs-lookup"><span data-stu-id="0f65c-139">Describes how to create an indexed view.</span></span>|[<span data-ttu-id="0f65c-140">Criar exibições indexadas</span><span class="sxs-lookup"><span data-stu-id="0f65c-140">Create Indexed Views</span></span>](../views/create-indexed-views.md)|  
|<span data-ttu-id="0f65c-141">Descreve como modificar a definição de exibição.</span><span class="sxs-lookup"><span data-stu-id="0f65c-141">Describes how to modify the view definition.</span></span>|[<span data-ttu-id="0f65c-142">Modificar exibições</span><span class="sxs-lookup"><span data-stu-id="0f65c-142">Modify Views</span></span>](../views/modify-views.md)|  
|<span data-ttu-id="0f65c-143">Descreve como modificar dados por uma exibição.</span><span class="sxs-lookup"><span data-stu-id="0f65c-143">Describes how to modify data through a view.</span></span>|[<span data-ttu-id="0f65c-144">Modificar dados por meio de uma exibição</span><span class="sxs-lookup"><span data-stu-id="0f65c-144">Modify Data Through a View</span></span>](../views/modify-data-through-a-view.md)|  
|<span data-ttu-id="0f65c-145">Descreve como excluir uma exibição.</span><span class="sxs-lookup"><span data-stu-id="0f65c-145">Describes how to delete a view.</span></span>|[<span data-ttu-id="0f65c-146">Excluir exibições</span><span class="sxs-lookup"><span data-stu-id="0f65c-146">Delete Views</span></span>](../views/delete-views.md)|  
|<span data-ttu-id="0f65c-147">Descreve como retornar informações sobre uma exibição como a definição de exibição.</span><span class="sxs-lookup"><span data-stu-id="0f65c-147">Describes how to return information about a view such as the view definition.</span></span>|[<span data-ttu-id="0f65c-148">Obter informações sobre uma exibição</span><span class="sxs-lookup"><span data-stu-id="0f65c-148">Get Information About a View</span></span>](../views/get-information-about-a-view.md)|  
|<span data-ttu-id="0f65c-149">Descreve como renomear uma exibição.</span><span class="sxs-lookup"><span data-stu-id="0f65c-149">Describes how to rename a view.</span></span>|[<span data-ttu-id="0f65c-150">Renomear exibições</span><span class="sxs-lookup"><span data-stu-id="0f65c-150">Rename Views</span></span>](../views/rename-views.md)|  
  
## <a name="see-also"></a><span data-ttu-id="0f65c-151">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0f65c-151">See Also</span></span>  
 <span data-ttu-id="0f65c-152">[Criar exibições sobre colunas XML](../xml/create-views-over-xml-columns.md) </span><span class="sxs-lookup"><span data-stu-id="0f65c-152">[Create Views over XML Columns](../xml/create-views-over-xml-columns.md) </span></span>  
 [<span data-ttu-id="0f65c-153">CREATE VIEW &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="0f65c-153">CREATE VIEW &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-view-transact-sql)  
  
  