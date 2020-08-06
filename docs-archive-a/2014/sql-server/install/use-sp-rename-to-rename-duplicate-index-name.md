---
title: Usar sp_rename para renomear o nome de índice duplicado | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- table names [SQL Server]
- duplicate table names
- index names [SQL Server]
- sp_rename
- duplicate index names
ms.assetid: ee66c7a5-eb6d-4fcf-970c-ab099d78c8d9
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: b8ffe3b9befd0c7239d32094e5738e0fb2947c5a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87686027"
---
# <a name="use-sp_rename-to-rename-duplicate-index-name"></a><span data-ttu-id="b516d-102">Usar sp_rename para renomear o nome do índice duplicado</span><span class="sxs-lookup"><span data-stu-id="b516d-102">Use sp_rename to rename duplicate index name</span></span>
  <span data-ttu-id="b516d-103">O Supervisor de Atualização detectou nomes de índices de exibição ou de tabelas duplicados.</span><span class="sxs-lookup"><span data-stu-id="b516d-103">Upgrade Advisor has detected duplicate table or view index names.</span></span> <span data-ttu-id="b516d-104">Renomeie os índices para remover os nomes duplicados antes de atualizar.</span><span class="sxs-lookup"><span data-stu-id="b516d-104">Rename the indexes to remove duplicates before upgrading.</span></span>  
  
## <a name="component"></a><span data-ttu-id="b516d-105">Componente</span><span class="sxs-lookup"><span data-stu-id="b516d-105">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="corrective-action"></a><span data-ttu-id="b516d-106">Ação corretiva</span><span class="sxs-lookup"><span data-stu-id="b516d-106">Corrective Action</span></span>  
  
1.  <span data-ttu-id="b516d-107">Localize os índices duplicados executando a seguinte consulta:</span><span class="sxs-lookup"><span data-stu-id="b516d-107">Locate the duplicate indexes by executing the following query.</span></span>  
  
    ```  
    SELECT DISTINCT OBJECT_NAME(o.id), name  
    FROM sysindexes as o  
    WHERE EXISTS   
        (SELECT name FROM sysindexes  as i  
          WHERE i.id = o.id  
          AND i.name = o.name and i.indid < o.indid);  
    ```  
  
2.  <span data-ttu-id="b516d-108">Use **sp_rename** para alterar o nome de um dos índices.</span><span class="sxs-lookup"><span data-stu-id="b516d-108">Use **sp_rename** to change one of the index names.</span></span> <span data-ttu-id="b516d-109">Como os nomes dos índices são os mesmos, você não pode determinar qual índice será renomeado.</span><span class="sxs-lookup"><span data-stu-id="b516d-109">Because the index names are the same, you cannot determine which index will be renamed.</span></span> <span data-ttu-id="b516d-110">Esta etapa lhe permite diferenciar os índices.</span><span class="sxs-lookup"><span data-stu-id="b516d-110">This step allows you to differentiate the indexes.</span></span>  
  
    ```  
    EXEC sp_rename N'table_name.index_name', N'new_index_name', N'INDEX'  
    ```  
  
3.  <span data-ttu-id="b516d-111">Verifique qual índice foi renomeado executando a consulta a seguir.</span><span class="sxs-lookup"><span data-stu-id="b516d-111">Verify which index was renamed by executing the following query.</span></span> <span data-ttu-id="b516d-112">Essa consulta retorna todos os índices (inclusive nomes de coluna de chaves) na tabela ou exibição especificada.</span><span class="sxs-lookup"><span data-stu-id="b516d-112">This query returns all indexes (including key column names) on the specified table or view.</span></span>  
  
    ```  
    SELECT i.name AS IndexName, c.name AS ColumnName, ik.colid, ik.keyno  
    FROM sysindexes i  
    JOIN sysindexkeys ik ON i.id = ik.id and i.indid = ik.indid   
    JOIN syscolumns c ON c.id = ik.id and ik.colid = c.colid  
    WHERE i.id = OBJECT_ID('table_or_view_name')  
    ```  
  
4.  <span data-ttu-id="b516d-113">Se necessário, use **sp_rename** novamente para corrigir os nomes de índices.</span><span class="sxs-lookup"><span data-stu-id="b516d-113">If necessary, use **sp_rename** again to correct the index names.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b516d-114">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b516d-114">See Also</span></span>  
 <span data-ttu-id="b516d-115">[Problemas de atualização do Mecanismo de Banco de Dados](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="b516d-115">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="b516d-116">Supervisor de atualização do SQL Server 2014 &#91;novo&#93;</span><span class="sxs-lookup"><span data-stu-id="b516d-116">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
