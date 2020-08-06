---
title: Funções definidas pelo usuário não são permitidas em system_function_schema | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- system functions [SQL Server]
- user-defined functions [SQL Server], system
ms.assetid: 3cb54053-ef65-4558-ae96-8686b6b22f4f
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 7242f9fda74288a2b7354ac0550ff4966e05c555
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87686026"
---
# <a name="user-defined-functions-are-not-allowed-in-system_function_schema"></a><span data-ttu-id="b418d-102">Funções definidas pelo usuário não são permitidas no system_function_schema</span><span class="sxs-lookup"><span data-stu-id="b418d-102">User-defined functions are not allowed in system_function_schema</span></span>
  <span data-ttu-id="b418d-103">O supervisor de atualização detectou funções definidas pelo usuário que são de Propriedade do usuário não documentado **system_function_schema**.</span><span class="sxs-lookup"><span data-stu-id="b418d-103">The Upgrade Advisor detected user-defined functions that are owned by the undocumented user **system_function_schema**.</span></span> <span data-ttu-id="b418d-104">Você não pode criar uma função de sistema definida pelo usuário especificando esse usuário.</span><span class="sxs-lookup"><span data-stu-id="b418d-104">You cannot create a user-defined system function by specifying this user.</span></span> <span data-ttu-id="b418d-105">O nome de usuário **system_function_schema** não existe e a ID de usuário que está associada a esse nome (UID = 4) é reservada para o esquema **Sys** e é restrita somente ao uso interno.</span><span class="sxs-lookup"><span data-stu-id="b418d-105">The **system_function_schema** user name does not exist, and the user ID that is associated with this name (UID = 4) is reserved for the **sys** schema and is restricted to internal use only.</span></span>  
  
## <a name="component"></a><span data-ttu-id="b418d-106">Componente</span><span class="sxs-lookup"><span data-stu-id="b418d-106">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="b418d-107">Descrição</span><span class="sxs-lookup"><span data-stu-id="b418d-107">Description</span></span>  
 <span data-ttu-id="b418d-108">O armazenamento de objeto de sistema mudou da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="b418d-108">System object storage and access has changed in the following ways:</span></span>  
  
-   <span data-ttu-id="b418d-109">Os objetos do sistema são armazenados no banco de dados de **recursos** somente leitura e as atualizações diretas do objeto do sistema não são permitidas.</span><span class="sxs-lookup"><span data-stu-id="b418d-109">System objects are stored in the read-only **Resource** database, and direct system object updates are not permitted.</span></span>  
  
     <span data-ttu-id="b418d-110">Os objetos do sistema aparecem logicamente no esquema **Sys** de cada banco de dados.</span><span class="sxs-lookup"><span data-stu-id="b418d-110">System objects logically appear in the **sys** schema of every database.</span></span> <span data-ttu-id="b418d-111">Isso mantém a habilidade para invocar funções de sistema de qualquer banco de dados especificando um nome de função de uma parte.</span><span class="sxs-lookup"><span data-stu-id="b418d-111">This maintains the ability to invoke system functions from any database by specifying a one-part function name.</span></span> <span data-ttu-id="b418d-112">Por exemplo, a instrução `SELECT * FROM fn_helpcollations()` pode ser executada de qualquer banco de dados.</span><span class="sxs-lookup"><span data-stu-id="b418d-112">For example, the statement `SELECT * FROM fn_helpcollations()` can be run from any database.</span></span>  
  
-   <span data-ttu-id="b418d-113">A **system_function_schema** de usuário não documentada foi removida.</span><span class="sxs-lookup"><span data-stu-id="b418d-113">The undocumented user **system_function_schema** has been removed.</span></span>  
  
-   <span data-ttu-id="b418d-114">A ID de usuário associada a **system_function_schema** (UID = 4) é reservada para o esquema **Sys** e é restrita somente ao uso interno.</span><span class="sxs-lookup"><span data-stu-id="b418d-114">The user ID associated with **system_function_schema** (UID = 4) is reserved for the **sys** schema and is restricted to internal use only.</span></span>  
  
 <span data-ttu-id="b418d-115">Essas alterações têm o seguinte efeito em funções de sistema definidas pelo usuário:</span><span class="sxs-lookup"><span data-stu-id="b418d-115">These changes have the following effect on user-defined system functions:</span></span>  
  
-   <span data-ttu-id="b418d-116">Instruções DDL (linguagem de definição de dados) que fazem referência a **system_function_schema** falharão.</span><span class="sxs-lookup"><span data-stu-id="b418d-116">Data Definition Language (DDL) statements that reference **system_function_schema** will fail.</span></span> <span data-ttu-id="b418d-117">Por exemplo, a instrução `CREATE FUNCTION system` _ `function` \_ `schema.fn` \_ `MySystemFunction` ... Não terá sucesso.</span><span class="sxs-lookup"><span data-stu-id="b418d-117">For example, the statement `CREATE FUNCTION system`_`function`\_`schema.fn`\_`MySystemFunction` ... will not succeed.</span></span>  
  
-   <span data-ttu-id="b418d-118">Depois de atualizar para o [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] , os objetos existentes que pertencem a **system_function_schema** estão contidos apenas no esquema **Sys** do banco de dados **mestre** .</span><span class="sxs-lookup"><span data-stu-id="b418d-118">After you upgrade to [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], existing objects that are owned by **system_function_schema** are contained only in the **sys** schema of the **master** database.</span></span> <span data-ttu-id="b418d-119">Como os objetos do sistema não podem ser modificados, essas funções nunca podem ser alteradas ou removidas do banco de dados **mestre** .</span><span class="sxs-lookup"><span data-stu-id="b418d-119">Because system objects cannot be modified, these functions can never be changed or dropped from the **master** database.</span></span> <span data-ttu-id="b418d-120">Além disso, essas funções não podem ser invocadas a partir de outros bancos de dados pela especificação apenas de um nome de função de uma parte.</span><span class="sxs-lookup"><span data-stu-id="b418d-120">Additionally, these functions cannot be invoked from other databases by specifying only a one-part function name.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="b418d-121">Ação corretiva</span><span class="sxs-lookup"><span data-stu-id="b418d-121">Corrective Action</span></span>  
 <span data-ttu-id="b418d-122">Antes da atualização, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="b418d-122">Before you upgrade , complete the following tasks:</span></span>  
  
1.  <span data-ttu-id="b418d-123">Altere a propriedade das funções definidas pelo usuário existentes para **dbo** usando o procedimento armazenado do sistema **sp_changeobjectowner** .</span><span class="sxs-lookup"><span data-stu-id="b418d-123">Change the ownership of existing user-defined functions to **dbo** by using the **sp_changeobjectowner** system stored procedure.</span></span>  
  
2.  <span data-ttu-id="b418d-124">Considere renomear a função de forma que ela não use o prefixo ‘fn_’.</span><span class="sxs-lookup"><span data-stu-id="b418d-124">Consider renaming the function so that is does not use the prefix 'fn_'.</span></span> <span data-ttu-id="b418d-125">Isso evitará potenciais conflitos de nome com atuais ou futuras funções de sistema.</span><span class="sxs-lookup"><span data-stu-id="b418d-125">This will avoid potential name conflicts with current or future system functions.</span></span>  
  
3.  <span data-ttu-id="b418d-126">Adicione uma cópia das funções modificadas a todos os bancos de dados que as usam.</span><span class="sxs-lookup"><span data-stu-id="b418d-126">Add a copy of the modified functions in every database that uses them.</span></span>  
  
4.  <span data-ttu-id="b418d-127">Substitua referências a **system_function_schema** com **dbo** em todos os scripts que contêm instruções DDL da função definida pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="b418d-127">Replace references to **system_function_schema** with **dbo** in all scripts that contain user-defined function DDL statements.</span></span>  
  
5.  <span data-ttu-id="b418d-128">Modifique os scripts que chamam essas funções para usar o nome dbo de duas partes **.** _function_name_ou o nome de três partes _database_name_**.** dbo. *function_name*.</span><span class="sxs-lookup"><span data-stu-id="b418d-128">Modify scripts that invoke these functions to use either the two-part name dbo **.**_function_name_, or the three-part name _database_name_**.** dbo.*function_name*.</span></span>  
  
 <span data-ttu-id="b418d-129">Para obter mais informações, consulte os seguintes tópicos dos Manuais Online do SQL Server:</span><span class="sxs-lookup"><span data-stu-id="b418d-129">For more information, see the following topics in SQL Server Books Online:</span></span>  
  
-   <span data-ttu-id="b418d-130">‘sp_changeobjectowner’</span><span class="sxs-lookup"><span data-stu-id="b418d-130">"sp_changeobjectowner"</span></span>  
  
-   <span data-ttu-id="b418d-131">‘Separação do esquema de usuário’</span><span class="sxs-lookup"><span data-stu-id="b418d-131">"User-schema Separation"</span></span>  
  
-   <span data-ttu-id="b418d-132">‘Banco de dados Recurso’</span><span class="sxs-lookup"><span data-stu-id="b418d-132">"Resource Database"</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b418d-133">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b418d-133">See Also</span></span>  
 <span data-ttu-id="b418d-134">[Supervisor de atualização do SQL Server 2014 &#91;novo&#93;](sql-server-2014-upgrade-advisor.md) </span><span class="sxs-lookup"><span data-stu-id="b418d-134">[SQL Server 2014 Upgrade Advisor &#91;new&#93;](sql-server-2014-upgrade-advisor.md) </span></span>  
 <span data-ttu-id="b418d-135">[Problemas de atualização do Mecanismo de Banco de Dados](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="b418d-135">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 <span data-ttu-id="b418d-136">[Remover instruções que modificam objetos do sistema](../../../2014/sql-server/install/remove-statements-that-modify-system-objects.md) </span><span class="sxs-lookup"><span data-stu-id="b418d-136">[Remove statements that modify system objects](../../../2014/sql-server/install/remove-statements-that-modify-system-objects.md) </span></span>  
 [<span data-ttu-id="b418d-137">Remover instruções que descartam objetos do sistema</span><span class="sxs-lookup"><span data-stu-id="b418d-137">Remove statements that drop system objects</span></span>](../../../2014/sql-server/install/remove-statements-that-drop-system-objects.md)  
  
  
