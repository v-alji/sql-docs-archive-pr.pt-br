---
title: Modificar os servidores de destino de um trabalho | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- modifying target servers
- SQL Server Agent jobs, target servers
- target servers [SQL Server], modifying
ms.assetid: 9dbe24f2-acec-4aa2-920c-e8e96efa18e4
author: stevestein
ms.author: sstein
ms.openlocfilehash: 246a5bb59a681a70734cc8cabef4f724cda1b52e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572340"
---
# <a name="modify-the-target-servers-for-a-job"></a><span data-ttu-id="1ae64-102">Modify the Target Servers for a Job</span><span class="sxs-lookup"><span data-stu-id="1ae64-102">Modify the Target Servers for a Job</span></span>
  <span data-ttu-id="1ae64-103">Este tópico descreve como alterar os servidores de destino para [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] trabalhos do Agent no usando o [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] ou o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1ae64-103">This topic describes how to change the target servers for [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="1ae64-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="1ae64-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="1ae64-105">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="1ae64-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="1ae64-106">Segurança</span><span class="sxs-lookup"><span data-stu-id="1ae64-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="1ae64-107">**Para modificar os servidores de destino de um trabalho usando:**</span><span class="sxs-lookup"><span data-stu-id="1ae64-107">**To modify the target servers for a job, using:**</span></span>  
  
     [<span data-ttu-id="1ae64-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1ae64-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="1ae64-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="1ae64-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="1ae64-110">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="1ae64-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="1ae64-111">Segurança</span><span class="sxs-lookup"><span data-stu-id="1ae64-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="1ae64-112">Permissões</span><span class="sxs-lookup"><span data-stu-id="1ae64-112">Permissions</span></span>  
 <span data-ttu-id="1ae64-113">Por padrão, os membros da função de servidor fixa sysadmin podem executar esse procedimento armazenado.</span><span class="sxs-lookup"><span data-stu-id="1ae64-113">By default, members of the sysadmin fixed server role can execute this stored procedure.</span></span> <span data-ttu-id="1ae64-114">Deve ser concedida a outros usuários uma das seguintes funções de banco de dados fixas do SQL Server Agent no banco de dados msdb:</span><span class="sxs-lookup"><span data-stu-id="1ae64-114">Other users must be granted one of the following SQL Server Agent fixed database roles in the msdb database:</span></span>  
  
1.  `SQLAgentUserRole`  
  
2.  `SQLAgentReaderRole`  
  
3.  <span data-ttu-id="1ae64-115">SQLAgentOperatorRole</span><span class="sxs-lookup"><span data-stu-id="1ae64-115">SQLAgentOperatorRole</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="1ae64-116">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1ae64-116">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-modify-the-target-servers-for-a-job"></a><span data-ttu-id="1ae64-117">Para modificar os servidores de destino de um trabalho</span><span class="sxs-lookup"><span data-stu-id="1ae64-117">To modify the target servers for a job</span></span>  
  
1.  <span data-ttu-id="1ae64-118">No Pesquisador de **objetos,** Conecte-se a uma instância do [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] e expanda essa instância.</span><span class="sxs-lookup"><span data-stu-id="1ae64-118">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="1ae64-119">Expanda **SQL Server Agent**, expanda **Trabalhos**, clique com o botão direito do mouse em um trabalho e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="1ae64-119">Expand **SQL Server Agent**, expand **Jobs**, right-click a job, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="1ae64-120">Na caixa de diálogo **Propriedades do Trabalho** , selecione a página **Destinos**e clique em **Servidor local de destino**ou **Vários servidores de destino**.</span><span class="sxs-lookup"><span data-stu-id="1ae64-120">In the **Job Properties** dialog, select the **Targets**page, and click **Target local server**, or **Target multiple servers**.</span></span>  
  
     <span data-ttu-id="1ae64-121">Se optar por **Vários servidores de destino**, designe os servidores a serem destino do trabalho, marcando a caixa à esquerda do nome do servidor.</span><span class="sxs-lookup"><span data-stu-id="1ae64-121">If you choose **Target multiple servers**, designate the servers that will be targets for the job by checking the box to the left of the server name.</span></span> <span data-ttu-id="1ae64-122">Verifique se as caixas de seleção dos servidores que não devem ser destino do trabalho estão desmarcadas.</span><span class="sxs-lookup"><span data-stu-id="1ae64-122">Verify that the check boxes for servers that will not be targets of the job are unchecked.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="1ae64-123">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="1ae64-123">Using Transact-SQL</span></span>  
  
#### <a name="to-modify-the-target-servers-for-a-job"></a><span data-ttu-id="1ae64-124">Para modificar os servidores de destino de um trabalho</span><span class="sxs-lookup"><span data-stu-id="1ae64-124">To modify the target servers for a job</span></span>  
  
1.  <span data-ttu-id="1ae64-125">Conecte-se ao [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1ae64-125">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="1ae64-126">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="1ae64-126">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="1ae64-127">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="1ae64-127">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="1ae64-128">Este exemplo atribui o trabalho multisservidor Backups de Vendas Semanais ao servidor SEATTLE2.</span><span class="sxs-lookup"><span data-stu-id="1ae64-128">This example assigns the multiserver job Weekly Sales Backups to the server SEATTLE2.</span></span>  
  
```  
USE msdb ;  
GO  
  
EXEC dbo.sp_add_jobserver  
    @job_name = N'Weekly Sales Backups',   
    @server_name = N'SEATTLE2' ;   
GO  
  
```  
  
 <span data-ttu-id="1ae64-129">Para obter mais informações, consulte [sp_add_jobserver &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-add-jobserver-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1ae64-129">For more information, see [sp_add_jobserver &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-jobserver-transact-sql).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ae64-130">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="1ae64-130">See Also</span></span>  
 [<span data-ttu-id="1ae64-131">Administração automatizada em toda a empresa</span><span class="sxs-lookup"><span data-stu-id="1ae64-131">Automated Administration Across an Enterprise</span></span>](automated-administration-across-an-enterprise.md)  
  
  
