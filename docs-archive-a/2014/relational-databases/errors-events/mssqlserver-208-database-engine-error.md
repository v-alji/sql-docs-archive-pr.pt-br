---
title: MSSQLSERVER_208 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 208 (Database Engine error)
ms.assetid: 4b1895f5-3197-4da1-af86-954c93507956
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 97ab3eb220c03c3de0c95251861f3b947890b090
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569534"
---
# <a name="mssqlserver_208"></a><span data-ttu-id="41d15-102">MSSQLSERVER_208</span><span class="sxs-lookup"><span data-stu-id="41d15-102">MSSQLSERVER_208</span></span>
    
## <a name="details"></a><span data-ttu-id="41d15-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="41d15-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="41d15-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="41d15-104">Product Name</span></span>|<span data-ttu-id="41d15-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="41d15-105">SQL Server</span></span>|  
|<span data-ttu-id="41d15-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="41d15-106">Event ID</span></span>|<span data-ttu-id="41d15-107">208</span><span class="sxs-lookup"><span data-stu-id="41d15-107">208</span></span>|  
|<span data-ttu-id="41d15-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="41d15-108">Event Source</span></span>|<span data-ttu-id="41d15-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="41d15-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="41d15-110">Componente</span><span class="sxs-lookup"><span data-stu-id="41d15-110">Component</span></span>|<span data-ttu-id="41d15-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="41d15-111">SQLEngine</span></span>|  
|<span data-ttu-id="41d15-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="41d15-112">Symbolic Name</span></span>|<span data-ttu-id="41d15-113">SQ_BADOBJECT</span><span class="sxs-lookup"><span data-stu-id="41d15-113">SQ_BADOBJECT</span></span>|  
|<span data-ttu-id="41d15-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="41d15-114">Message Text</span></span>|<span data-ttu-id="41d15-115">Nome de objeto '%.\*ls' inválido.</span><span class="sxs-lookup"><span data-stu-id="41d15-115">Invalid object name '%.\*ls'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="41d15-116">Explicação</span><span class="sxs-lookup"><span data-stu-id="41d15-116">Explanation</span></span>  
 <span data-ttu-id="41d15-117">O objeto especificado não foi encontrado.</span><span class="sxs-lookup"><span data-stu-id="41d15-117">The specified object cannot be found.</span></span>  
  
### <a name="possible-causes"></a><span data-ttu-id="41d15-118">Possíveis causas</span><span class="sxs-lookup"><span data-stu-id="41d15-118">Possible Causes</span></span>  
 <span data-ttu-id="41d15-119">Esse erro pode ser causado por um dos seguintes problemas:</span><span class="sxs-lookup"><span data-stu-id="41d15-119">This error can be caused by one of the following problems:</span></span>  
  
-   <span data-ttu-id="41d15-120">O objeto não foi especificado corretamente.</span><span class="sxs-lookup"><span data-stu-id="41d15-120">The object is not specified correctly.</span></span>  
  
-   <span data-ttu-id="41d15-121">O objeto não existe no banco de dados atual ou no banco de dados especificado.</span><span class="sxs-lookup"><span data-stu-id="41d15-121">The object does not exist in the current database or in the specified database.</span></span>  
  
-   <span data-ttu-id="41d15-122">O objeto existe, mas não pôde ser exposto ao usuário.</span><span class="sxs-lookup"><span data-stu-id="41d15-122">The object exists, but could not be exposed to the user.</span></span> <span data-ttu-id="41d15-123">Por exemplo, o usuário pode não ter as permissões no objeto ou talvez o objeto foi criado em uma instrução EXECUTE, mas acessado fora dela.</span><span class="sxs-lookup"><span data-stu-id="41d15-123">For example, the user might not have permissions on the object or the object is created within an EXECUTE statement but accessed outside the scope of the EXECUTE statement.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="41d15-124">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="41d15-124">User Action</span></span>  
 <span data-ttu-id="41d15-125">Verifique as informações a seguir e corrija a instrução conforme apropriado.</span><span class="sxs-lookup"><span data-stu-id="41d15-125">Verify the following information and correct the statement as appropriate.</span></span>  
  
-   <span data-ttu-id="41d15-126">O nome do objeto foi digitado corretamente.</span><span class="sxs-lookup"><span data-stu-id="41d15-126">The object name is spelled correctly.</span></span>  
  
-   <span data-ttu-id="41d15-127">O contexto do banco de dados atual está correto.</span><span class="sxs-lookup"><span data-stu-id="41d15-127">The current database context is correct.</span></span> <span data-ttu-id="41d15-128">Se um nome de banco de dados não for especificado para o objeto, este deverá existir no banco de dados atual.</span><span class="sxs-lookup"><span data-stu-id="41d15-128">If a database name for the object is not specified, the object must exist in the current database.</span></span> <span data-ttu-id="41d15-129">Para obter mais informações sobre como definir o contexto do banco de dados, consulte [USE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/use-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="41d15-129">For more information about setting the database context, see [USE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/use-transact-sql).</span></span>  
  
-   <span data-ttu-id="41d15-130">O objeto existe nas tabelas do sistema.</span><span class="sxs-lookup"><span data-stu-id="41d15-130">The object exists in the system tables.</span></span> <span data-ttu-id="41d15-131">Para verificar se uma tabela ou outro objeto no escopo do esquema existe, consulte a exibição do catálogo **sys.objects**.</span><span class="sxs-lookup"><span data-stu-id="41d15-131">To verify whether a table or other schema-scoped object exists, query the **sys.objects** catalog view.</span></span> <span data-ttu-id="41d15-132">Se o objeto não estiver nas tabelas do sistema, isso indica que ele foi excluído ou que o usuário não tem permissão para exibir metadados do objeto.</span><span class="sxs-lookup"><span data-stu-id="41d15-132">If the object is not in the system tables, the object has been deleted, or the user does not have permissions to view the object metadata.</span></span> <span data-ttu-id="41d15-133">Para obter mais informações sobre as permissões para exibir metadados de objeto, consulte [Configuração de visibilidade de metadados](../security/metadata-visibility-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="41d15-133">For more information about permissions to view object metadata, see [Metadata Visibility Configuration](../security/metadata-visibility-configuration.md).</span></span>  
  
-   <span data-ttu-id="41d15-134">O objeto está contido no esquema padrão do usuário.</span><span class="sxs-lookup"><span data-stu-id="41d15-134">The object is contained in the default schema of the user.</span></span> <span data-ttu-id="41d15-135">Se ele não estiver, o objeto deverá ser especificado no formato de duas partes *schema_name.object_name*.</span><span class="sxs-lookup"><span data-stu-id="41d15-135">If it is not, the object must be specified using the two-part format *schema_name.object_name*.</span></span> <span data-ttu-id="41d15-136">Observe que as funções com valor escalar sempre devem ser chamadas usando-se pelo menos um nome de duas partes.</span><span class="sxs-lookup"><span data-stu-id="41d15-136">Note that scalar-valued functions must always be invoked by using at least a two-part name.</span></span>  
  
-   <span data-ttu-id="41d15-137">A diferenciação de maiúsculas e minúsculas da ordenação de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="41d15-137">The case sensitivity of the database collation.</span></span>  
  
     <span data-ttu-id="41d15-138">Quando um banco de dados usa uma ordenação com diferenciação de maiúsculas e minúsculas, o nome do objeto deve corresponder ao uso de maiúsculas e minúsculas do objeto no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="41d15-138">When a database uses a case-sensitive collation, the object name must match the case of the object in the database.</span></span> <span data-ttu-id="41d15-139">Por exemplo, quando um objeto for especificado como **MyTable** em um banco de dados com uma ordenação com diferenciação de maiúsculas e minúsculas, as consultas que fizerem referência ao objeto como **mytable** ou **Mytable** retornarão o erro 208, pois os nomes dos objetos não são correspondentes.</span><span class="sxs-lookup"><span data-stu-id="41d15-139">For example, when an object is specified as **MyTable** in a database with a case sensitive collation, queries that refer to the object as **mytable** or **Mytable** will cause error 208 to return because the object names do not match.</span></span>  
  
     <span data-ttu-id="41d15-140">Você pode verificar a ordenação de banco de dados executando a instrução a seguir.</span><span class="sxs-lookup"><span data-stu-id="41d15-140">You can verify the database collation by running the following statement.</span></span>  
  
    ```  
    SELECT collation_name FROM sys.databases WHERE name = 'database_name';  
    ```  
  
     <span data-ttu-id="41d15-141">A abreviação CS no nome da ordenação indica que ela diferencia maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="41d15-141">The abbreviation CS in the collation name indicates the collation is case sensitive.</span></span> <span data-ttu-id="41d15-142">Por exemplo, Latin1_General_CS_AS é uma ordenação que tem diferenciação de maiúsculas e minúsculas e também de acentos.</span><span class="sxs-lookup"><span data-stu-id="41d15-142">For example, Latin1_General_CS_AS is a case sensitive, accent sensitive collation.</span></span> <span data-ttu-id="41d15-143">CI indica uma ordenação sem diferenciação de maiúsculas e minúsculas.</span><span class="sxs-lookup"><span data-stu-id="41d15-143">CI indicates a case insensitive collation.</span></span>  
  
-   <span data-ttu-id="41d15-144">O usuário tem permissão para acessar o objeto.</span><span class="sxs-lookup"><span data-stu-id="41d15-144">The user has permission to access the object.</span></span> <span data-ttu-id="41d15-145">Para verificar as permissões do usuário no objeto, use a função de sistema **Has_Perms_By_Name**.</span><span class="sxs-lookup"><span data-stu-id="41d15-145">To verify the permissions the user has on the object, use the **Has_Perms_By_Name** system function.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41d15-146">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="41d15-146">See Also</span></span>  
 <span data-ttu-id="41d15-147">[USAR&#41;&#40;Transact-SQL](/sql/t-sql/language-elements/use-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="41d15-147">[USE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/use-transact-sql) </span></span>  
 <span data-ttu-id="41d15-148">[Configuração de visibilidade de metadados](../security/metadata-visibility-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="41d15-148">[Metadata Visibility Configuration](../security/metadata-visibility-configuration.md) </span></span>  
 [<span data-ttu-id="41d15-149">HAS_PERMS_BY_NAME &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="41d15-149">HAS_PERMS_BY_NAME &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/has-perms-by-name-transact-sql)  
  
  
