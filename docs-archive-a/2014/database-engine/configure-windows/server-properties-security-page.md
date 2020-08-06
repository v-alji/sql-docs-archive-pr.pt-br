---
title: Propriedades do servidor (página Segurança) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
f1_keywords:
- sql12.swb.serverproperties.security.f1
ms.assetid: b8a131c7-e7bd-4203-bf26-234f1ebfe622
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 5f45c0a04a0d7cc627901d8de24175f1d63a99fe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583829"
---
# <a name="server-properties-security-page"></a><span data-ttu-id="fb385-102">Propriedades do Servidor (página Segurança)</span><span class="sxs-lookup"><span data-stu-id="fb385-102">Server Properties (Security Page)</span></span>
  <span data-ttu-id="fb385-103">Use esta página para exibir ou modificar as opções de segurança do servidor.</span><span class="sxs-lookup"><span data-stu-id="fb385-103">Use this page to view or modify your server security options.</span></span>  
  
## <a name="server-authentication"></a><span data-ttu-id="fb385-104">Autenticação do servidor</span><span class="sxs-lookup"><span data-stu-id="fb385-104">Server Authentication</span></span>  
 <span data-ttu-id="fb385-105">**Modo de Autenticação do Windows**</span><span class="sxs-lookup"><span data-stu-id="fb385-105">**Windows Authentication mode**</span></span>  
 <span data-ttu-id="fb385-106">Usa a autenticação do Windows para validar as conexões tentadas.</span><span class="sxs-lookup"><span data-stu-id="fb385-106">Uses Windows Authentication to validate attempted connections.</span></span> <span data-ttu-id="fb385-107">Se a senha **sa** estiver em branco quando o modo de segurança estiver sendo alterado, será solicitado ao usuário que digite a senha **sa** .</span><span class="sxs-lookup"><span data-stu-id="fb385-107">If the **sa** password is blank when the security mode is being changed, the user is prompted to enter an **sa** password.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="fb385-108">A autenticação do Windows é muito mais segura do que a autenticação do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="fb385-108">Windows Authentication is much more secure than SQL Server Authentication.</span></span> <span data-ttu-id="fb385-109">Quando possível, você deve usar a autenticação do Windows.</span><span class="sxs-lookup"><span data-stu-id="fb385-109">When possible, you should use Windows Authentication.</span></span>  
  
 <span data-ttu-id="fb385-110">**Modo de autenticação do SQL Server e do Windows**</span><span class="sxs-lookup"><span data-stu-id="fb385-110">**SQL Server and Windows Authentication mode**</span></span>  
 <span data-ttu-id="fb385-111">Usa autenticação de modo misto para verificar conexões tentadas, para compatibilidade com versões anteriores do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fb385-111">Uses mixed mode authentication to verify attempted connections, for backward compatibility with earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="fb385-112">Se a senha **sa** estiver em branco quando o modo de segurança estiver sendo alterado, será solicitado ao usuário que digite a senha **sa** .</span><span class="sxs-lookup"><span data-stu-id="fb385-112">If the **sa** password is blank when the security mode is being changed, the user is prompted to enter an **sa** password.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fb385-113">A alteração da configuração de segurança requer que o serviço seja reiniciado.</span><span class="sxs-lookup"><span data-stu-id="fb385-113">Changing the security configuration requires a restart of the service.</span></span> <span data-ttu-id="fb385-114">Ao alterar a autenticação do servidor para o modo de autenticação do SQL Server e do Windows a conta SA não é habilitada automaticamente.</span><span class="sxs-lookup"><span data-stu-id="fb385-114">When changing the Server Authentication to SQL Server and Windows Authentication mode the SA account is not automatically enabled.</span></span> <span data-ttu-id="fb385-115">Para usar a conta SA, execute [ALTER LOGIN](/sql/t-sql/statements/alter-login-transact-sql) com a opção ENABLE.</span><span class="sxs-lookup"><span data-stu-id="fb385-115">To use the SA account, execute [ALTER LOGIN](/sql/t-sql/statements/alter-login-transact-sql) with the ENABLE option.</span></span>  
  
## <a name="login-auditing"></a><span data-ttu-id="fb385-116">Auditoria de logon</span><span class="sxs-lookup"><span data-stu-id="fb385-116">Login Auditing</span></span>  
 <span data-ttu-id="fb385-117">**Nenhuma**</span><span class="sxs-lookup"><span data-stu-id="fb385-117">**None**</span></span>  
 <span data-ttu-id="fb385-118">Desativa a auditoria de logon.</span><span class="sxs-lookup"><span data-stu-id="fb385-118">Turns off login auditing.</span></span>  
  
 <span data-ttu-id="fb385-119">**Somente logons com falha**</span><span class="sxs-lookup"><span data-stu-id="fb385-119">**Failed logins only**</span></span>  
 <span data-ttu-id="fb385-120">Auditoria somente de logons sem-êxito.</span><span class="sxs-lookup"><span data-stu-id="fb385-120">Audits unsuccessful logins only.</span></span>  
  
 <span data-ttu-id="fb385-121">**Somente logons bem sucedidos**</span><span class="sxs-lookup"><span data-stu-id="fb385-121">**Successful logins only**</span></span>  
 <span data-ttu-id="fb385-122">Auditoria somente de logons bem sucedidos.</span><span class="sxs-lookup"><span data-stu-id="fb385-122">Audits successful logins only.</span></span>  
  
 <span data-ttu-id="fb385-123">**Logons com falha e bem sucedidos**</span><span class="sxs-lookup"><span data-stu-id="fb385-123">**Both failed and successful logins**</span></span>  
 <span data-ttu-id="fb385-124">Auditoria de todas as tentativas de logon.</span><span class="sxs-lookup"><span data-stu-id="fb385-124">Audits all login attempts.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fb385-125">A alteração do nível de auditoria requer que o serviço seja reiniciado.</span><span class="sxs-lookup"><span data-stu-id="fb385-125">Changing the audit level requires restarting the service.</span></span>  
  
## <a name="server-proxy-account"></a><span data-ttu-id="fb385-126">Conta proxy do servidor</span><span class="sxs-lookup"><span data-stu-id="fb385-126">Server Proxy Account</span></span>  
 <span data-ttu-id="fb385-127">**Habilitar conta proxy do servidor**</span><span class="sxs-lookup"><span data-stu-id="fb385-127">**Enable server proxy account**</span></span>  
 <span data-ttu-id="fb385-128">Habilita uma conta para uso do **xp_cmdshell**.</span><span class="sxs-lookup"><span data-stu-id="fb385-128">Enables an account for use by **xp_cmdshell**.</span></span> <span data-ttu-id="fb385-129">As contas proxy permitem a representação de logons, funções de servidor e funções de bancos de dados quando um comando do sistema operacional está sendo executado.</span><span class="sxs-lookup"><span data-stu-id="fb385-129">Proxy accounts allow for the impersonation of logins, server roles, and database roles when an operating system command is being executed.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="fb385-130">O logon usado pela conta proxy do servidor dever ter os privilégios mínimos exigidos para executar o trabalho pretendido.</span><span class="sxs-lookup"><span data-stu-id="fb385-130">The login used by the server proxy account should have the least privileges required to perform the intended work.</span></span> <span data-ttu-id="fb385-131">Privilégios excessivos para a conta proxy podem ser usados por um usuário mal-intencionado para comprometer a segurança de seu sistema.</span><span class="sxs-lookup"><span data-stu-id="fb385-131">Excessive privileges for the proxy account could be used by a malicious user to compromise your system security.</span></span>  
  
 <span data-ttu-id="fb385-132">**Conta proxy**</span><span class="sxs-lookup"><span data-stu-id="fb385-132">**Proxy account**</span></span>  
 <span data-ttu-id="fb385-133">Especifica a conta proxy usada.</span><span class="sxs-lookup"><span data-stu-id="fb385-133">Specify the proxy account used.</span></span>  
  
 <span data-ttu-id="fb385-134">**Senha**</span><span class="sxs-lookup"><span data-stu-id="fb385-134">**Password**</span></span>  
 <span data-ttu-id="fb385-135">Especifica a senha para a conta proxy.</span><span class="sxs-lookup"><span data-stu-id="fb385-135">Specify the password for the proxy account.</span></span>  
  
## <a name="options"></a><span data-ttu-id="fb385-136">Opções</span><span class="sxs-lookup"><span data-stu-id="fb385-136">Options</span></span>  
 <span data-ttu-id="fb385-137">**Habilitar rastreamento de auditoria C2**</span><span class="sxs-lookup"><span data-stu-id="fb385-137">**Enable C2 audit tracing**</span></span>  
 <span data-ttu-id="fb385-138">Audita todas as tentativas de acessar instruções e objetos e as registra em um arquivo no diretório \MSSQL\Data para as instâncias padrão do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]ou o diretório \MSSQL$*instancename*\Data para instâncias nomeadas do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fb385-138">Audits all attempts to access statements and objects and records them to a file in the \MSSQL\Data directory for default instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], or the \MSSQL$*instancename*\Data directory for named instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="fb385-139">Para obter mais informações, veja [Opção c2 audit mode de configuração de servidor](c2-audit-mode-server-configuration-option.md).</span><span class="sxs-lookup"><span data-stu-id="fb385-139">For more information, see [c2 audit mode Server Configuration Option](c2-audit-mode-server-configuration-option.md).</span></span>  
  
 <span data-ttu-id="fb385-140">**Encadeamento de propriedades de bancos de dados**</span><span class="sxs-lookup"><span data-stu-id="fb385-140">**Cross database ownership chaining**</span></span>  
 <span data-ttu-id="fb385-141">Selecione para permitir que o banco de dados seja a origem ou o destino de um encadeamento de propriedades de bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="fb385-141">Select to allow the database to be the source or target of a cross-database ownership chain.</span></span> <span data-ttu-id="fb385-142">Para obter mais informações, veja [Opção cross db ownership chaining de configuração de servidor](cross-db-ownership-chaining-server-configuration-option.md).</span><span class="sxs-lookup"><span data-stu-id="fb385-142">For more information, see [cross db ownership chaining Server Configuration Option](cross-db-ownership-chaining-server-configuration-option.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb385-143">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="fb385-143">See Also</span></span>  
 [<span data-ttu-id="fb385-144">Opções de configuração do servidor &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="fb385-144">Server Configuration Options &#40;SQL Server&#41;</span></span>](server-configuration-options-sql-server.md)  
  
  
