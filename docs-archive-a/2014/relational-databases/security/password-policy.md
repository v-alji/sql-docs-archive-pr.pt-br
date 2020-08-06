---
title: Política de senha | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- ALTER LOGIN statement
- passwords [SQL Server], policy enforcement
- logins [SQL Server], passwords
- CHECK_EXPIRATION option
- complex passwords [SQL Server]
- passwords [SQL Server], expiration
- manual bad password count resets
- MUST_CHANGE option
- expiration [SQL Server]
- expired password [SQL Server]
- symbols [SQL Server]
- NetValidatePasswordPolicy() API
- passwords [SQL Server]
- password policy [SQL Server]
- resetting bad password counts
- security [SQL Server], passwords
- CHECK_POLICY option
- passwords [SQL Server], symbols
- bad password counts
- passwords [SQL Server], complexity
- characters [SQL Server], password policies
ms.assetid: c0040c0a-a18f-45b9-9c40-0625685649b1
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 902c46b4609a32139450843414a3c4d97b52fcf7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570562"
---
# <a name="password-policy"></a><span data-ttu-id="7aa89-102">Política de senha</span><span class="sxs-lookup"><span data-stu-id="7aa89-102">Password Policy</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="7aa89-103">pode usar os mecanismos de política de senha do Windows.</span><span class="sxs-lookup"><span data-stu-id="7aa89-103">can use Windows password policy mechanisms.</span></span> <span data-ttu-id="7aa89-104">A política de senha se aplica a um logon que usa a autenticação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e a um usuário de banco de dados independente com senha.</span><span class="sxs-lookup"><span data-stu-id="7aa89-104">The password policy applies to a login that uses [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] authentication, and to a contained database user with password.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="7aa89-105">pode aplicar as mesmas políticas de complexidade e expiração usadas no Windows para senhas usadas no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7aa89-105">can apply the same complexity and expiration policies used in Windows to passwords used inside [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="7aa89-106">Esta funcionalidade depende da `NetValidatePasswordPolicy` API.</span><span class="sxs-lookup"><span data-stu-id="7aa89-106">This functionality depends on the `NetValidatePasswordPolicy` API.</span></span>  
  
## <a name="password-complexity"></a><span data-ttu-id="7aa89-107">Complexidade de senha</span><span class="sxs-lookup"><span data-stu-id="7aa89-107">Password Complexity</span></span>  
 <span data-ttu-id="7aa89-108">As políticas de complexidade de senha são projetadas para deter ataques de força bruta aumentando o número de possíveis senhas.</span><span class="sxs-lookup"><span data-stu-id="7aa89-108">Password complexity policies are designed to deter brute force attacks by increasing the number of possible passwords.</span></span> <span data-ttu-id="7aa89-109">Quando a política de complexidade de senha é imposta, as novas senhas devem atender às seguintes diretrizes:</span><span class="sxs-lookup"><span data-stu-id="7aa89-109">When password complexity policy is enforced, new passwords must meet the following guidelines:</span></span>  
  
-   <span data-ttu-id="7aa89-110">A senha não contém o nome de conta do usuário.</span><span class="sxs-lookup"><span data-stu-id="7aa89-110">The password does not contain the account name of the user.</span></span>  
  
-   <span data-ttu-id="7aa89-111">A senha tem um comprimento de pelo menos oito caracteres.</span><span class="sxs-lookup"><span data-stu-id="7aa89-111">The password is at least eight characters long.</span></span>  
  
-   <span data-ttu-id="7aa89-112">A senha contém caracteres de três das quatro categorias seguintes:</span><span class="sxs-lookup"><span data-stu-id="7aa89-112">The password contains characters from three of the following four categories:</span></span>  
  
    -   <span data-ttu-id="7aa89-113">Letras maiúsculas latinas (A a Z)</span><span class="sxs-lookup"><span data-stu-id="7aa89-113">Latin uppercase letters (A through Z)</span></span>  
  
    -   <span data-ttu-id="7aa89-114">Letras minúsculas latinas (a a z)</span><span class="sxs-lookup"><span data-stu-id="7aa89-114">Latin lowercase letters (a through z)</span></span>  
  
    -   <span data-ttu-id="7aa89-115">10 dígitos base (0 a 9)</span><span class="sxs-lookup"><span data-stu-id="7aa89-115">Base 10 digits (0 through 9)</span></span>  
  
    -   <span data-ttu-id="7aa89-116">Caracteres não alfanuméricos como: ponto de exclamação (!), cifrão ($), sinal numérico (#) ou porcentagem (%).</span><span class="sxs-lookup"><span data-stu-id="7aa89-116">Non-alphanumeric characters such as: exclamation point (!), dollar sign ($), number sign (#), or percent (%).</span></span>  
  
 <span data-ttu-id="7aa89-117">As senhas podem ter até 128 caracteres.</span><span class="sxs-lookup"><span data-stu-id="7aa89-117">Passwords can be up to 128 characters long.</span></span> <span data-ttu-id="7aa89-118">Você deve usar senhas que sejam longas e complexas.</span><span class="sxs-lookup"><span data-stu-id="7aa89-118">You should use passwords that are as long and complex as possible.</span></span>  
  
## <a name="password-expiration"></a><span data-ttu-id="7aa89-119">Vencimento da senha</span><span class="sxs-lookup"><span data-stu-id="7aa89-119">Password Expiration</span></span>  
 <span data-ttu-id="7aa89-120">As políticas de vencimento da senha são usadas para gerenciar o tempo de vida de uma senha.</span><span class="sxs-lookup"><span data-stu-id="7aa89-120">Password expiration policies are used to manage the lifespan of a password.</span></span> <span data-ttu-id="7aa89-121">Quando o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] impõe a política de expiração de senha, os usuários são lembrados a alterar as senhas antigas e as contas com senhas expiradas são desabilitadas.</span><span class="sxs-lookup"><span data-stu-id="7aa89-121">When [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] enforces password expiration policy, users are reminded to change old passwords, and accounts that have expired passwords are disabled.</span></span>  
  
## <a name="policy-enforcement"></a><span data-ttu-id="7aa89-122">Imposição de política</span><span class="sxs-lookup"><span data-stu-id="7aa89-122">Policy Enforcement</span></span>  
 <span data-ttu-id="7aa89-123">A imposição da política de senha pode ser configurada separadamente para cada logon do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7aa89-123">The enforcement of password policy can be configured separately for each SQL Server login.</span></span> <span data-ttu-id="7aa89-124">Use [ALTER LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-login-transact-sql) Para configurar as opções da política de senha de um logon do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7aa89-124">Use [ALTER LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-login-transact-sql) to configure the password policy options of a SQL Server login.</span></span> <span data-ttu-id="7aa89-125">As regras seguintes se aplicam à configuração da imposição de política de senha:</span><span class="sxs-lookup"><span data-stu-id="7aa89-125">The following rules apply to the configuration of password policy enforcement:</span></span>  
  
-   <span data-ttu-id="7aa89-126">Quando CHECK_POLICY é alterado para ON, o seguinte comportamento ocorre:</span><span class="sxs-lookup"><span data-stu-id="7aa89-126">When CHECK_POLICY is changed to ON, the following behaviors occur:</span></span>  
  
    -   <span data-ttu-id="7aa89-127">CHECK_EXPIRATION também é definido como ON, a menos que seja definido explicitamente como OFF.</span><span class="sxs-lookup"><span data-stu-id="7aa89-127">CHECK_EXPIRATION is also set to ON unless it is explicitly set to OFF.</span></span>  
  
    -   <span data-ttu-id="7aa89-128">O histórico de senhas é inicializado com o valor do hash da senha atual.</span><span class="sxs-lookup"><span data-stu-id="7aa89-128">The password history is initialized with the value of the current password hash.</span></span>  
  
    -   <span data-ttu-id="7aa89-129">As opções**duração do bloqueio de conta**, **limite de bloqueio de conta**e **zerar contador de bloqueios de conta após** também estão habilitadas.</span><span class="sxs-lookup"><span data-stu-id="7aa89-129">**Account lockout duration**, **account lockout threshold**, and **reset account lockout counter after** are also enabled.</span></span>  
  
-   <span data-ttu-id="7aa89-130">Quando CHECK_POLICY é alterado para OFF, o seguinte comportamento ocorre:</span><span class="sxs-lookup"><span data-stu-id="7aa89-130">When CHECK_POLICY is changed to OFF, the following behaviors occur:</span></span>  
  
    -   <span data-ttu-id="7aa89-131">CHECK_EXPIRATION também será definido como OFF.</span><span class="sxs-lookup"><span data-stu-id="7aa89-131">CHECK_EXPIRATION is also set to OFF.</span></span>  
  
    -   <span data-ttu-id="7aa89-132">O histórico de senhas será apagado.</span><span class="sxs-lookup"><span data-stu-id="7aa89-132">The password history is cleared.</span></span>  
  
    -   <span data-ttu-id="7aa89-133">O valor de `lockout_time` é redefinido.</span><span class="sxs-lookup"><span data-stu-id="7aa89-133">The value of `lockout_time` is reset.</span></span>  
  
 <span data-ttu-id="7aa89-134">Algumas combinações de opções de política não têm suporte.</span><span class="sxs-lookup"><span data-stu-id="7aa89-134">Some combinations of policy options are not supported.</span></span>  
  
-   <span data-ttu-id="7aa89-135">Se MUST_CHANGE for especificado, CHECK_EXPIRATION e CHECK_POLICY deverão ser definidos como ON.</span><span class="sxs-lookup"><span data-stu-id="7aa89-135">If MUST_CHANGE is specified, CHECK_EXPIRATION and CHECK_POLICY must be set to ON.</span></span> <span data-ttu-id="7aa89-136">Caso contrário, a instrução falhará.</span><span class="sxs-lookup"><span data-stu-id="7aa89-136">Otherwise, the statement will fail.</span></span>  
  
-   <span data-ttu-id="7aa89-137">Se CHECK_POLICY for definido como OFF, CHECK_EXPIRATION não poderá ser definido como ON.</span><span class="sxs-lookup"><span data-stu-id="7aa89-137">If CHECK_POLICY is set to OFF, CHECK_EXPIRATION cannot be set to ON.</span></span> <span data-ttu-id="7aa89-138">Uma instrução ALTER LOGON com essa combinação de opções falhará.</span><span class="sxs-lookup"><span data-stu-id="7aa89-138">An ALTER LOGIN statement that has this combination of options will fail.</span></span>  
  
 <span data-ttu-id="7aa89-139">A definição de CHECK_POLICY = ON impedirá a criação de senhas que são:</span><span class="sxs-lookup"><span data-stu-id="7aa89-139">Setting CHECK_POLICY = ON will prevent the creation of passwords that are:</span></span>  
  
-   <span data-ttu-id="7aa89-140">Nulas ou em branco</span><span class="sxs-lookup"><span data-stu-id="7aa89-140">Null or empty</span></span>  
  
-   <span data-ttu-id="7aa89-141">A mesma do computador ou logon</span><span class="sxs-lookup"><span data-stu-id="7aa89-141">Same as name of computer or login</span></span>  
  
-   <span data-ttu-id="7aa89-142">Qualquer dos seguintes: "password", "admin", "administrator", "sa", "sysadmin"</span><span class="sxs-lookup"><span data-stu-id="7aa89-142">Any of the following: "password", "admin", "administrator", "sa", "sysadmin"</span></span>  
  
 <span data-ttu-id="7aa89-143">A política de senha pode ser configurada no Windows ou transmitida por um domínio.</span><span class="sxs-lookup"><span data-stu-id="7aa89-143">The security policy might be set in Windows, or might be received from the domain.</span></span> <span data-ttu-id="7aa89-144">Para exibir a política de senha do computador, use o snap-in do MMC da Política de Segurança Local (**secpol.msc**).</span><span class="sxs-lookup"><span data-stu-id="7aa89-144">To view the password policy on the computer, use the Local Security Policy MMC snap-in (**secpol.msc**).</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="7aa89-145">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="7aa89-145">Related Tasks</span></span>  
 [<span data-ttu-id="7aa89-146">CREATE LOGIN &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="7aa89-146">CREATE LOGIN &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-login-transact-sql)  
  
 [<span data-ttu-id="7aa89-147">ALTER LOGIN &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="7aa89-147">ALTER LOGIN &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-login-transact-sql)  
  
 [<span data-ttu-id="7aa89-148">CREATE USER &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="7aa89-148">CREATE USER &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-user-transact-sql)  
  
 [<span data-ttu-id="7aa89-149">ALTER USER &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="7aa89-149">ALTER USER &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-user-transact-sql)  
  
 [<span data-ttu-id="7aa89-150">Criar um logon</span><span class="sxs-lookup"><span data-stu-id="7aa89-150">Create a Login</span></span>](authentication-access/create-a-login.md)  
  
 [<span data-ttu-id="7aa89-151">Criar um usuário de banco de dados</span><span class="sxs-lookup"><span data-stu-id="7aa89-151">Create a Database User</span></span>](authentication-access/create-a-database-user.md)  
  
## <a name="related-content"></a><span data-ttu-id="7aa89-152">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="7aa89-152">Related Content</span></span>  
 [<span data-ttu-id="7aa89-153">Senhas fortes</span><span class="sxs-lookup"><span data-stu-id="7aa89-153">Strong Passwords</span></span>](strong-passwords.md)  
  
  
