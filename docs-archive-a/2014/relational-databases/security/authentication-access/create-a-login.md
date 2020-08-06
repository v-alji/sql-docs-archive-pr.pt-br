---
title: Criar um logon | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- SQL12.SWB.LOGIN.SERVERROLES.F1
- sql12.swb.login.databaseaccess.f1
- sql12.swb.login.general.f1
- sql12.swb.login.effectivepermissions.f1
- sql12.swb.login.status.f1
helpviewer_keywords:
- authentication [SQL Server], logins
- logins [SQL Server], creating
- creating logins with Management Studio
- Create login [SQL Server]
- SQL Server logins
ms.assetid: fb163e47-1546-4682-abaa-8c9494e9ddc7
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: e476880103a69ae016c6720f36e26ef884db6f5d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679805"
---
# <a name="create-a-login"></a><span data-ttu-id="3e02e-102">Crie um logon</span><span class="sxs-lookup"><span data-stu-id="3e02e-102">Create a Login</span></span>
  <span data-ttu-id="3e02e-103">Este tópico descreve como criar um logon no [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3e02e-103">This topic describes how to create a login in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span> <span data-ttu-id="3e02e-104">Um logon é a identidade da pessoa ou do processo que está se conectando a uma instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3e02e-104">A login is the identity of the person or process that is connecting to an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="3e02e-105">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="3e02e-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="3e02e-106">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="3e02e-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="3e02e-107">Tela de fundo</span><span class="sxs-lookup"><span data-stu-id="3e02e-107">Background</span></span>](#Background)  
  
     [<span data-ttu-id="3e02e-108">Segurança</span><span class="sxs-lookup"><span data-stu-id="3e02e-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="3e02e-109">**Para criar um logon usando:**</span><span class="sxs-lookup"><span data-stu-id="3e02e-109">**To create a login, using:**</span></span>  
  
     [<span data-ttu-id="3e02e-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="3e02e-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="3e02e-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="3e02e-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="3e02e-112">**Acompanhamento:**  [etapas a serem executadas após criar um logon](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="3e02e-112">**Follow Up:**  [Steps to take after you create a login](#FollowUp)</span></span>  
  
##  <a name="background"></a><a name="Background"></a> <span data-ttu-id="3e02e-113">Plano de fundo</span><span class="sxs-lookup"><span data-stu-id="3e02e-113">Background</span></span>  
 <span data-ttu-id="3e02e-114">Um logon é uma entidade de segurança ou uma entidade que pode ser autenticada por um sistema seguro.</span><span class="sxs-lookup"><span data-stu-id="3e02e-114">A login is a security principal, or an entity that can be authenticated by a secure system.</span></span> <span data-ttu-id="3e02e-115">Usuários precisam de um logon para se conectar ao [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3e02e-115">Users need a login to connect to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="3e02e-116">Você pode criar um logon com base em uma entidade de segurança do Windows (como um usuário de domínio ou um grupo de domínio do Windows) ou pode criar um logon que não esteja baseado em uma entidade de segurança do Windows (como um logon do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] ).</span><span class="sxs-lookup"><span data-stu-id="3e02e-116">You can create a login based on a Windows principal (such as a domain user or a Windows domain group) or you can create a login that is not based on a Windows principal (such as an [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] login).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3e02e-117">Para usar a Autenticação do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], o [!INCLUDE[ssDE](../../../includes/ssde-md.md)] deve usar a autenticação de modo misto.</span><span class="sxs-lookup"><span data-stu-id="3e02e-117">To use [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Authentication, the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] must use mixed mode authentication.</span></span> <span data-ttu-id="3e02e-118">Para obter mais informações, veja [Escolher um modo de autenticação](../choose-an-authentication-mode.md).</span><span class="sxs-lookup"><span data-stu-id="3e02e-118">For more information, see [Choose an Authentication Mode](../choose-an-authentication-mode.md).</span></span>  
  
 <span data-ttu-id="3e02e-119">Como uma entidade de segurança, as permissões podem ser concedidas a logons.</span><span class="sxs-lookup"><span data-stu-id="3e02e-119">As a security principal, permissions can be granted to logins.</span></span> <span data-ttu-id="3e02e-120">O escopo de um logon é o [!INCLUDE[ssDE](../../../includes/ssde-md.md)]inteiro.</span><span class="sxs-lookup"><span data-stu-id="3e02e-120">The scope of a login is the whole [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span> <span data-ttu-id="3e02e-121">Para se conectar a um banco de dados específico na instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], um logon deve ser mapeado para um usuário de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="3e02e-121">To connect to a specific database on the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], a login must be mapped to a database user.</span></span> <span data-ttu-id="3e02e-122">Permissões, e não o logon, são concedidas dentro do banco de dados e são negadas ao usuário de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="3e02e-122">Permissions inside the database are granted and denied to the database user, not the login.</span></span> <span data-ttu-id="3e02e-123">Permissões que têm o escopo da instância inteira do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (por exemplo, a permissão `CREATE ENDPOINT`) podem ser concedidas a um logon.</span><span class="sxs-lookup"><span data-stu-id="3e02e-123">Permissions that have the scope of the whole instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (for example, the `CREATE ENDPOINT` permission) can be granted to a login.</span></span>  
  
##  <a name="security"></a><a name="Security"></a> <span data-ttu-id="3e02e-124">Segurança</span><span class="sxs-lookup"><span data-stu-id="3e02e-124">Security</span></span>  
  
### <a name="permissions"></a><span data-ttu-id="3e02e-125">Permissões</span><span class="sxs-lookup"><span data-stu-id="3e02e-125">Permissions</span></span>  
 <span data-ttu-id="3e02e-126">Requer a permissão `ALTER ANY LOGIN` ou `ALTER LOGIN` no servidor.</span><span class="sxs-lookup"><span data-stu-id="3e02e-126">Requires `ALTER ANY LOGIN` or `ALTER LOGIN` permission on the server.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="3e02e-127">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="3e02e-127">Using SQL Server Management Studio</span></span>  
  
##### <a name="to-create-a-sql-server-login"></a><span data-ttu-id="3e02e-128">Para criar um logon do SQL Server</span><span class="sxs-lookup"><span data-stu-id="3e02e-128">To create a SQL Server login</span></span>  
  
1.  <span data-ttu-id="3e02e-129">No Pesquisador de Objetos, expanda a pasta da instância de servidor no qual deseja criar o novo logon.</span><span class="sxs-lookup"><span data-stu-id="3e02e-129">In Object Explorer, expand the folder of the server instance in which you want to create the new login.</span></span>  
  
2.  <span data-ttu-id="3e02e-130">Clique com o botão direito do mouse na pasta **Segurança**, aponte para **Novo** e selecione **Logon...** .</span><span class="sxs-lookup"><span data-stu-id="3e02e-130">Right-click the **Security** folder, point to **New**, and select **Login...**.</span></span>  
  
3.  <span data-ttu-id="3e02e-131">Na caixa de diálogo **Logon – Novo**, na página **Geral**, insira o nome de um usuário na caixa **Nome de logon**.</span><span class="sxs-lookup"><span data-stu-id="3e02e-131">In the **Login - New** dialog box, on the **General** page, enter the name of a user in the **Login name** box.</span></span> <span data-ttu-id="3e02e-132">Como alternativa, clique em **Pesquisar...** para abrir a caixa de diálogo **Selecionar Usuário ou Grupo**.</span><span class="sxs-lookup"><span data-stu-id="3e02e-132">Alternately, click **Search...** to open the **Select User or Group** dialog box.</span></span>  
  
     <span data-ttu-id="3e02e-133">Se você clicar em **Pesquisar...** :</span><span class="sxs-lookup"><span data-stu-id="3e02e-133">If you click **Search...**:</span></span>  
  
    1.  <span data-ttu-id="3e02e-134">Em **Selecionar este tipo de objeto**, clique em **Tipos de Objeto...** para abrir a caixa de diálogo **Tipos de Objeto** e selecione uma ou todas as seguintes opções: **Entidades de segurança internas**, **Grupos** e **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="3e02e-134">Under **Select this object type**, click **Object Types...** to open the **Object Types** dialog box and select any or all of the following: **Built-in security principals**, **Groups**, and **Users**.</span></span> <span data-ttu-id="3e02e-135">**Entidades de segurança internas** e **Usuários** estão selecionados por padrão.</span><span class="sxs-lookup"><span data-stu-id="3e02e-135">**Built-in security principals** and **Users** are selected by default.</span></span> <span data-ttu-id="3e02e-136">Quando terminar, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="3e02e-136">When finished, click **OK**.</span></span>  
  
    2.  <span data-ttu-id="3e02e-137">Em **Desta localização**, clique em **Localizações...** para abrir a caixa de diálogo **Localizações** e selecione um dos locais de servidor disponíveis.</span><span class="sxs-lookup"><span data-stu-id="3e02e-137">Under **From this location**, click **Locations...** to open the **Locations** dialog box and select one of the available server locations.</span></span> <span data-ttu-id="3e02e-138">Quando terminar, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="3e02e-138">When finished, click **OK**.</span></span>  
  
    3.  <span data-ttu-id="3e02e-139">Sob **Inserir os nomes de objeto a serem selecionados (exemplos)** , insira o nome de usuário ou de grupo que você deseja localizar.</span><span class="sxs-lookup"><span data-stu-id="3e02e-139">Under **Enter the object name to select (examples)**, enter the user or group name that you want to find.</span></span> <span data-ttu-id="3e02e-140">Para obter mais informações, consulte [Caixa de Diálogo Selecionar Usuários, Computadores ou Grupos](https://technet.microsoft.com/library/cc771712.aspx).</span><span class="sxs-lookup"><span data-stu-id="3e02e-140">For more information, see [Select Users, Computers, or Groups Dialog Box](https://technet.microsoft.com/library/cc771712.aspx).</span></span>  
  
    4.  <span data-ttu-id="3e02e-141">Clique em **Avançado...** para mais opções de pesquisa avançada.</span><span class="sxs-lookup"><span data-stu-id="3e02e-141">Click **Advanced...** for more advanced search options.</span></span> <span data-ttu-id="3e02e-142">Para obter mais informações, veja [Caixa de Diálogo Selecionar Usuários, Computadores ou Grupos – Página Avançada](https://technet.microsoft.com/library/cc733110.aspx).</span><span class="sxs-lookup"><span data-stu-id="3e02e-142">For more information, see [Select Users, Computers, or Groups Dialog Box - Advanced Page](https://technet.microsoft.com/library/cc733110.aspx).</span></span>  
  
    5.  <span data-ttu-id="3e02e-143">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="3e02e-143">Click **OK**.</span></span>  
  
4.  <span data-ttu-id="3e02e-144">Para criar um logon fundado em uma entidade de segurança de Windows, selecione **Autenticação do Windows**.</span><span class="sxs-lookup"><span data-stu-id="3e02e-144">To create a login based on a Windows principal, select **Windows authentication**.</span></span> <span data-ttu-id="3e02e-145">Essa é a seleção padrão.</span><span class="sxs-lookup"><span data-stu-id="3e02e-145">This is the default selection.</span></span>  
  
5.  <span data-ttu-id="3e02e-146">Para criar um logon salvo em um banco de dados do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , selecione **Autenticação do SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="3e02e-146">To create a login that is saved on a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] database, select **SQL Server authentication**.</span></span>  
  
    1.  <span data-ttu-id="3e02e-147">Na caixa **Senha** , digite uma senha para o novo usuário.</span><span class="sxs-lookup"><span data-stu-id="3e02e-147">In the **Password** box, enter a password for the new user.</span></span> <span data-ttu-id="3e02e-148">Insira novamente essa senha na caixa **Confirmar Senha** .</span><span class="sxs-lookup"><span data-stu-id="3e02e-148">Enter that password again into the **Confirm Password** box.</span></span>  
  
    2.  <span data-ttu-id="3e02e-149">Ao alterar uma senha existente, selecione **Especificar senha antiga**e digite a senha antiga na caixa **Senha antiga** .</span><span class="sxs-lookup"><span data-stu-id="3e02e-149">When changing an existing password, select **Specify old password**, and then type the old password in the **Old password** box.</span></span>  
  
    3.  <span data-ttu-id="3e02e-150">Para impor opções de política de senha para complexidade e execução, selecione **Impor política de senha**.</span><span class="sxs-lookup"><span data-stu-id="3e02e-150">To enforce password policy options for complexity and enforcement, select **Enforce password policy**.</span></span> <span data-ttu-id="3e02e-151">Para obter mais informações, consulte [Password Policy](../password-policy.md).</span><span class="sxs-lookup"><span data-stu-id="3e02e-151">For more information, see [Password Policy](../password-policy.md).</span></span> <span data-ttu-id="3e02e-152">Esta será uma opção padrão quando **Autenticação do SQL Server** estiver selecionada.</span><span class="sxs-lookup"><span data-stu-id="3e02e-152">This is a default option when **SQL Server authentication** is selected.</span></span>  
  
    4.  <span data-ttu-id="3e02e-153">Para impor opções de política de senha para expiração, selecione **Impor expiração de senha**.</span><span class="sxs-lookup"><span data-stu-id="3e02e-153">To enforce password policy options for expiration, select **Enforce password expiration**.</span></span> <span data-ttu-id="3e02e-154">**Impor política de senha** deve ser selecionada para habilitar esta caixa de seleção.</span><span class="sxs-lookup"><span data-stu-id="3e02e-154">**Enforce password policy** must be selected to enable this checkbox.</span></span> <span data-ttu-id="3e02e-155">Esta será uma opção padrão quando **Autenticação do SQL Server** estiver selecionada.</span><span class="sxs-lookup"><span data-stu-id="3e02e-155">This is a default option when **SQL Server authentication** is selected.</span></span>  
  
    5.  <span data-ttu-id="3e02e-156">Para forçar o usuário a criar uma nova senha depois da primeira vez que o logon for usado, selecione **O usuário deve alterar senha a próximo logon**.</span><span class="sxs-lookup"><span data-stu-id="3e02e-156">To force the user to create a new password after the first time the login is used, select **User must change password at next login**.</span></span> <span data-ttu-id="3e02e-157">**Impor expiração de senha** deve ser selecionada para habilitar esta caixa de seleção.</span><span class="sxs-lookup"><span data-stu-id="3e02e-157">**Enforce password expiration** must be selected to enable this checkbox.</span></span> <span data-ttu-id="3e02e-158">Esta será uma opção padrão quando **Autenticação do SQL Server** estiver selecionada.</span><span class="sxs-lookup"><span data-stu-id="3e02e-158">This is a default option when **SQL Server authentication** is selected.</span></span>  
  
6.  <span data-ttu-id="3e02e-159">Para associar o logon a um certificado de segurança autônomo, selecione **Mapeado para certificado** e selecione o nome de um certificado existente na lista.</span><span class="sxs-lookup"><span data-stu-id="3e02e-159">To associate the login with a stand-alone security certificate, select **Mapped to certificate** and then select the name of an existing certificate from the list.</span></span>  
  
7.  <span data-ttu-id="3e02e-160">Para associar o logon a uma chave assimétrica autônoma, selecione **Mapeado para chave assimétrica** e selecione o nome de uma chave existente na lista.</span><span class="sxs-lookup"><span data-stu-id="3e02e-160">To associate the login with a stand-alone asymmetric key, select **Mapped to asymmetric key** to, and then select the name of an existing key from the list.</span></span>  
  
8.  <span data-ttu-id="3e02e-161">Para associar o logon a uma credencial de segurança, marque a caixa de seleção **Mapeado para Credencial** e então selecione uma credencial existente na lista ou clique em **Adicionar** para criar uma nova credencial.</span><span class="sxs-lookup"><span data-stu-id="3e02e-161">To associate the login with a security credential, select the **Mapped to Credential** check box, and then either select an existing credential from the list or click **Add** to create a new credential.</span></span> <span data-ttu-id="3e02e-162">Para remover um mapeamento a uma credencial de segurança do logon, selecione a credencial de **Credenciais Mapeadas** e clique em **Remover**.</span><span class="sxs-lookup"><span data-stu-id="3e02e-162">To remove a mapping to a security credential from the login, select the credential from **Mapped Credentials** and click **Remove**.</span></span> <span data-ttu-id="3e02e-163">Para obter mais informações sobre credenciais em geral, veja [Credenciais &#40;Mecanismo de Banco de Dados&#41;](credentials-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="3e02e-163">For more information about credentials in general, see [Credentials &#40;Database Engine&#41;](credentials-database-engine.md).</span></span>  
  
9. <span data-ttu-id="3e02e-164">Na lista **Banco de dados padrão** , selecione um banco de dados padrão para o logon.</span><span class="sxs-lookup"><span data-stu-id="3e02e-164">From the **Default database** list, select a default database for the login.</span></span> <span data-ttu-id="3e02e-165">**Master** é o padrão dessa opção.</span><span class="sxs-lookup"><span data-stu-id="3e02e-165">**Master** is the default for this option.</span></span>  
  
10. <span data-ttu-id="3e02e-166">Na lista **Idioma padrão** , selecione um idioma padrão para o logon.</span><span class="sxs-lookup"><span data-stu-id="3e02e-166">From the **Default language** list, select a default language for the login.</span></span>  
  
11. [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
### <a name="additional-options"></a><span data-ttu-id="3e02e-167">Opções adicionais</span><span class="sxs-lookup"><span data-stu-id="3e02e-167">Additional Options</span></span>  
 <span data-ttu-id="3e02e-168">A caixa de diálogo **Logon – Novo** também oferece opções em quatro páginas adicionais: **Funções de Servidor**, **Mapeamento de Usuário**, **Protegíveis** e **Status**.</span><span class="sxs-lookup"><span data-stu-id="3e02e-168">The **Login - New** dialog box also offers options on four additional pages: **Server Roles**, **User Mapping**, **Securables**, and **Status**.</span></span>  
  
### <a name="server-roles"></a><span data-ttu-id="3e02e-169">Funções de Servidor</span><span class="sxs-lookup"><span data-stu-id="3e02e-169">Server Roles</span></span>  
 <span data-ttu-id="3e02e-170">A página **Funções de Servidor** lista todas as funções possíveis que podem ser atribuídas ao novo logon.</span><span class="sxs-lookup"><span data-stu-id="3e02e-170">The **Server Roles** page lists all possible roles that can be assigned to the new login.</span></span> <span data-ttu-id="3e02e-171">As seguintes opções estão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="3e02e-171">The following options are available:</span></span>  
  
 <span data-ttu-id="3e02e-172">Caixa de seleção**bulkadmin**</span><span class="sxs-lookup"><span data-stu-id="3e02e-172">**bulkadmin** check box</span></span>  
 <span data-ttu-id="3e02e-173">Os membros da função de servidor fixa **bulkadmin** podem executar a instrução BULK INSERT.</span><span class="sxs-lookup"><span data-stu-id="3e02e-173">Members of the **bulkadmin** fixed server role can run the BULK INSERT statement.</span></span>  
  
 <span data-ttu-id="3e02e-174">Caixa de seleção**dbcreator**</span><span class="sxs-lookup"><span data-stu-id="3e02e-174">**dbcreator** check box</span></span>  
 <span data-ttu-id="3e02e-175">Os membros da função de servidor fixa **dbcreator** podem criar, alterar, remover e restaurar qualquer banco de dados.</span><span class="sxs-lookup"><span data-stu-id="3e02e-175">Members of the **dbcreator** fixed server role can create, alter, drop, and restore any database.</span></span>  
  
 <span data-ttu-id="3e02e-176">Caixa de seleção**diskadmin**</span><span class="sxs-lookup"><span data-stu-id="3e02e-176">**diskadmin** check box</span></span>  
 <span data-ttu-id="3e02e-177">Os membros da função de servidor fixa **diskadmin** podem gerenciar arquivos em disco.</span><span class="sxs-lookup"><span data-stu-id="3e02e-177">Members of the **diskadmin** fixed server role can manage disk files.</span></span>  
  
 <span data-ttu-id="3e02e-178">Caixa de seleção**processadmin**</span><span class="sxs-lookup"><span data-stu-id="3e02e-178">**processadmin** check box</span></span>  
 <span data-ttu-id="3e02e-179">Os membros da função de servidor fixa **processadmin** podem encerrar processos em execução em uma instância do [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3e02e-179">Members of the **processadmin** fixed server role can terminate processes running in an instance of the [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
 <span data-ttu-id="3e02e-180">Caixa de seleção**public**</span><span class="sxs-lookup"><span data-stu-id="3e02e-180">**public** check box</span></span>  
 <span data-ttu-id="3e02e-181">Todos os usuários, grupos e funções do SQL Server pertencem à função de servidor fixa **public** .</span><span class="sxs-lookup"><span data-stu-id="3e02e-181">All SQL Server users, groups, and roles belong to the **public** fixed server role by default.</span></span>  
  
 <span data-ttu-id="3e02e-182">Caixa de seleção**securityadmin**</span><span class="sxs-lookup"><span data-stu-id="3e02e-182">**securityadmin** check box</span></span>  
 <span data-ttu-id="3e02e-183">Os membros da função de servidor fixa **securityadmin** gerenciam logons e suas propriedades.</span><span class="sxs-lookup"><span data-stu-id="3e02e-183">Members of the **securityadmin** fixed server role manage logins and their properties.</span></span> <span data-ttu-id="3e02e-184">Eles podem CONCEDER, NEGAR e REVOGAR permissões de nível de servidor.</span><span class="sxs-lookup"><span data-stu-id="3e02e-184">They can GRANT, DENY, and REVOKE server-level permissions.</span></span> <span data-ttu-id="3e02e-185">Eles também podem CONCEDER, NEGAR e REVOGAR permissões de nível de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="3e02e-185">They can also GRANT, DENY, and REVOKE database-level permissions.</span></span> <span data-ttu-id="3e02e-186">Além disso, eles podem redefinir senhas para logons do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3e02e-186">Additionally, they can reset passwords for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] logins.</span></span>  
  
 <span data-ttu-id="3e02e-187">Caixa de seleção**serveradmin**</span><span class="sxs-lookup"><span data-stu-id="3e02e-187">**serveradmin** check box</span></span>  
 <span data-ttu-id="3e02e-188">Os membros da função de servidor fixa **serveradmin** podem alterar as opções de configuração de todo o servidor e fechar o servidor.</span><span class="sxs-lookup"><span data-stu-id="3e02e-188">Members of the **serveradmin** fixed server role can change server-wide configuration options and shut down the server.</span></span>  
  
 <span data-ttu-id="3e02e-189">Caixa de seleção**setupadmin**</span><span class="sxs-lookup"><span data-stu-id="3e02e-189">**setupadmin** check box</span></span>  
 <span data-ttu-id="3e02e-190">Os membros da função de servidor fixa **setupadmin** podem adicionar e remover servidores vinculados e podem executar alguns procedimentos armazenados no sistema.</span><span class="sxs-lookup"><span data-stu-id="3e02e-190">Members of the **setupadmin** fixed server role can add and remove linked servers, and they can execute some system stored procedures.</span></span>  
  
 <span data-ttu-id="3e02e-191">Caixa de seleção**sysadmin**</span><span class="sxs-lookup"><span data-stu-id="3e02e-191">**sysadmin** check box</span></span>  
 <span data-ttu-id="3e02e-192">Os membros da função de servidor fixa **sysadmin** podem executar qualquer atividade no [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3e02e-192">Members of the **sysadmin** fixed server role can perform any activity in the [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
### <a name="user-mapping"></a><span data-ttu-id="3e02e-193">Mapeamento de Usuário</span><span class="sxs-lookup"><span data-stu-id="3e02e-193">User Mapping</span></span>  
 <span data-ttu-id="3e02e-194">A página **Mapeamento de Usuário** lista todos os possíveis bancos de dados e associações de função de banco de dados nesses bancos de dados que podem ser se aplicados ao logon.</span><span class="sxs-lookup"><span data-stu-id="3e02e-194">The **User Mapping** page lists all possible databases and the database role memberships on those databases that can be applied to the login.</span></span> <span data-ttu-id="3e02e-195">Os bancos de dados selecionados determinam as associações de função que estão disponíveis para o logon.</span><span class="sxs-lookup"><span data-stu-id="3e02e-195">The databases selected determine the role memberships that are available for the login.</span></span> <span data-ttu-id="3e02e-196">As opções a seguir estão disponíveis nesta página:</span><span class="sxs-lookup"><span data-stu-id="3e02e-196">The following options are available on this page:</span></span>  
  
 <span data-ttu-id="3e02e-197">**Usuários mapeados para este logon**</span><span class="sxs-lookup"><span data-stu-id="3e02e-197">**Users mapped to this login**</span></span>  
 <span data-ttu-id="3e02e-198">Selecione os bancos de dados que este logon pode acessar.</span><span class="sxs-lookup"><span data-stu-id="3e02e-198">Select the databases that this login can access.</span></span> <span data-ttu-id="3e02e-199">Quando você seleciona um banco de dados, as funções de banco de dados válidas dele são exibidas no painel **Associação à função de banco de dados para:** _database_name_.</span><span class="sxs-lookup"><span data-stu-id="3e02e-199">When you select a database, its valid database roles are displayed in the **Database role membership for:** _database_name_ pane.</span></span>  
  
 <span data-ttu-id="3e02e-200">**Map**</span><span class="sxs-lookup"><span data-stu-id="3e02e-200">**Map**</span></span>  
 <span data-ttu-id="3e02e-201">Permita que o logon acesse os bancos de dados listados abaixo.</span><span class="sxs-lookup"><span data-stu-id="3e02e-201">Allow the login to access the databases listed below.</span></span>  
  
 <span data-ttu-id="3e02e-202">**Backup de banco de dados**</span><span class="sxs-lookup"><span data-stu-id="3e02e-202">**Database**</span></span>  
 <span data-ttu-id="3e02e-203">Liste os bancos de dados disponíveis no servidor.</span><span class="sxs-lookup"><span data-stu-id="3e02e-203">Lists the databases available on the server.</span></span>  
  
 <span data-ttu-id="3e02e-204">**Usuário**</span><span class="sxs-lookup"><span data-stu-id="3e02e-204">**User**</span></span>  
 <span data-ttu-id="3e02e-205">Especifique um usuário de banco de dados a ser mapeado para o logon.</span><span class="sxs-lookup"><span data-stu-id="3e02e-205">Specify a database user to map to the login.</span></span> <span data-ttu-id="3e02e-206">Por padrão, o usuário de banco de dados tem o mesmo nome do logon.</span><span class="sxs-lookup"><span data-stu-id="3e02e-206">By default, the database user has the same name as the login.</span></span>  
  
 <span data-ttu-id="3e02e-207">**Esquema Padrão**</span><span class="sxs-lookup"><span data-stu-id="3e02e-207">**Default Schema**</span></span>  
 <span data-ttu-id="3e02e-208">Especifica o esquema padrão do usuário.</span><span class="sxs-lookup"><span data-stu-id="3e02e-208">Specifies the default schema of the user.</span></span> <span data-ttu-id="3e02e-209">Quando um usuário é criado pela primeira vez, seu esquema padrão é **dbo**.</span><span class="sxs-lookup"><span data-stu-id="3e02e-209">When a user is first created, its default schema is **dbo**.</span></span> <span data-ttu-id="3e02e-210">É possível especificar um esquema padrão que ainda não existe.</span><span class="sxs-lookup"><span data-stu-id="3e02e-210">It is possible to specify a default schema that does not yet exist.</span></span> <span data-ttu-id="3e02e-211">Você não pode especificar um esquema padrão para um usuário mapeado para um grupo do Windows, um certificado ou uma chave assimétrica.</span><span class="sxs-lookup"><span data-stu-id="3e02e-211">You cannot specify a default schema for a user that is mapped to a Windows group, a certificate, or an asymmetric key.</span></span>  
  
 <span data-ttu-id="3e02e-212">**Conta Convidado habilitada para:** _database_name_</span><span class="sxs-lookup"><span data-stu-id="3e02e-212">**Guest account enabled for:**  _database_name_</span></span>  
 <span data-ttu-id="3e02e-213">Atributo somente leitura que indica se a conta de Convidado está habilitada no banco de dados selecionado.</span><span class="sxs-lookup"><span data-stu-id="3e02e-213">Read-only attribute indicating whether the Guest account is enabled on the selected database.</span></span> <span data-ttu-id="3e02e-214">Use a página **Status** da caixa de diálogo **Propriedades de Logon** da conta Convidado para habilitar ou desabilitar a conta Convidado.</span><span class="sxs-lookup"><span data-stu-id="3e02e-214">Use the **Status** page of the **Login Properties** dialog box of the Guest account to enable or disable the Guest account.</span></span>  
  
 <span data-ttu-id="3e02e-215">**Associação à função de banco de dados para:** _database_name_</span><span class="sxs-lookup"><span data-stu-id="3e02e-215">**Database role membership for:**  _database_name_</span></span>  
 <span data-ttu-id="3e02e-216">Selecione as funções para o usuário no banco de dados especificado.</span><span class="sxs-lookup"><span data-stu-id="3e02e-216">Select the roles for the user in the specified database.</span></span> <span data-ttu-id="3e02e-217">Todos os usuários são membros da função **pública** em todo banco de dados e não podem ser removidos.</span><span class="sxs-lookup"><span data-stu-id="3e02e-217">All users are members of the **public** role in every database and cannot be removed.</span></span> <span data-ttu-id="3e02e-218">Para obter mais informações sobre as funções de banco de dados, veja [Funções no nível de banco de dados](database-level-roles.md).</span><span class="sxs-lookup"><span data-stu-id="3e02e-218">For more information about database roles, see [Database-Level Roles](database-level-roles.md).</span></span>  
  
### <a name="securables"></a><span data-ttu-id="3e02e-219">Protegíveis</span><span class="sxs-lookup"><span data-stu-id="3e02e-219">Securables</span></span>  
 <span data-ttu-id="3e02e-220">A página **Protegíveis** lista todos os protegíveis e as permissões possíveis nesses protegíveis que podem ser concedidos ao logon.</span><span class="sxs-lookup"><span data-stu-id="3e02e-220">The **Securables** page lists all possible securables and the permissions on those securables that can be granted to the login.</span></span> <span data-ttu-id="3e02e-221">As opções a seguir estão disponíveis nesta página:</span><span class="sxs-lookup"><span data-stu-id="3e02e-221">The following options are available on this page:</span></span>  
  
 <span data-ttu-id="3e02e-222">**Grade superior**</span><span class="sxs-lookup"><span data-stu-id="3e02e-222">**Upper Grid**</span></span>  
 <span data-ttu-id="3e02e-223">Contém um ou mais itens para os quais podem ser definidas permissões.</span><span class="sxs-lookup"><span data-stu-id="3e02e-223">Contains one or more items for which permissions can be set.</span></span> <span data-ttu-id="3e02e-224">As colunas que são exibidas na grade superior variam, dependendo da entidade ou protegível.</span><span class="sxs-lookup"><span data-stu-id="3e02e-224">The columns that are displayed in the upper grid vary depending on the principal or securable.</span></span>  
  
 <span data-ttu-id="3e02e-225">Para adicionar itens à grade superior:</span><span class="sxs-lookup"><span data-stu-id="3e02e-225">To add items to the upper grid:</span></span>  
  
1.  <span data-ttu-id="3e02e-226">Clique em **Pesquisar**.</span><span class="sxs-lookup"><span data-stu-id="3e02e-226">Click **Search**.</span></span>  
  
2.  <span data-ttu-id="3e02e-227">Na caixa de diálogo **Adicionar objetos** , selecione uma das seguintes opções: **objetos específicos...**, **todos os objetos dos tipos...** ou_server_name_do **servidor**.</span><span class="sxs-lookup"><span data-stu-id="3e02e-227">In the **Add Objects** dialog box, select one of the following options: **Specific objects...**, **All objects of the types...**, or **The server**_server_name_.</span></span> [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
    > [!NOTE]  
    >  <span data-ttu-id="3e02e-228">**A seleção do servidor**_server_name_ preenche automaticamente a grade superior com todos os objetos protegíveis dos servidores.</span><span class="sxs-lookup"><span data-stu-id="3e02e-228">Selecting **The server**_server_name_ automatically fills the upper grid with all of that servers' securable objects.</span></span>  
  
3.  <span data-ttu-id="3e02e-229">Se você selecionar **Objetos específicos...** :</span><span class="sxs-lookup"><span data-stu-id="3e02e-229">If you select **Specific objects...**:</span></span>  
  
    1.  <span data-ttu-id="3e02e-230">Na caixa de diálogo **Selecionar Objetos**, em **Selecionar estes tipos de objeto**, clique em **Tipos de Objeto...** .</span><span class="sxs-lookup"><span data-stu-id="3e02e-230">In the **Select Objects** dialog box, under **Select these object types**, click **Object Types...**.</span></span>  
  
    2.  <span data-ttu-id="3e02e-231">Na caixa de diálogo **Selecionar Tipos de Objeto**, selecione um ou todos os seguintes tipos de objeto: **Pontos de extremidade**, **Logons**, **Servidores**, **Grupos de Disponibilidade** e **Funções de servidor**.</span><span class="sxs-lookup"><span data-stu-id="3e02e-231">In the **Select Object Types** dialog box, select any or all of the following object types: **Endpoints**, **Logins**, **Servers**, **Availability Groups**, and **Server roles**.</span></span> [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
    3.  <span data-ttu-id="3e02e-232">Em **Inserir os nomes de objeto a serem selecionados (exemplos)** , clique em **Procurar...** .</span><span class="sxs-lookup"><span data-stu-id="3e02e-232">Under **Enter the object names to select (examples)**, click **Browse...**.</span></span>  
  
    4.  <span data-ttu-id="3e02e-233">Na caixa de diálogo **Procurar por Objetos** , selecione qualquer um dos objetos disponíveis do tipo que você selecionou na caixa de diálogo **Selecionar Tipos de Objeto** e então clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="3e02e-233">In the **Browse for Objects** dialog box, select any of the available objects of the type that you selected in the **Select Object Types** dialog box, and then click **OK**.</span></span>  
  
    5.  <span data-ttu-id="3e02e-234">Na caixa de diálogo **Selecionar Objetos** , clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="3e02e-234">In the **Select Objects** dialog box, click **OK**.</span></span>  
  
4.  <span data-ttu-id="3e02e-235">Se você selecionar **Todos os objetos dos tipos...** , na caixa de diálogo **Selecionar Tipos de Objeto**, selecione um ou todos os seguintes tipos de objeto: **Pontos de extremidade**, **Logons**, **Servidores**, **Grupos de Disponibilidade** e **Funções de servidor**.</span><span class="sxs-lookup"><span data-stu-id="3e02e-235">If you select **All objects of the types...**, in the **Select Object Types** dialog box, select any or all of the following object types: **Endpoints**, **Logins**, **Servers**, **Availability Groups**, and **Server roles**.</span></span> [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
 <span data-ttu-id="3e02e-236">**Nome**</span><span class="sxs-lookup"><span data-stu-id="3e02e-236">**Name**</span></span>  
 <span data-ttu-id="3e02e-237">O nome de cada entidade ou protegível que é adicionado à grade.</span><span class="sxs-lookup"><span data-stu-id="3e02e-237">The name of each principal or securable that is added to the grid.</span></span>  
  
 <span data-ttu-id="3e02e-238">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="3e02e-238">**Type**</span></span>  
 <span data-ttu-id="3e02e-239">Descreve o tipo de cada item.</span><span class="sxs-lookup"><span data-stu-id="3e02e-239">Describes the type of each item.</span></span>  
  
 <span data-ttu-id="3e02e-240">**Guia Explícita**</span><span class="sxs-lookup"><span data-stu-id="3e02e-240">**Explicit Tab**</span></span>  
 <span data-ttu-id="3e02e-241">Lista as permissões possíveis para o protegível que está selecionado na grade superior.</span><span class="sxs-lookup"><span data-stu-id="3e02e-241">Lists the possible permissions for the securable that are selected in the upper grid.</span></span> <span data-ttu-id="3e02e-242">Nem todas as opções estão disponíveis para todas as permissões explícitas.</span><span class="sxs-lookup"><span data-stu-id="3e02e-242">Not all options are available for all explicit permissions.</span></span>  
  
 <span data-ttu-id="3e02e-243">**Permissões**</span><span class="sxs-lookup"><span data-stu-id="3e02e-243">**Permissions**</span></span>  
 <span data-ttu-id="3e02e-244">O nome da permissão.</span><span class="sxs-lookup"><span data-stu-id="3e02e-244">The name of the permission.</span></span>  
  
 <span data-ttu-id="3e02e-245">**Concessor**</span><span class="sxs-lookup"><span data-stu-id="3e02e-245">**Grantor**</span></span>  
 <span data-ttu-id="3e02e-246">A entidade que concedeu a permissão.</span><span class="sxs-lookup"><span data-stu-id="3e02e-246">The principal that granted the permission.</span></span>  
  
 <span data-ttu-id="3e02e-247">**Conceder**</span><span class="sxs-lookup"><span data-stu-id="3e02e-247">**Grant**</span></span>  
 <span data-ttu-id="3e02e-248">Selecione para conceder essa permissão ao logon.</span><span class="sxs-lookup"><span data-stu-id="3e02e-248">Select to grant this permission to the login.</span></span> <span data-ttu-id="3e02e-249">Desmarque para revogar essa permissão.</span><span class="sxs-lookup"><span data-stu-id="3e02e-249">Clear to revoke this permission.</span></span>  
  
 <span data-ttu-id="3e02e-250">**Com Concessão**</span><span class="sxs-lookup"><span data-stu-id="3e02e-250">**With Grant**</span></span>  
 <span data-ttu-id="3e02e-251">Reflete o estado da opção WITH GRANT para a permissão listada.</span><span class="sxs-lookup"><span data-stu-id="3e02e-251">Reflects the state of the WITH GRANT option for the listed permission.</span></span> <span data-ttu-id="3e02e-252">Essa caixa é somente leitura.</span><span class="sxs-lookup"><span data-stu-id="3e02e-252">This box is read-only.</span></span> <span data-ttu-id="3e02e-253">Para aplicar essa permissão, use a instrução [GRANT](/sql/t-sql/statements/grant-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="3e02e-253">To apply this permission, use the [GRANT](/sql/t-sql/statements/grant-transact-sql) statement.</span></span>  
  
 <span data-ttu-id="3e02e-254">**Deny**</span><span class="sxs-lookup"><span data-stu-id="3e02e-254">**Deny**</span></span>  
 <span data-ttu-id="3e02e-255">Selecione para negar essa permissão ao logon.</span><span class="sxs-lookup"><span data-stu-id="3e02e-255">Select to deny this permission to the login.</span></span> <span data-ttu-id="3e02e-256">Desmarque para revogar essa permissão.</span><span class="sxs-lookup"><span data-stu-id="3e02e-256">Clear to revoke this permission.</span></span>  
  
### <a name="status"></a><span data-ttu-id="3e02e-257">Status</span><span class="sxs-lookup"><span data-stu-id="3e02e-257">Status</span></span>  
 <span data-ttu-id="3e02e-258">A página **Status** lista algumas das opções de autenticação e de autorização que podem ser configuradas no logo do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] selecionado.</span><span class="sxs-lookup"><span data-stu-id="3e02e-258">The **Status** page lists some of the authentication and authorization options that can be configured on the selected [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] login.</span></span>  
  
 <span data-ttu-id="3e02e-259">As opções a seguir estão disponíveis nesta página:</span><span class="sxs-lookup"><span data-stu-id="3e02e-259">The following options are available on this page:</span></span>  
  
 <span data-ttu-id="3e02e-260">**Permissão para conexão com mecanismo de banco de dados**</span><span class="sxs-lookup"><span data-stu-id="3e02e-260">**Permission to connect to database engine**</span></span>  
 <span data-ttu-id="3e02e-261">Quando você trabalha nessa configuração, deve pensar no logon selecionado como uma entidade que pode ter a permissão concedida ou recusada em um protegível.</span><span class="sxs-lookup"><span data-stu-id="3e02e-261">When you work with this setting, you should think of the selected login as a principal that can be granted or denied permission on a securable.</span></span>  
  
 <span data-ttu-id="3e02e-262">Selecione **Conceder** para conceder a permissão CONNECT SQL ao logon.</span><span class="sxs-lookup"><span data-stu-id="3e02e-262">Select **Grant** to grant CONNECT SQL permission to the login.</span></span> <span data-ttu-id="3e02e-263">Selecione **Negar** para negar CONNECT SQL ao logon.</span><span class="sxs-lookup"><span data-stu-id="3e02e-263">Select **Deny** to deny CONNECT SQL to the login.</span></span>  
  
 <span data-ttu-id="3e02e-264">**Logon**</span><span class="sxs-lookup"><span data-stu-id="3e02e-264">**Login**</span></span>  
 <span data-ttu-id="3e02e-265">Quando você trabalha nessa configuração, deve pensar no logon selecionado como um registro em uma tabela.</span><span class="sxs-lookup"><span data-stu-id="3e02e-265">When you work with this setting, you should think of the selected login as a record in a table.</span></span> <span data-ttu-id="3e02e-266">As alterações dos valores listados aqui serão aplicadas ao registro.</span><span class="sxs-lookup"><span data-stu-id="3e02e-266">Changes to the values listed here will be applied to the record.</span></span>  
  
 <span data-ttu-id="3e02e-267">Um logon que foi desabilitado continua existindo como um registro.</span><span class="sxs-lookup"><span data-stu-id="3e02e-267">A login that has been disabled continues to exist as a record.</span></span> <span data-ttu-id="3e02e-268">Mas se tentar se conectar a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], o logon não será autenticado.</span><span class="sxs-lookup"><span data-stu-id="3e02e-268">But if it tries to connect to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], the login will not be authenticated.</span></span>  
  
 <span data-ttu-id="3e02e-269">Selecione esta opção para habilitar ou desabilitar o logon.</span><span class="sxs-lookup"><span data-stu-id="3e02e-269">Select this option to enable or disable this login.</span></span> <span data-ttu-id="3e02e-270">Esta opção usa a instrução ALTER LOGON com a opção ENABLE ou DISABLE.</span><span class="sxs-lookup"><span data-stu-id="3e02e-270">This option uses the ALTER LOGIN statement with the either ENABLE or DISABLE option.</span></span>  
  
 <span data-ttu-id="3e02e-271">**Autenticação do SQL Server**</span><span class="sxs-lookup"><span data-stu-id="3e02e-271">**SQL Server Authentication**</span></span>  
 <span data-ttu-id="3e02e-272">A caixa de seleção **O logon está bloqueado** só estará disponível se o logon selecionado se conectar usando a Autenticação do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] e se estiver bloqueado. Esta configuração é somente leitura.</span><span class="sxs-lookup"><span data-stu-id="3e02e-272">The check box **Login is locked out** is only available if the selected login connects using [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Authentication and the login has been locked out. This setting is read-only.</span></span> <span data-ttu-id="3e02e-273">Para desbloquear um logon bloqueado, execute ALTER LOGIN com a opção UNLOCK.</span><span class="sxs-lookup"><span data-stu-id="3e02e-273">To unlock a login that is locked out, execute ALTER LOGIN with the UNLOCK option.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="3e02e-274">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="3e02e-274">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-login-using-windows-authentication"></a><span data-ttu-id="3e02e-275">Para criar um logon usando a Autenticação do Windows</span><span class="sxs-lookup"><span data-stu-id="3e02e-275">To create a login using Windows Authentication</span></span>  
  
1.  <span data-ttu-id="3e02e-276">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3e02e-276">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="3e02e-277">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="3e02e-277">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="3e02e-278">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="3e02e-278">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- Create a login for SQL Server by specifying a server name and a Windows domain account name.  
  
    CREATE LOGIN [<domainName>\<loginName>] FROM WINDOWS;  
    GO  
  
    ```  
  
#### <a name="to-create-a-login-using-sql-server-authentication"></a><span data-ttu-id="3e02e-279">Para criar um logon usando a Autenticação do SQL Server</span><span class="sxs-lookup"><span data-stu-id="3e02e-279">To create a login using SQL Server Authentication</span></span>  
  
1.  <span data-ttu-id="3e02e-280">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3e02e-280">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="3e02e-281">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="3e02e-281">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="3e02e-282">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="3e02e-282">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- Creates the user "shcooper" for SQL Server using the security credential "RestrictedFaculty"   
    -- The user login starts with the password "Baz1nga," but that password must be changed after the first login.  
  
    CREATE LOGIN shcooper   
       WITH PASSWORD = 'Baz1nga' MUST_CHANGE,  
       CREDENTIAL = RestrictedFaculty;  
    GO  
  
    ```  
  
 <span data-ttu-id="3e02e-283">Para obter mais informações, veja [CREATE LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-login-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="3e02e-283">For more information, see [CREATE LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-login-transact-sql).</span></span>  
  
##  <a name="follow-up-steps-to-take-after-you-create-a-login"></a><a name="FollowUp"></a> <span data-ttu-id="3e02e-284">Acompanhamento: etapas a serem executadas após criar um logon</span><span class="sxs-lookup"><span data-stu-id="3e02e-284">Follow Up: Steps to take after you create a login</span></span>  
 <span data-ttu-id="3e02e-285">Após ser criado, o logon pode se conectar ao [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], mas não necessariamente tem permissão suficiente para executar qualquer trabalho útil.</span><span class="sxs-lookup"><span data-stu-id="3e02e-285">After creating a login, the login can connect to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], but does not necessarily have sufficient permission to perform any useful work.</span></span> <span data-ttu-id="3e02e-286">A lista a seguir fornece links a ações de logon comuns.</span><span class="sxs-lookup"><span data-stu-id="3e02e-286">The following list provides links to common login actions.</span></span>  
  
-   <span data-ttu-id="3e02e-287">Para associar o logon a uma função, veja [Unir uma função](join-a-role.md).</span><span class="sxs-lookup"><span data-stu-id="3e02e-287">To have the login join a role, see [Join a Role](join-a-role.md).</span></span>  
  
-   <span data-ttu-id="3e02e-288">Para autorizar um logon a usar um banco de dados, veja [Criar um usuário de banco de dados](../authentication-access/create-a-database-user.md).</span><span class="sxs-lookup"><span data-stu-id="3e02e-288">To authorize a login to use a database, see [Create a Database User](../authentication-access/create-a-database-user.md).</span></span>  
  
-   <span data-ttu-id="3e02e-289">Para conceder uma permissão a um logon, veja [Conceder uma permissão a uma entidade](grant-a-permission-to-a-principal.md).</span><span class="sxs-lookup"><span data-stu-id="3e02e-289">To grant a permission to a login, see [Grant a Permission to a Principal](grant-a-permission-to-a-principal.md).</span></span>  
  
  
