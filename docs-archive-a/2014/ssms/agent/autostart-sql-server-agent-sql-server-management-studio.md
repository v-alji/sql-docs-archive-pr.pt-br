---
title: Iniciar o SQL Server Agent automaticamente (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent, starting
- autostart SQL Server Agent
ms.assetid: 2ea332da-0ede-4d2b-b122-c4c10eaca191
author: stevestein
ms.author: sstein
ms.openlocfilehash: a39c7c7a112370797a965cfa601bc07f983a7a37
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575546"
---
# <a name="autostart-sql-server-agent-sql-server-management-studio"></a><span data-ttu-id="0d142-102">Autostart SQL Server Agent (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="0d142-102">Autostart SQL Server Agent (SQL Server Management Studio)</span></span>
  <span data-ttu-id="0d142-103">Este tópico descreve como configurar o [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent para reiniciar automaticamente se ele deve parar inesperadamente no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0d142-103">This topic describes how to configure [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to automatically restart if it should stop unexpectedly in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span>  
  
 <span data-ttu-id="0d142-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="0d142-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="0d142-105">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="0d142-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="0d142-106">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="0d142-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="0d142-107">Segurança</span><span class="sxs-lookup"><span data-stu-id="0d142-107">Security</span></span>](#Security)  
  
-   [<span data-ttu-id="0d142-108">Para configurar o SQL Server Agent para reiniciar automaticamente usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="0d142-108">To configure SQL Server Agent to automatically restart, using SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="0d142-109">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="0d142-109">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="0d142-110">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="0d142-110">Limitations and Restrictions</span></span>  
 <span data-ttu-id="0d142-111">O Pesquisador de Objetos só exibirá o nó [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent se você tiver permissão para usá-lo.</span><span class="sxs-lookup"><span data-stu-id="0d142-111">Object Explorer only displays the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent node if you have permission to use it.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="0d142-112">Segurança</span><span class="sxs-lookup"><span data-stu-id="0d142-112">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="0d142-113">Permissões</span><span class="sxs-lookup"><span data-stu-id="0d142-113">Permissions</span></span>  
 <span data-ttu-id="0d142-114">Para executar suas funções, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent deve ser configurado de modo a usar as credenciais de uma conta que seja membro da função de servidor fixa **sysadmin** no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0d142-114">To perform its functions, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent must be configured to use the credentials of an account that is a member of the **sysadmin** fixed server role in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="0d142-115">A conta deve ter as seguintes permissões do Windows:</span><span class="sxs-lookup"><span data-stu-id="0d142-115">The account must have the following Windows permissions:</span></span>  
  
-   <span data-ttu-id="0d142-116">Fazer logon como um serviço (SeServiceLogonRight)</span><span class="sxs-lookup"><span data-stu-id="0d142-116">Log on as a service (SeServiceLogonRight)</span></span>  
  
-   <span data-ttu-id="0d142-117">Substituir um token de nível de processo (SeAssignPrimaryTokenPrivilege)</span><span class="sxs-lookup"><span data-stu-id="0d142-117">Replace a process-level token (SeAssignPrimaryTokenPrivilege)</span></span>  
  
-   <span data-ttu-id="0d142-118">Ignorar verificação completa (SeChangeNotifyPrivilege)</span><span class="sxs-lookup"><span data-stu-id="0d142-118">Bypass traverse checking (SeChangeNotifyPrivilege)</span></span>  
  
-   <span data-ttu-id="0d142-119">Ajustar cotas de memória para um processo (SeIncreaseQuotaPrivilege)</span><span class="sxs-lookup"><span data-stu-id="0d142-119">Adjust memory quotas for a process (SeIncreaseQuotaPrivilege)</span></span>  
  
 <span data-ttu-id="0d142-120">Para obter mais informações sobre as permissões do Windows necessárias para a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] conta de serviço do Agent, consulte [selecionar uma conta para o serviço de SQL Server Agent](select-an-account-for-the-sql-server-agent-service.md) e [Configurar contas de serviço e permissões do Windows](../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="0d142-120">For more information about the Windows permissions required for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service account, see [Select an Account for the SQL Server Agent Service](select-an-account-for-the-sql-server-agent-service.md) and [Configure Windows Service Accounts and Permissions](../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="0d142-121">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="0d142-121">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-sql-server-agent-to-automatically-restart"></a><span data-ttu-id="0d142-122">Para configurar o SQL Server Agent para reiniciar automaticamente</span><span class="sxs-lookup"><span data-stu-id="0d142-122">To configure SQL Server Agent to automatically restart</span></span>  
  
1.  <span data-ttu-id="0d142-123">No **Pesquisador de Objetos**, clique no sinal de adição para expandir o servidor no qual você deseja configurar o SQL Server Agent para reiniciar automaticamente.</span><span class="sxs-lookup"><span data-stu-id="0d142-123">In **Object Explorer**, click the plus sign to expand the server where you want to configure SQL Server Agent to automatically restart.</span></span>  
  
2.  <span data-ttu-id="0d142-124">Clique com o botão direito do mouse em **SQL Server Agent**e então clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="0d142-124">Right-click **SQL Server Agent**, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="0d142-125">Na página **Geral** , marque **Reiniciar automaticamente o SQL Server Agent se ele parar inesperadamente**.</span><span class="sxs-lookup"><span data-stu-id="0d142-125">On the **General** page, check **Auto restart SQL Server Agent if it stops unexpectedly**.</span></span>  
  
  
