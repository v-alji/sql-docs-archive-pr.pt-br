---
title: Criar uma credencial | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- credentials [SQL Server], creating
- authentication [SQL Server], credentials
- logins [SQL Server], credentials
ms.assetid: c1e77e91-2a69-40d9-b8b3-97cffc710586
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 23221424699449ac3775b0e805bb02ae0ad233f2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679812"
---
# <a name="create-a-credential"></a><span data-ttu-id="38c27-102">Create a Credential</span><span class="sxs-lookup"><span data-stu-id="38c27-102">Create a Credential</span></span>
  <span data-ttu-id="38c27-103">Este tópico descreve como criar uma credencial no [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="38c27-103">This topic describes how to create a credential in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="38c27-104">As credenciais oferecem um modo para permitir que os usuários de Autenticação do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] tenham uma identidade fora do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="38c27-104">Credentials provide a way to allow [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Authentication users to have an identity outside of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="38c27-105">Isso é usado principalmente para executar código em Assemblies com conjunto de permissões EXTERNAL_ACCESS.</span><span class="sxs-lookup"><span data-stu-id="38c27-105">This is primarily used to execute code in Assemblies with EXTERNAL_ACCESS permission set.</span></span> <span data-ttu-id="38c27-106">As credenciais podem também ser usadas quando um usuário de Autenticação do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] precisa acessar recursos de um domínio, como o local de um arquivo para armazenar um backup.</span><span class="sxs-lookup"><span data-stu-id="38c27-106">Credentials can also be used when a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Authentication user needs access to a domain resource, such as a file location to store a backup.</span></span>  
  
 <span data-ttu-id="38c27-107">Uma credencial pode ser mapeada para vários logons de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="38c27-107">A credential can be mapped to several [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] logins at the same time.</span></span> <span data-ttu-id="38c27-108">Entretanto, um logon do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] só pode ser mapeado para uma credencial ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="38c27-108">A [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] login can only be mapped to one credential at a time.</span></span> <span data-ttu-id="38c27-109">Depois que uma credencial é criada, use **Propriedades de Logon (Página Geral)** para mapear um logon para uma credencial.</span><span class="sxs-lookup"><span data-stu-id="38c27-109">After a credential is created, use the **Login Properties (General Page)** to map a login to a credential.</span></span>  
  
 <span data-ttu-id="38c27-110">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="38c27-110">**In This Topic**</span></span>  
  
-   <span data-ttu-id="38c27-111">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="38c27-111">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="38c27-112">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="38c27-112">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="38c27-113">Segurança</span><span class="sxs-lookup"><span data-stu-id="38c27-113">Security</span></span>](#Security)  
  
-   <span data-ttu-id="38c27-114">**Para criar uma credencial, usando:**</span><span class="sxs-lookup"><span data-stu-id="38c27-114">**To create a credential, using:**</span></span>  
  
     [<span data-ttu-id="38c27-115">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="38c27-115">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="38c27-116">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="38c27-116">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="38c27-117">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="38c27-117">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="38c27-118">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="38c27-118">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="38c27-119">Se não houver nenhuma credencial mapeada de logon para o provedor, a credencial mapeada para a conta de serviço do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] será usada.</span><span class="sxs-lookup"><span data-stu-id="38c27-119">If there is no login mapped credential for the provider, the credential mapped to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] service account is used.</span></span>  
  
-   <span data-ttu-id="38c27-120">Um logon pode ter várias credenciais mapeadas, contanto que elas sejam usadas com provedores diferentes.</span><span class="sxs-lookup"><span data-stu-id="38c27-120">A login can have multiple credentials mapped to it as long as they are used with distinctive providers.</span></span> <span data-ttu-id="38c27-121">Deve haver só uma credencial mapeada por provedor por logon.</span><span class="sxs-lookup"><span data-stu-id="38c27-121">There must be only one mapped credential per provider per login.</span></span> <span data-ttu-id="38c27-122">A mesma credencial pode ser mapeada para outros logons.</span><span class="sxs-lookup"><span data-stu-id="38c27-122">The same credential can be mapped to other logins.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="38c27-123">Segurança</span><span class="sxs-lookup"><span data-stu-id="38c27-123">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="38c27-124">Permissões</span><span class="sxs-lookup"><span data-stu-id="38c27-124">Permissions</span></span>  
 <span data-ttu-id="38c27-125">Exige permissão de ALTER ANY CREDENCIAL para criar ou modificar uma credencial e ALTER ANY LOGIN para mapear um logon para uma credencial.</span><span class="sxs-lookup"><span data-stu-id="38c27-125">Requires ALTER ANY CREDENTIAL permission to create or modify a credential and ALTER ANY LOGIN permission to map a login to a credential.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="38c27-126">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="38c27-126">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-credential"></a><span data-ttu-id="38c27-127">Para criar uma credencial</span><span class="sxs-lookup"><span data-stu-id="38c27-127">To create a credential</span></span>  
  
1.  <span data-ttu-id="38c27-128">No Pesquisador de Objetos, expanda a pasta **Segurança** .</span><span class="sxs-lookup"><span data-stu-id="38c27-128">In Object Explorer, expand  the **Security** folder.</span></span>  
  
2.  <span data-ttu-id="38c27-129">Clique com o botão direito do mouse na pasta **Credenciais** e selecione **Nova Credencial...** .</span><span class="sxs-lookup"><span data-stu-id="38c27-129">Right-click the **Credentials** folder and select **New Credential...**.</span></span>  
  
3.  <span data-ttu-id="38c27-130">Na caixa de diálogo **Nova Credencial** , na caixa **Nome da Credencial** , digite um nome para a credencial.</span><span class="sxs-lookup"><span data-stu-id="38c27-130">In the **New Credential** dialog box, in the **Credential Name** box, type a name for the credential.</span></span>  
  
4.  <span data-ttu-id="38c27-131">Na caixa **Identidade** , digite o nome da conta usada para conexões de saída (ao deixar o contexto do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="38c27-131">In the **Identity** box, type the name of the account used for outgoing connections (when leaving the context of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]).</span></span> <span data-ttu-id="38c27-132">Normalmente, esta será uma conta de usuário do Windows, mas a identidade pode ser uma conta de outro tipo.</span><span class="sxs-lookup"><span data-stu-id="38c27-132">Typically, this will be a Windows user account, but the identity can be an account of another type.</span></span>  
  
     <span data-ttu-id="38c27-133">Como alternativa, clique nas reticências **(…)** para abrir a caixa de diálogo **Selecionar Usuário ou Grupo**.</span><span class="sxs-lookup"><span data-stu-id="38c27-133">Alternately, click the ellipsis **(...)** to open the **Select User or Group** dialog box.</span></span>  
  
5.  <span data-ttu-id="38c27-134">Nas caixas **Senha** e **Confirmar senha** , digite a senha da conta especificada na caixa **Identidade** .</span><span class="sxs-lookup"><span data-stu-id="38c27-134">In the **Password** and **Confirm password** boxes, type the password of the account specified in the **Identity** box.</span></span> <span data-ttu-id="38c27-135">Se **Identidade** for uma conta de usuário do Windows, esta será a senha Windows.</span><span class="sxs-lookup"><span data-stu-id="38c27-135">If **Identity** is a Windows user account, this is the Windows password.</span></span> <span data-ttu-id="38c27-136">A **Senha** poderá ficar em branco se nenhuma senha for requerida.</span><span class="sxs-lookup"><span data-stu-id="38c27-136">The **Password** can be blank, if no password is required.</span></span>  
  
6.  <span data-ttu-id="38c27-137">Selecione **Usar Provedor de Criptografia** para definir a credencial a ser verificada por um Provedor de EKM (Gerenciamento de Chave Extensível).</span><span class="sxs-lookup"><span data-stu-id="38c27-137">Select **Use Encryption Provider** to set the credential to be verified by an Extensible Key Management (EKM) Provider.</span></span> <span data-ttu-id="38c27-138">Para obter mais informações, veja [EKM &#40;Gerenciamento de Chave Extensível&#41;](../encryption/extensible-key-management-ekm.md)</span><span class="sxs-lookup"><span data-stu-id="38c27-138">For more information, see [Extensible Key Management &#40;EKM&#41;](../encryption/extensible-key-management-ekm.md)</span></span>  
  
7.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="38c27-139">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="38c27-139">Using Transact-SQL</span></span>  
  
###  <a name="to-create-a-credential"></a><a name="Credential"></a><span data-ttu-id="38c27-140">Para criar uma credencial</span><span class="sxs-lookup"><span data-stu-id="38c27-140">To create a credential</span></span>  
  
1.  <span data-ttu-id="38c27-141">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="38c27-141">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="38c27-142">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="38c27-142">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="38c27-143">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="38c27-143">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- Creates the credential called "AlterEgo.".   
    -- The credential contains the Windows user "Mary5" and a password.  
    CREATE CREDENTIAL AlterEgo WITH IDENTITY = 'Mary5',   
        SECRET = '<EnterStrongPasswordHere>';  
    GO  
    ```  
  
 <span data-ttu-id="38c27-144">Para obter mais informações, veja [CREATE CREDENTIAL &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-credential-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="38c27-144">For more information, see [CREATE CREDENTIAL &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-credential-transact-sql).</span></span>  
  
  
