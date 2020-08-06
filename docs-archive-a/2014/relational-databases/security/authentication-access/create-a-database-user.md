---
title: Criar um usuário de banco de dados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- SQL12.SWB.DATABASEUSER.GENERAL.F1
- sql12.swb.user.securables.f1
helpviewer_keywords:
- database users, creating
- creating users with Management Studio
- mapping users
- users [SQL Server], creating
- database user additions [SQL Server]
- database users, mapping
- CREATE USER [Management Studio]
- users [SQL Server], adding
- mapping database users
ms.assetid: 782798d3-9552-4514-9f58-e87be4b264e4
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 97fc758c754f5fc8803e988d55147670fc3ff45b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679807"
---
# <a name="create-a-database-user"></a><span data-ttu-id="b5650-102">Criar um usuário de banco de dados</span><span class="sxs-lookup"><span data-stu-id="b5650-102">Create a Database User</span></span>
  <span data-ttu-id="b5650-103">Este tópico descreve como criar um usuário de banco de dados mapeado para um logon no [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b5650-103">This topic describes how to create a database user mapped to a login in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span> <span data-ttu-id="b5650-104">O usuário de banco de dados é a identidade do logon quando é conectado a um banco de dados.</span><span class="sxs-lookup"><span data-stu-id="b5650-104">The database user is the identity of the login when it is connected to a database.</span></span> <span data-ttu-id="b5650-105">O usuário de banco de dados pode usar o mesmo nome como o logon, mas isso não é requerido.</span><span class="sxs-lookup"><span data-stu-id="b5650-105">The database user can use the same name as the login, but that is not required.</span></span> <span data-ttu-id="b5650-106">Este tópico pressupõe que já exista um logon no [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b5650-106">This topic assumes that a login already exists in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="b5650-107">Para obter informações sobre como criar um logon, consulte [criar um logon](create-a-login.md).</span><span class="sxs-lookup"><span data-stu-id="b5650-107">For information about how to create a login, see [Create a Login](create-a-login.md).</span></span>  
  
 <span data-ttu-id="b5650-108">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="b5650-108">**In This Topic**</span></span>  
  
-   <span data-ttu-id="b5650-109">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="b5650-109">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="b5650-110">Tela de fundo</span><span class="sxs-lookup"><span data-stu-id="b5650-110">Background</span></span>](#Restrictions)  
  
     [<span data-ttu-id="b5650-111">Segurança</span><span class="sxs-lookup"><span data-stu-id="b5650-111">Security</span></span>](#Security)  
  
-   <span data-ttu-id="b5650-112">**Para criar um usuário de banco de dados usando:**</span><span class="sxs-lookup"><span data-stu-id="b5650-112">**To create a database user, using:**</span></span>  
  
     [<span data-ttu-id="b5650-113">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b5650-113">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="b5650-114">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b5650-114">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="b5650-115">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="b5650-115">Before You Begin</span></span>  
  
###  <a name="background"></a><a name="Restrictions"></a> <span data-ttu-id="b5650-116">Plano de fundo</span><span class="sxs-lookup"><span data-stu-id="b5650-116">Background</span></span>  
 <span data-ttu-id="b5650-117">Um usuário é uma entidade de segurança no nível de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="b5650-117">A user is a database level security principal.</span></span> <span data-ttu-id="b5650-118">Logons devem ser mapeados para um usuário de banco de dados para ser conectados a um banco de dados.</span><span class="sxs-lookup"><span data-stu-id="b5650-118">Logins must be mapped to a database user to connect to a database.</span></span> <span data-ttu-id="b5650-119">Um logon pode ser mapeado para bancos de dados diferentes como usuários diferentes, mas pode ser mapeado somente como um usuário em cada banco de dados.</span><span class="sxs-lookup"><span data-stu-id="b5650-119">A login can be mapped to different databases as different users but can only be mapped as one user in each database.</span></span> <span data-ttu-id="b5650-120">Em um banco de dados parcialmente independente, um usuário pode ser criado sem logon.</span><span class="sxs-lookup"><span data-stu-id="b5650-120">In a partially contained database, a user can be created that does not have a login.</span></span> <span data-ttu-id="b5650-121">Para obter mais informações sobre os usuários de banco de dados independente, veja [CREATE USER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-user-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b5650-121">For more information about contained database users, see [CREATE USER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-user-transact-sql).</span></span> <span data-ttu-id="b5650-122">Se o usuário convidado em um banco de dados estiver habilitado, um logon que não estiver mapeado para um usuário de banco de dados poderá acessar o banco de dados como um usuário convidado.</span><span class="sxs-lookup"><span data-stu-id="b5650-122">If the guest user in a database is enabled, a login that is not mapped to a database user can enter the database as the guest user.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="b5650-123">O usuário convidado normalmente é desabilitado.</span><span class="sxs-lookup"><span data-stu-id="b5650-123">The guest user is ordinarily disabled.</span></span> <span data-ttu-id="b5650-124">Não habilite o usuário convidado, a menos que seja necessário.</span><span class="sxs-lookup"><span data-stu-id="b5650-124">Do not enable the guest user unless it is necessary.</span></span>  
  
 <span data-ttu-id="b5650-125">Como uma entidade de segurança, permissões podem ser concedidas a usuários.</span><span class="sxs-lookup"><span data-stu-id="b5650-125">As a security principal, permissions can be granted to users.</span></span> <span data-ttu-id="b5650-126">O escopo de um usuário é o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="b5650-126">The scope of a user is the database.</span></span> <span data-ttu-id="b5650-127">Para se conectar a um banco de dados específico na instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], um logon deve ser mapeado para um usuário de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="b5650-127">To connect to a specific database on the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], a login must be mapped to a database user.</span></span> <span data-ttu-id="b5650-128">Permissões, e não o logon, são concedidas dentro do banco de dados e são negadas ao usuário de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="b5650-128">Permissions inside the database are granted and denied to the database user, not the login.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="b5650-129">Segurança</span><span class="sxs-lookup"><span data-stu-id="b5650-129">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="b5650-130">Permissões</span><span class="sxs-lookup"><span data-stu-id="b5650-130">Permissions</span></span>  
 <span data-ttu-id="b5650-131">Requer a permissão `ALTER ANY USER` no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="b5650-131">Requires `ALTER ANY USER` permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="b5650-132">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b5650-132">Using SQL Server Management Studio</span></span>  
  
##### <a name="to-create-a-database-user"></a><span data-ttu-id="b5650-133">Para criar um usuário de banco de dados</span><span class="sxs-lookup"><span data-stu-id="b5650-133">To create a database user</span></span>  
  
1.  <span data-ttu-id="b5650-134">No Pesquisador de Objetos, expanda a pasta **Bancos de Dados** .</span><span class="sxs-lookup"><span data-stu-id="b5650-134">In Object Explorer, expand the **Databases** folder.</span></span>  
  
2.  <span data-ttu-id="b5650-135">Expanda o banco de dados no qual o novo usuário de banco de dados será criado.</span><span class="sxs-lookup"><span data-stu-id="b5650-135">Expand the database in which to create the new database user.</span></span>  
  
3.  <span data-ttu-id="b5650-136">Clique com o botão direito do mouse na pasta **Segurança**, aponte para **Novo** e selecione **Usuário...** .</span><span class="sxs-lookup"><span data-stu-id="b5650-136">Right-click the **Security** folder, point to **New**, and select **User...**.</span></span>  
  
4.  <span data-ttu-id="b5650-137">Na caixa de diálogo **usuário do banco de dados – novo** , na página **geral** , selecione um dos seguintes tipos de usuário na lista **tipo de usuário** : **usuário do SQL com logon**, usuário do **SQL sem logon**, **usuário mapeado para um certificado**, **usuário mapeado para uma chave assimétrica**ou **usuário do Windows**.</span><span class="sxs-lookup"><span data-stu-id="b5650-137">In the **Database User - New** dialog box, on the **General** page, select one of the following user types from the **User type** list: **SQL user with login**, **SQL user without login**, **User mapped to a certificate**, **User mapped to an asymmetric key**, or **Windows user**.</span></span>  
  
5.  <span data-ttu-id="b5650-138">Na caixa **Nome do usuário** , digite um nome para o novo usuário.</span><span class="sxs-lookup"><span data-stu-id="b5650-138">In the **User name** box, enter a name for the new user.</span></span> <span data-ttu-id="b5650-139">Se você tiver escolhido **Usuário do Windows** na lista **Tipo de usuário**, também poderá clicar nas reticências **(...)** para abrir a caixa de diálogo **Selecionar Usuário ou Grupo**.</span><span class="sxs-lookup"><span data-stu-id="b5650-139">If you have chosen **Windows user** from the **User type** list, you can also click the ellipsis **(...)** to open the **Select User or Group** dialog box.</span></span>  
  
6.  <span data-ttu-id="b5650-140">Na caixa **Nome de logon** , digite o logon do usuário.</span><span class="sxs-lookup"><span data-stu-id="b5650-140">In the **Login name** box, enter the login for the user.</span></span> <span data-ttu-id="b5650-141">Como alternativa, clique nas reticências **(...)** para abrir a caixa de diálogo **Selecionar Logon**.</span><span class="sxs-lookup"><span data-stu-id="b5650-141">Alternately, click the ellipsis **(...)** to open the **Select Login** dialog box.</span></span> <span data-ttu-id="b5650-142">**Nome de logon** estará disponível se você ou selecionar **Usuário do SQL com logon** ou **Usuário do Windows** na lista **Tipo de usuário** .</span><span class="sxs-lookup"><span data-stu-id="b5650-142">**Login name** is available if you select either **SQL user with login** or **Windows user** from the **User type** list.</span></span>  
  
7.  <span data-ttu-id="b5650-143">Na caixa **Esquema padrão** , especifica o esquema que terá a propriedade dos objetos criados por esse usuário.</span><span class="sxs-lookup"><span data-stu-id="b5650-143">In the **Default schema** box, specifies the schema that will own objects created by this user.</span></span> <span data-ttu-id="b5650-144">Como alternativa, clique nas reticências **(...)** para abrir a caixa de diálogo **Selecionar Esquema**.</span><span class="sxs-lookup"><span data-stu-id="b5650-144">Alternately, click the ellipsis **(...)** to open the **Select Schema** dialog box.</span></span> <span data-ttu-id="b5650-145">**Esquema padrão** estará disponível se você ou selecionar **Usuário do SQL com logon**, **Usuário do SQL sem logon**ou **Usuário do Windows** na lista **Tipo de usuário** .</span><span class="sxs-lookup"><span data-stu-id="b5650-145">**Default schema** is available if you select either **SQL user with login**, **SQL user without login**, or **Windows user** from the **User type** list.</span></span>  
  
8.  <span data-ttu-id="b5650-146">Na caixa **Nome do certificado** , digite o certificado a ser usado para o usuário de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="b5650-146">In the **Certificate name** box, enter the certificate to be used for the database user.</span></span> <span data-ttu-id="b5650-147">Opcionalmente, clique nas reticências **(...)** para abrir a caixa de diálogo **Selecionar Certificado**.</span><span class="sxs-lookup"><span data-stu-id="b5650-147">Alternately, click the ellipsis **(...)** to open the **Select Certificate** dialog box.</span></span> <span data-ttu-id="b5650-148">**Nome de certificado** estará disponível se você selecionar **Usuário mapeado para um certificado** na lista **Tipo de Usuário** .</span><span class="sxs-lookup"><span data-stu-id="b5650-148">**Certificate name** is available if you select **User mapped to a certificate** from the **User type** list.</span></span>  
  
9. <span data-ttu-id="b5650-149">Na caixa **Nome da chave assimétrica**  , digite a chave a ser usada para o usuário de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="b5650-149">In the **Asymmetric key name**  box, enter the key to be used for the database user.</span></span> <span data-ttu-id="b5650-150">Como alternativa, clique nas reticências **(...)** para abrir a caixa de diálogo **Selecionar Chave Assimétrica**.</span><span class="sxs-lookup"><span data-stu-id="b5650-150">Alternately, click the ellipsis **(...)** to open the **Select Asymmetric Key** dialog box.</span></span> <span data-ttu-id="b5650-151">**Nome da chave assimétrica** estará disponível se você selecionar **Usuário mapeado para uma chave assimétrica** na lista **Tipo de usuário** .</span><span class="sxs-lookup"><span data-stu-id="b5650-151">**Asymmetric key name** is available if you select **User mapped to an asymmetric key** from the **User type** list.</span></span>  
  
10. [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
### <a name="additional-options"></a><span data-ttu-id="b5650-152">Opções adicionais</span><span class="sxs-lookup"><span data-stu-id="b5650-152">Additional Options</span></span>  
 <span data-ttu-id="b5650-153">A caixa de diálogo **Usuário de banco de dados – Novo** também oferece opções em quatro páginas adicionais: **Esquemas Proprietários**, **Associação**, **Protegíveis** e **Propriedades Estendidas**.</span><span class="sxs-lookup"><span data-stu-id="b5650-153">The **Database User - New** dialog box also offers options on four additional pages: **Owned Schemas**, **Membership**, **Securables**, and **Extended Properties**.</span></span>  
  
-   <span data-ttu-id="b5650-154">A página **Esquemas Proprietários** lista todos os possíveis esquemas que podem ser possuídos pelo novo usuário de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="b5650-154">The **Owned Schemas** page lists all possible schemas that can be owned by the new database user.</span></span> <span data-ttu-id="b5650-155">Para adicionar esquemas a ou removê-los de um usuário de banco de dados, sob **Esquemas possuídos por este usuário**, marque ou desmarque as caixas de seleção ao lado dos esquemas.</span><span class="sxs-lookup"><span data-stu-id="b5650-155">To add schemas to or remove them from a database user, under **Schemas owned by this user**, select or clear the check boxes next to the schemas.</span></span>  
  
-   <span data-ttu-id="b5650-156">A página **Associação** lista todas as funções de associação de banco de dados possíveis que podem pertencer ao novo usuário de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="b5650-156">The **Membership** page lists all possible database membership roles that can be owned by the new database user.</span></span> <span data-ttu-id="b5650-157">Para adicionar funções a ou removê-los de um usuário de banco de dados, em **Associação à função de banco de dados**, marque ou desmarque as caixas de seleção ao lado das funções.</span><span class="sxs-lookup"><span data-stu-id="b5650-157">To add roles to or remove them from a database user, under **Database role membership**, select or clear the check boxes next to the roles.</span></span>  
  
-   <span data-ttu-id="b5650-158">A página **Protegíveis** lista todos os protegíveis e as permissões possíveis nesses protegíveis que podem ser concedidos ao logon.</span><span class="sxs-lookup"><span data-stu-id="b5650-158">The **Securables** page lists all possible securables and the permissions on those securables that can be granted to the login.</span></span>  
  
-   <span data-ttu-id="b5650-159">A página **Propriedades estendidas** permite adicionar propriedades personalizadas a usuários de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="b5650-159">The **Extended properties** page allows you to add custom properties to database users.</span></span> <span data-ttu-id="b5650-160">As opções a seguir estão disponíveis nesta página.</span><span class="sxs-lookup"><span data-stu-id="b5650-160">The following options are available on this page.</span></span>  
  
     <span data-ttu-id="b5650-161">**Backup de banco de dados**</span><span class="sxs-lookup"><span data-stu-id="b5650-161">**Database**</span></span>  
     <span data-ttu-id="b5650-162">Exibe o nome do banco de dados selecionado.</span><span class="sxs-lookup"><span data-stu-id="b5650-162">Displays the name of the selected database.</span></span> <span data-ttu-id="b5650-163">Esse campo é somente leitura.</span><span class="sxs-lookup"><span data-stu-id="b5650-163">This field is read-only.</span></span>  
  
     <span data-ttu-id="b5650-164">**Ordenação**</span><span class="sxs-lookup"><span data-stu-id="b5650-164">**Collation**</span></span>  
     <span data-ttu-id="b5650-165">Exibe a ordenação usada para o banco de dados selecionado.</span><span class="sxs-lookup"><span data-stu-id="b5650-165">Displays the collation used for the selected database.</span></span> <span data-ttu-id="b5650-166">Esse campo é somente leitura.</span><span class="sxs-lookup"><span data-stu-id="b5650-166">This field is read-only.</span></span>  
  
     <span data-ttu-id="b5650-167">**Propriedades**</span><span class="sxs-lookup"><span data-stu-id="b5650-167">**Properties**</span></span>  
     <span data-ttu-id="b5650-168">Exiba ou especifique as propriedades estendidas do objeto.</span><span class="sxs-lookup"><span data-stu-id="b5650-168">View or specify the extended properties for the object.</span></span> <span data-ttu-id="b5650-169">Cada propriedade estendida consiste em um par de nomes/valores de metadados associado ao objeto.</span><span class="sxs-lookup"><span data-stu-id="b5650-169">Each extended property consists of a name/value pair of metadata associated with the object.</span></span>  
  
     <span data-ttu-id="b5650-170">**Reticências (...)**</span><span class="sxs-lookup"><span data-stu-id="b5650-170">**Ellipsis (...)**</span></span>  
     <span data-ttu-id="b5650-171">Clique nas reticências **(...)** depois do **Valor** para abrir a caixa de diálogo **Valor da Propriedade Estendida**.</span><span class="sxs-lookup"><span data-stu-id="b5650-171">Click the ellipsis **(...)** after **Value** to open the **Value for Extended Property** dialog box.</span></span> <span data-ttu-id="b5650-172">Digite ou exiba o valor da propriedade estendida neste local maior.</span><span class="sxs-lookup"><span data-stu-id="b5650-172">Type or view the value of the extended property in this larger location.</span></span> <span data-ttu-id="b5650-173">Para obter mais informações, consulte [Caixa de diálogo Valor da Propriedade Estendida](../../databases/value-for-extended-property-dialog-box.md).</span><span class="sxs-lookup"><span data-stu-id="b5650-173">For more information, see [Value for Extended Property Dialog Box](../../databases/value-for-extended-property-dialog-box.md).</span></span>  
  
     <span data-ttu-id="b5650-174">**Delete (excluir)**</span><span class="sxs-lookup"><span data-stu-id="b5650-174">**Delete**</span></span>  
     <span data-ttu-id="b5650-175">Remove a propriedade estendida selecionada.</span><span class="sxs-lookup"><span data-stu-id="b5650-175">Removes the selected extended property.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="b5650-176">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b5650-176">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-database-user"></a><span data-ttu-id="b5650-177">Para criar um usuário de banco de dados</span><span class="sxs-lookup"><span data-stu-id="b5650-177">To create a database user</span></span>  
  
1.  <span data-ttu-id="b5650-178">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b5650-178">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="b5650-179">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="b5650-179">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="b5650-180">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="b5650-180">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- Creates the login AbolrousHazem with password '340$Uuxwp7Mcxo7Khy'.  
    CREATE LOGIN AbolrousHazem   
        WITH PASSWORD = '340$Uuxwp7Mcxo7Khy';  
    GO  
  
    -- Creates a database user for the login created above.  
    CREATE USER AbolrousHazem FOR LOGIN AbolrousHazem;  
    GO  
    ```  
  
 <span data-ttu-id="b5650-181">Para obter mais informações, consulte [CREATE USER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-user-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b5650-181">For more information, see [CREATE USER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-user-transact-sql).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5650-182">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b5650-182">See Also</span></span>  
 [<span data-ttu-id="b5650-183">Entidades &#40;Mecanismo de Banco de Dados&#41;</span><span class="sxs-lookup"><span data-stu-id="b5650-183">Principals &#40;Database Engine&#41;</span></span>](principals-database-engine.md)  
  
  
