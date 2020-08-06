---
title: Criar uma função de aplicativo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- sql12.swb.approle.general.f1
helpviewer_keywords:
- application roles [SQL Server], creating
ms.assetid: 6b8da1f5-3d8e-4f88-b111-b915788b06f1
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 51272dad57558cdb771f9b98a2f5e5b3da7609cb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581729"
---
# <a name="create-an-application-role"></a><span data-ttu-id="7d7b9-102">Criar uma função de aplicativo</span><span class="sxs-lookup"><span data-stu-id="7d7b9-102">Create an Application Role</span></span>
  <span data-ttu-id="7d7b9-103">Este tópico descreve como criar uma função de aplicativo no [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7d7b9-103">This topic describes how to create an application role in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span> <span data-ttu-id="7d7b9-104">As funções de aplicativo restringem o acesso do usuário a um banco de dados exceto quando feito por aplicativos específicos.</span><span class="sxs-lookup"><span data-stu-id="7d7b9-104">Application roles restrict user access to a database except through specific applications.</span></span> <span data-ttu-id="7d7b9-105">As funções de aplicativo não têm nenhum usuário, assim a lista **Membros da Função** não é exibida quando é selecionada a **Função de aplicativo** .</span><span class="sxs-lookup"><span data-stu-id="7d7b9-105">Application roles have no users, so the **Role Members** list is not displayed when **Application role** is selected.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="7d7b9-106">A complexidade de Senha é verificada quando as senhas de função de aplicativo são definidas.</span><span class="sxs-lookup"><span data-stu-id="7d7b9-106">Password complexity is checked when application role passwords are set.</span></span> <span data-ttu-id="7d7b9-107">Os aplicativos que invocam funções de aplicativo devem armazenar suas senhas.</span><span class="sxs-lookup"><span data-stu-id="7d7b9-107">Applications that invoke application roles must store their passwords.</span></span> <span data-ttu-id="7d7b9-108">As senhas de função de aplicativo devem sempre ser criptografadas ao serem armazenadas.</span><span class="sxs-lookup"><span data-stu-id="7d7b9-108">Application role passwords should always be stored encrypted.</span></span>  
  
 <span data-ttu-id="7d7b9-109">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="7d7b9-109">**In This Topic**</span></span>  
  
-   <span data-ttu-id="7d7b9-110">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="7d7b9-110">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="7d7b9-111">Segurança</span><span class="sxs-lookup"><span data-stu-id="7d7b9-111">Security</span></span>](#Security)  
  
-   <span data-ttu-id="7d7b9-112">**Para criar uma função de aplicativo usando:**</span><span class="sxs-lookup"><span data-stu-id="7d7b9-112">**To create an application role, using:**</span></span>  
  
     [<span data-ttu-id="7d7b9-113">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7d7b9-113">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="7d7b9-114">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7d7b9-114">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="7d7b9-115">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="7d7b9-115">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="7d7b9-116">Segurança</span><span class="sxs-lookup"><span data-stu-id="7d7b9-116">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="7d7b9-117">Permissões</span><span class="sxs-lookup"><span data-stu-id="7d7b9-117">Permissions</span></span>  
 <span data-ttu-id="7d7b9-118">Requer a permissão ALTER ANY APPLICATION ROLE no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="7d7b9-118">Requires ALTER ANY APPLICATION ROLE permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="7d7b9-119">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7d7b9-119">Using SQL Server Management Studio</span></span>  
  
##### <a name="to-create-an-application-role"></a><span data-ttu-id="7d7b9-120">Para criar uma função de aplicativo</span><span class="sxs-lookup"><span data-stu-id="7d7b9-120">To create an application role</span></span>  
  
1.  <span data-ttu-id="7d7b9-121">No Pesquisador de Objetos, expanda o banco de dados onde você deseja criar uma função de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="7d7b9-121">In Object Explorer, expand the database where you want to create an application role.</span></span>  
  
2.  <span data-ttu-id="7d7b9-122">Expanda a pasta **Segurança** .</span><span class="sxs-lookup"><span data-stu-id="7d7b9-122">Expand the **Security** folder.</span></span>  
  
3.  <span data-ttu-id="7d7b9-123">Expanda a pasta **Funções** .</span><span class="sxs-lookup"><span data-stu-id="7d7b9-123">Expand the **Roles** folder.</span></span>  
  
4.  <span data-ttu-id="7d7b9-124">Clique com o botão direito do mouse na pasta **Funções de Aplicativo** e selecione **Nova Função de Aplicativo...** .</span><span class="sxs-lookup"><span data-stu-id="7d7b9-124">Right-click the **Application Roles** folder and select **New Application Role...**.</span></span>  
  
5.  <span data-ttu-id="7d7b9-125">Na caixa de diálogo **Função de Aplicativo – Nova**, na **Página Geral**, digite o novo nome da nova função de aplicativo na caixa **Nome da função**.</span><span class="sxs-lookup"><span data-stu-id="7d7b9-125">In the **Application Role - New** dialog box, on the **General Page**, enter the new name of the new application role in the **Role name** box.</span></span>  
  
6.  <span data-ttu-id="7d7b9-126">Na caixa **Esquema Padrão** , especifique o esquema que possuirá objetos criados por essa função digitando os nomes dos objetos.</span><span class="sxs-lookup"><span data-stu-id="7d7b9-126">In the **Default Schema** box, specify the schema that will own objects created by this role by entering the object names.</span></span> <span data-ttu-id="7d7b9-127">Como alternativa, clique nas reticências **(…)** para abrir a caixa de diálogo **Localizar Esquema**.</span><span class="sxs-lookup"><span data-stu-id="7d7b9-127">Alternately, click the ellipsis **(...)** to open the **Locate Schema** dialog box.</span></span>  
  
7.  <span data-ttu-id="7d7b9-128">Na caixa **Senha** , digite uma senha para a nova função.</span><span class="sxs-lookup"><span data-stu-id="7d7b9-128">In the **Password** box, enter a password for the new role.</span></span> <span data-ttu-id="7d7b9-129">Insira novamente essa senha na caixa **Confirmar Senha** .</span><span class="sxs-lookup"><span data-stu-id="7d7b9-129">Enter that password again into the **Confirm Password** box.</span></span>  
  
8.  <span data-ttu-id="7d7b9-130">Em **Esquemas de propriedade dessa função**, selecione ou confira os esquemas que serão de propriedade desta função.</span><span class="sxs-lookup"><span data-stu-id="7d7b9-130">Under **Schemas owned by this role**, select or view schemas that will be owned by this role.</span></span> <span data-ttu-id="7d7b9-131">Um esquema pode ser de propriedade de um só esquema ou função.</span><span class="sxs-lookup"><span data-stu-id="7d7b9-131">A schema can be owned by only one schema or role.</span></span>  
  
9. [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
### <a name="additional-options"></a><span data-ttu-id="7d7b9-132">Opções adicionais</span><span class="sxs-lookup"><span data-stu-id="7d7b9-132">Additional Options</span></span>  
 <span data-ttu-id="7d7b9-133">A caixa de diálogo **Função de aplicativo - Nova** também oferece opções em duas páginas adicionais: **Protegíveis** e **Propriedades Estendidas**.</span><span class="sxs-lookup"><span data-stu-id="7d7b9-133">The **Application Role - New** dialog box also offers options on two additional pages: **Securables** and **Extended Properties**.</span></span>  
  
-   <span data-ttu-id="7d7b9-134">A página **Protegíveis** lista todos os protegíveis e as permissões possíveis nesses protegíveis que podem ser concedidos ao logon.</span><span class="sxs-lookup"><span data-stu-id="7d7b9-134">The **Securables** page lists all possible securables and the permissions on those securables that can be granted to the login.</span></span>  
  
-   <span data-ttu-id="7d7b9-135">A página **Propriedades estendidas** permite adicionar propriedades personalizadas a usuários de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="7d7b9-135">The **Extended properties** page allows you to add custom properties to database users.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="7d7b9-136">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7d7b9-136">Using Transact-SQL</span></span>  
  
#### <a name="to-create-an-application-role"></a><span data-ttu-id="7d7b9-137">Para criar uma função de aplicativo</span><span class="sxs-lookup"><span data-stu-id="7d7b9-137">To create an application role</span></span>  
  
1.  <span data-ttu-id="7d7b9-138">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7d7b9-138">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="7d7b9-139">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="7d7b9-139">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="7d7b9-140">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="7d7b9-140">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- Creates an application role called "weekly_receipts" that has the password "987Gbv876sPYY5m23" and "Sales" as its default schema.  
  
    CREATE APPLICATION ROLE weekly_receipts   
        WITH PASSWORD = '987G^bv876sPY)Y5m23'   
        , DEFAULT_SCHEMA = Sales;  
    GO  
    ```  
  
 <span data-ttu-id="7d7b9-141">Para obter mais informações, veja [CREATE APPLICATION ROLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-application-role-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="7d7b9-141">For more information, see [CREATE APPLICATION ROLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-application-role-transact-sql).</span></span>  
  
  
