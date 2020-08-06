---
title: Configurar um usuário para criar e gerenciar trabalhos do SQL Server Agent | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent jobs, user configuration
- jobs [SQL Server Agent], user configuration
- SQLAgentUserRole database role
- proxy accounts [SQL Server Agent]
ms.assetid: 67897e3e-b7d0-43dd-a2e2-2840ec4dd1ef
author: stevestein
ms.author: sstein
ms.openlocfilehash: 83313389b3b872004fb23b0babdad19cfb5b8e7d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583320"
---
# <a name="configure-a-user-to-create-and-manage-sql-server-agent-jobs"></a><span data-ttu-id="032ad-102">Configure a User to Create and Manage SQL Server Agent Jobs</span><span class="sxs-lookup"><span data-stu-id="032ad-102">Configure a User to Create and Manage SQL Server Agent Jobs</span></span>
  <span data-ttu-id="032ad-103">Este tópico descreve como configurar um usuário para criar ou executar [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] trabalhos do Agent.</span><span class="sxs-lookup"><span data-stu-id="032ad-103">This topic describes how to configure a user to create or execute [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs.</span></span>  
  
-   <span data-ttu-id="032ad-104">**Antes de começar:**  [Segurança](#Security)</span><span class="sxs-lookup"><span data-stu-id="032ad-104">**Before you begin:**  [Security](#Security)</span></span>  
  
-   <span data-ttu-id="032ad-105">**Para configurar um usuário para criar e gerenciar trabalhos do SQL Server Agent, usando:**  [SQL Server Management Studio](#SSMS)</span><span class="sxs-lookup"><span data-stu-id="032ad-105">**To configure a user to create and manage SQL Server Agent jobs, using:**  [SQL Server Management Studio](#SSMS)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="032ad-106">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="032ad-106">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="032ad-107">Segurança</span><span class="sxs-lookup"><span data-stu-id="032ad-107">Security</span></span>  
 <span data-ttu-id="032ad-108">Para configurar um usuário para criar ou executar [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] trabalhos do Agent, primeiro você deve adicionar um logon de SQL Server existente ou uma função msdb a uma das seguintes [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] funções de banco de dados fixas do agente no banco de dados msdb: SQLAgentUserRole, SQLAgentReaderRole ou SQLAgentOperatorRole.</span><span class="sxs-lookup"><span data-stu-id="032ad-108">To configure a user to create or execute [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs, you must first add an existing SQL Server login or msdb role to one of the following [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent fixed database roles in the msdb database: SQLAgentUserRole, SQLAgentReaderRole, or SQLAgentOperatorRole.</span></span>  
  
 <span data-ttu-id="032ad-109">Por padrão, os membros dessas funções de banco de dados podem criar suas próprias etapas de trabalho, executadas como eles mesmos.</span><span class="sxs-lookup"><span data-stu-id="032ad-109">By default, members of these database roles can create their own job steps that run as themselves.</span></span> <span data-ttu-id="032ad-110">Se esses usuários não administrativos quiserem executar trabalhos que executam outros tipos de etapa de trabalho (por exemplo, pacotes [!INCLUDE[ssIS](../../includes/ssis-md.md)] ), eles precisarão ter acesso a uma conta proxy.</span><span class="sxs-lookup"><span data-stu-id="032ad-110">If these non-administrative users want to run jobs that execute other job step types (for example, [!INCLUDE[ssIS](../../includes/ssis-md.md)] packages), they will need to have access to a proxy account.</span></span> <span data-ttu-id="032ad-111">Todos os membros da função de servidor fixa sysadmin têm permissão para criar, modificar e excluir contas proxy.</span><span class="sxs-lookup"><span data-stu-id="032ad-111">All members of the sysadmin fixed server role have permission to create, modify, and delete proxy accounts.</span></span> <span data-ttu-id="032ad-112">Para obter mais informações sobre as permissões associadas a essas funções de banco de dados fixas do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent, consulte [Funções de banco de dados fixas do SQL Server Agent](sql-server-agent-fixed-database-roles.md).</span><span class="sxs-lookup"><span data-stu-id="032ad-112">For more information about the permissions that are associated with these [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent fixed database roles, see [SQL Server Agent Fixed Database Roles](sql-server-agent-fixed-database-roles.md).</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="032ad-113">Permissões</span><span class="sxs-lookup"><span data-stu-id="032ad-113">Permissions</span></span>  
 <span data-ttu-id="032ad-114">Para obter informações detalhadas, consulte [Implementar a segurança do SQL Server Agent](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="032ad-114">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="032ad-115">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="032ad-115">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="032ad-116">**Para adicionar um logon de SQL ou função msdb a uma função de banco de dados fixa do SQL Server Agent**</span><span class="sxs-lookup"><span data-stu-id="032ad-116">**To add a SQL login or msdb role to a SQL Server Agent fixed database role**</span></span>  
  
1.  <span data-ttu-id="032ad-117">No **Pesquisador de Objetos**, expanda um servidor.</span><span class="sxs-lookup"><span data-stu-id="032ad-117">In **Object Explorer**, expand a server.</span></span>  
  
2.  <span data-ttu-id="032ad-118">Expanda **Segurança**e, em seguida, **Logons**.</span><span class="sxs-lookup"><span data-stu-id="032ad-118">Expand **Security**, and then expand **Logins**.</span></span>  
  
3.  <span data-ttu-id="032ad-119">Clique com o botão direito do mouse no logon que deseja adicionar a uma função de banco de dados fixa do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="032ad-119">Right-click the login you wish to add to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent fixed database role, and select **Properties**.</span></span>  
  
4.  <span data-ttu-id="032ad-120">Na página **mapeamento de usuário** da caixa de diálogo **Propriedades de logon** , selecione a linha que contém `msdb` .</span><span class="sxs-lookup"><span data-stu-id="032ad-120">On the **User Mapping** page of the **Login Properties** dialog box, select the row containing `msdb`.</span></span>  
  
5.  <span data-ttu-id="032ad-121">Em **Associação à função de banco de dados para: msdb**, selecione a função de banco de dados fixa apropriada do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="032ad-121">Under **Database role membership for: msdb**, check the appropriate [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent fixed database role.</span></span>  
  
 <span data-ttu-id="032ad-122">**Para configurar uma conta proxy para criar e gerenciar etapas de trabalho do SQL Server Agent**</span><span class="sxs-lookup"><span data-stu-id="032ad-122">**To configure a proxy account to create and manage SQL Server Agent job steps**</span></span>  
  
1.  <span data-ttu-id="032ad-123">No **Pesquisador de Objetos**, expanda um servidor.</span><span class="sxs-lookup"><span data-stu-id="032ad-123">In **Object Explorer**, expand a server.</span></span>  
  
2.  <span data-ttu-id="032ad-124">Expanda o **SQL Server Agent**.</span><span class="sxs-lookup"><span data-stu-id="032ad-124">Expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="032ad-125">Clique com o botão direito do mouse em **Proxies** e selecione **Novo Proxy**.</span><span class="sxs-lookup"><span data-stu-id="032ad-125">Right-click **Proxies** and select **New Proxy**.</span></span>  
  
4.  <span data-ttu-id="032ad-126">Na página **Geral** da caixa de diálogo **Nova Conta Proxy** , especifique o nome do proxy, o nome da credencial e a descrição do novo proxy.</span><span class="sxs-lookup"><span data-stu-id="032ad-126">On the **General** page of the **New Proxy Account** dialog, specify the proxy name, credential name, and description for the new proxy.</span></span> <span data-ttu-id="032ad-127">Observe que primeiramente você deve criar uma credencial para poder criar um proxy do SQL Server Agent.</span><span class="sxs-lookup"><span data-stu-id="032ad-127">Note that you must create a credential first before creating a SQL Server Agent proxy.</span></span> <span data-ttu-id="032ad-128">Para obter mais informações sobre como criar uma credencial, consulte [criar uma credencial](../../relational-databases/security/authentication-access/create-a-credential.md) e [criar credencial &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-credential-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="032ad-128">For more information about creating a credential, see [Create a Credential](../../relational-databases/security/authentication-access/create-a-credential.md) and [CREATE CREDENTIAL &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-credential-transact-sql).</span></span>  
  
5.  <span data-ttu-id="032ad-129">Marque os subsistemas apropriados para esse proxy.</span><span class="sxs-lookup"><span data-stu-id="032ad-129">Check the appropriate subsystems for this proxy.</span></span>  
  
6.  <span data-ttu-id="032ad-130">Na página **Entidades** , adicione ou remova logons ou funções para conceder ou remover acesso à conta proxy.</span><span class="sxs-lookup"><span data-stu-id="032ad-130">On the **Principals** page, add or remove logins or roles to grant or remove access to the proxy account.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="032ad-131">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="032ad-131">See Also</span></span>  
 [<span data-ttu-id="032ad-132">Implementar a segurança do SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="032ad-132">Implement SQL Server Agent Security</span></span>](implement-sql-server-agent-security.md)  
  
  
