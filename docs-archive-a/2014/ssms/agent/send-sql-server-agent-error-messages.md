---
title: Enviar mensagens de erro do SQL Server Agent | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- messages [SQL Server], SQL Server Agent
- sending messages
- SQL Server Agent, errors
- errors [SQL Server Agent]
ms.assetid: 2597d0d7-951a-48cf-989f-abb67b9fdb36
author: stevestein
ms.author: sstein
ms.openlocfilehash: 03e38b02188eaced65a86b22ed4f22cb6984ce0e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575538"
---
# <a name="send-sql-server-agent-error-messages"></a><span data-ttu-id="78ffe-102">Send SQL Server Agent Error Messages</span><span class="sxs-lookup"><span data-stu-id="78ffe-102">Send SQL Server Agent Error Messages</span></span>
  <span data-ttu-id="78ffe-103">Este tópico descreve como configurar [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o Agent para enviar suas mensagens de erro por meio do net send no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="78ffe-103">This topic describes how to how to configure [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to send its error messages by way of net send in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="78ffe-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="78ffe-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="78ffe-105">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="78ffe-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="78ffe-106">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="78ffe-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="78ffe-107">Segurança</span><span class="sxs-lookup"><span data-stu-id="78ffe-107">Security</span></span>](#Security)  
  
-   [<span data-ttu-id="78ffe-108">Para enviar mensagens de erro do SQL Server Agent usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="78ffe-108">To send SQL Server Agent error messages using SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="78ffe-109">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="78ffe-109">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="78ffe-110">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="78ffe-110">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="78ffe-111">O Pesquisador de Objetos só exibirá o nó [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent se você tiver permissão para usá-lo.</span><span class="sxs-lookup"><span data-stu-id="78ffe-111">Object Explorer only displays the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent node if you have permission to use it.</span></span>  
  
-   <span data-ttu-id="78ffe-112">O serviço do [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Messenger deve estar em execução para o recebimento de eventos net send.</span><span class="sxs-lookup"><span data-stu-id="78ffe-112">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Messenger service must be running to receive net send events.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="78ffe-113">Segurança</span><span class="sxs-lookup"><span data-stu-id="78ffe-113">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="78ffe-114">Permissões</span><span class="sxs-lookup"><span data-stu-id="78ffe-114">Permissions</span></span>  
 <span data-ttu-id="78ffe-115">Para executar suas funções, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent deve ser configurado de modo a usar as credenciais de uma conta que seja membro da função de servidor fixa **sysadmin** no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="78ffe-115">To perform its functions, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent must be configured to use the credentials of an account that is a member of the **sysadmin** fixed server role in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="78ffe-116">A conta deve ter as seguintes permissões do Windows:</span><span class="sxs-lookup"><span data-stu-id="78ffe-116">The account must have the following Windows permissions:</span></span>  
  
-   <span data-ttu-id="78ffe-117">Fazer logon como um serviço (SeServiceLogonRight)</span><span class="sxs-lookup"><span data-stu-id="78ffe-117">Log on as a service (SeServiceLogonRight)</span></span>  
  
-   <span data-ttu-id="78ffe-118">Substituir um token de nível de processo (SeAssignPrimaryTokenPrivilege)</span><span class="sxs-lookup"><span data-stu-id="78ffe-118">Replace a process-level token (SeAssignPrimaryTokenPrivilege)</span></span>  
  
-   <span data-ttu-id="78ffe-119">Ignorar verificação completa (SeChangeNotifyPrivilege)</span><span class="sxs-lookup"><span data-stu-id="78ffe-119">Bypass traverse checking (SeChangeNotifyPrivilege)</span></span>  
  
-   <span data-ttu-id="78ffe-120">Ajustar cotas de memória para um processo (SeIncreaseQuotaPrivilege)</span><span class="sxs-lookup"><span data-stu-id="78ffe-120">Adjust memory quotas for a process (SeIncreaseQuotaPrivilege)</span></span>  
  
 <span data-ttu-id="78ffe-121">Para obter mais informações sobre as permissões do Windows necessárias para a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] conta de serviço do Agent, consulte [selecionar uma conta para o serviço de SQL Server Agent](select-an-account-for-the-sql-server-agent-service.md) e [Configurar contas de serviço e permissões do Windows](../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="78ffe-121">For more information about the Windows permissions required for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service account, see [Select an Account for the SQL Server Agent Service](select-an-account-for-the-sql-server-agent-service.md) and [Configure Windows Service Accounts and Permissions](../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="78ffe-122">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="78ffe-122">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-send-sql-server-agent-error-messages"></a><span data-ttu-id="78ffe-123">Para enviar mensagens de erro do SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="78ffe-123">To send SQL Server Agent error messages</span></span>  
  
1.  <span data-ttu-id="78ffe-124">No **Pesquisador de Objetos**, clique no sinal de adição para expandir o servidor que contém o log de erros do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent do qual você deseja enviar mensagens de erro via net send.</span><span class="sxs-lookup"><span data-stu-id="78ffe-124">In **Object Explorer**, click the plus sign to expand the server that contains the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent error log from which you want to send error messages via net send.</span></span>  
  
2.  <span data-ttu-id="78ffe-125">Clique com o botão direito do mouse em **SQL Server Agent** e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="78ffe-125">Right-click **SQL Server Agent** and select **Properties**.</span></span>  
  
3.  <span data-ttu-id="78ffe-126">Na caixa de diálogo **Propriedades do SQL Server Agent –**_server_name_ , **em log de erros** na página **geral** , digite o nome do usuário ou o nome do computador para o qual você deseja enviar mensagens de erro na caixa **destinatário do net send** .</span><span class="sxs-lookup"><span data-stu-id="78ffe-126">In the **SQL Server Agent Properties -**_server_name_ dialog box, under **Error log** on the **General** page, , type the user name or computer name to which you want to send error messages in the **Net send recipient** box.</span></span>  
  
4.  <span data-ttu-id="78ffe-127">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="78ffe-127">Click **OK**.</span></span>  
  
  
