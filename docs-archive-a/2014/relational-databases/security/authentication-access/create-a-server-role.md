---
title: Criar uma função de servidor | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- sql12.swb.serverrole.members.f1
- SQL12.SWB.SERVERROLE.GENERAL.F1
- sql12.swb.serverrole.memberships.f1
helpviewer_keywords:
- SERVER ROLE, creating
ms.assetid: 74f19992-8082-4ed7-92a1-04fe676ee82d
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 45c3d5bb9c9c7fdae9abe18ab3cb808cae4c1fa1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581731"
---
# <a name="create-a-server-role"></a><span data-ttu-id="243df-102">Criar uma função de servidor</span><span class="sxs-lookup"><span data-stu-id="243df-102">Create a Server Role</span></span>
  <span data-ttu-id="243df-103">Este tópico descreve como criar uma nova função de servidor no [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="243df-103">This topic describes how to create a new server role in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="243df-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="243df-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="243df-105">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="243df-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="243df-106">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="243df-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="243df-107">Segurança</span><span class="sxs-lookup"><span data-stu-id="243df-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="243df-108">**Para criar uma nova função de servidor usando:**</span><span class="sxs-lookup"><span data-stu-id="243df-108">**To create a new server role, using:**</span></span>  
  
     [<span data-ttu-id="243df-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="243df-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="243df-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="243df-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="243df-111">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="243df-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="243df-112">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="243df-112">Limitations and Restrictions</span></span>  
 <span data-ttu-id="243df-113">As funções de servidor não podem receber permissão nos protegíveis do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="243df-113">Server roles cannot be granted permission on database-level securables.</span></span> <span data-ttu-id="243df-114">Para criar funções de banco de dados, veja [CREATE ROLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-role-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="243df-114">To create database roles, see [CREATE ROLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-role-transact-sql).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="243df-115">Segurança</span><span class="sxs-lookup"><span data-stu-id="243df-115">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="243df-116">Permissões</span><span class="sxs-lookup"><span data-stu-id="243df-116">Permissions</span></span>  
  
-   <span data-ttu-id="243df-117">Exige a permissão CREATE SERVER ROLE ou associação na função de servidor fixa sysadmin.</span><span class="sxs-lookup"><span data-stu-id="243df-117">Requires CREATE SERVER ROLE permission or membership in the sysadmin fixed server role.</span></span>  
  
-   <span data-ttu-id="243df-118">Também exige IMPERSONATE no *server_principal* para logons, permissão ALTER para funções de servidor usadas como o *server_principal*ou associação em um grupo do Windows que é usado como o server_principal.</span><span class="sxs-lookup"><span data-stu-id="243df-118">Also requires IMPERSONATE on the *server_principal* for logins, ALTER permission for server roles used as the *server_principal*, or membership in a Windows group that is used as the server_principal.</span></span>  
  
-   <span data-ttu-id="243df-119">Ao usar a opção AUTHORIZATION para atribuir a propriedade de um função de servidor, as seguintes permissões também são necessárias:</span><span class="sxs-lookup"><span data-stu-id="243df-119">When you use the AUTHORIZATION option to assign server role ownership, the following permissions are also required:</span></span>  
  
    -   <span data-ttu-id="243df-120">Para atribuir a propriedade de uma função de servidor a outro logon, a permissão IMPERSONATE é necessária naquele logon.</span><span class="sxs-lookup"><span data-stu-id="243df-120">To assign ownership of a server role to another login, requires IMPERSONATE permission on that login.</span></span>  
  
    -   <span data-ttu-id="243df-121">Para atribuir a propriedade de uma função de servidor para outra, é necessária associação na função de servidor ou a permissão ALTER naquela função de servidor.</span><span class="sxs-lookup"><span data-stu-id="243df-121">To assign ownership of a server role to another server role, requires membership in the recipient server role or ALTER permission on that server role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="243df-122">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="243df-122">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-new-server-role"></a><span data-ttu-id="243df-123">Para criar uma nova função de servidor</span><span class="sxs-lookup"><span data-stu-id="243df-123">To create a new server role</span></span>  
  
1.  <span data-ttu-id="243df-124">No Pesquisador de Objetos, expanda o servidor onde você deseja criar a nova função de servidor.</span><span class="sxs-lookup"><span data-stu-id="243df-124">In Object Explorer, expand the server where you want to create the new server role.</span></span>  
  
2.  <span data-ttu-id="243df-125">Expanda a pasta **Segurança** .</span><span class="sxs-lookup"><span data-stu-id="243df-125">Expand the **Security** folder.</span></span>  
  
3.  <span data-ttu-id="243df-126">Clique com o botão direito do mouse na pasta **Funções de Servidor** e selecione **Nova Função de Servidor...** .</span><span class="sxs-lookup"><span data-stu-id="243df-126">Right-click the **Server Roles** folder and select **New Server Role...**.</span></span>  
  
4.  <span data-ttu-id="243df-127">Na caixa de diálogo **nova função de servidor –**_server_role_name_ , na página **geral** , insira um nome para a nova função de servidor na caixa **nome da função de servidor** .</span><span class="sxs-lookup"><span data-stu-id="243df-127">In the **New Server Role -**_server_role_name_ dialog box, on the **General** page, enter a name for the new server role in the **Server role name** box.</span></span>  
  
5.  <span data-ttu-id="243df-128">Na caixa **Proprietário** , digite o nome da entidade de segurança de servidor que será proprietária da nova função.</span><span class="sxs-lookup"><span data-stu-id="243df-128">In the **Owner** box, enter the name of the server principal that will own the new role.</span></span> <span data-ttu-id="243df-129">Como alternativa, clique nas reticências **(...)** para abrir a caixa de diálogo **Selecionar Logon ou Função de Servidor**.</span><span class="sxs-lookup"><span data-stu-id="243df-129">Alternately, click the ellipsis **(...)** to open the **Select Server Login or Role** dialog box.</span></span>  
  
6.  <span data-ttu-id="243df-130">Em **Protegíveis**, selecione um ou mais protegíveis do nível do servidor.</span><span class="sxs-lookup"><span data-stu-id="243df-130">Under **Securables**, select one or more server-level securables.</span></span> <span data-ttu-id="243df-131">Quando um protegível é selecionado, essa função de servidor pode receber ou ter as permissões negadas naquele protegível.</span><span class="sxs-lookup"><span data-stu-id="243df-131">When a securable is selected, this server role can be granted or denied permissions on that securable.</span></span>  
  
7.  <span data-ttu-id="243df-132">Na caixa **Permissões: explícitas**, marque a caixa de seleção para conceder, conceder com concessão ou negar permissão a esta função de servidor para os protegíveis selecionados.</span><span class="sxs-lookup"><span data-stu-id="243df-132">In the **Permissions: Explicit** box, select the check box to grant, grant with grant, or deny permission to this server role for the selected securables.</span></span> <span data-ttu-id="243df-133">Se uma permissão não puder ser concedida ou negada a todos os protegíveis selecionados, a permissão será representada como uma seleção parcial.</span><span class="sxs-lookup"><span data-stu-id="243df-133">If a permission cannot be granted or denied to all of the selected securables, the permission is represented as a partial select.</span></span>  
  
8.  <span data-ttu-id="243df-134">Na página **Membros** , use o botão **Adicionar** para adicionar logons que representam indivíduos ou grupos à nova função de servidor.</span><span class="sxs-lookup"><span data-stu-id="243df-134">On the **Members** page, use the **Add** button to add logins that represent individuals or groups to the new server role.</span></span>  
  
9. <span data-ttu-id="243df-135">Uma função de servidor definida pelo usuário pode ser membro de outra função de servidor.</span><span class="sxs-lookup"><span data-stu-id="243df-135">A user-defined server role can be a member of another server role.</span></span> <span data-ttu-id="243df-136">Na página **Associações** , marque uma caixa de seleção para tornar a função de servidor definida pelo usuário atual um membro de uma função de servidor selecionada.</span><span class="sxs-lookup"><span data-stu-id="243df-136">On the **Memberships** page, select a check box to make the current user-defined server role a member of a selected server role.</span></span>  
  
10. [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="243df-137">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="243df-137">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-new-server-role"></a><span data-ttu-id="243df-138">Para criar uma nova função de servidor</span><span class="sxs-lookup"><span data-stu-id="243df-138">To create a new server role</span></span>  
  
1.  <span data-ttu-id="243df-139">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="243df-139">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="243df-140">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="243df-140">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="243df-141">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="243df-141">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    --Creates the server role auditors that is owned the securityadmin fixed server role.  
    USE master;  
    CREATE SERVER ROLE auditors AUTHORIZATION securityadmin;  
    GO  
    ```  
  
 <span data-ttu-id="243df-142">Para obter mais informações, veja [CREATE SERVER ROLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-server-role-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="243df-142">For more information, see [CREATE SERVER ROLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-server-role-transact-sql).</span></span>  
  
  
