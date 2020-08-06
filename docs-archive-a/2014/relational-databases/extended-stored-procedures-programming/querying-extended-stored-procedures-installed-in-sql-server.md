---
title: Consultando procedimentos armazenados estendidos instalados no SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- extended stored procedures [SQL Server], querying
ms.assetid: e02348e6-dba6-438a-98b6-684244bb034d
author: rothja
ms.author: jroth
ms.openlocfilehash: 3f44db9053ad18c3a6902a30aaab4f81610c5a8c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571401"
---
# <a name="querying-extended-stored-procedures-installed-in-sql-server"></a><span data-ttu-id="fe161-102">Consultando procedimentos armazenados estendidos no SQL Server</span><span class="sxs-lookup"><span data-stu-id="fe161-102">Querying Extended Stored Procedures Installed in SQL Server</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="fe161-103">Em vez disso, use a Integração CLR.</span><span class="sxs-lookup"><span data-stu-id="fe161-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="fe161-104">Um [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usuário autenticado pode exibir os procedimentos armazenados estendidos definidos no momento e o nome da dll à qual cada um pertence executando o procedimento do sistema **sp_helpextendedproc** .</span><span class="sxs-lookup"><span data-stu-id="fe161-104">A [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] authenticated user can display the currently defined extended stored procedures and the name of the DLL to which each belongs by running the **sp_helpextendedproc** system procedure.</span></span> <span data-ttu-id="fe161-105">Por exemplo, o exemplo a seguir retorna a DLL à qual **xp_hello** pertence:</span><span class="sxs-lookup"><span data-stu-id="fe161-105">For example, the following example returns the DLL to which **xp_hello** belongs:</span></span>  
  
```  
sp_helpextendedproc 'xp_hello'  
```  
  
 <span data-ttu-id="fe161-106">Se **sp_helpextendedproc** for executado sem especificar um procedimento armazenado estendido, todos os procedimentos armazenados estendidos e suas DLLs serão exibidos.</span><span class="sxs-lookup"><span data-stu-id="fe161-106">If **sp_helpextendedproc** is executed without specifying an extended stored procedure, all the extended stored procedures and their DLLs are displayed.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="fe161-107">Serão passadas informações de retorno apenas para os procedimentos armazenados estendidos de propriedade do usuário ou para os quais o usuário tenha permissão.</span><span class="sxs-lookup"><span data-stu-id="fe161-107">Information will be returned for only those extended stored procedures that the logged in user owns or has permissions to.</span></span> <span data-ttu-id="fe161-108">Somente os membros da função de servidor fixa **sysadmin** e o **db_owner**, **db_securityadmin**e as **db_ddladmin** funções de banco de dados fixas podem exibir informações de todos os procedimentos armazenados estendidos.</span><span class="sxs-lookup"><span data-stu-id="fe161-108">Only members of the **sysadmin** fixed server role and the **db_owner**, **db_securityadmin**, and the **db_ddladmin** fixed database roles can view information for all extended stored procedures.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe161-109">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="fe161-109">See Also</span></span>  
 <span data-ttu-id="fe161-110">[&#41;&#40;Transact-SQL de sp_helpextendedproc](/sql/relational-databases/system-stored-procedures/sp-helpextendedproc-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="fe161-110">[sp_helpextendedproc &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helpextendedproc-transact-sql) </span></span>  
 <span data-ttu-id="fe161-111">[&#41;&#40;Transact-SQL de sp_addextendedproc](/sql/relational-databases/system-stored-procedures/sp-addextendedproc-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="fe161-111">[sp_addextendedproc &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addextendedproc-transact-sql) </span></span>  
 [<span data-ttu-id="fe161-112">sp_dropextendedproc &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="fe161-112">sp_dropextendedproc &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-dropextendedproc-transact-sql)  
  
  
