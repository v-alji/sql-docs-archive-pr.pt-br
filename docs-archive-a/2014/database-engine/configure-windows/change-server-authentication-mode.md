---
title: Alterar o modo de autenticação do servidor | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- sa account
- authentication [SQL Server], changing modes
- server authentication mode [SQL Server]
- modifying server authentication mode
ms.assetid: 79babcf8-19fd-4495-b8eb-453dc575cac0
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 8bda31ca7d0c5949173a9a3e5ea656c1757c04f7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684905"
---
# <a name="change-server-authentication-mode"></a><span data-ttu-id="3e0f1-102">Alterar modo de autenticação do servidor</span><span class="sxs-lookup"><span data-stu-id="3e0f1-102">Change Server Authentication Mode</span></span>
  <span data-ttu-id="3e0f1-103">Este tópico descreve como alterar o modo de autenticação de servidor no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3e0f1-103">This topic describes how to change the server authentication mode in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="3e0f1-104">Durante a instalação, o [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] é definido como **Modo de Autenticação do Windows** ou **Modo de Autenticação do SQL Server e do Windows**.</span><span class="sxs-lookup"><span data-stu-id="3e0f1-104">During installation, [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] is set to either **Windows Authentication mode** or **SQL Server and Windows Authentication mode**.</span></span> <span data-ttu-id="3e0f1-105">Após a instalação, você pode alterar o modo de autenticação a qualquer momento.</span><span class="sxs-lookup"><span data-stu-id="3e0f1-105">After installation, you can change the authentication mode at any time.</span></span>  
  
 <span data-ttu-id="3e0f1-106">Se **modo de Autenticação do Windows** for selecionado durante a instalação, o logon sa será desabilitado e uma senha será atribuída por meio da instalação.</span><span class="sxs-lookup"><span data-stu-id="3e0f1-106">If **Windows Authentication mode** is selected during installation, the sa login is disabled and a password is assigned by setup.</span></span> <span data-ttu-id="3e0f1-107">Se você alterar posteriormente o modo de autenticação para **Modo de Autenticação do SQL Server e do Windows**, o logon sa permanecerá desabilitado.</span><span class="sxs-lookup"><span data-stu-id="3e0f1-107">If you later change authentication mode to **SQL Server and Windows Authentication mode**, the sa login remains disabled.</span></span> <span data-ttu-id="3e0f1-108">Para usar o logon sa, use a instrução ALTER LOGIN para habilitar o logon de sa e atribuir uma nova senha.</span><span class="sxs-lookup"><span data-stu-id="3e0f1-108">To use the sa login, use the ALTER LOGIN statement to enable the sa login and assign a new password.</span></span> <span data-ttu-id="3e0f1-109">O logon sa só pode se conectar ao servidor usando a Autenticação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3e0f1-109">The sa login can only connect to the server by using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span>  
  
 <span data-ttu-id="3e0f1-110">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="3e0f1-110">**In This Topic**</span></span>  
  
-   <span data-ttu-id="3e0f1-111">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="3e0f1-111">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="3e0f1-112">Segurança</span><span class="sxs-lookup"><span data-stu-id="3e0f1-112">Security</span></span>](#Security)  
  
-   <span data-ttu-id="3e0f1-113">**Para alterar o modo de autenticação de servidor usando:**</span><span class="sxs-lookup"><span data-stu-id="3e0f1-113">**To change server authentication mode, using:**</span></span>  
  
     [<span data-ttu-id="3e0f1-114">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="3e0f1-114">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="3e0f1-115">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="3e0f1-115">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="3e0f1-116">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="3e0f1-116">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="3e0f1-117">Segurança</span><span class="sxs-lookup"><span data-stu-id="3e0f1-117">Security</span></span>  
 <span data-ttu-id="3e0f1-118">A conta sa é uma conta bem conhecida do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e geralmente é visada por usuários mal-intencionados.</span><span class="sxs-lookup"><span data-stu-id="3e0f1-118">The sa account is a well-known [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account and it is often targeted by malicious users.</span></span> <span data-ttu-id="3e0f1-119">Não habilite a conta sa, a menos que seu aplicativo exija isso.</span><span class="sxs-lookup"><span data-stu-id="3e0f1-119">Do not enable the sa account unless your application requires it.</span></span> <span data-ttu-id="3e0f1-120">É muito importante que você use uma senha segura para o logon de sa.</span><span class="sxs-lookup"><span data-stu-id="3e0f1-120">It is very important that you use a strong password for the sa login.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="3e0f1-121">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="3e0f1-121">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-change-security-authentication-mode"></a><span data-ttu-id="3e0f1-122">Alterar modo de autenticação de segurança</span><span class="sxs-lookup"><span data-stu-id="3e0f1-122">To change security authentication mode</span></span>  
  
1.  <span data-ttu-id="3e0f1-123">No Pesquisador de Objetos do [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , clique com o botão direito do mouse no servidor e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="3e0f1-123">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] Object Explorer, right-click the server, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="3e0f1-124">Na página **Segurança** , em **Autenticação de Servidor**, selecione o novo modo de autenticação de servidor e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="3e0f1-124">On the **Security** page, under **Server authentication**, select the new server authentication mode, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="3e0f1-125">Na caixa de diálogo [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , clique em **OK** para confirmar o requisito para reiniciar o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3e0f1-125">In the [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] dialog box, click **OK** to acknowledge the requirement to restart [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
4.  <span data-ttu-id="3e0f1-126">No Object Explorer, clique com o botão direito do mouse no seu servidor, e em seguida, clique em **Reiniciar**.</span><span class="sxs-lookup"><span data-stu-id="3e0f1-126">In Object Explorer, right-click your server, and then click **Restart**.</span></span> <span data-ttu-id="3e0f1-127">Se o agente do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] estiver em execução, ele também deverá ser reiniciado.</span><span class="sxs-lookup"><span data-stu-id="3e0f1-127">If [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent is running, it must also be restarted.</span></span>  
  
#### <a name="to-enable-the-sa-login"></a><span data-ttu-id="3e0f1-128">Para habilitar o logon sa</span><span class="sxs-lookup"><span data-stu-id="3e0f1-128">To enable the sa login</span></span>  
  
1.  <span data-ttu-id="3e0f1-129">No Pesquisador de objetos, expanda **segurança**, logons, clique com o botão direito do mouse `sa` e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="3e0f1-129">In Object Explorer, expand **Security**, expand Logins, right-click `sa`, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="3e0f1-130">Na página **Geral** , talvez seja necessário criar e confirmar uma senha para o logon.</span><span class="sxs-lookup"><span data-stu-id="3e0f1-130">On the **General** page, you might have to create and confirm a password for the  login.</span></span>  
  
3.  <span data-ttu-id="3e0f1-131">Na página **Status** , na seção **Logon** , clique em **Habilitado**e, em seguida, em **OK**.</span><span class="sxs-lookup"><span data-stu-id="3e0f1-131">On the **Status** page, in the **Login** section, click **Enabled**, and then click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="3e0f1-132">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="3e0f1-132">Using Transact-SQL</span></span>  
 <span data-ttu-id="3e0f1-133">**Para habilitar o logon sa**</span><span class="sxs-lookup"><span data-stu-id="3e0f1-133">**To enable the sa login**</span></span>  
  
1.  <span data-ttu-id="3e0f1-134">No Pesquisador de Objetos, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3e0f1-134">In Object Explorer, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="3e0f1-135">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="3e0f1-135">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="3e0f1-136">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="3e0f1-136">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="3e0f1-137">O exemplo a seguir habilita o logon sa e define uma nova senha.</span><span class="sxs-lookup"><span data-stu-id="3e0f1-137">The following example enables the sa login and sets a new password.</span></span>  
  
    ```  
    ALTER LOGIN sa ENABLE ;  
    GO  
    ALTER LOGIN sa WITH PASSWORD = '<enterStrongPasswordHere>' ;  
    GO  
  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="3e0f1-138">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="3e0f1-138">See Also</span></span>  
 <span data-ttu-id="3e0f1-139">[Senhas fortes](../../relational-databases/security/strong-passwords.md) </span><span class="sxs-lookup"><span data-stu-id="3e0f1-139">[Strong Passwords](../../relational-databases/security/strong-passwords.md) </span></span>  
 <span data-ttu-id="3e0f1-140">[Considerações de segurança para uma instalação do SQL Server](../../sql-server/install/security-considerations-for-a-sql-server-installation.md) </span><span class="sxs-lookup"><span data-stu-id="3e0f1-140">[Security Considerations for a SQL Server Installation](../../sql-server/install/security-considerations-for-a-sql-server-installation.md) </span></span>  
 <span data-ttu-id="3e0f1-141">[ALTER LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-login-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3e0f1-141">[ALTER LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-login-transact-sql) </span></span>  
 [<span data-ttu-id="3e0f1-142">Conectar-se ao SQL Server quando os administradores do sistema estão bloqueados</span><span class="sxs-lookup"><span data-stu-id="3e0f1-142">Connect to SQL Server When System Administrators Are Locked Out</span></span>](connect-to-sql-server-when-system-administrators-are-locked-out.md)  
  
  
