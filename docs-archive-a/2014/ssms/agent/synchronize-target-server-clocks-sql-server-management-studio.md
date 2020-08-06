---
title: Sincronizar relógios dos servidores de destino (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent jobs, target servers
- clocks [SQL Server]
- master servers [SQL Server], clock synchronization
- synchronization [SQL Server], target server clocks
- target servers [SQL Server], clock synchronization
ms.assetid: 4fb80502-d271-4d06-bcbc-bfbbceb5f2a2
author: stevestein
ms.author: sstein
ms.openlocfilehash: 8e7150cd42699503ab22cdd89fb6206194bd64e1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678558"
---
# <a name="synchronize-target-server-clocks-sql-server-management-studio"></a><span data-ttu-id="9c356-102">Synchronize Target Server Clocks (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="9c356-102">Synchronize Target Server Clocks (SQL Server Management Studio)</span></span>
  <span data-ttu-id="9c356-103">Este tópico descreve como sincronizar os relógios dos servidores de destino no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] com o relógio do servidor mestre usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9c356-103">This topic describes how to synchronize target server clocks in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] with the master server clock by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="9c356-104">Sincronizar esses relógios do sistema dá suporte às agendas de trabalho.</span><span class="sxs-lookup"><span data-stu-id="9c356-104">Synchronizing these system clocks supports your job schedules.</span></span>  
  
 <span data-ttu-id="9c356-105">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="9c356-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="9c356-106">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="9c356-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="9c356-107">Segurança</span><span class="sxs-lookup"><span data-stu-id="9c356-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="9c356-108">**Para sincronizar os relógios dos servidores de destino usando:**</span><span class="sxs-lookup"><span data-stu-id="9c356-108">**To synchronize target server clocks, using:**</span></span>  
  
     [<span data-ttu-id="9c356-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="9c356-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="9c356-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="9c356-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="9c356-111">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="9c356-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="9c356-112">Segurança</span><span class="sxs-lookup"><span data-stu-id="9c356-112">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="9c356-113">Permissões</span><span class="sxs-lookup"><span data-stu-id="9c356-113">Permissions</span></span>  
 <span data-ttu-id="9c356-114">Exige associação à função de servidor fixa **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="9c356-114">Requires membership in the **sysadmin** fixed server role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="9c356-115">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="9c356-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-synchronize-target-server-clocks"></a><span data-ttu-id="9c356-116">Para sincronizar os relógios dos servidores de destino</span><span class="sxs-lookup"><span data-stu-id="9c356-116">To synchronize target server clocks</span></span>  
  
1.  <span data-ttu-id="9c356-117">No **Pesquisador de Objetos,** clique no sinal de adição para expandir o servidor onde você deseja sincronizar os relógios dos servidores de destino com o relógio do servidor mestre.</span><span class="sxs-lookup"><span data-stu-id="9c356-117">In **Object Explorer,** click the plus sign to expand the server where you want to synchronize the target server clocks with the master server clock.</span></span>  
  
2.  <span data-ttu-id="9c356-118">Clique com o botão direito do mouse em **SQL Server Agent**, aponte para **Administração Multisservidor**e selecione **Gerenciar Servidores de Destino**.</span><span class="sxs-lookup"><span data-stu-id="9c356-118">Right-click **SQL Server Agent**, point to **Multi Server Administration**, and select **Manage Target Servers**.</span></span>  
  
3.  <span data-ttu-id="9c356-119">Na caixa de diálogo **Gerenciar Servidores de Destino** , clique em **Postar Instruções**.</span><span class="sxs-lookup"><span data-stu-id="9c356-119">In the **Manage Target Servers** dialog box, click **Post Instructions**.</span></span>  
  
4.  <span data-ttu-id="9c356-120">Na lista **Tipo de instrução** , selecione **Sincronizar relógios**.</span><span class="sxs-lookup"><span data-stu-id="9c356-120">In the **Instruction type** list, select **Synchronize clocks**.</span></span>  
  
5.  <span data-ttu-id="9c356-121">Em **Destinatários**, siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="9c356-121">Under **Recipients**, do one of the following:</span></span>  
  
    -   <span data-ttu-id="9c356-122">Clique em **Todos os servidores de destino** para sincronizar os relógios de todos os servidores de destino com o relógio do servidor mestre.</span><span class="sxs-lookup"><span data-stu-id="9c356-122">Click **All target servers** to synchronize all target server clocks with the master server clock.</span></span>  
  
    -   <span data-ttu-id="9c356-123">Clique em **Estes servidores de destino** para sincronizar os relógios de apenas alguns servidores de destino com o relógio do servidor mestre, selecionando cada um deles.</span><span class="sxs-lookup"><span data-stu-id="9c356-123">Click **These target servers** to synchronize certain server clocks, and then select each target server whose clock you want to synchronize with the master server clock.</span></span>  
  
6.  <span data-ttu-id="9c356-124">Quando terminar, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="9c356-124">When finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="9c356-125">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="9c356-125">Using Transact-SQL</span></span>  
  
#### <a name="to-synchronize-target-server-clocks"></a><span data-ttu-id="9c356-126">Para sincronizar os relógios dos servidores de destino</span><span class="sxs-lookup"><span data-stu-id="9c356-126">To synchronize target server clocks</span></span>  
  
1.  <span data-ttu-id="9c356-127">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9c356-127">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="9c356-128">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="9c356-128">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="9c356-129">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="9c356-129">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE msdb ;  
    GO  
    -- resynchronizes the SEATTLE1 target server  
    EXEC dbo.sp_resync_targetserver  
        N'SEATTLE1' ;  
    GO  
    ```  
  
 <span data-ttu-id="9c356-130">Para obter mais informações, consulte [sp_resync_targetserver &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-resync-targetserver-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="9c356-130">For more information, see [sp_resync_targetserver &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-resync-targetserver-transact-sql).</span></span>  
  
  
