---
title: Escrever eventos de auditoria do SQL Server no log de segurança | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- logs [SQL Server], Security Log
- server audit [SQL Server]
- audits [SQL Server], writing to Security Log
- security logs [SQL Server]
ms.assetid: 6fabeea3-7a42-4769-a0f3-7e04daada314
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: d59134b278f29c9b604208d8cab7e982144b9c9a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570574"
---
# <a name="write-sql-server-audit-events-to-the-security-log"></a><span data-ttu-id="3c2df-102">Gravar eventos de auditoria do SQL Server no log de segurança</span><span class="sxs-lookup"><span data-stu-id="3c2df-102">Write SQL Server Audit Events to the Security Log</span></span>
  <span data-ttu-id="3c2df-103">em um ambiente de alta segurança, o log de Segurança do Windows é o local apropriado para gravar eventos que registram o acesso a objetos.</span><span class="sxs-lookup"><span data-stu-id="3c2df-103">In a high security environment, the Windows Security log is the appropriate location to write events that record object access.</span></span> <span data-ttu-id="3c2df-104">Outros locais de auditoria têm suporte, mas estão mais sujeitos a falsificações.</span><span class="sxs-lookup"><span data-stu-id="3c2df-104">Other audit locations are supported but are more subject to tampering.</span></span>  
  
 <span data-ttu-id="3c2df-105">Há dois requisitos principais para gravar auditorias do servidor [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] no log de Segurança do Windows:</span><span class="sxs-lookup"><span data-stu-id="3c2df-105">There are two key requirements for writing [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] server audits to the Windows Security log:</span></span>  
  
-   <span data-ttu-id="3c2df-106">É necessário configurar o acesso ao objeto de auditoria para capturar os eventos.</span><span class="sxs-lookup"><span data-stu-id="3c2df-106">The audit object access setting must be configured to capture the events.</span></span> <span data-ttu-id="3c2df-107">A ferramenta de política de auditoria (`auditpol.exe`) expõe uma variedade de configurações de subpolíticas na categoria **acesso ao objeto de auditoria** .</span><span class="sxs-lookup"><span data-stu-id="3c2df-107">The audit policy tool (`auditpol.exe`) exposes a variety of sub-policies settings in the **audit object access** category.</span></span> <span data-ttu-id="3c2df-108">Para permitir que o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] audite o acesso a objetos, defina a configuração de **aplicativo gerado** .</span><span class="sxs-lookup"><span data-stu-id="3c2df-108">To allow [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to audit object access, configure the **application generated** setting.</span></span>  
  
-   <span data-ttu-id="3c2df-109">A conta que o serviço [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] está executando deve ter a permissão **gerar auditorias de segurança** para gravar no log de Segurança do Windows.</span><span class="sxs-lookup"><span data-stu-id="3c2df-109">The account that the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] service is running under must have the **generate security audits** permission to write to the Windows Security log.</span></span> <span data-ttu-id="3c2df-110">Por padrão, as contas LOCAL SERVICE e NETWORK SERVICE têm essa permissão.</span><span class="sxs-lookup"><span data-stu-id="3c2df-110">By default, the LOCAL SERVICE and the NETWORK SERVICE accounts have this permission.</span></span> <span data-ttu-id="3c2df-111">Esta etapa não será necessária se o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] estiver sendo executado em uma dessas contas.</span><span class="sxs-lookup"><span data-stu-id="3c2df-111">This step is not required if [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] is running under one of those accounts.</span></span>  
  
 <span data-ttu-id="3c2df-112">A política de auditoria do Windows poderá afetar a auditoria do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] se estiver configurada para gravar no log de segurança do Windows, com a possibilidade de se perder eventos se a política de auditoria não estiver configurada corretamente.</span><span class="sxs-lookup"><span data-stu-id="3c2df-112">The Windows audit policy can affect [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] auditing if it is configured to write to the Windows Security log, with the potential of losing events if the audit policy is incorrectly configured.</span></span> <span data-ttu-id="3c2df-113">Normalmente, o log de segurança do Windows é definido para substituir os eventos mais antigos.</span><span class="sxs-lookup"><span data-stu-id="3c2df-113">Typically, the Windows Security log is set to overwrite the older events.</span></span> <span data-ttu-id="3c2df-114">Isso preserva os eventos mais recentes.</span><span class="sxs-lookup"><span data-stu-id="3c2df-114">This preserves the most recent events.</span></span> <span data-ttu-id="3c2df-115">No entanto, se o log de segurança do Windows não estiver definido para substituir eventos mais antigos, quando ele estiver cheio, o sistema emitirá o evento 1104 do Windows (O log está cheio).</span><span class="sxs-lookup"><span data-stu-id="3c2df-115">However, if the Windows Security log is not set to overwrite older events, then if the Security log is full, the system will issue Windows event 1104 (Log is full).</span></span> <span data-ttu-id="3c2df-116">Nesse momento:</span><span class="sxs-lookup"><span data-stu-id="3c2df-116">At that point:</span></span>  
  
-   <span data-ttu-id="3c2df-117">Nenhum outro evento de segurança será registrado</span><span class="sxs-lookup"><span data-stu-id="3c2df-117">No further security events will be recorded</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="3c2df-118">não conseguirá detectar que o sistema não pode registrar os eventos no log de segurança, o que resultará na possível perda de eventos de auditoria</span><span class="sxs-lookup"><span data-stu-id="3c2df-118">will not be able to detect that the system is not able to record the events in the Security log, resulting in the potential loss of audit events</span></span>  
  
-   <span data-ttu-id="3c2df-119">Depois que o administrador do computador corrigir o log de segurança, o comportamento de log voltará ao normal.</span><span class="sxs-lookup"><span data-stu-id="3c2df-119">After the box administrator fixes the Security log, the logging behavior will return to normal.</span></span>  
  
 <span data-ttu-id="3c2df-120">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="3c2df-120">**In This Topic**</span></span>  
  
-   <span data-ttu-id="3c2df-121">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="3c2df-121">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="3c2df-122">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="3c2df-122">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="3c2df-123">Segurança</span><span class="sxs-lookup"><span data-stu-id="3c2df-123">Security</span></span>](#Security)  
  
-   <span data-ttu-id="3c2df-124">**Para gravar eventos de auditoria do SQL Server no log de segurança:**</span><span class="sxs-lookup"><span data-stu-id="3c2df-124">**To write SQL Server audit events to the Security Log:**</span></span>  
  
     [<span data-ttu-id="3c2df-125">Definir a configuração de acesso ao objeto de auditoria no Windows usando auditpol</span><span class="sxs-lookup"><span data-stu-id="3c2df-125">Configure the audit object access setting in Windows using auditpol</span></span>](#auditpolAccess)  
  
     [<span data-ttu-id="3c2df-126">Definir a configuração de acesso ao objeto de auditoria no Windows usando secpol</span><span class="sxs-lookup"><span data-stu-id="3c2df-126">Configure the audit object access setting in Windows using secpol</span></span>](#secpolAccess)  
  
     [<span data-ttu-id="3c2df-127">Conceder a permissão gerar auditorias de segurança a uma conta usando secpol</span><span class="sxs-lookup"><span data-stu-id="3c2df-127">Grant the generate security audits permission to an account using secpol</span></span>](#secpolPermission)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="3c2df-128">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="3c2df-128">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="3c2df-129">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="3c2df-129">Limitations and Restrictions</span></span>  
 <span data-ttu-id="3c2df-130">Os administradores do computador com o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] devem entender que as configurações locais do log de segurança podem ser substituídas por uma política de domínio.</span><span class="sxs-lookup"><span data-stu-id="3c2df-130">Administrators of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] computer should understand that local settings for the Security log can be overwritten by a domain policy.</span></span> <span data-ttu-id="3c2df-131">Nesse caso, a política de domínio poderá substituir a configuração de subcategoria (**auditpol /get /subcategory:"application generated"** ).</span><span class="sxs-lookup"><span data-stu-id="3c2df-131">In this case, the domain policy might overwrite the subcategory setting (**auditpol /get /subcategory:"application generated"**).</span></span> <span data-ttu-id="3c2df-132">Isso pode afetar a capacidade do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] de registrar eventos em log, sem que haja uma maneira de detectar que os eventos que o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] está tentando auditar não serão registrados.</span><span class="sxs-lookup"><span data-stu-id="3c2df-132">This can affect [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] ability to log events without having any way to detect that the events that [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] is trying to audit are not going to be recorded.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="3c2df-133">Segurança</span><span class="sxs-lookup"><span data-stu-id="3c2df-133">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="3c2df-134">Permissões</span><span class="sxs-lookup"><span data-stu-id="3c2df-134">Permissions</span></span>  
 <span data-ttu-id="3c2df-135">Você deve ser um administrador do Windows para definir essas configurações.</span><span class="sxs-lookup"><span data-stu-id="3c2df-135">You must be a Windows administrator to configure these settings.</span></span>  
  
##  <a name="to-configure-the-audit-object-access-setting-in-windows-using-auditpol"></a><a name="auditpolAccess"></a> <span data-ttu-id="3c2df-136">Para definir a configuração de acesso ao objeto de auditoria no Windows usando auditpol</span><span class="sxs-lookup"><span data-stu-id="3c2df-136">To configure the audit object access setting in Windows using auditpol</span></span>  
  
1.  <span data-ttu-id="3c2df-137">Abra um prompt de comando com permissões administrativas.</span><span class="sxs-lookup"><span data-stu-id="3c2df-137">Open a command prompt with administrative permissions.</span></span>  
  
    1.  <span data-ttu-id="3c2df-138">No menu **Iniciar** , aponte para **Todos os Programas**, para **Acessórios**, clique com o botão direito do mouse no **Prompt de Comando**e clique em **Executar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="3c2df-138">On the **Start** menu, point to **All Programs**, point to **Accessories**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>  
  
    2.  <span data-ttu-id="3c2df-139">Se a caixa de diálogo **Controle de Conta de Usuário** for aberta, clique em **Continuar**.</span><span class="sxs-lookup"><span data-stu-id="3c2df-139">If the **User Account Control** dialog box opens, click **Continue**.</span></span>  
  
2.  <span data-ttu-id="3c2df-140">Execute a instrução a seguir para habilitar a auditoria de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3c2df-140">Execute the following statement to enable auditing from [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
    ```  
    auditpol /set /subcategory:"application generated" /success:enable /failure:enable  
    ```  
  
3.  <span data-ttu-id="3c2df-141">Feche a janela do prompt de comando.</span><span class="sxs-lookup"><span data-stu-id="3c2df-141">Close the command prompt window.</span></span>  
  
##  <a name="to-grant-the-generate-security-audits-permission-to-an-account-using-secpol"></a><a name="secpolAccess"></a> <span data-ttu-id="3c2df-142">Para conceder a permissão gerar auditorias de segurança a uma conta usando secpol</span><span class="sxs-lookup"><span data-stu-id="3c2df-142">To grant the generate security audits permission to an account using secpol</span></span>  
  
1.  <span data-ttu-id="3c2df-143">Para qualquer sistema operacional Windows, no menu **Iniciar** , clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="3c2df-143">For any Windows operating system, on the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="3c2df-144">Digite **secpol.msc** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="3c2df-144">Type **secpol.msc** and then click **OK**.</span></span> <span data-ttu-id="3c2df-145">Se a caixa de diálogo **Controle de Acesso de Usuário** aparecer, clique em **Continuar**.</span><span class="sxs-lookup"><span data-stu-id="3c2df-145">If the **User Access Control** dialog box appears, click **Continue**.</span></span>  
  
3.  <span data-ttu-id="3c2df-146">Na ferramenta Política de Segurança Local, expanda **Configurações de Segurança**, **Políticas Locais**e clique em **Atribuição de Direitos de Usuário**.</span><span class="sxs-lookup"><span data-stu-id="3c2df-146">In the Local Security Policy tool, expand **Security Settings**, expand **Local Policies**, and then click **User Rights Assignment**.</span></span>  
  
4.  <span data-ttu-id="3c2df-147">No painel de resultados, clique duas vezes em **Gerar auditoria de segurança**.</span><span class="sxs-lookup"><span data-stu-id="3c2df-147">In the results pane, double-click **Generate security audits**.</span></span>  
  
5.  <span data-ttu-id="3c2df-148">Na guia **Configuração de Segurança Local** , clique em **Adicionar Usuário ou Grupo**.</span><span class="sxs-lookup"><span data-stu-id="3c2df-148">On the **Local Security Setting** tab, click **Add User or Group**.</span></span>  
  
6.  <span data-ttu-id="3c2df-149">Na caixa de diálogo **Selecionar Usuários, Computadores ou Grupos** , digite o nome da conta de usuário, como **domain1\user1** e clique em **OK**ou em **Avançado** e procure a conta.</span><span class="sxs-lookup"><span data-stu-id="3c2df-149">In the **Select Users, Computers, or Groups** dialog box, either type the name of the user account, such as **domain1\user1** and then click **OK**, or click **Advanced** and search for the account.</span></span>  
  
7.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
8.  <span data-ttu-id="3c2df-150">Feche a ferramenta Política de Segurança.</span><span class="sxs-lookup"><span data-stu-id="3c2df-150">Close the Security Policy tool.</span></span>  
  
9. <span data-ttu-id="3c2df-151">Reinicie [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] para habilitar essa configuração.</span><span class="sxs-lookup"><span data-stu-id="3c2df-151">Restart [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to enable this setting.</span></span>  
  
##  <a name="to-configure-the-audit-object-access-setting-in-windows-using-secpol"></a><a name="secpolPermission"></a> <span data-ttu-id="3c2df-152">Para definir a configuração de acesso ao objeto de auditoria no Windows usando secpol</span><span class="sxs-lookup"><span data-stu-id="3c2df-152">To configure the audit object access setting in Windows using secpol</span></span>  
  
1.  <span data-ttu-id="3c2df-153">Se o sistema operacional for anterior ao [!INCLUDE[wiprlhext](../../../includes/wiprlhext-md.md)] ou Windows Server 2008, no menu **Iniciar** , clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="3c2df-153">If the operating system is earlier than [!INCLUDE[wiprlhext](../../../includes/wiprlhext-md.md)] or Windows Server 2008, on the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="3c2df-154">Digite **secpol.msc** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="3c2df-154">Type **secpol.msc** and then click **OK**.</span></span> <span data-ttu-id="3c2df-155">Se a caixa de diálogo **Controle de Acesso de Usuário** aparecer, clique em **Continuar**.</span><span class="sxs-lookup"><span data-stu-id="3c2df-155">If the **User Access Control** dialog box appears, click **Continue**.</span></span>  
  
3.  <span data-ttu-id="3c2df-156">Na ferramenta Política de Segurança Local, expanda **Configurações de segurança**, **Políticas Locais**e clique em **Política de Auditoria**.</span><span class="sxs-lookup"><span data-stu-id="3c2df-156">In the Local Security Policy tool, expand **Security Settings**, expand **Local Policies**, and then click **Audit Policy**.</span></span>  
  
4.  <span data-ttu-id="3c2df-157">No painel de resultados, clique duas vezes em **Auditar acesso ao objeto**.</span><span class="sxs-lookup"><span data-stu-id="3c2df-157">In the results pane, double-click **Audit object access**.</span></span>  
  
5.  <span data-ttu-id="3c2df-158">Na guia **Configuração de Segurança Local** , na área **Fazer a auditoria dessas tentativas** , selecione **Êxito** e **Falha**.</span><span class="sxs-lookup"><span data-stu-id="3c2df-158">On the **Local Security Setting** tab, in the **Audit these attempts** area, select both **Success** and **Failure**.</span></span>  
  
6.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
7.  <span data-ttu-id="3c2df-159">Feche a ferramenta Política de Segurança.</span><span class="sxs-lookup"><span data-stu-id="3c2df-159">Close the Security Policy tool.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c2df-160">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="3c2df-160">See Also</span></span>  
 [<span data-ttu-id="3c2df-161">Auditoria do SQL Server &#40;Mecanismo de Banco de Dados&#41;</span><span class="sxs-lookup"><span data-stu-id="3c2df-161">SQL Server Audit &#40;Database Engine&#41;</span></span>](sql-server-audit-database-engine.md)  
  
  
