---
title: Definir a conexão de SQL Server para o serviço de SQL Server Agent (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent, connections
- connections [SQL Server], SQL Server Agent service
ms.assetid: 28b6178b-0a9e-4f2c-8562-7a62d2d2a285
author: stevestein
ms.author: sstein
ms.openlocfilehash: 30f68967d6bdb8b0495cbddb1a5b0bd447cd5168
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583965"
---
# <a name="set-the-sql-server-connection-for-the-sql-server-agent-service-sql-server-management-studio"></a><span data-ttu-id="bba19-102">Definir a Conexão do SQL Server para o Serviço do SQL Server Agent (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="bba19-102">Set the SQL Server Connection for the SQL Server Agent Service (SQL Server Management Studio)</span></span>
  <span data-ttu-id="bba19-103">Este tópico descreve como definir a conexão entre o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent e o [!INCLUDE[ssDE](../../includes/ssde-md.md)] no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bba19-103">This topic describes how to set the connection between [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent and the [!INCLUDE[ssDE](../../includes/ssde-md.md)] in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="bba19-104">O serviço do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent pode se conectar a uma instância local do SQL Server usando autenticação do Windows.</span><span class="sxs-lookup"><span data-stu-id="bba19-104">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service can connect to a local instance of SQL Server by using Windows Authentication.</span></span>  
  
 <span data-ttu-id="bba19-105">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="bba19-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="bba19-106">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="bba19-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="bba19-107">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="bba19-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="bba19-108">Segurança</span><span class="sxs-lookup"><span data-stu-id="bba19-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="bba19-109">**Para definir a conexão do SQL Server para o SQL Server Agent, usando:**</span><span class="sxs-lookup"><span data-stu-id="bba19-109">**To set the SQL Server Connection for the SQL Server Agent, using:**</span></span>  
  
     [<span data-ttu-id="bba19-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="bba19-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="bba19-111">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="bba19-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="bba19-112">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="bba19-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="bba19-113">O Pesquisador de Objetos só exibirá o nó [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent se você tiver permissão para usá-lo.</span><span class="sxs-lookup"><span data-stu-id="bba19-113">Object Explorer only displays the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent node if you have permission to use it.</span></span>  
  
-   <span data-ttu-id="bba19-114">A partir do [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent deixou de ter suporte à autenticação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bba19-114">Beginning with [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent does not support [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="bba19-115">Essa opção só está disponível para a administração de versões antigas do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bba19-115">This option is available only when you administer an earlier version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="bba19-116">Segurança</span><span class="sxs-lookup"><span data-stu-id="bba19-116">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="bba19-117">Permissões</span><span class="sxs-lookup"><span data-stu-id="bba19-117">Permissions</span></span>  
 <span data-ttu-id="bba19-118">Para executar suas funções, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent deve ser configurado de modo a usar as credenciais de uma conta que seja membro da função de servidor fixa **sysadmin** no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bba19-118">To perform its functions, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent must be configured to use the credentials of an account that is a member of the **sysadmin** fixed server role in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="bba19-119">A conta deve ter as seguintes permissões do Windows:</span><span class="sxs-lookup"><span data-stu-id="bba19-119">The account must have the following Windows permissions:</span></span>  
  
-   <span data-ttu-id="bba19-120">Fazer logon como um serviço (SeServiceLogonRight)</span><span class="sxs-lookup"><span data-stu-id="bba19-120">Log on as a service (SeServiceLogonRight)</span></span>  
  
-   <span data-ttu-id="bba19-121">Substituir um token de nível de processo (SeAssignPrimaryTokenPrivilege)</span><span class="sxs-lookup"><span data-stu-id="bba19-121">Replace a process-level token (SeAssignPrimaryTokenPrivilege)</span></span>  
  
-   <span data-ttu-id="bba19-122">Ignorar verificação completa (SeChangeNotifyPrivilege)</span><span class="sxs-lookup"><span data-stu-id="bba19-122">Bypass traverse checking (SeChangeNotifyPrivilege)</span></span>  
  
-   <span data-ttu-id="bba19-123">Ajustar cotas de memória para um processo (SeIncreaseQuotaPrivilege)</span><span class="sxs-lookup"><span data-stu-id="bba19-123">Adjust memory quotas for a process (SeIncreaseQuotaPrivilege)</span></span>  
  
 <span data-ttu-id="bba19-124">Para obter mais informações sobre as permissões do Windows necessárias para a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] conta de serviço do Agent, consulte [selecionar uma conta para o serviço de SQL Server Agent](select-an-account-for-the-sql-server-agent-service.md) e [Configurar contas de serviço e permissões do Windows](../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="bba19-124">For more information about the Windows permissions required for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service account, see [Select an Account for the SQL Server Agent Service](select-an-account-for-the-sql-server-agent-service.md) and [Configure Windows Service Accounts and Permissions](../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="bba19-125">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="bba19-125">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-set-the-sql-server-connection"></a><span data-ttu-id="bba19-126">Para definir a conexão do SQL Server</span><span class="sxs-lookup"><span data-stu-id="bba19-126">To set the SQL Server connection</span></span>  
  
1.  <span data-ttu-id="bba19-127">No **Pesquisador de Objetos,** clique no sinal de mais para expandir o servidor que você deseja definir com uma conexão como seu Serviço SQL Server Agent.</span><span class="sxs-lookup"><span data-stu-id="bba19-127">In **Object Explorer**, click the plus sign to expand the server that you want to set up with a connection to its SQL Server Agent Service.</span></span>  
  
2.  <span data-ttu-id="bba19-128">Clique com o botão direito do mouse em **SQL Server Agent** e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="bba19-128">Right-click **SQL Server Agent** and select **Properties**.</span></span>  
  
3.  <span data-ttu-id="bba19-129">Na caixa de diálogo **Propriedades do SQL Server Agent**, em **Selecionar uma página**, clique em **Conexão**.</span><span class="sxs-lookup"><span data-stu-id="bba19-129">In the **SQL Server Agent Properties** dialog box, under **Select a page**, click **Connection**.</span></span>  
  
4.  <span data-ttu-id="bba19-130">Em **Conexão do SQL Server**, selecione **Usar Autenticação do Windows** para permitir que o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent se conecte a uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] com Autenticação do [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="bba19-130">Under **SQL Server connection**, select **Use Windows Authentication** to enable [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to connect to an instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] with [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Authentication.</span></span> <span data-ttu-id="bba19-131">Conexões com bancos de dados do [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] e versões posteriores exigem a Autenticação do Windows.</span><span class="sxs-lookup"><span data-stu-id="bba19-131">Connections to [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and later databases require Windows Authentication.</span></span>  
  
  
