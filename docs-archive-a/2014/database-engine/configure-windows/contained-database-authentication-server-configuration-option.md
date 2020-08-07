---
title: Opção de configuração de servidor contained database authentication | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
f1_keywords:
- contained_database_authentication_TSQL
- contained database authentication
helpviewer_keywords:
- contained database, enabling
- contained database authentication option
ms.assetid: b80768d2-ac20-4035-a335-d9adb74b3f6e
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: cf5bf07c8b0913ff81f31ff0ca64a18eee0f2ac2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575326"
---
# <a name="contained-database-authentication-server-configuration-option"></a><span data-ttu-id="d735b-102">Opção de configuração de servidor contained database authentication</span><span class="sxs-lookup"><span data-stu-id="d735b-102">contained database authentication Server Configuration Option</span></span>
  <span data-ttu-id="d735b-103">Use a opção **contained database authentication** para habilitar bancos de dados independentes na instância do [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d735b-103">Use the **contained database authentication** option to enable contained databases on the instance of [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span></span>  
  
 <span data-ttu-id="d735b-104">Essa opção de servidor permite controlar **contained database authentication**.</span><span class="sxs-lookup"><span data-stu-id="d735b-104">This server option allows you to control **contained database authentication**.</span></span>  
  
-   <span data-ttu-id="d735b-105">Quando **contained database authentication** estiver desativada (0) para a instância, os bancos de dados independentes não poderão ser criados, nem conectados ao [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d735b-105">When **contained database authentication** is off (0) for the instance, contained databases cannot be created, or attached to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
-   <span data-ttu-id="d735b-106">Quando **contained database authentication** estiver ativada (1) para a instância, os bancos de dados independentes poderão ser criados ou conectados ao [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d735b-106">When **contained database authentication** is on (1) for the instance, contained databases can be created, or attached to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
 <span data-ttu-id="d735b-107">Um banco de dados independente inclui todas as configurações de banco de dados e metadados necessários para definir o banco de dados e não tem nenhuma dependência de configuração da instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)] onde o banco de dados está instalado.</span><span class="sxs-lookup"><span data-stu-id="d735b-107">A contained database includes all database settings and metadata required to define the database and has no configuration dependencies on the instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] where the database is installed.</span></span> <span data-ttu-id="d735b-108">Os usuários podem se conectar ao banco de dados sem autenticar um logon no nível do [!INCLUDE[ssDE](../../includes/ssde-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d735b-108">Users can connect to the database without authenticating a login at the [!INCLUDE[ssDE](../../includes/ssde-md.md)] level.</span></span> <span data-ttu-id="d735b-109">O isolamento do banco de dados do Mecanismo de Banco de Dados facilita mover o banco de dados para outra instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d735b-109">Isolating the database from the Database Engine makes it possible to easily move the database to another instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="d735b-110">A inclusão de todas as configurações no banco de dados permite que os proprietários do banco de dados gerenciem todas as configurações do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="d735b-110">Including all the database settings in the database enables database owners to manage all the configuration settings for the database.</span></span> <span data-ttu-id="d735b-111">Para obter mais informações sobre bancos de dados independentes, consulte [Contained Databases](../../relational-databases/databases/contained-databases.md).</span><span class="sxs-lookup"><span data-stu-id="d735b-111">For more information about contained databases, see [Contained Databases](../../relational-databases/databases/contained-databases.md).</span></span>  
  
 <span data-ttu-id="d735b-112">Se uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tiver bancos de dados independentes, a configuração **contained database authentication** poderá ser definida como 0 por meio da instrução **RECONFIGURE WITH OVERRIDE** .</span><span class="sxs-lookup"><span data-stu-id="d735b-112">If an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has any contained databases the **contained database authentication** setting can be set to 0 by using the **RECONFIGURE WITH OVERRIDE** statement.</span></span> <span data-ttu-id="d735b-113">Definir **contained database authentication** como 0 desabilitará a autenticação dos bancos de dados independentes.</span><span class="sxs-lookup"><span data-stu-id="d735b-113">Setting **contained database authentication** to 0 will disable contained database authentication for the contained databases.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="d735b-114">Quando os bancos de dados independentes estiverem habilitados, os usuários dos bancos de dados com a permissão ALTER ANY USER, como membros das funções de banco de dados db_owner e db_accessadmin, podem conceder acesso aos bancos de dados e, ao fazer isso, garantir acesso ao [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d735b-114">When contained databases are enabled, database users with the ALTER ANY USER permission, such as members of the db_owner and db_accessadmin database roles, can grant access to databases and by doing so, grant access to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="d735b-115">Isso significa que o controle sobre o acesso ao servidor não está mais limitado aos membros do sysadmin e securityadmin fixo de função de servidor e logons com a permissão de CONTROL SERVER e ALTER ANY LOGIN de nível do servidor.</span><span class="sxs-lookup"><span data-stu-id="d735b-115">This means that control over access to the server is no longer limited to members of the sysadmin and securityadmin fixed server role, and logins with the server level CONTROL SERVER and ALTER ANY LOGIN permission.</span></span> <span data-ttu-id="d735b-116">Antes de permitir bancos de dados independentes, você deve entender os riscos associados a eles.</span><span class="sxs-lookup"><span data-stu-id="d735b-116">Before allowing contained databases, you should understand the risks associated with contained databases.</span></span> <span data-ttu-id="d735b-117">Para obter mais informações, consulte [Security Best Practices with Contained Databases](../../relational-databases/databases/security-best-practices-with-contained-databases.md).</span><span class="sxs-lookup"><span data-stu-id="d735b-117">For more information, see [Security Best Practices with Contained Databases](../../relational-databases/databases/security-best-practices-with-contained-databases.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="d735b-118">Exemplos</span><span class="sxs-lookup"><span data-stu-id="d735b-118">Examples</span></span>  
 <span data-ttu-id="d735b-119">O exemplo a seguir habilita bancos de dados independentes na instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d735b-119">The following example enables contained databases on the instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
```sql  
sp_configure 'contained database authentication', 1;  
GO  
RECONFIGURE;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="d735b-120">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d735b-120">See Also</span></span>  
 <span data-ttu-id="d735b-121">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="d735b-121">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 <span data-ttu-id="d735b-122">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="d735b-122">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 [<span data-ttu-id="d735b-123">Opções de configuração do servidor &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="d735b-123">Server Configuration Options &#40;SQL Server&#41;</span></span>](server-configuration-options-sql-server.md)  
  
  
