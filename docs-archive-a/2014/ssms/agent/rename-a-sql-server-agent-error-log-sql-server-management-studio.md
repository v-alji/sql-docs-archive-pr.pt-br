---
title: Renomear um log de erros do SQL Server Agent (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- logs [SQL Server], SQL Server Agent
- renaming SQL Server Agent error log
- SQL Server Agent, errors
- errors [SQL Server Agent]
ms.assetid: dee2b199-48af-44cb-9177-d029a5edb169
author: stevestein
ms.author: sstein
ms.openlocfilehash: c1c85550a29bfff316ffc275ba2d4e4df10686d7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583294"
---
# <a name="rename-a-sql-server-agent-error-log-sql-server-management-studio"></a><span data-ttu-id="23cb3-102">Rename a SQL Server Agent Error Log (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="23cb3-102">Rename a SQL Server Agent Error Log (SQL Server Management Studio)</span></span>
  <span data-ttu-id="23cb3-103">Este tópico descreve como renomear o arquivo onde os [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] erros do Agent são gravados no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="23cb3-103">This topic describes how to rename the file where [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent errors are written in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="23cb3-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="23cb3-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="23cb3-105">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="23cb3-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="23cb3-106">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="23cb3-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="23cb3-107">Segurança</span><span class="sxs-lookup"><span data-stu-id="23cb3-107">Security</span></span>](#Security)  
  
-   [<span data-ttu-id="23cb3-108">Para renomear um log de erros do SQL Server Agent usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="23cb3-108">To rename a SQL Server Agent error log using SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="23cb3-109">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="23cb3-109">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="23cb3-110">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="23cb3-110">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="23cb3-111">O Pesquisador de Objetos só exibirá o nó [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent se você tiver permissão para usá-lo.</span><span class="sxs-lookup"><span data-stu-id="23cb3-111">Object Explorer only displays the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent node if you have permission to use it.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="23cb3-112">Agent não irá gravar no novo arquivo de log até que o serviço do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent seja reiniciado.</span><span class="sxs-lookup"><span data-stu-id="23cb3-112">Agent will not write to the new log file until the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service is restarted.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="23cb3-113">Segurança</span><span class="sxs-lookup"><span data-stu-id="23cb3-113">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="23cb3-114">Permissões</span><span class="sxs-lookup"><span data-stu-id="23cb3-114">Permissions</span></span>  
 <span data-ttu-id="23cb3-115">Para executar suas funções, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent deve ser configurado de modo a usar as credenciais de uma conta que seja membro da função de servidor fixa **sysadmin** no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="23cb3-115">To perform its functions, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent must be configured to use the credentials of an account that is a member of the **sysadmin** fixed server role in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="23cb3-116">A conta deve ter as seguintes permissões do Windows:</span><span class="sxs-lookup"><span data-stu-id="23cb3-116">The account must have the following Windows permissions:</span></span>  
  
-   <span data-ttu-id="23cb3-117">Fazer logon como um serviço (SeServiceLogonRight)</span><span class="sxs-lookup"><span data-stu-id="23cb3-117">Log on as a service (SeServiceLogonRight)</span></span>  
  
-   <span data-ttu-id="23cb3-118">Substituir um token de nível de processo (SeAssignPrimaryTokenPrivilege)</span><span class="sxs-lookup"><span data-stu-id="23cb3-118">Replace a process-level token (SeAssignPrimaryTokenPrivilege)</span></span>  
  
-   <span data-ttu-id="23cb3-119">Ignorar verificação completa (SeChangeNotifyPrivilege)</span><span class="sxs-lookup"><span data-stu-id="23cb3-119">Bypass traverse checking (SeChangeNotifyPrivilege)</span></span>  
  
-   <span data-ttu-id="23cb3-120">Ajustar cotas de memória para um processo (SeIncreaseQuotaPrivilege)</span><span class="sxs-lookup"><span data-stu-id="23cb3-120">Adjust memory quotas for a process (SeIncreaseQuotaPrivilege)</span></span>  
  
 <span data-ttu-id="23cb3-121">Para obter mais informações sobre as permissões do Windows necessárias para a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] conta de serviço do Agent, consulte [selecionar uma conta para o serviço de SQL Server Agent](select-an-account-for-the-sql-server-agent-service.md) e [Configurar contas de serviço e permissões do Windows](../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="23cb3-121">For more information about the Windows permissions required for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service account, see [Select an Account for the SQL Server Agent Service](select-an-account-for-the-sql-server-agent-service.md) and [Configure Windows Service Accounts and Permissions](../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="23cb3-122">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="23cb3-122">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-rename-a-sql-server-agent-error-log"></a><span data-ttu-id="23cb3-123">Para renomear o log de erros do SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="23cb3-123">To rename a SQL Server Agent error log</span></span>  
  
1.  <span data-ttu-id="23cb3-124">No **Pesquisador de Objetos**, clique no sinal de adição para expandir o servidor que contém o log de erros do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent que você deseja renomear.</span><span class="sxs-lookup"><span data-stu-id="23cb3-124">In **Object Explorer**, click the plus sign to expand the server that contains the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent error log that you want to rename.</span></span>  
  
2.  <span data-ttu-id="23cb3-125">Clique no sinal de adição para expandir o **SQL Server Agent**.</span><span class="sxs-lookup"><span data-stu-id="23cb3-125">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="23cb3-126">Clique com o botão direito do mouse na pasta **Logs de Erros** e selecione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="23cb3-126">Right-click the **Error Logs** folder and select **Configure**.</span></span>  
  
4.  <span data-ttu-id="23cb3-127">Na caixa de diálogo **Configurar logs de erros do SQL Server Agent** , na caixa **Arquivo do log de erros** , insira o novo caminho de arquivo e o nome de arquivo para o log de erros.</span><span class="sxs-lookup"><span data-stu-id="23cb3-127">In the **Configure SQL Server Agent Error Logs** dialog box, in the **Error log file** box, enter the new file path and file name for the error log.</span></span> <span data-ttu-id="23cb3-128">Como alternativa, clique nas reticências **(...)** para abrir a caixa de diálogo **Especifique o local do log de erros do agente** .</span><span class="sxs-lookup"><span data-stu-id="23cb3-128">Alternately, click the ellipsis **(...)** to open the **Specify agent error log location** dialog box.</span></span>  
  
5.  <span data-ttu-id="23cb3-129">Quando terminar, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="23cb3-129">When finished, click **OK**.</span></span>  
  
  
