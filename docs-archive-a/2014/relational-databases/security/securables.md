---
title: Protegíveis | Microsoft Docs
ms.custom: ''
ms.date: 10/14/2015
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- sql12.swb.roleproperties.selectobject.f1
helpviewer_keywords:
- securables [SQL Server]
- schemas [SQL Server], securables
- database securables [SQL Server]
- hierarchies [SQL Server], securables
- server securables [SQL Server]
ms.assetid: bfa748f0-70b0-453c-870a-04b7b205b9ff
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: ff2aaba72e2e5489694d31b35e594622c099acab
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679785"
---
# <a name="securables"></a><span data-ttu-id="91270-102">Protegíveis</span><span class="sxs-lookup"><span data-stu-id="91270-102">Securables</span></span>
  <span data-ttu-id="91270-103">Protegíveis são os recursos cujo acesso é regulado pelo sistema de autorização do [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="91270-103">Securables are the resources to which the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] authorization system regulates access.</span></span> <span data-ttu-id="91270-104">Por exemplo, uma tabela é um protegível.</span><span class="sxs-lookup"><span data-stu-id="91270-104">For example, a table is a securable.</span></span> <span data-ttu-id="91270-105">Alguns protegíveis podem ser contidos dentro de outros, criando hierarquias aninhadas chamadas "escopos" que podem ser protegidos.</span><span class="sxs-lookup"><span data-stu-id="91270-105">Some securables can be contained within others, creating nested hierarchies called "scopes" that can themselves be secured.</span></span> <span data-ttu-id="91270-106">Os escopos protegíveis são **servidor**, **banco de dados**e **esquema**.</span><span class="sxs-lookup"><span data-stu-id="91270-106">The securable scopes are **server**, **database**, and **schema**.</span></span>  
  
## <a name="securable-scope-server"></a><span data-ttu-id="91270-107">Escopo protegível: Servidor</span><span class="sxs-lookup"><span data-stu-id="91270-107">Securable scope: Server</span></span>  
 <span data-ttu-id="91270-108">O escopo protegível **servidor** contém os seguintes protegíveis:</span><span class="sxs-lookup"><span data-stu-id="91270-108">The **server** securable scope contains the following securables:</span></span>  
  
-   <span data-ttu-id="91270-109">grupo de disponibilidade</span><span class="sxs-lookup"><span data-stu-id="91270-109">Availability group</span></span>  
  
-   <span data-ttu-id="91270-110">Ponto de extremidade</span><span class="sxs-lookup"><span data-stu-id="91270-110">Endpoint</span></span>  
  
-   <span data-ttu-id="91270-111">Logon</span><span class="sxs-lookup"><span data-stu-id="91270-111">Login</span></span>  
  
-   <span data-ttu-id="91270-112">Função de servidor</span><span class="sxs-lookup"><span data-stu-id="91270-112">Server role</span></span>  
  
-   <span data-ttu-id="91270-113">Banco de dados</span><span class="sxs-lookup"><span data-stu-id="91270-113">Database</span></span>  
  
## <a name="securable-scope-database"></a><span data-ttu-id="91270-114">Escopo protegível: Banco de dados</span><span class="sxs-lookup"><span data-stu-id="91270-114">Securable scope: Database</span></span>  
 <span data-ttu-id="91270-115">O escopo protegível **banco de dados** contém os seguintes protegíveis:</span><span class="sxs-lookup"><span data-stu-id="91270-115">The **database** securable scope contains the following securables:</span></span>  
  
-   <span data-ttu-id="91270-116">Função de aplicativo</span><span class="sxs-lookup"><span data-stu-id="91270-116">Application role</span></span>  
  
-   <span data-ttu-id="91270-117">Assembly</span><span class="sxs-lookup"><span data-stu-id="91270-117">Assembly</span></span>  
  
-   <span data-ttu-id="91270-118">Chave assimétrica</span><span class="sxs-lookup"><span data-stu-id="91270-118">Asymmetric key</span></span>  
  
-   <span data-ttu-id="91270-119">Certificado</span><span class="sxs-lookup"><span data-stu-id="91270-119">Certificate</span></span>  
  
-   <span data-ttu-id="91270-120">Contrato</span><span class="sxs-lookup"><span data-stu-id="91270-120">Contract</span></span>  
  
-   <span data-ttu-id="91270-121">Catálogo de texto completo</span><span class="sxs-lookup"><span data-stu-id="91270-121">Fulltext catalog</span></span>  
  
-   <span data-ttu-id="91270-122">Lista de palavras irrelevantes completa</span><span class="sxs-lookup"><span data-stu-id="91270-122">Fulltext stoplist</span></span>  
  
-   <span data-ttu-id="91270-123">Tipo de mensagem</span><span class="sxs-lookup"><span data-stu-id="91270-123">Message type</span></span>  
  
-   <span data-ttu-id="91270-124">Associação de serviço remoto</span><span class="sxs-lookup"><span data-stu-id="91270-124">Remote Service Binding</span></span>  
  
-   <span data-ttu-id="91270-125">Função (banco de dados)</span><span class="sxs-lookup"><span data-stu-id="91270-125">(Database) Role</span></span>  
  
-   <span data-ttu-id="91270-126">Rota</span><span class="sxs-lookup"><span data-stu-id="91270-126">Route</span></span>  
  
-   <span data-ttu-id="91270-127">Esquema</span><span class="sxs-lookup"><span data-stu-id="91270-127">Schema</span></span>  
  
-   <span data-ttu-id="91270-128">Lista de propriedades de pesquisa</span><span class="sxs-lookup"><span data-stu-id="91270-128">Search property list</span></span>  
  
-   <span data-ttu-id="91270-129">Serviço</span><span class="sxs-lookup"><span data-stu-id="91270-129">Service</span></span>  
  
-   <span data-ttu-id="91270-130">Chave simétrica</span><span class="sxs-lookup"><span data-stu-id="91270-130">Symmetric key</span></span>  
  
-   <span data-ttu-id="91270-131">Usuário</span><span class="sxs-lookup"><span data-stu-id="91270-131">User</span></span>  
  
## <a name="securable-scope-schema"></a><span data-ttu-id="91270-132">Escopo protegível: Esquema</span><span class="sxs-lookup"><span data-stu-id="91270-132">Securable scope: Schema</span></span>  
 <span data-ttu-id="91270-133">O escopo protegível **esquema** contém os seguintes protegíveis:</span><span class="sxs-lookup"><span data-stu-id="91270-133">The **schema** securable scope contains the following securables:</span></span>  
  
-   <span data-ttu-id="91270-134">Type</span><span class="sxs-lookup"><span data-stu-id="91270-134">Type</span></span>  
  
-   <span data-ttu-id="91270-135">Coleção de esquemas XML</span><span class="sxs-lookup"><span data-stu-id="91270-135">XML schema collection</span></span>  
  
-   <span data-ttu-id="91270-136">Objeto – a classe de objeto tem os seguintes membros:</span><span class="sxs-lookup"><span data-stu-id="91270-136">Object - The object class has the following members:</span></span>  
  
    -   <span data-ttu-id="91270-137">Agregado</span><span class="sxs-lookup"><span data-stu-id="91270-137">Aggregate</span></span>  
  
    -   <span data-ttu-id="91270-138">Função</span><span class="sxs-lookup"><span data-stu-id="91270-138">Function</span></span>  
  
    -   <span data-ttu-id="91270-139">Procedimento</span><span class="sxs-lookup"><span data-stu-id="91270-139">Procedure</span></span>  
  
    -   <span data-ttu-id="91270-140">Fila</span><span class="sxs-lookup"><span data-stu-id="91270-140">Queue</span></span>  
  
    -   <span data-ttu-id="91270-141">Sinônimo</span><span class="sxs-lookup"><span data-stu-id="91270-141">Synonym</span></span>  
  
    -   <span data-ttu-id="91270-142">Tabela</span><span class="sxs-lookup"><span data-stu-id="91270-142">Table</span></span>  
  
    -   <span data-ttu-id="91270-143">Visualizar</span><span class="sxs-lookup"><span data-stu-id="91270-143">View</span></span>  
  
## <a name="controlling-access-to-a-securable"></a><span data-ttu-id="91270-144">Controlando o acesso a um protegível</span><span class="sxs-lookup"><span data-stu-id="91270-144">Controlling Access to a Securable</span></span>  
 <span data-ttu-id="91270-145">A entidade que recebe permissão para um protegível é chamada de entidade de segurança.</span><span class="sxs-lookup"><span data-stu-id="91270-145">The entity that receives permission to a securable is called a principal.</span></span> <span data-ttu-id="91270-146">As entidades de segurança mais comuns são logons e usuários de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="91270-146">The most common principals are logins and database users.</span></span> <span data-ttu-id="91270-147">O acesso a protegíveis é controlado pela concessão ou negação de permissões, ou pela adição de logons e de usuários a funções que têm acesso.</span><span class="sxs-lookup"><span data-stu-id="91270-147">Access to securables is controlled by granting or denying permissions, or by adding logins and user to roles which have access.</span></span> <span data-ttu-id="91270-148">Para obter informações sobre como controlar permissões, veja [GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql), [REVOKE &#40;Transact-SQL&#41;](/sql/t-sql/statements/revoke-transact-sql), [DENY &#40;Transact-SQL&#41;](/sql/t-sql/statements/deny-transact-sql), [sp_addrolemember &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addrolemember-transact-sql) e [sp_droprolemember &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-droprolemember-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="91270-148">For information about controlling permissions, see [GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql), [REVOKE &#40;Transact-SQL&#41;](/sql/t-sql/statements/revoke-transact-sql), [DENY &#40;Transact-SQL&#41;](/sql/t-sql/statements/deny-transact-sql), [sp_addrolemember &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addrolemember-transact-sql), and [sp_droprolemember &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-droprolemember-transact-sql).</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="91270-149">As permissões padrão concedidas aos objetos de sistema no momento da instalação são avaliadas cuidadosamente contra possíveis ameaças e não precisam ser alteradas como parte do sistema de proteção de instalação do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="91270-149">The default permissions that are granted to system objects at the time of setup are carefully evaluated against possible threats and need not be altered as part of hardening the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] installation.</span></span> <span data-ttu-id="91270-150">Qualquer alteração nas permissões nos objetos de sistema poderia limitar ou interromper a funcionalidade e potencialmente pode deixar a instalação do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] em um estado sem suporte.</span><span class="sxs-lookup"><span data-stu-id="91270-150">Any changes to the permissions on the system objects could limit or break the functionality and could potentially leave your [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] installation in an unsupported state.</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="91270-151">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="91270-151">Related Content</span></span>  
 [<span data-ttu-id="91270-152">Protegendo o SQL Server</span><span class="sxs-lookup"><span data-stu-id="91270-152">Securing SQL Server</span></span>](securing-sql-server.md)  
  
 [<span data-ttu-id="91270-153">sys.database_principals &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="91270-153">sys.database_principals &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-database-principals-transact-sql)  
  
 [<span data-ttu-id="91270-154">sys.database_role_members &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="91270-154">sys.database_role_members &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-database-role-members-transact-sql)  
  
 [<span data-ttu-id="91270-155">sys.server_principals &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="91270-155">sys.server_principals &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-server-principals-transact-sql)  
  
 [<span data-ttu-id="91270-156">sys.server_role_members &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="91270-156">sys.server_role_members &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-server-role-members-transact-sql)  
  
 [<span data-ttu-id="91270-157">sys.sql_logins &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="91270-157">sys.sql_logins &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-sql-logins-transact-sql)  
  
  
