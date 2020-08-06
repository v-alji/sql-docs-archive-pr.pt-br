---
title: Concedendo acesso a um objeto de banco de dados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- granting access to database objects
ms.assetid: a44d9bbf-f58e-4734-b7f4-eb3b492b777b
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 22bd0bb1f01e59ec30f7cf1bbf128c890d3d5d64
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582718"
---
# <a name="granting-access-to-a-database-object"></a><span data-ttu-id="54ae5-102">concedendo acesso a um objeto de banco de dados</span><span class="sxs-lookup"><span data-stu-id="54ae5-102">Granting Access to a Database Object</span></span>
  <span data-ttu-id="54ae5-103">Como administrador, você pode executar SELECT na tabela **Produtos** e na exibição **vw_Names**, além de executar o procedimento **pr_Names**; no entanto, Marina não pode.</span><span class="sxs-lookup"><span data-stu-id="54ae5-103">As an administrator, you can execute the SELECT from the **Products** table and the **vw_Names** view, and execute the **pr_Names** procedure; however, Mary cannot.</span></span> <span data-ttu-id="54ae5-104">Para conceder as permissões necessárias à Mary, use a instrução GRANT.</span><span class="sxs-lookup"><span data-stu-id="54ae5-104">To grant Mary the necessary permissions, use the GRANT statement.</span></span>  
  
### <a name="procedure-title"></a><span data-ttu-id="54ae5-105">Título do procedimento</span><span class="sxs-lookup"><span data-stu-id="54ae5-105">Procedure Title</span></span>  
  
1.  <span data-ttu-id="54ae5-106">Execute a instrução a seguir para conceder a `Mary` a permissão `EXECUTE` para o procedimento armazenado `pr_Names` .</span><span class="sxs-lookup"><span data-stu-id="54ae5-106">Execute the following statement to give `Mary` the `EXECUTE` permission for the `pr_Names` stored procedure.</span></span>  
  
    ```  
    GRANT EXECUTE ON pr_Names TO Mary;  
    GO  
    ```  
  
 <span data-ttu-id="54ae5-107">Nesse cenário, Mary pode acessar apenas a tabela **Products** usando o procedimento armazenado.</span><span class="sxs-lookup"><span data-stu-id="54ae5-107">In this scenario, Mary can only access the **Products** table by using the stored procedure.</span></span> <span data-ttu-id="54ae5-108">Para que Mary possa executar a instrução SELECT na exibição, você também deve executar `GRANT SELECT ON vw_Names TO Mary`.</span><span class="sxs-lookup"><span data-stu-id="54ae5-108">If you want Mary to be able to execute a SELECT statement against the view, then you must also execute `GRANT SELECT ON vw_Names TO Mary`.</span></span> <span data-ttu-id="54ae5-109">Para remover acesso a objetos de banco de dados, use a instrução REVOKE.</span><span class="sxs-lookup"><span data-stu-id="54ae5-109">To remove access to database objects, use the REVOKE statement.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="54ae5-110">Se a tabela, a exibição e o procedimento armazenado não pertencerem ao mesmo esquema, a concessão de permissões ficará mais complexa.</span><span class="sxs-lookup"><span data-stu-id="54ae5-110">If the table, the view, and the stored procedure are not owned by the same schema, granting permissions becomes more complex.</span></span>  
  
## <a name="about-grant"></a><span data-ttu-id="54ae5-111">Sobre GRANT</span><span class="sxs-lookup"><span data-stu-id="54ae5-111">About GRANT</span></span>  
 <span data-ttu-id="54ae5-112">É preciso ter permissão EXECUTE para executar um procedimento armazenado.</span><span class="sxs-lookup"><span data-stu-id="54ae5-112">You must have EXECUTE permission to execute a stored procedure.</span></span> <span data-ttu-id="54ae5-113">É preciso ter permissões SELECT, INSERT, UPDATE e DELETE para acessar e alterar dados.</span><span class="sxs-lookup"><span data-stu-id="54ae5-113">You must have SELECT, INSERT, UPDATE, and DELETE permissions to access and change data.</span></span> <span data-ttu-id="54ae5-114">A instrução GRANT também é usada para outras permissões, como permissão para criar tabelas.</span><span class="sxs-lookup"><span data-stu-id="54ae5-114">The GRANT statement is also used for other permissions, such as permission to create tables.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="54ae5-115">Próxima tarefa da lição</span><span class="sxs-lookup"><span data-stu-id="54ae5-115">Next Task in Lesson</span></span>  
 [<span data-ttu-id="54ae5-116">resumo: configurando permissões em objetos de banco de dados</span><span class="sxs-lookup"><span data-stu-id="54ae5-116">Summary: Configuring Permissions on Database Objects</span></span>](lesson-2-5-summary-configuring-permissions-on-database-objects.md)  
  
## <a name="see-also"></a><span data-ttu-id="54ae5-117">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="54ae5-117">See Also</span></span>  
 <span data-ttu-id="54ae5-118">[GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="54ae5-118">[GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql) </span></span>  
 [<span data-ttu-id="54ae5-119">REVOKE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="54ae5-119">REVOKE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/revoke-transact-sql)  
  
  
