---
title: Fazer failover manual de uma sessão de espelhamento de banco de dados (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- failover [SQL Server], database mirroring
- manual failover [SQL Server]
- database mirroring [SQL Server], failover
ms.assetid: 4ecf9c63-b3a4-4c54-b553-5bc37973232b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 7f7f4547058b2dfd4229142dca73a7d9b4bdb239
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685924"
---
# <a name="manually-fail-over-a-database-mirroring-session-sql-server-management-studio"></a><span data-ttu-id="31da4-102">Realizar failover manualmente de uma sessão de espelhamento de banco de dados (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="31da4-102">Manually Fail Over a Database Mirroring Session (SQL Server Management Studio)</span></span>
  <span data-ttu-id="31da4-103">Quando o banco de dados espelho for sincronizado (ou seja, quando o banco de dados estiver no estado SYNCHRONIZED), o proprietário do banco de dados poderá iniciar failover manual para o servidor espelho.</span><span class="sxs-lookup"><span data-stu-id="31da4-103">When the mirrored database is synchronized (that is, when the database is in the SYNCHRONIZED state), the database owner can initiate manual failover to the mirror server.</span></span>  
  
 <span data-ttu-id="31da4-104">Durante um failover manual, as funções do servidor principal e espelho são trocadas para o banco de dados no qual ocorre o failover.</span><span class="sxs-lookup"><span data-stu-id="31da4-104">During a manual failover, the principal and mirror server roles are swapped for the database on which the failover occurs.</span></span> <span data-ttu-id="31da4-105">O banco de dados espelho torna-se o banco de dados principal, o espelho.</span><span class="sxs-lookup"><span data-stu-id="31da4-105">The mirror database becomes the principal database and the principal database becomes the mirror.</span></span> <span data-ttu-id="31da4-106">Por exemplo, a tabela a seguir mostra como um failover manual troca as funções de dois parceiros de espelhamento: `SQLDBENGINE0_1` e `SQLDBENGINE0_2`.</span><span class="sxs-lookup"><span data-stu-id="31da4-106">For example, the following table shows the how a manual failover swaps the roles of two mirroring partners: `SQLDBENGINE0_1` and `SQLDBENGINE0_2`.</span></span>  
  
|<span data-ttu-id="31da4-107">Servidor</span><span class="sxs-lookup"><span data-stu-id="31da4-107">Server</span></span>|<span data-ttu-id="31da4-108">Antes do failover</span><span class="sxs-lookup"><span data-stu-id="31da4-108">Before failover</span></span>|<span data-ttu-id="31da4-109">Depois do failover</span><span class="sxs-lookup"><span data-stu-id="31da4-109">After failover</span></span>|  
|------------|---------------------|--------------------|  
|`SQLDBENGINE0_1`|<span data-ttu-id="31da4-110">PRINCIPAL</span><span class="sxs-lookup"><span data-stu-id="31da4-110">PRINCIPAL</span></span>|<span data-ttu-id="31da4-111">MIRROR</span><span class="sxs-lookup"><span data-stu-id="31da4-111">MIRROR</span></span>|  
|`SQLDBENGINE0_2`|<span data-ttu-id="31da4-112">MIRROR</span><span class="sxs-lookup"><span data-stu-id="31da4-112">MIRROR</span></span>|<span data-ttu-id="31da4-113">PRINCIPAL</span><span class="sxs-lookup"><span data-stu-id="31da4-113">PRINCIPAL</span></span>|  
  
 <span data-ttu-id="31da4-114">Observe que as funções do servidor para outras sessões de espelhamento de banco de dados não são afetadas.</span><span class="sxs-lookup"><span data-stu-id="31da4-114">Note that the server roles for other database mirroring sessions are not affected.</span></span> <span data-ttu-id="31da4-115">Para obter mais informações, consulte [Troca de função durante uma sessão de espelhamento de banco de dados &#40;SQL Server&#41;](role-switching-during-a-database-mirroring-session-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="31da4-115">For more information, see [Role Switching During a Database Mirroring Session &#40;SQL Server&#41;](role-switching-during-a-database-mirroring-session-sql-server.md).</span></span>  
  
### <a name="to-manually-fail-over-database-mirroring"></a><span data-ttu-id="31da4-116">Para realizar failover manualmente de espelhamento de banco de dados</span><span class="sxs-lookup"><span data-stu-id="31da4-116">To manually fail over database mirroring</span></span>  
  
1.  <span data-ttu-id="31da4-117">Conecte-se à instância do servidor principal e, no painel **Pesquisador de Objetos** , clique no nome do servidor para expandir a árvore do servidor.</span><span class="sxs-lookup"><span data-stu-id="31da4-117">Connect to the principal server instance and, in the **Object Explorer** pane, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="31da4-118">Expanda os **Bancos de Dados**e selecione o banco de dados a receber o failover.</span><span class="sxs-lookup"><span data-stu-id="31da4-118">Expand **Databases**, and select the database to be failed over.</span></span>  
  
3.  <span data-ttu-id="31da4-119">Clique com o botão direito do mouse no banco de dados, selecione **Tarefas**e clique em **Espelhar**.</span><span class="sxs-lookup"><span data-stu-id="31da4-119">Right-click the database, select **Tasks**, and then click **Mirror**.</span></span> <span data-ttu-id="31da4-120">Isso abre a página **Espelhamento** da caixa de diálogo **Propriedades do Banco de Dados** .</span><span class="sxs-lookup"><span data-stu-id="31da4-120">This opens the **Mirroring** page of the **Database Properties** dialog box.</span></span>  
  
4.  <span data-ttu-id="31da4-121">Clique em **Failover**.</span><span class="sxs-lookup"><span data-stu-id="31da4-121">Click **Failover**.</span></span>  
  
     <span data-ttu-id="31da4-122">Uma caixa de confirmação é exibida.</span><span class="sxs-lookup"><span data-stu-id="31da4-122">A confirmation box appears.</span></span>  <span data-ttu-id="31da4-123">O servidor principal começa tentando conectar-se ao servidor espelho usando a Autenticação do Windows.</span><span class="sxs-lookup"><span data-stu-id="31da4-123">The principal server begins by trying to connect to the mirror server by using Windows Authentication.</span></span> <span data-ttu-id="31da4-124">Se a Autenticação do Windows não funcionar, o servidor principal exibirá a caixa de diálogo **Conectar-se ao Servidor** .</span><span class="sxs-lookup"><span data-stu-id="31da4-124">If Windows Authentication does not work, the principal server displays the **Connect to Server** dialog box.</span></span> <span data-ttu-id="31da4-125">Se o servidor espelho usar a Autenticação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , selecione **Autenticação do SQL Server** na caixa **Autenticação** .</span><span class="sxs-lookup"><span data-stu-id="31da4-125">If the mirror server uses [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication, select **SQL Server Authentication** in the **Authentication** box.</span></span> <span data-ttu-id="31da4-126">Na caixa de texto **Logon** , especifique a conta de logon com a qual você se conectará no servidor espelho e, na caixa de texto **Senha** , especifique a senha da conta.</span><span class="sxs-lookup"><span data-stu-id="31da4-126">In the **Login** text box, specify the login account to connect with on the mirror server, and in the **Password** text box, specify the password for that account.</span></span>  
  
     <span data-ttu-id="31da4-127">Se o failover for bem-sucedido, a caixa de diálogo **Propriedades do Banco de Dados** será fechada.</span><span class="sxs-lookup"><span data-stu-id="31da4-127">If failover succeeds, the **Database Properties** dialog box closes.</span></span> <span data-ttu-id="31da4-128">O banco de dados espelho torna-se o banco de dados principal, o espelho.</span><span class="sxs-lookup"><span data-stu-id="31da4-128">The mirror database becomes the principal database and the principal database becomes the mirror.</span></span>  
  
     <span data-ttu-id="31da4-129">Se o failover falhar, uma mensagem de erro será exibida e a caixa de diálogo permanecerá aberta.</span><span class="sxs-lookup"><span data-stu-id="31da4-129">If failover fails, an error message is displayed and the dialog box remains open.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="31da4-130">Se você modificou qualquer propriedade desde que abriu a página **Espelhamento** , essas alterações não serão salvas.</span><span class="sxs-lookup"><span data-stu-id="31da4-130">If you have modified any properties since opening the **Mirroring** page, those changes will not be saved.</span></span>  
  
     <span data-ttu-id="31da4-131">A caixa de diálogo é fechada automaticamente.</span><span class="sxs-lookup"><span data-stu-id="31da4-131">The dialog box closes automatically.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31da4-132">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="31da4-132">See Also</span></span>  
 <span data-ttu-id="31da4-133">[Propriedades do banco de dados &#40;página Espelhamento&#41;](../../relational-databases/databases/database-properties-mirroring-page.md) </span><span class="sxs-lookup"><span data-stu-id="31da4-133">[Database Properties &#40;Mirroring Page&#41;](../../relational-databases/databases/database-properties-mirroring-page.md) </span></span>  
 <span data-ttu-id="31da4-134">[Espelhamento de banco de dados &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="31da4-134">[Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span></span>  
 <span data-ttu-id="31da4-135">[Fazer failover manual de uma sessão de espelhamento de banco de dados &#40;Transact-SQL&#41;](manually-fail-over-a-database-mirroring-session-transact-sql.md) </span><span class="sxs-lookup"><span data-stu-id="31da4-135">[Manually Fail Over a Database Mirroring Session &#40;Transact-SQL&#41;](manually-fail-over-a-database-mirroring-session-transact-sql.md) </span></span>  
 <span data-ttu-id="31da4-136">[Pausar ou retomar uma sessão de espelhamento de banco de dados &#40;SQL Server&#41;](pause-or-resume-a-database-mirroring-session-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="31da4-136">[Pause or Resume a Database Mirroring Session &#40;SQL Server&#41;](pause-or-resume-a-database-mirroring-session-sql-server.md) </span></span>  
 [<span data-ttu-id="31da4-137">Remover o espelhamento de banco de dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="31da4-137">Remove Database Mirroring &#40;SQL Server&#41;</span></span>](remove-database-mirroring-sql-server.md)  
  
  
