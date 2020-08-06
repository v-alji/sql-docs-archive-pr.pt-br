---
title: Hierarquia de permissões (Mecanismo de Banco de Dados) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- sql12.swb.server.permissions.f1--May use common.permissions
helpviewer_keywords:
- security [SQL Server], denying access
- hierarchies [SQL Server], permissions
- securables [SQL Server]
- security [SQL Server], permissions
- permissions [SQL Server], hierarchy
- security [SQL Server], granting access
ms.assetid: f6d20a55-ef03-4e14-85f9-009902889866
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 9a04e5595e509de63b362b31b240e113e635581d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679803"
---
# <a name="permissions-hierarchy-database-engine"></a><span data-ttu-id="98780-102">Hierarquia de permissões (Mecanismo de Banco de Dados)</span><span class="sxs-lookup"><span data-stu-id="98780-102">Permissions Hierarchy (Database Engine)</span></span>
  <span data-ttu-id="98780-103">O [!INCLUDE[ssDE](../../../includes/ssde-md.md)] gerencia uma coleção hierárquica de entidades que podem ser protegidas com permissões.</span><span class="sxs-lookup"><span data-stu-id="98780-103">The [!INCLUDE[ssDE](../../../includes/ssde-md.md)] manages a hierarchical collection of entities that can be secured with permissions.</span></span> <span data-ttu-id="98780-104">Essas entidades são conhecidas como *protegíveis*.</span><span class="sxs-lookup"><span data-stu-id="98780-104">These entities are known as *securables*.</span></span> <span data-ttu-id="98780-105">Os protegíveis mais proeminentes são servidores e bancos de dados, mas podem ser definidas permissões discretas em um nível muito mais específico.</span><span class="sxs-lookup"><span data-stu-id="98780-105">The most prominent securables are servers and databases, but discrete permissions can be set at a much finer level.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="98780-106">regula as ações de entidades de segurança em protegíveis verificando se as permissões apropriadas foram concedidas.</span><span class="sxs-lookup"><span data-stu-id="98780-106">regulates the actions of principals on securables by verifying that they have been granted appropriate permissions.</span></span>

 <span data-ttu-id="98780-107">A ilustração a seguir mostra todas as relações entre as hierarquias de permissões do [!INCLUDE[ssDE](../../../includes/ssde-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="98780-107">The following illustration shows the relationships among the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] permissions hierarchies.</span></span>

 <span data-ttu-id="98780-108">![Diagrama de hierarquias de permissões do Mecanismo de Banco de Dados](../../database-engine/media/wj-security-layers.gif "Diagrama de hierarquias de permissões do Mecanismo de Banco de Dados")</span><span class="sxs-lookup"><span data-stu-id="98780-108">![Diagram of Database Engine permissions hierarchies](../../database-engine/media/wj-security-layers.gif "Diagram of Database Engine permissions hierarchies")</span></span>

## <a name="chart-of-sql-server-permissions"></a><span data-ttu-id="98780-109">Gráfico de permissões do SQL Server</span><span class="sxs-lookup"><span data-stu-id="98780-109">Chart of SQL Server Permissions</span></span>
 <span data-ttu-id="98780-110">Para obter um gráfico com tamanho de um cartaz de todas as permissões do [!INCLUDE[ssDE](../../../includes/ssde-md.md)] em formato pdf, consulte [https://github.com/microsoft/sql-server-samples/blob/master/samples/features/security/permissions-posters/Microsoft_SQL_Server_2017_and_Azure_SQL_Database_permissions_infographic.pdf](https://github.com/microsoft/sql-server-samples/blob/master/samples/features/security/permissions-posters/Microsoft_SQL_Server_2017_and_Azure_SQL_Database_permissions_infographic.pdf).</span><span class="sxs-lookup"><span data-stu-id="98780-110">For a poster sized chart of all [!INCLUDE[ssDE](../../../includes/ssde-md.md)] permissions in pdf format, see [https://github.com/microsoft/sql-server-samples/blob/master/samples/features/security/permissions-posters/Microsoft_SQL_Server_2017_and_Azure_SQL_Database_permissions_infographic.pdf](https://github.com/microsoft/sql-server-samples/blob/master/samples/features/security/permissions-posters/Microsoft_SQL_Server_2017_and_Azure_SQL_Database_permissions_infographic.pdf).</span></span>

## <a name="working-with-permissions"></a><span data-ttu-id="98780-111">Trabalhando com permissões</span><span class="sxs-lookup"><span data-stu-id="98780-111">Working with Permissions</span></span>
 <span data-ttu-id="98780-112">As permissões podem ser manipuladas com as conhecidas consultas [!INCLUDE[tsql](../../includes/tsql-md.md)] GRANT, DENY e REVOKE.</span><span class="sxs-lookup"><span data-stu-id="98780-112">Permissions can be manipulated with the familiar [!INCLUDE[tsql](../../includes/tsql-md.md)] queries GRANT, DENY, and REVOKE.</span></span> <span data-ttu-id="98780-113">Informações sobre permissões são visíveis nas exibições de catálogo [sys.server_permissions](/sql/relational-databases/system-catalog-views/sys-server-permissions-transact-sql) e [sys.database_permissions](/sql/relational-databases/system-catalog-views/sys-database-permissions-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="98780-113">Information about permissions is visible in the [sys.server_permissions](/sql/relational-databases/system-catalog-views/sys-server-permissions-transact-sql) and [sys.database_permissions](/sql/relational-databases/system-catalog-views/sys-database-permissions-transact-sql) catalog views.</span></span> <span data-ttu-id="98780-114">Há também suporte para informações de permissões de consulta usando funções internas.</span><span class="sxs-lookup"><span data-stu-id="98780-114">There is also support for querying permissions information by using built-in functions.</span></span>

## <a name="see-also"></a><span data-ttu-id="98780-115">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="98780-115">See Also</span></span>
 <span data-ttu-id="98780-116">[Protegendo SQL Server](securing-sql-server.md) [permissões &#40;mecanismo de banco de dados&#41;as](permissions-database-engine.md) [Securables](securables.md) [entidades protegíveis &#40;](authentication-access/principals-database-engine.md) mecanismo de banco de dados&#41;[conceder &#40;o TRANSACT-](/sql/t-sql/statements/grant-transact-sql) sql&#41;[revogar &#40;Transact-SQL&#41;](/sql/t-sql/statements/revoke-transact-sql) [negar &#40;transact-SQL&#41;](/sql/t-sql/statements/deny-transact-sql) HAS_PERMS_BY_NAME &#40;o [transact](/sql/t-sql/functions/has-perms-by-name-transact-sql) -SQL&#41;[Sys. fn_builtin_permissions](/sql/relational-databases/system-functions/sys-fn-builtin-permissions-transact-sql) &#40;Transact-SQL&#41;[Sys. server_permissions &#40;Transact-SQL](/sql/relational-databases/system-catalog-views/sys-server-permissions-transact-sql)&#41;sys [. database_permissions &#40;Transact-](/sql/relational-databases/system-catalog-views/sys-database-permissions-transact-sql) SQL</span><span class="sxs-lookup"><span data-stu-id="98780-116">[Securing SQL Server](securing-sql-server.md) [Permissions &#40;Database Engine&#41;](permissions-database-engine.md) [Securables](securables.md) [Principals &#40;Database Engine&#41;](authentication-access/principals-database-engine.md) [GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql) [REVOKE &#40;Transact-SQL&#41;](/sql/t-sql/statements/revoke-transact-sql) [DENY &#40;Transact-SQL&#41;](/sql/t-sql/statements/deny-transact-sql) [HAS_PERMS_BY_NAME &#40;Transact-SQL&#41;](/sql/t-sql/functions/has-perms-by-name-transact-sql) [sys.fn_builtin_permissions &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-builtin-permissions-transact-sql) [sys.server_permissions &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-permissions-transact-sql) [sys.database_permissions &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-permissions-transact-sql)</span></span>


