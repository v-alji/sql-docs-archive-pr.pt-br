---
title: Configurar um banco de dados espelho para usar a propriedade confiável (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- TRUSTWORTHY database option
- mirror database [SQL Server]
- database mirroring [SQL Server], security
ms.assetid: 6993b076-78ef-453e-b0ea-e341b8e5ee3e
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 6cd46a08037bcb6eee178a96d84bdab358e5350d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681140"
---
# <a name="set-up-a-mirror-database-to-use-the-trustworthy-property-transact-sql"></a><span data-ttu-id="8409f-102">Configurar um banco de dados espelho para usar a propriedade confiável (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="8409f-102">Set Up a Mirror Database to Use the Trustworthy Property (Transact-SQL)</span></span>
  <span data-ttu-id="8409f-103">Quando é feito backup de um banco de dados, a propriedade TRUSTWORTHY do banco de dados é definida como OFF.</span><span class="sxs-lookup"><span data-stu-id="8409f-103">When a database is backed up, the TRUSTWORTHY database property is set to OFF.</span></span> <span data-ttu-id="8409f-104">Portanto, em um novo banco de dados espelho, TRUSTWORTHY está sempre OFF.</span><span class="sxs-lookup"><span data-stu-id="8409f-104">Therefore, on a new mirror database TRUSTWORTHY is always OFF.</span></span> <span data-ttu-id="8409f-105">Se o banco de dados precisar estar confiável após um failover, serão necessárias etapas adicionais de instalação após o início do espelhamento.</span><span class="sxs-lookup"><span data-stu-id="8409f-105">If the database needs to be trustworthy after a failover, extra setup steps are necessary after mirroring begins.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8409f-106">Para obter informações sobre essa propriedade de banco de dados, veja [propriedade TRUSTWORTHY do banco de dados](../../relational-databases/security/trustworthy-database-property.md).</span><span class="sxs-lookup"><span data-stu-id="8409f-106">For information about this database property, see [TRUSTWORTHY Database Property](../../relational-databases/security/trustworthy-database-property.md).</span></span>  
  
## <a name="procedure"></a><span data-ttu-id="8409f-107">Procedimento</span><span class="sxs-lookup"><span data-stu-id="8409f-107">Procedure</span></span>  
  
#### <a name="to-setup-a-mirror-database-to-use-the-trustworthy-property"></a><span data-ttu-id="8409f-108">Para configurar um banco de dados espelho para usar a Propriedade Trustworthy</span><span class="sxs-lookup"><span data-stu-id="8409f-108">To setup a mirror database to use the Trustworthy Property</span></span>  
  
1.  <span data-ttu-id="8409f-109">Na instância de servidor principal, verifique se o banco de dados principal está com a propriedade Trustworthy ativada.</span><span class="sxs-lookup"><span data-stu-id="8409f-109">On the principal server instance, verify that the principal database has the Trustworthy property turned on.</span></span>  
  
    ```  
    SELECT name, database_id, is_trustworthy_on FROM sys.databases   
    ```  
  
     <span data-ttu-id="8409f-110">Para obter mais informações, veja [sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="8409f-110">For more information, see [sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql).</span></span>  
  
2.  <span data-ttu-id="8409f-111">Depois de iniciar o espelhamento, verifique se o banco de dados é atualmente o banco de dados principal, se a sessão está usando um modo operacional síncrono e se a sessão já está sincronizada.</span><span class="sxs-lookup"><span data-stu-id="8409f-111">After starting mirroring, verify that the database is currently the principal database, the session is using a synchronous operating mode, and the session is already synchronized.</span></span>  
  
    ```  
    SELECT database_id, mirroring_role, mirroring_safety_level_desc, mirroring_state_desc FROM sys.database_mirroring  
    ```  
  
     <span data-ttu-id="8409f-112">Para obter mais informações, veja [sys.database_mirroring &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-mirroring-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="8409f-112">For more information, see [sys.database_mirroring &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-mirroring-transact-sql).</span></span>  
  
3.  <span data-ttu-id="8409f-113">Quando a sessão de espelhamento está sincronizada, faça o failover manualmente para o banco de dados espelho.</span><span class="sxs-lookup"><span data-stu-id="8409f-113">Once the mirroring session is synchronized, manually fail over to the mirror database.</span></span>  
  
     <span data-ttu-id="8409f-114">Isto pode ser feito no SQL Server Management Studio ou usando o Transact-SQL:</span><span class="sxs-lookup"><span data-stu-id="8409f-114">This can be done in either SQL Server Management Studio or using Transact-SQL:</span></span>  
  
    -   [<span data-ttu-id="8409f-115">Executar failover manualmente de uma sessão de espelhamento de banco de dados &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="8409f-115">Manually Fail Over a Database Mirroring Session &#40;SQL Server Management Studio&#41;</span></span>](manually-fail-over-a-database-mirroring-session-sql-server-management-studio.md)  
  
    -   [<span data-ttu-id="8409f-116">Executar failover manualmente em uma sessão de espelhamento de banco de dados &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="8409f-116">Manually Fail Over a Database Mirroring Session &#40;Transact-SQL&#41;</span></span>](manually-fail-over-a-database-mirroring-session-transact-sql.md)  
  
4.  <span data-ttu-id="8409f-117">Ative a propriedade de banco de dados confiável que usa o seguinte comando ALTER DATABASE:</span><span class="sxs-lookup"><span data-stu-id="8409f-117">Turn on the trustworthy database property using the following ALTER DATABASE command:</span></span>  
  
    ```  
    ALTER DATABASE <database_name> SET TRUSTWORTHY ON  
    ```  
  
     <span data-ttu-id="8409f-118">Para obter mais informações, veja [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="8409f-118">For more information, see[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql).</span></span>  
  
5.  <span data-ttu-id="8409f-119">Opcionalmente, faça novamente o failover manualmente para voltar ao principal original.</span><span class="sxs-lookup"><span data-stu-id="8409f-119">Optionally, manually failover again to return to the original principal.</span></span>  
  
6.  <span data-ttu-id="8409f-120">Opcionalmente, alterne para o modo assíncrono, de alto desempenho, definindo SAFETY como OFF e assegurando que WITNESS também esteja definido como OFF.</span><span class="sxs-lookup"><span data-stu-id="8409f-120">Optionally, switch to asynchronous, high-performance mode by setting SAFETY to OFF and ensuring that WITNESS is also set to OFF.</span></span>  
  
     <span data-ttu-id="8409f-121">No Transact-SQL:</span><span class="sxs-lookup"><span data-stu-id="8409f-121">In Transact-SQL:</span></span>  
  
    -   [<span data-ttu-id="8409f-122">Alterar a segurança da transação em uma sessão de espelhamento de banco de dados &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="8409f-122">Change Transaction Safety in a Database Mirroring Session &#40;Transact-SQL&#41;</span></span>](change-transaction-safety-in-a-database-mirroring-session-transact-sql.md)  
  
    -   [<span data-ttu-id="8409f-123">Remover a testemunha de uma sessão de espelhamento de banco de dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="8409f-123">Remove the Witness from a Database Mirroring Session &#40;SQL Server&#41;</span></span>](remove-the-witness-from-a-database-mirroring-session-sql-server.md)  
  
     <span data-ttu-id="8409f-124">No SQL Server Management Studio:</span><span class="sxs-lookup"><span data-stu-id="8409f-124">In SQL Server Management Studio:</span></span>  
  
    -   [<span data-ttu-id="8409f-125">Estabelecer uma sessão de espelhamento de banco de dados usando a Autenticação do Windows &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="8409f-125">Establish a Database Mirroring Session Using Windows Authentication &#40;SQL Server Management Studio&#41;</span></span>](establish-database-mirroring-session-windows-authentication.md)  
  
## <a name="see-also"></a><span data-ttu-id="8409f-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8409f-126">See Also</span></span>  
 <span data-ttu-id="8409f-127">[propriedade TRUSTWORTHY do banco de dados](../../relational-databases/security/trustworthy-database-property.md) </span><span class="sxs-lookup"><span data-stu-id="8409f-127">[TRUSTWORTHY Database Property](../../relational-databases/security/trustworthy-database-property.md) </span></span>  
 [<span data-ttu-id="8409f-128">Configurar um banco de dados espelho criptografado</span><span class="sxs-lookup"><span data-stu-id="8409f-128">Set Up an Encrypted Mirror Database</span></span>](set-up-an-encrypted-mirror-database.md)  
  
  
