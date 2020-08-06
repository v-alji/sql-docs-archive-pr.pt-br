---
title: Definir o intervalo de sondagem para servidores de destino | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- interval for polling [SQL Server]
- target servers [SQL Server], polling interval
- polling interval [SQL Server]
ms.assetid: 4ffbbefa-77fb-442e-a77c-cb8c6cab9f3c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 36517f60a99a1a844f6d14d489587eef1de9cb13
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87686012"
---
# <a name="set-the-polling-interval-for-target-servers"></a><span data-ttu-id="dee28-102">Set the Polling Interval for Target Servers</span><span class="sxs-lookup"><span data-stu-id="dee28-102">Set the Polling Interval for Target Servers</span></span>
  <span data-ttu-id="dee28-103">Este tópico descreve como definir a frequência com que o [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent atualiza informações do mestre para os servidores de destino.</span><span class="sxs-lookup"><span data-stu-id="dee28-103">This topic describes how to set the frequency that [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent refreshes information from the master to the target servers.</span></span> <span data-ttu-id="dee28-104">Um trabalho é uma série especificada de ações que o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent executa.</span><span class="sxs-lookup"><span data-stu-id="dee28-104">A job is a specified series of actions that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent performs.</span></span> <span data-ttu-id="dee28-105">Um trabalho multisservidor é um trabalho executado por um servidor mestre em um ou mais servidores de destino.</span><span class="sxs-lookup"><span data-stu-id="dee28-105">A multiserver job is a job that a master server runs on one or more target servers.</span></span>  
  
-   <span data-ttu-id="dee28-106">**Antes de começar:**  [Segurança](#Security)</span><span class="sxs-lookup"><span data-stu-id="dee28-106">**Before you begin:**  [Security](#Security)</span></span>  
  
-   <span data-ttu-id="dee28-107">**Para definir o intervalo de sondagem para servidores de destino usando:**  [SQL Server Management Studio](#SSMS), [Transact-SQL](#TSQL)</span><span class="sxs-lookup"><span data-stu-id="dee28-107">**To set the polling interval for target servers, using:**  [SQL Server Management Studio](#SSMS), [Transact-SQL](#TSQL)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="dee28-108">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="dee28-108">Before You Begin</span></span>  
 <span data-ttu-id="dee28-109">Cada servidor de destino pode executar uma instância do mesmo trabalho ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="dee28-109">Each target server can run one instance of the same job at the same time.</span></span> <span data-ttu-id="dee28-110">Cada servidor de destino sonda o servidor mestre periodicamente, baixa uma cópia dos eventuais trabalhos novos a ele atribuídos e, em seguida, desconecta-se.</span><span class="sxs-lookup"><span data-stu-id="dee28-110">Each target server periodically polls the master server, downloads a copy of any new jobs assigned to the target server, and then disconnects.</span></span> <span data-ttu-id="dee28-111">O servidor de destino executa o trabalho localmente e, depois, reconecta-se ao servidor mestre para carregar o status do resultado do trabalho.</span><span class="sxs-lookup"><span data-stu-id="dee28-111">The target server runs the job locally and then reconnects to the master server to upload the job outcome status.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="dee28-112">Se o servidor mestre não estiver acessível quando o servidor de destino tentar carregar o status do trabalho, este será colocado em spool até que o servidor mestre esteja novamente acessível.</span><span class="sxs-lookup"><span data-stu-id="dee28-112">If the master server is inaccessible when the target server tries to upload job status, the job status is spooled until the master server can be accessed.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="dee28-113">Segurança</span><span class="sxs-lookup"><span data-stu-id="dee28-113">Security</span></span>  
 <span data-ttu-id="dee28-114">Para obter informações detalhadas, consulte [Implement SQL Server Agent Security](implement-sql-server-agent-security.md) e [Choose the Right SQL Server Agent Service Account for Multiserver Environments](choose-the-right-sql-server-agent-service-account-for-multiserver-environments.md).</span><span class="sxs-lookup"><span data-stu-id="dee28-114">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md) and [Choose the Right SQL Server Agent Service Account for Multiserver Environments](choose-the-right-sql-server-agent-service-account-for-multiserver-environments.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="dee28-115">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="dee28-115">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="dee28-116">**Para definir o intervalo de sondagem de servidores de destino**</span><span class="sxs-lookup"><span data-stu-id="dee28-116">**To set the polling interval for target servers**</span></span>  
  
1.  <span data-ttu-id="dee28-117">No Pesquisador de **objetos,** Conecte-se a uma instância do [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] e expanda essa instância.</span><span class="sxs-lookup"><span data-stu-id="dee28-117">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="dee28-118">Clique com o botão direito do mouse em **SQL Server Agent**, aponte para **Administração Multisservidor**e clique em **Gerenciar Servidores de Destino**.</span><span class="sxs-lookup"><span data-stu-id="dee28-118">Right-click **SQL Server Agent**, point to **Multi Server Administration**, and then click **Manage Target Servers**.</span></span>  
  
3.  <span data-ttu-id="dee28-119">Na guia **Status do Servidor de Destino** , clique em **Postar Instruções**.</span><span class="sxs-lookup"><span data-stu-id="dee28-119">On the **Target Server Status** tab, click **Post Instructions**.</span></span>  
  
4.  <span data-ttu-id="dee28-120">Na lista **Tipo de instrução** , selecione **Definir intervalo de sondagem**.</span><span class="sxs-lookup"><span data-stu-id="dee28-120">In the **Instruction type** list, select **Set polling interval**.</span></span>  
  
5.  <span data-ttu-id="dee28-121">Na caixa **Intervalo de sondagem** , insira o número de segundos, de 10 a 28.800, a decorrer entre uma sondagem e outra do servidor mestre pelo servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="dee28-121">In the **Polling interval** box, enter the number of seconds from 10 through 28,800 that must pass before the target server polls the master server.</span></span>  
  
6.  <span data-ttu-id="dee28-122">Em **Destinatários**, siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="dee28-122">Under **Recipients**, do one of the following:</span></span>  
  
    1.  <span data-ttu-id="dee28-123">Clique em **Todos os servidores de destino** se todos os servidores de destino compartilharem o mesmo intervalo de sondagem.</span><span class="sxs-lookup"><span data-stu-id="dee28-123">Click **All target servers** if all target servers share the same polling interval.</span></span>  
  
    2.  <span data-ttu-id="dee28-124">Clique em **Estes servidores de destino** se nem todos os servidores de destino compartilharem o mesmo intervalo de sondagem, e selecione cada servidor de destino que usará o intervalo de sondagem que está sendo definido.</span><span class="sxs-lookup"><span data-stu-id="dee28-124">Click **These target servers** if not all target servers share the same polling interval, and then select each target server that will use this polling interval.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="dee28-125">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="dee28-125">Using Transact-SQL</span></span>  
 <span data-ttu-id="dee28-126">**Para definir o intervalo de sondagem de servidores de destino**</span><span class="sxs-lookup"><span data-stu-id="dee28-126">**To set the polling interval for target servers**</span></span>  
  
1.  <span data-ttu-id="dee28-127">No Pesquisador de Objetos, conecte-se a uma instância do Mecanismo de Banco de Dados e expanda-a.</span><span class="sxs-lookup"><span data-stu-id="dee28-127">In Object Explorer, connect to an instance of the Database Engine, and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="dee28-128">Na barra de ferramentas, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="dee28-128">On the toolbar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="dee28-129">Na janela de consulta, use o sp_post_msx_operation &#40;procedimento armazenado do sistema [&#41;Transact-SQL](/sql/relational-databases/system-stored-procedures/sp-post-msx-operation-transact-sql) para definir o intervalo de sondagem para servidores de destino.</span><span class="sxs-lookup"><span data-stu-id="dee28-129">In the query window, use the [sp_post_msx_operation &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-post-msx-operation-transact-sql) system stored procedure to set the polling interval for target servers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dee28-130">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="dee28-130">See Also</span></span>  
 [<span data-ttu-id="dee28-131">dbo.sysdownloadlist &#40;&#41;Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="dee28-131">dbo.sysdownloadlist &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-tables/dbo-sysdownloadlist-transact-sql)  
  
  
