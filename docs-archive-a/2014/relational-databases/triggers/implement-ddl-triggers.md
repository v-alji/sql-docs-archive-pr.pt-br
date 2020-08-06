---
title: Implementar gatilhos DDL | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- DDL triggers, implementing
ms.assetid: f44e5340-1d18-40e9-828e-0ffcca091ae3
author: rothja
ms.author: jroth
ms.openlocfilehash: 110e69aca31df75d4b4d7a732de5c58556bd3e24
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582868"
---
# <a name="implement-ddl-triggers"></a><span data-ttu-id="07774-102">Implementar gatilhos DDL</span><span class="sxs-lookup"><span data-stu-id="07774-102">Implement DDL Triggers</span></span>
  <span data-ttu-id="07774-103">Este tópico fornece informações para ajudá-lo a criar gatilhos DDL, modificar gatilhos DDL e desabilitar ou cancelar gatilhos DDL.</span><span class="sxs-lookup"><span data-stu-id="07774-103">This topic provides information to help you create DDL triggers, modify DDL triggers, and disable or drop DDL triggers.</span></span>  
  
## <a name="creating-ddl-triggers"></a><span data-ttu-id="07774-104">Criando gatilhos DDL</span><span class="sxs-lookup"><span data-stu-id="07774-104">Creating DDL Triggers</span></span>  
 <span data-ttu-id="07774-105">Os gatilhos DDL são criados usando a instrução [!INCLUDE[tsql](../../includes/tsql-md.md)] CREATE TRIGGER para gatilhos DDL.</span><span class="sxs-lookup"><span data-stu-id="07774-105">DDL triggers are created by using the [!INCLUDE[tsql](../../includes/tsql-md.md)] CREATE TRIGGER statement for DDL triggers.</span></span>  
  
 <span data-ttu-id="07774-106">**Para criar um gatilho DDL**</span><span class="sxs-lookup"><span data-stu-id="07774-106">**To create a DDL trigger**</span></span>  
  
-   [<span data-ttu-id="07774-107">CREATE TRIGGER &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="07774-107">CREATE TRIGGER &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-trigger-transact-sql)  
  
> [!IMPORTANT]  
>  <span data-ttu-id="07774-108">A habilidade de retornar conjuntos de resultados de gatilhos será removida em uma versão futura do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="07774-108">The ability to return result sets from triggers will be removed in a future version of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="07774-109">Os gatilhos que retornam conjuntos de resultados podem causar um comportamento inesperado em aplicativos que não são projetados para trabalhar com eles.</span><span class="sxs-lookup"><span data-stu-id="07774-109">Triggers that return result sets may cause unexpected behavior in applications that are not designed to work with them.</span></span> <span data-ttu-id="07774-110">Evite retornar conjuntos de resultados de gatilhos em novos trabalhos de desenvolvimento e planeje a modificação de aplicativos que atualmente fazem isso.</span><span class="sxs-lookup"><span data-stu-id="07774-110">Avoid returning result sets from triggers in new development work, and plan to modify applications that currently do this.</span></span> <span data-ttu-id="07774-111">Para impedir que os gatilhos retornem conjuntos de resultados no [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], defina a [Opção disallow results from triggers](../../database-engine/configure-windows/disallow-results-from-triggers-server-configuration-option.md) como 1.</span><span class="sxs-lookup"><span data-stu-id="07774-111">To prevent triggers from returning result sets in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], set the [disallow results from triggers Option](../../database-engine/configure-windows/disallow-results-from-triggers-server-configuration-option.md) to 1.</span></span> <span data-ttu-id="07774-112">A configuração padrão dessa opção será 1 em uma versão futura do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="07774-112">The default setting of this option will be 1 in a future version of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="modifying-ddl-triggers"></a><span data-ttu-id="07774-113">Modificando gatilhos DDL</span><span class="sxs-lookup"><span data-stu-id="07774-113">Modifying DDL Triggers</span></span>  
 <span data-ttu-id="07774-114">Para modificar a definição de um gatilho DDL, você pode cancelar e recriar o gatilho ou redefinir o gatilho existente em uma única etapa.</span><span class="sxs-lookup"><span data-stu-id="07774-114">If you have to modify the definition of a DDL trigger, you can either drop and re-create the trigger or redefine the existing trigger in a single step.</span></span>  
  
 <span data-ttu-id="07774-115">Se você alterar o nome de um objeto referenciado por um gatilho DDL, modifique o gatilho para que seu texto reflita o novo nome.</span><span class="sxs-lookup"><span data-stu-id="07774-115">If you change the name of an object that is referenced by a DDL trigger, you must modify the trigger so that its text reflects the new name.</span></span> <span data-ttu-id="07774-116">Portanto, antes de renomear um objeto, exiba primeiramente as dependências do objeto para determinar se algum gatilho foi afetado pela mudança proposta.</span><span class="sxs-lookup"><span data-stu-id="07774-116">Therefore, before renaming an object, display the dependencies of the object first to determine whether any triggers are affected by the proposed change.</span></span>  
  
 <span data-ttu-id="07774-117">Um gatilho também pode ser modificado para codificar sua definição.</span><span class="sxs-lookup"><span data-stu-id="07774-117">A trigger can also be modified to encrypt its definition.</span></span>  
  
 <span data-ttu-id="07774-118">**Para modificar um gatilho**</span><span class="sxs-lookup"><span data-stu-id="07774-118">**To modify a trigger**</span></span>  
  
-   [<span data-ttu-id="07774-119">ALTER TRIGGER &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="07774-119">ALTER TRIGGER &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-trigger-transact-sql)  
  
 <span data-ttu-id="07774-120">**Para exibir as dependências de um gatilho**</span><span class="sxs-lookup"><span data-stu-id="07774-120">**To view the dependencies of a trigger**</span></span>  
  
-   [<span data-ttu-id="07774-121">sys.sql_expression_dependencies &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="07774-121">sys.sql_expression_dependencies &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-sql-expression-dependencies-transact-sql)  
  
-   [<span data-ttu-id="07774-122">sys.dm_sql_referenced_entities &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="07774-122">sys.dm_sql_referenced_entities &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-sql-referenced-entities-transact-sql)  
  
-   [<span data-ttu-id="07774-123">sys.dm_sql_referencing_entities &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="07774-123">sys.dm_sql_referencing_entities &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-sql-referencing-entities-transact-sql)  
  
## <a name="disabling-and-dropping-ddl-triggers"></a><span data-ttu-id="07774-124">Desabilitando e cancelando gatilhos DDL</span><span class="sxs-lookup"><span data-stu-id="07774-124">Disabling and Dropping DDL Triggers</span></span>  
 <span data-ttu-id="07774-125">Quando um gatilho DDL não é mais necessário, pode ser desabilitado ou excluído.</span><span class="sxs-lookup"><span data-stu-id="07774-125">When a DDL trigger is no longer needed, you can disable it or delete it.</span></span>  
  
 <span data-ttu-id="07774-126">Ao desabilitar um gatilho DDL, você não o cancela.</span><span class="sxs-lookup"><span data-stu-id="07774-126">Disabling a DDL trigger does not drop it.</span></span> <span data-ttu-id="07774-127">O gatilho ainda existe como um objeto no banco de dados atual.</span><span class="sxs-lookup"><span data-stu-id="07774-127">The trigger still exists as an object in the current database.</span></span> <span data-ttu-id="07774-128">Porém, o gatilho não será acionado quando qualquer instrução [!INCLUDE[tsql](../../includes/tsql-md.md)] , em que ele tenha sido programado, for executada.</span><span class="sxs-lookup"><span data-stu-id="07774-128">However, the trigger will not fire when any [!INCLUDE[tsql](../../includes/tsql-md.md)] statements on which it was programmed are run.</span></span> <span data-ttu-id="07774-129">Os gatilhos DDL desabilitados podem ser habilitados novamente.</span><span class="sxs-lookup"><span data-stu-id="07774-129">DDL triggers that are disabled can be reenabled.</span></span> <span data-ttu-id="07774-130">A habilitação de um gatilho DDL faz com que ele seja acionado da mesma maneira que era ao ser criado originalmente.</span><span class="sxs-lookup"><span data-stu-id="07774-130">Enabling a DDL trigger causes it to fire in the same way the trigger did when it was originally created.</span></span> <span data-ttu-id="07774-131">Quando os gatilhos DDL são criados, eles são habilitados por padrão.</span><span class="sxs-lookup"><span data-stu-id="07774-131">When DDL triggers are created, they are enabled by default.</span></span>  
  
 <span data-ttu-id="07774-132">Quando um gatilho DDL é excluído, ele é cancelado do banco de dados atual.</span><span class="sxs-lookup"><span data-stu-id="07774-132">When a DDL trigger is deleted, it is dropped from the current database.</span></span> <span data-ttu-id="07774-133">Quaisquer objetos ou dados que servem de escopo para o gatilho DDL não são afetados.</span><span class="sxs-lookup"><span data-stu-id="07774-133">Any objects or data upon which the DDL trigger is scoped are not affected.</span></span>  
  
 <span data-ttu-id="07774-134">**Para desabilitar um gatilho DDL**</span><span class="sxs-lookup"><span data-stu-id="07774-134">**To disable a DDL trigger**</span></span>  
  
-   [<span data-ttu-id="07774-135">DISABLE TRIGGER &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="07774-135">DISABLE TRIGGER &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/disable-trigger-transact-sql)  
  
-   [<span data-ttu-id="07774-136">ALTER TABLE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="07774-136">ALTER TABLE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-table-transact-sql)  
  
 <span data-ttu-id="07774-137">**Para habilitar um gatilho DDL**</span><span class="sxs-lookup"><span data-stu-id="07774-137">**To enable a DDL trigger**</span></span>  
  
-   [<span data-ttu-id="07774-138">ENABLE TRIGGER &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="07774-138">ENABLE TRIGGER &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/enable-trigger-transact-sql)  
  
-   [<span data-ttu-id="07774-139">ALTER TABLE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="07774-139">ALTER TABLE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-table-transact-sql)  
  
 <span data-ttu-id="07774-140">**Para excluir um gatilho DDL**</span><span class="sxs-lookup"><span data-stu-id="07774-140">**To delete a DDL trigger**</span></span>  
  
-   [<span data-ttu-id="07774-141">DROP TRIGGER &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="07774-141">DROP TRIGGER &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/drop-trigger-transact-sql)  
  
  
