---
title: Configurar a opção de configuração de servidor default language | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- default language option
ms.assetid: c08c26d8-5a62-487e-a4ee-4c529e4f9287
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: b0e62fef112dad2c6c307946bc720adf1f14d82b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685272"
---
# <a name="configure-the-default-language-server-configuration-option"></a><span data-ttu-id="1c853-102">Configurar opção default language de configuração de servidor</span><span class="sxs-lookup"><span data-stu-id="1c853-102">Configure the default language Server Configuration Option</span></span>
  <span data-ttu-id="1c853-103">Este tópico descreve como configurar a opção de configuração de servidor **default language** no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1c853-103">This topic describes how to configure the **default language** server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="1c853-104">A opção **default language** especifica o idioma padrão para logons recém-criados.</span><span class="sxs-lookup"><span data-stu-id="1c853-104">The **default language** option specifies the default language for all newly created logins.</span></span> <span data-ttu-id="1c853-105">Para definir o idioma padrão, especifique o valor **langid** do idioma desejado.</span><span class="sxs-lookup"><span data-stu-id="1c853-105">To set default language, specify the **langid** value of the language you want.</span></span> <span data-ttu-id="1c853-106">O valor **langid** pode ser obtido consultando a exibição de compatibilidade **sys.syslanguages** .</span><span class="sxs-lookup"><span data-stu-id="1c853-106">The **langid** value can be obtained by querying the **sys.syslanguages** compatibility view.</span></span>  
  
 <span data-ttu-id="1c853-107">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="1c853-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="1c853-108">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="1c853-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="1c853-109">Recomendações</span><span class="sxs-lookup"><span data-stu-id="1c853-109">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="1c853-110">Segurança</span><span class="sxs-lookup"><span data-stu-id="1c853-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="1c853-111">**Para configurar a opção default language, usando:**</span><span class="sxs-lookup"><span data-stu-id="1c853-111">**To configure the default language option, using:**</span></span>  
  
     [<span data-ttu-id="1c853-112">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1c853-112">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="1c853-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="1c853-113">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="1c853-114">**Acompanhamento:**  [depois de configurar a opção default language](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="1c853-114">**Follow Up:**  [After you configure the default language option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="1c853-115">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="1c853-115">Before You Begin</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="1c853-116">Recomendações</span><span class="sxs-lookup"><span data-stu-id="1c853-116">Recommendations</span></span>  
  
-   <span data-ttu-id="1c853-117">O idioma padrão de um logon pode ser substituído usando CREATE LOGIN ou ALTER LOGIN.</span><span class="sxs-lookup"><span data-stu-id="1c853-117">The default language for a login can be overridden by using CREATE LOGIN or ALTER LOGIN.</span></span> <span data-ttu-id="1c853-118">O idioma padrão de uma sessão é o idioma do logon daquela sessão, a menos que substituído por uma sessão individual usando APIs ODBC (Conectividade Aberta de Banco de Dados) ou OLE DB.</span><span class="sxs-lookup"><span data-stu-id="1c853-118">The default language for a session is the language for that session's login, unless overridden on a per-session basis by using the Open Database Connectivity (ODBC) or OLE DB APIs.</span></span> <span data-ttu-id="1c853-119">Observe que você só pode definir a opção **default language** como uma ID de idioma definida em [sys.syslanguages](/sql/relational-databases/system-compatibility-views/sys-syslanguages-transact-sql) (0-32).</span><span class="sxs-lookup"><span data-stu-id="1c853-119">Note that you can only set the **default language** option to a language ID defined in [sys.syslanguages](/sql/relational-databases/system-compatibility-views/sys-syslanguages-transact-sql) (0-32).</span></span> <span data-ttu-id="1c853-120">Ao usar bancos de dados independentes, você pode definir um idioma padrão para um banco de dados usando CREATE DATABASE ou ALTER DATABASE, e para usuários de bancos de dados independentes, usando CREATE USER ou ALTER USER.</span><span class="sxs-lookup"><span data-stu-id="1c853-120">When you are using contained databases, a default language can be set for a database by using CREATE DATABASE or ALTER DATABASE, and for contained database users by using CREATE USER or ALTER USER.</span></span> <span data-ttu-id="1c853-121">A definição dos idiomas padrão em um banco de dados independente aceita o valor **langid** , o nome do idioma ou um alias do idioma, conforme listado em **sys.syslanguages**.</span><span class="sxs-lookup"><span data-stu-id="1c853-121">Setting default languages in a contained database accepts **langid** value, the language name, or a language alias as listed in **sys.syslanguages**.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="1c853-122">Segurança</span><span class="sxs-lookup"><span data-stu-id="1c853-122">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="1c853-123">Permissões</span><span class="sxs-lookup"><span data-stu-id="1c853-123">Permissions</span></span>  
 <span data-ttu-id="1c853-124">Permissões de execução sem parâmetros ou com apenas o primeiro parâmetro em **sp_configure** são concedidas a todos os usuários por padrão.</span><span class="sxs-lookup"><span data-stu-id="1c853-124">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="1c853-125">Para executar **sp_configure** com ambos os parâmetros para alterar uma opção de configuração ou executar a instrução RECONFIGURE, o usuário deve ter a permissão ALTER SETTINGS no nível do servidor.</span><span class="sxs-lookup"><span data-stu-id="1c853-125">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="1c853-126">A permissão ALTER SETTINGS é implicitamente mantida pelas funções de servidor fixas **sysadmin** e **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="1c853-126">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="1c853-127">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1c853-127">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-default-language-option"></a><span data-ttu-id="1c853-128">Para configurar a opção default language</span><span class="sxs-lookup"><span data-stu-id="1c853-128">To configure the default language option</span></span>  
  
1.  <span data-ttu-id="1c853-129">No Pesquisador de Objetos, clique com o botão direito do mouse em um servidor e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="1c853-129">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="1c853-130">Clique no nó **Configuração de servidores diversos** .</span><span class="sxs-lookup"><span data-stu-id="1c853-130">Click the **Misc server settings** node.</span></span>  
  
3.  <span data-ttu-id="1c853-131">Na caixa **Idioma padrão para usuários** , escolha o idioma no qual o [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] deve exibir as mensagens do sistema.</span><span class="sxs-lookup"><span data-stu-id="1c853-131">In the **Default language for users** box, choose the language in which [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] should display system messages.</span></span>  
  
     <span data-ttu-id="1c853-132">O idioma padrão é inglês.</span><span class="sxs-lookup"><span data-stu-id="1c853-132">The default language is English.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="1c853-133">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="1c853-133">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-default-language-option"></a><span data-ttu-id="1c853-134">Para configurar a opção default language</span><span class="sxs-lookup"><span data-stu-id="1c853-134">To configure the default language option</span></span>  
  
1.  <span data-ttu-id="1c853-135">Conecte-se ao [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1c853-135">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="1c853-136">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="1c853-136">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="1c853-137">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="1c853-137">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="1c853-138">Este exemplo mostra como usar [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) para configurar a opção `default language` como francês (`2`).</span><span class="sxs-lookup"><span data-stu-id="1c853-138">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to configure the `default language` option to French (`2`).</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'default language', 2 ;  
GO  
RECONFIGURE ;  
GO  
```  
  
 <span data-ttu-id="1c853-139">Para obter mais informações, veja [Opções de configuração do servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="1c853-139">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-default-language-option"></a><a name="FollowUp"></a> <span data-ttu-id="1c853-140">Acompanhamento: depois de configurar a opção default language</span><span class="sxs-lookup"><span data-stu-id="1c853-140">Follow Up: After you configure the default language option</span></span>  
 <span data-ttu-id="1c853-141">A configuração entra em vigor imediatamente sem reiniciar o servidor.</span><span class="sxs-lookup"><span data-stu-id="1c853-141">The setting takes effect immediately without restarting the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c853-142">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="1c853-142">See Also</span></span>  
 <span data-ttu-id="1c853-143">[CREATE LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-login-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1c853-143">[CREATE LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-login-transact-sql) </span></span>  
 <span data-ttu-id="1c853-144">[ALTER LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-login-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1c853-144">[ALTER LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-login-transact-sql) </span></span>  
 <span data-ttu-id="1c853-145">[CREATE USER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-user-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1c853-145">[CREATE USER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-user-transact-sql) </span></span>  
 <span data-ttu-id="1c853-146">[ALTER USER &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-user-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1c853-146">[ALTER USER &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-user-transact-sql) </span></span>  
 <span data-ttu-id="1c853-147">[CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1c853-147">[CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span></span>  
 <span data-ttu-id="1c853-148">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1c853-148">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 <span data-ttu-id="1c853-149">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1c853-149">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="1c853-150">[Opções de configuração do servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="1c853-150">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="1c853-151">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="1c853-151">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
