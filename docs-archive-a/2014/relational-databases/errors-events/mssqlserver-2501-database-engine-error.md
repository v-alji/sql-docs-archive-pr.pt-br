---
title: MSSQLSERVER_2501 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2501 (Database Engine error)
ms.assetid: 895aafe3-a4e7-4ed8-acc5-93be76ef3664
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 200997dcfe7bf8a5933b9fce492daabd5baffd04
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681665"
---
# <a name="mssqlserver_2501"></a><span data-ttu-id="5eae4-102">MSSQLSERVER_2501</span><span class="sxs-lookup"><span data-stu-id="5eae4-102">MSSQLSERVER_2501</span></span>
    
## <a name="details"></a><span data-ttu-id="5eae4-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="5eae4-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5eae4-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="5eae4-104">Product Name</span></span>|<span data-ttu-id="5eae4-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="5eae4-105">SQL Server</span></span>|  
|<span data-ttu-id="5eae4-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="5eae4-106">Event ID</span></span>|<span data-ttu-id="5eae4-107">2501</span><span class="sxs-lookup"><span data-stu-id="5eae4-107">2501</span></span>|  
|<span data-ttu-id="5eae4-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="5eae4-108">Event Source</span></span>|<span data-ttu-id="5eae4-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="5eae4-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="5eae4-110">Componente</span><span class="sxs-lookup"><span data-stu-id="5eae4-110">Component</span></span>|<span data-ttu-id="5eae4-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="5eae4-111">SQLEngine</span></span>|  
|<span data-ttu-id="5eae4-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="5eae4-112">Symbolic Name</span></span>|<span data-ttu-id="5eae4-113">DBCC_NO_SUCH_TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="5eae4-113">DBCC_NO_SUCH_TABLE_NAME</span></span>|  
|<span data-ttu-id="5eae4-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="5eae4-114">Message Text</span></span>|<span data-ttu-id="5eae4-115">Não foi possível encontrar uma tabela ou um objeto com o nome 'NAME'.</span><span class="sxs-lookup"><span data-stu-id="5eae4-115">Cannot find a table or object with the name 'NAME'.</span></span> <span data-ttu-id="5eae4-116">Verifique o catálogo do sistema.</span><span class="sxs-lookup"><span data-stu-id="5eae4-116">Check the system catalog.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="5eae4-117">Explicação</span><span class="sxs-lookup"><span data-stu-id="5eae4-117">Explanation</span></span>  
 <span data-ttu-id="5eae4-118">O objeto especificado não foi encontrado.</span><span class="sxs-lookup"><span data-stu-id="5eae4-118">The specified object cannot be found.</span></span>  
  
### <a name="possible-causes"></a><span data-ttu-id="5eae4-119">Possíveis causas</span><span class="sxs-lookup"><span data-stu-id="5eae4-119">Possible Causes</span></span>  
 <span data-ttu-id="5eae4-120">Esse erro pode ser causado por um dos seguintes problemas:</span><span class="sxs-lookup"><span data-stu-id="5eae4-120">This error can be caused by one of the following problems:</span></span>  
  
-   <span data-ttu-id="5eae4-121">O objeto não foi especificado corretamente.</span><span class="sxs-lookup"><span data-stu-id="5eae4-121">The object is not specified correctly.</span></span>  
  
-   <span data-ttu-id="5eae4-122">O objeto não existe ou foi descartado antes que uma instrução tentasse utilizá-lo.</span><span class="sxs-lookup"><span data-stu-id="5eae4-122">The object does not exist, or the object was dropped before a statement tried to use it.</span></span>  
  
-   <span data-ttu-id="5eae4-123">Talvez o objeto exista, mas não foi possível expô-lo para o usuário.</span><span class="sxs-lookup"><span data-stu-id="5eae4-123">The object might exist, but could not be exposed to the user.</span></span> <span data-ttu-id="5eae4-124">Por exemplo, talvez o usuário não tenha permissões no objeto ou o objeto é uma tabela interna que não pôde ser vista pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="5eae4-124">For example, the user might not have permissions on the object, or the object is an internal table that could not be seen by a user.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="5eae4-125">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="5eae4-125">User Action</span></span>  
  
-   <span data-ttu-id="5eae4-126">Verifique se o contexto do banco de dados atual está correto.</span><span class="sxs-lookup"><span data-stu-id="5eae4-126">Verify the current database context is correct.</span></span> <span data-ttu-id="5eae4-127">Para obter mais informações, veja [USE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/use-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="5eae4-127">For more information, see [USE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/use-transact-sql).</span></span>  
  
-   <span data-ttu-id="5eae4-128">Verifique se o nome da tabela ou do objeto foi digitado corretamente.</span><span class="sxs-lookup"><span data-stu-id="5eae4-128">Verify that the table or object name is spelled correctly.</span></span>  
  
-   <span data-ttu-id="5eae4-129">Verifique o nome do esquema que contém o objeto.</span><span class="sxs-lookup"><span data-stu-id="5eae4-129">Verify the schema name that contains the object.</span></span> <span data-ttu-id="5eae4-130">Se o objeto pertencer a um esquema diferente do esquema padrão (**dbo**), você deverá especificar o nome da tabela ou do objeto usando o formato de duas partes *schema_name.object_name*.</span><span class="sxs-lookup"><span data-stu-id="5eae4-130">If the object belongs to a schema other than the default (**dbo**) schema, you must specify the table or object name by using the two-part format *schema_name.object_name*.</span></span>  
  
-   <span data-ttu-id="5eae4-131">Verifique se o objeto existe nas tabelas do sistema.</span><span class="sxs-lookup"><span data-stu-id="5eae4-131">Verify that the object exists in the system tables.</span></span> <span data-ttu-id="5eae4-132">Para verificar se uma tabela ou outro objeto no escopo do esquema existe, consulte a exibição do catálogo [sys.objects](/sql/relational-databases/system-catalog-views/sys-objects-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="5eae4-132">To verify whether a table or other schema-scoped object exists, query the [sys.objects](/sql/relational-databases/system-catalog-views/sys-objects-transact-sql) catalog view.</span></span> <span data-ttu-id="5eae4-133">Se o objeto não estiver nas tabelas do sistema, isso indica que ele foi excluído ou que o usuário não tem permissão para exibir metadados do objeto.</span><span class="sxs-lookup"><span data-stu-id="5eae4-133">If the object is not in the system tables, the object has been deleted, or the user does not have permissions to view the object metadata.</span></span> <span data-ttu-id="5eae4-134">Para obter mais informações sobre como exibir metadados de objeto, consulte [Configuração de visibilidade de metadados](../security/metadata-visibility-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="5eae4-134">For more information about how to view object metadata, see [Metadata Visibility Configuration](../security/metadata-visibility-configuration.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5eae4-135">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="5eae4-135">See Also</span></span>  
 [<span data-ttu-id="5eae4-136">Exibições de catálogo &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="5eae4-136">Catalog Views &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/catalog-views-transact-sql)  
  
  
