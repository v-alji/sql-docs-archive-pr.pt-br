---
title: Configuração de Mecanismo de Banco de Dados – provisionamento de conta | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 834b26bc-49de-4033-88d5-6aa7b1609720
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 7885bdda72668ac96e90b0900772a4f56575d5fd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569052"
---
# <a name="database-engine-configuration---account-provisioning"></a><span data-ttu-id="0ea12-102">Configuração do Mecanismo de Banco de Dados – Provisionamento de conta</span><span class="sxs-lookup"><span data-stu-id="0ea12-102">Database Engine Configuration - Account Provisioning</span></span>
  <span data-ttu-id="0ea12-103">Use esta página para definir o modo de segurança do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e adicionar grupos ou usuários do Windows como administradores do [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0ea12-103">Use this page to set the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] security mode, and to add Windows users or groups as administrators of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span></span>  
  
## <a name="considerations-for-running-sscurrent"></a><span data-ttu-id="0ea12-104">Considerações sobre execução do [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0ea12-104">Considerations for Running [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]</span></span>  
 <span data-ttu-id="0ea12-105">Nas versões anteriores do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], o grupo **BUILTIN\Administradores** era provisionado como um logon no [!INCLUDE[ssDE](../../includes/ssde-md.md)] e os membros do grupo local Administradores podiam fazer logon usando as credenciais de Administrador.</span><span class="sxs-lookup"><span data-stu-id="0ea12-105">On previous versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the **BUILTIN\Administrators** group was provisioned as a login in the [!INCLUDE[ssDE](../../includes/ssde-md.md)] and members of the local Administrators group could login using their Administrator credentials.</span></span> <span data-ttu-id="0ea12-106">O uso de permissões elevadas não é uma prática recomendada.</span><span class="sxs-lookup"><span data-stu-id="0ea12-106">Using elevated permissions is not a best practice.</span></span> <span data-ttu-id="0ea12-107">No [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] , o grupo **BUILTIN\Administradores** não é provisionado como logon.</span><span class="sxs-lookup"><span data-stu-id="0ea12-107">In [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] the **BUILTIN\Administrators** group is not provisioned as a login.</span></span> <span data-ttu-id="0ea12-108">Por isso, você deve criar um logon do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para cada usuário administrativo e adicionar esse logon à função de servidor fixa sysadmin durante a instalação de uma nova instância do [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0ea12-108">As a result, you should create a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login for each administrative user, and add that login to the sysadmin fixed server role during installation of a new instance of [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="0ea12-109">Você também deve fazer isso para as contas do Windows usadas para executar trabalhos de agente do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0ea12-109">You should also do this for Windows accounts that are used to run [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] agent jobs.</span></span> <span data-ttu-id="0ea12-110">Eles incluem trabalhos do agente de replicação.</span><span class="sxs-lookup"><span data-stu-id="0ea12-110">These include replication agent jobs.</span></span>  
  
## <a name="options"></a><span data-ttu-id="0ea12-111">Opções</span><span class="sxs-lookup"><span data-stu-id="0ea12-111">Options</span></span>  
 <span data-ttu-id="0ea12-112">**Modo de Segurança** – Selecione Autenticação do Windows ou Autenticação de Modo Misto para sua instalação.</span><span class="sxs-lookup"><span data-stu-id="0ea12-112">**Security Mode** - Select Windows Authentication or Mixed Mode Authentication for your installation.</span></span>  
  
 <span data-ttu-id="0ea12-113">**Provisionamento de Entidade do Windows** – Nas versões anteriores do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], o grupo local Windows Builtin\Administrator era colocado na função de servidor [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sysadmin, concedendo efetivamente aos administradores do Windows o acesso à instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0ea12-113">**Windows Principal Provisioning** - In previous versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the Windows Builtin\Administrator local group was placed into the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sysadmin server role, effectively granting Windows administrators access to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="0ea12-114">No [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], o grupo Builtin\Administradores não é provisionado na função de servidor sysadmin.</span><span class="sxs-lookup"><span data-stu-id="0ea12-114">In [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], the Builtin\Administrator group is not provisioned in the sysadmin server role.</span></span> <span data-ttu-id="0ea12-115">Em vez disso, você deve provisionar explicitamente administradores do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para as novas instalações durante a Instalação.</span><span class="sxs-lookup"><span data-stu-id="0ea12-115">Instead, you should explicitly provision [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] administrators for new installations during Setup.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="0ea12-116">Você deve provisionar explicitamente administradores do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para as novas instalações durante a Instalação.</span><span class="sxs-lookup"><span data-stu-id="0ea12-116">You must explicitly provision [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] administrators for new installations during Setup.</span></span> <span data-ttu-id="0ea12-117">A Instalação não permitirá que você continue até que conclua esta etapa.</span><span class="sxs-lookup"><span data-stu-id="0ea12-117">Setup will not allow you to continue until you complete this step.</span></span>  
  
 <span data-ttu-id="0ea12-118">**Especificar Administradores do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]** – É necessário especificar, pelo menos, uma entidade do Windows para a instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0ea12-118">**Specify [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Administrators** - You must specify at least one Windows principal for the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="0ea12-119">Para adicionar a conta sob a qual a Instalação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] está sendo executada, clique no botão **Usuário Atual** .</span><span class="sxs-lookup"><span data-stu-id="0ea12-119">To add the account under which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup is running, click the **Current User** button.</span></span> <span data-ttu-id="0ea12-120">Para adicionar ou remover contas da lista de administradores do sistema, clique em **Adicionar** ou **Remover**e edite a lista de usuários, grupos ou computadores que terão privilégios de administrador para a instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0ea12-120">To add or remove accounts from the list of system administrators, click **Add** or **Remove**, and then edit the list of users, groups, or computers that will have administrator privileges for the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="0ea12-121">Depois de concluir a edição da lista, clique em **OK**e verifique a lista de administradores na caixa de diálogo de configuração.</span><span class="sxs-lookup"><span data-stu-id="0ea12-121">When you are finished editing the list, click **OK**, then verify the list of administrators in the configuration dialog.</span></span> <span data-ttu-id="0ea12-122">Quando a lista estiver concluída, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="0ea12-122">When the list is complete, click **Next**.</span></span>  
  
 <span data-ttu-id="0ea12-123">Se você selecionar Autenticação de Modo Misto, deverá fornecer credenciais de logon para a conta interna AS (administrador do sistema) do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0ea12-123">If you select Mixed Mode Authentication, you must provide logon credentials for the builtin [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system administrator (SA) account.</span></span>  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteStrongPass](../../includes/ssnotestrongpass-md.md)]  
  
 <span data-ttu-id="0ea12-124">**Modo de autenticação do Windows**</span><span class="sxs-lookup"><span data-stu-id="0ea12-124">**Windows Authentication Mode**</span></span>  
 <span data-ttu-id="0ea12-125">Quando um usuário se conecta por uma conta de usuário do Windows, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] valida o nome e a senha da conta usando o token da entidade do Windows no sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="0ea12-125">When a user connects through a Windows user account, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] validates the account name and password using the Windows principal token in the operating system.</span></span> <span data-ttu-id="0ea12-126">Este é o modo de autenticação padrão e é muito mais seguro que o Modo Misto.</span><span class="sxs-lookup"><span data-stu-id="0ea12-126">This is the default authentication mode, and is much more secure than Mixed Mode.</span></span> <span data-ttu-id="0ea12-127">A Autenticação do Windows usa o protocolo de segurança Kerberos, fornece imposição de política de senha e termos de validação de complexidade para senhas fortes, dá suporte ao bloqueio de contas e dá suporte à expiração de senhas.</span><span class="sxs-lookup"><span data-stu-id="0ea12-127">Windows Authentication utilizes Kerberos security protocol, provides password policy enforcement in terms of complexity validation for strong passwords, provides support for account lockout, and supports password expiration.</span></span>  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteWinAuthentication](../../includes/ssnotewinauthentication-md.md)]  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteStrongPass](../../includes/ssnotestrongpass-md.md)] <span data-ttu-id="0ea12-128">Nunca defina uma senha de sa em branco ou fraca.</span><span class="sxs-lookup"><span data-stu-id="0ea12-128">Never set a blank or weak sa password.</span></span>  
  
 <span data-ttu-id="0ea12-129">**Modo misto (autenticação do Windows ou [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] autenticação)**</span><span class="sxs-lookup"><span data-stu-id="0ea12-129">**Mixed Mode (Windows Authentication or [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication)**</span></span>  
 <span data-ttu-id="0ea12-130">Permite que os usuários se conectem usando Autenticação do Windows ou Autenticação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0ea12-130">Allows users to connect by using Windows Authentication or [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="0ea12-131">Os usuários que se conectarem por uma conta de usuário do Windows podem usar conexões confiáveis que são validadas pelo Windows.</span><span class="sxs-lookup"><span data-stu-id="0ea12-131">Users who connect through a Windows user account can use trusted connections that are validated by Windows.</span></span>  
  
 <span data-ttu-id="0ea12-132">Se você deve escolher Autenticação de Modo Misto e tem um requisito para usar logons do SQL a fim de acomodar aplicativos herdados, deverá definir senhas fortes para todas as contas do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0ea12-132">If you must choose Mixed Mode Authentication and you have a requirement for using SQL logins to accommodate legacy applications, you must set strong passwords for all [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] accounts.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0ea12-133">A autenticação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] é fornecida somente para fins de compatibilidade com versões anteriores.</span><span class="sxs-lookup"><span data-stu-id="0ea12-133">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication is provided for backward compatibility only.</span></span> [!INCLUDE[ssNoteWinAuthentication](../../includes/ssnotewinauthentication-md.md)]  
  
 <span data-ttu-id="0ea12-134">**Inserir senha**</span><span class="sxs-lookup"><span data-stu-id="0ea12-134">**Enter Password**</span></span>  
 <span data-ttu-id="0ea12-135">Insira e confirme o logon de administrador de sistema (sa).</span><span class="sxs-lookup"><span data-stu-id="0ea12-135">Enter and confirm the system administrator (sa) login.</span></span> <span data-ttu-id="0ea12-136">As senhas são a primeira linha de defesa contra intrusos; portanto, a configuração de senhas fortes é essencial para a segurança do seu sistema.</span><span class="sxs-lookup"><span data-stu-id="0ea12-136">Passwords are the first line of defense against intruders, so setting strong passwords is essential to the security of your system.</span></span> <span data-ttu-id="0ea12-137">Nunca defina uma senha de sa em branco ou fraca.</span><span class="sxs-lookup"><span data-stu-id="0ea12-137">Never set a blank or weak sa password.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0ea12-138">Senhas [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] podem conter de 1 até 128 caracteres, incluindo qualquer combinação de letras, símbolos e números.</span><span class="sxs-lookup"><span data-stu-id="0ea12-138">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] passwords can contain from 1 to 128 characters, including any combination of letters, symbols, and numbers.</span></span> <span data-ttu-id="0ea12-139">Se você escolher a autenticação de Modo Misto, deverá inserir uma senha forte de sa antes de continuar na próxima página do Assistente de Instalação.</span><span class="sxs-lookup"><span data-stu-id="0ea12-139">If you choose Mixed Mode authentication, you must enter a strong sa password before you can continue to the next page of the Installation Wizard.</span></span>  
  
 <span data-ttu-id="0ea12-140">**Diretrizes de senha forte**</span><span class="sxs-lookup"><span data-stu-id="0ea12-140">**Strong Password Guidelines**</span></span>  
 <span data-ttu-id="0ea12-141">As senhas fortes não são prontamente adivinhadas por uma pessoa e não são facilmente violadas usando-se um programa de computador.</span><span class="sxs-lookup"><span data-stu-id="0ea12-141">Strong passwords are not readily guessed by a person, and are not easily hacked using a computer program.</span></span> <span data-ttu-id="0ea12-142">As senhas fortes não podem usar condições ou termos proibidos, incluindo:</span><span class="sxs-lookup"><span data-stu-id="0ea12-142">Strong passwords cannot use prohibited conditions or terms, including:</span></span>  
  
-   <span data-ttu-id="0ea12-143">Um espaço em branco ou condição NULL</span><span class="sxs-lookup"><span data-stu-id="0ea12-143">A blank or NULL condition</span></span>  
  
-   <span data-ttu-id="0ea12-144">"Password"</span><span class="sxs-lookup"><span data-stu-id="0ea12-144">"Password"</span></span>  
  
-   <span data-ttu-id="0ea12-145">"Admin"</span><span class="sxs-lookup"><span data-stu-id="0ea12-145">"Admin"</span></span>  
  
-   <span data-ttu-id="0ea12-146">"Administrador"</span><span class="sxs-lookup"><span data-stu-id="0ea12-146">"Administrator"</span></span>  
  
-   <span data-ttu-id="0ea12-147">"sa"</span><span class="sxs-lookup"><span data-stu-id="0ea12-147">"sa"</span></span>  
  
-   <span data-ttu-id="0ea12-148">"sysadmin"</span><span class="sxs-lookup"><span data-stu-id="0ea12-148">"sysadmin"</span></span>  
  
 <span data-ttu-id="0ea12-149">Uma senha forte não pode ter os termos a seguir associados ao computador de instalação:</span><span class="sxs-lookup"><span data-stu-id="0ea12-149">A strong password cannot be the following terms associated with the installation computer:</span></span>  
  
-   <span data-ttu-id="0ea12-150">O nome do usuário atualmente conectado à máquina.</span><span class="sxs-lookup"><span data-stu-id="0ea12-150">The name of the user currently logged onto the machine.</span></span>  
  
-   <span data-ttu-id="0ea12-151">O nome do computador.</span><span class="sxs-lookup"><span data-stu-id="0ea12-151">The computer name.</span></span>  
  
 <span data-ttu-id="0ea12-152">Uma senha forte deve ter mais de 8 caracteres e satisfazer pelo menos três dos quatro critérios a seguir:</span><span class="sxs-lookup"><span data-stu-id="0ea12-152">A strong password must be more than 8 characters in length and satisfy at least three of the following four criteria:</span></span>  
  
-   <span data-ttu-id="0ea12-153">Deve conter letras maiúsculas.</span><span class="sxs-lookup"><span data-stu-id="0ea12-153">It must contain uppercase letters.</span></span>  
  
-   <span data-ttu-id="0ea12-154">Deve conter letras minúsculas.</span><span class="sxs-lookup"><span data-stu-id="0ea12-154">It must contain lowercase letters.</span></span>  
  
-   <span data-ttu-id="0ea12-155">Deve conter números.</span><span class="sxs-lookup"><span data-stu-id="0ea12-155">It must contain numbers.</span></span>  
  
-   <span data-ttu-id="0ea12-156">Deve conter caracteres não alfanuméricos; por exemplo, #,% ou ^.</span><span class="sxs-lookup"><span data-stu-id="0ea12-156">It must contain non-alphanumeric characters; for example, #, %, or ^.</span></span>  
  
 <span data-ttu-id="0ea12-157">As senhas inseridas nessa página devem satisfazer os requisitos de política de senha forte.</span><span class="sxs-lookup"><span data-stu-id="0ea12-157">Passwords entered on this page must meet strong password policy requirements.</span></span> <span data-ttu-id="0ea12-158">Se você tiver qualquer automação que use Autenticação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , assegure-se de que a senha satisfaça os requisitos de política de senha forte.</span><span class="sxs-lookup"><span data-stu-id="0ea12-158">If you have any automation that uses [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication, ensure that the password meets strong password policy requirements.</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="0ea12-159">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="0ea12-159">Related Content</span></span>  
 <span data-ttu-id="0ea12-160">Para obter mais informações sobre como escolher a Autenticação do Windows vs. Autenticação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , veja o tópico **Escolher um Modo de Autenticação** nos Manuais Online do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0ea12-160">For more information about choosing Windows Authentication vs. [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication, see the topic **Choose an Authentication Mode** in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
 <span data-ttu-id="0ea12-161">Para obter mais informações sobre como escolher uma conta para executar o [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], consulte o tópico **Configurar contas de serviço e permissões do Windows** nos Manuais Online do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0ea12-161">For more information about choosing an account to run the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], see the topic **Configure Windows Service Accounts and Permissions** in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ea12-162">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0ea12-162">See Also</span></span>  
 [<span data-ttu-id="0ea12-163">Configurar contas de serviço e permissões do Windows</span><span class="sxs-lookup"><span data-stu-id="0ea12-163">Configure Windows Service Accounts and Permissions</span></span>](../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md)  
  
  