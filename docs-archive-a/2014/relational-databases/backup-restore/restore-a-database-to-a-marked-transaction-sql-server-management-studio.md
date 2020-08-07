---
title: Restaurar um banco de dados para uma transação marcada (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
f1_keywords:
- sql12.swb.restoretlog.markedtransaction.f1
helpviewer_keywords:
- database restores [SQL Server], marked transactions
- restoring databases [SQL Server], marked transactions
- marked transactions [SQL Server], restoring
ms.assetid: 8f0ea144-1819-4832-905f-e5d0f49b066b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 8de9ef5bed389f020f14e60ccd99f39698e7110f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581414"
---
# <a name="restore-a-database-to-a-marked-transaction-sql-server-management-studio"></a><span data-ttu-id="14b91-102">Restaurar um banco de dados para uma transação marcada (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="14b91-102">Restore a Database to a Marked Transaction (SQL Server Management Studio)</span></span>
  <span data-ttu-id="14b91-103">Quando um banco de dados está no estado de restauração, é possível usar a caixa de diálogo **Restaurar Log de Transações** para restaurar o banco de dados para uma transação marcada nos backups de log disponíveis.</span><span class="sxs-lookup"><span data-stu-id="14b91-103">When a database is in the restoring state, you can use the **Restore Transaction Log** dialog box to restore the database to a marked transaction in the available log backups.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="14b91-104">Para obter mais informações, veja [Usar transações marcadas para recuperar bancos de dados relacionados de forma consistente &#40;Modelo de recuperação completa&#41;](use-marked-transactions-to-recover-related-databases-consistently.md) e [Recuperação de bancos de dados relacionados que contêm transação marcada](recovery-of-related-databases-that-contain-marked-transaction.md).</span><span class="sxs-lookup"><span data-stu-id="14b91-104">For more information, see [Use Marked Transactions to Recover Related Databases Consistently &#40;Full Recovery Model&#41;](use-marked-transactions-to-recover-related-databases-consistently.md) and [Recovery of Related  Databases That Contain Marked Transaction](recovery-of-related-databases-that-contain-marked-transaction.md).</span></span>  
  
### <a name="to-restore-a-marked-transaction"></a><span data-ttu-id="14b91-105">Para restaurar uma transação marcada</span><span class="sxs-lookup"><span data-stu-id="14b91-105">To restore a marked transaction</span></span>  
  
1.  <span data-ttu-id="14b91-106">Depois de se conectar à instância apropriada do [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], em Pesquisador de Objetos, clique no nome do servidor para expandir a árvore do servidor.</span><span class="sxs-lookup"><span data-stu-id="14b91-106">After connecting to the appropriate instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="14b91-107">Expanda **Bancos de Dados**e, dependendo do banco de dados, selecione um banco de dados de usuário ou expanda **Bancos de Dados do Sistema** e selecione um banco de dados do sistema.</span><span class="sxs-lookup"><span data-stu-id="14b91-107">Expand **Databases**, and, depending on the database, either select a user database or expand **System Databases** and select a system database.</span></span>  
  
3.  <span data-ttu-id="14b91-108">Clique com o botão direito do mouse no banco de dados, aponte para **Tarefas**e clique em **Restaurar**.</span><span class="sxs-lookup"><span data-stu-id="14b91-108">Right-click the database, point to **Tasks**, and then click **Restore**.</span></span>  
  
4.  <span data-ttu-id="14b91-109">Clique em **Log de Transações**, o que abrirá a caixa de diálogo **Restaurar Log de Transações** .</span><span class="sxs-lookup"><span data-stu-id="14b91-109">Click **Transaction Log**, which opens the **Restore Transaction Log** dialog box.</span></span>  
  
5.  <span data-ttu-id="14b91-110">Na página **Geral** , na seção **Restaurar para** , selecione **Transação marcada**, o que abrirá a caixa de diálogo **Selecionar Transação Marcada** .</span><span class="sxs-lookup"><span data-stu-id="14b91-110">On the **General** page, in the **Restore To** section, select **Marked transaction**, which opens the **Select Marked Transaction** dialog box.</span></span> <span data-ttu-id="14b91-111">Essa caixa de diálogo exibe uma grade que lista as transações marcadas disponíveis nos backups de log de transações selecionados.</span><span class="sxs-lookup"><span data-stu-id="14b91-111">This dialog box displays a grid listing the marked transactions available in the selected transaction log backups.</span></span>  
  
     <span data-ttu-id="14b91-112">Por padrão, a restauração vai até a transação marcada, mas a exclui.</span><span class="sxs-lookup"><span data-stu-id="14b91-112">By default, the restore is up to, but excluding, the marked transaction.</span></span> <span data-ttu-id="14b91-113">Para restaurar também a transação marcada, selecione **Incluir transação marcada**.</span><span class="sxs-lookup"><span data-stu-id="14b91-113">To restore the marked transaction also, select **Include marked transaction**.</span></span>  
  
     <span data-ttu-id="14b91-114">A tabela a seguir lista os cabeçalhos de coluna da grade e descreve seus valores.</span><span class="sxs-lookup"><span data-stu-id="14b91-114">The following table lists the column headers of the grid and describes their values.</span></span>  
  
    |<span data-ttu-id="14b91-115">Cabeçalho</span><span class="sxs-lookup"><span data-stu-id="14b91-115">Header</span></span>|<span data-ttu-id="14b91-116">Valor</span><span class="sxs-lookup"><span data-stu-id="14b91-116">Value</span></span>|  
    |------------|-----------|  
    |\<blank>|<span data-ttu-id="14b91-117">Exibe uma caixa de seleção para selecionar a marca.</span><span class="sxs-lookup"><span data-stu-id="14b91-117">Displays a checkbox for selecting the mark.</span></span>|  
    |<span data-ttu-id="14b91-118">**Transaction Mark**</span><span class="sxs-lookup"><span data-stu-id="14b91-118">**Transaction Mark**</span></span>|<span data-ttu-id="14b91-119">Nome da transação marcada especificado pelo usuário quando a transação foi confirmada.</span><span class="sxs-lookup"><span data-stu-id="14b91-119">Name of the marked transaction specified by the user when the transaction was committed.</span></span>|  
    |<span data-ttu-id="14b91-120">**Data**</span><span class="sxs-lookup"><span data-stu-id="14b91-120">**Date**</span></span>|<span data-ttu-id="14b91-121">Data e hora de confirmação da transação.</span><span class="sxs-lookup"><span data-stu-id="14b91-121">Date and time of the transaction when it was committed.</span></span> <span data-ttu-id="14b91-122">A data e hora da transação são exibidas como registradas na tabela **msdbgmarkhistory** , não a data e hora do computador cliente.</span><span class="sxs-lookup"><span data-stu-id="14b91-122">Transaction date and time are displayed as recorded in the **msdbgmarkhistory** table, not in the client computer's date and time.</span></span>|  
    |<span data-ttu-id="14b91-123">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="14b91-123">**Description**</span></span>|<span data-ttu-id="14b91-124">Descrição da transação marcada especificada pelo usuário quando a transação foi confirmada (se houver).</span><span class="sxs-lookup"><span data-stu-id="14b91-124">Description of marked transaction specified by the user when the transaction was committed (if any).</span></span>|  
    |<span data-ttu-id="14b91-125">**LSN**</span><span class="sxs-lookup"><span data-stu-id="14b91-125">**LSN**</span></span>|<span data-ttu-id="14b91-126">Número de sequência de log da transação marcada.</span><span class="sxs-lookup"><span data-stu-id="14b91-126">Log sequence number of the marked transaction.</span></span>|  
    |<span data-ttu-id="14b91-127">**Backup de banco de dados**</span><span class="sxs-lookup"><span data-stu-id="14b91-127">**Database**</span></span>|<span data-ttu-id="14b91-128">Nome do banco de dados em que a transação marcada foi confirmada.</span><span class="sxs-lookup"><span data-stu-id="14b91-128">Name of the database where the marked transaction was committed.</span></span>|  
    |<span data-ttu-id="14b91-129">**Nome de usuário**</span><span class="sxs-lookup"><span data-stu-id="14b91-129">**User Name**</span></span>|<span data-ttu-id="14b91-130">Nome do usuário do banco de dados que confirmou a transação marcada.</span><span class="sxs-lookup"><span data-stu-id="14b91-130">Name of the database user who committed the marked transaction.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="14b91-131">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="14b91-131">See Also</span></span>  
 <span data-ttu-id="14b91-132">[Restaurar um backup de banco de dados &#40;SQL Server Management Studio&#41;](restore-a-database-backup-using-ssms.md) </span><span class="sxs-lookup"><span data-stu-id="14b91-132">[Restore a Database Backup &#40;SQL Server Management Studio&#41;](restore-a-database-backup-using-ssms.md) </span></span>  
 [<span data-ttu-id="14b91-133">Restaurar um backup de log de transações &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="14b91-133">Restore a Transaction Log Backup &#40;SQL Server&#41;</span></span>](restore-a-transaction-log-backup-sql-server.md)  
  
  
