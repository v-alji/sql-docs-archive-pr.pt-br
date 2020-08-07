---
title: Gravar mensagens de rastreamento de execução para o SQL Server Agent log de erros (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- logs [SQL Server], SQL Server Agent
- writing trace messages
- traces [SQL Server], SQL Server Agent logs
- SQL Server Agent, errors
- errors [SQL Server Agent]
ms.assetid: 90e3731e-6fae-43db-833e-9accecdd1c03
author: stevestein
ms.author: sstein
ms.openlocfilehash: 38b08452ef2680b654dd735b901488cb5f5f5f97
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87682059"
---
# <a name="write-execution-trace-messages-to-the-sql-server-agent-error-log-sql-server-management-studio"></a><span data-ttu-id="5a4f7-102">Write Execution Trace Messages to the SQL Server Agent Error Log (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="5a4f7-102">Write Execution Trace Messages to the SQL Server Agent Error Log (SQL Server Management Studio)</span></span>
  <span data-ttu-id="5a4f7-103">Este tópico descreve como configurar o [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent para incluir mensagens de rastreamento de execução em seu log de erros no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5a4f7-103">This topic describes how to configure [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to include execution trace messages in its error log in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="5a4f7-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="5a4f7-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="5a4f7-105">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="5a4f7-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="5a4f7-106">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="5a4f7-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="5a4f7-107">Segurança</span><span class="sxs-lookup"><span data-stu-id="5a4f7-107">Security</span></span>](#Security)  
  
-   [<span data-ttu-id="5a4f7-108">Para gravar mensagens de rastreamento de execução no log de erros do SQL Server Agent usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5a4f7-108">To write execution trace messages to the SQL Server Agent Error Log using SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="5a4f7-109">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="5a4f7-109">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="5a4f7-110">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="5a4f7-110">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="5a4f7-111">O Pesquisador de Objetos só exibirá o nó [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent se você tiver permissão para usá-lo.</span><span class="sxs-lookup"><span data-stu-id="5a4f7-111">Object Explorer only displays the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent node if you have permission to use it.</span></span>  
  
-   <span data-ttu-id="5a4f7-112">Como essa opção pode fazer com que o log de erros torne-se muito grande, somente inclua as mensagens de rastreamento de execução nos logs de erro do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent ao investigar um problema específico do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="5a4f7-112">Because this option can cause the error log to become large, only include execution trace messages in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent error logs when investigating a specific [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent problem.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="5a4f7-113">Segurança</span><span class="sxs-lookup"><span data-stu-id="5a4f7-113">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="5a4f7-114">Permissões</span><span class="sxs-lookup"><span data-stu-id="5a4f7-114">Permissions</span></span>  
 <span data-ttu-id="5a4f7-115">Para executar suas funções, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent deve ser configurado de modo a usar as credenciais de uma conta que seja membro da função de servidor fixa **sysadmin** no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5a4f7-115">To perform its functions, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent must be configured to use the credentials of an account that is a member of the **sysadmin** fixed server role in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="5a4f7-116">A conta deve ter as seguintes permissões do Windows:</span><span class="sxs-lookup"><span data-stu-id="5a4f7-116">The account must have the following Windows permissions:</span></span>  
  
-   <span data-ttu-id="5a4f7-117">Fazer logon como um serviço (SeServiceLogonRight)</span><span class="sxs-lookup"><span data-stu-id="5a4f7-117">Log on as a service (SeServiceLogonRight)</span></span>  
  
-   <span data-ttu-id="5a4f7-118">Substituir um token de nível de processo (SeAssignPrimaryTokenPrivilege)</span><span class="sxs-lookup"><span data-stu-id="5a4f7-118">Replace a process-level token (SeAssignPrimaryTokenPrivilege)</span></span>  
  
-   <span data-ttu-id="5a4f7-119">Ignorar verificação completa (SeChangeNotifyPrivilege)</span><span class="sxs-lookup"><span data-stu-id="5a4f7-119">Bypass traverse checking (SeChangeNotifyPrivilege)</span></span>  
  
-   <span data-ttu-id="5a4f7-120">Ajustar cotas de memória para um processo (SeIncreaseQuotaPrivilege)</span><span class="sxs-lookup"><span data-stu-id="5a4f7-120">Adjust memory quotas for a process (SeIncreaseQuotaPrivilege)</span></span>  
  
 <span data-ttu-id="5a4f7-121">Para obter mais informações sobre as permissões do Windows necessárias para a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] conta de serviço do Agent, consulte [selecionar uma conta para o serviço de SQL Server Agent](select-an-account-for-the-sql-server-agent-service.md) e [Configurar contas de serviço e permissões do Windows](../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="5a4f7-121">For more information about the Windows permissions required for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service account, see [Select an Account for the SQL Server Agent Service](select-an-account-for-the-sql-server-agent-service.md) and [Configure Windows Service Accounts and Permissions](../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md).</span></span>  
  
##  <a name="SSMSProcedure"></a>   
#### <a name="to-write-execution-trace-messages-to-the-sql-server-agent-error-log"></a><span data-ttu-id="5a4f7-122">Para gravar mensagens de rastreamento de execução no log de erros do SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="5a4f7-122">To write execution trace messages to the SQL Server Agent error log</span></span>  
  
1.  <span data-ttu-id="5a4f7-123">No **Pesquisador de Objetos**, clique no sinal de adição para expandir o servidor que contém o log de erros do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent para o qual você deseja gravar mensagens de rastreamento de execução.</span><span class="sxs-lookup"><span data-stu-id="5a4f7-123">In **Object Explorer**, click the plus sign to expand the server that contains the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent error log to which you want to write execution trace messages.</span></span>  
  
2.  <span data-ttu-id="5a4f7-124">Clique com o botão direito do mouse em **SQL Server Agent** e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="5a4f7-124">Right-click **SQL Server Agent** and select **Properties**.</span></span>  
  
3.  <span data-ttu-id="5a4f7-125">Na caixa de diálogo **Propriedades do SQL Server Agent –**_server_name_ , **em log de erros** na página **geral** , marque a caixa de seleção **incluir mensagens de rastreamento de execução** .</span><span class="sxs-lookup"><span data-stu-id="5a4f7-125">In the **SQL Server Agent Properties -**_server_name_ dialog box, under **Error log** on the **General** page, select the **Include execution trace messages** check box.</span></span>  
  
4.  <span data-ttu-id="5a4f7-126">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="5a4f7-126">Click **OK**.</span></span>  
  
  
