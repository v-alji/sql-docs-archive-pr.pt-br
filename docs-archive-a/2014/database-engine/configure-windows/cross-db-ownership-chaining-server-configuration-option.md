---
title: Opção de configuração de servidor cross db ownership chaining | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- cross-database ownership chaining
- cross db ownership chaining option
- chaining ownership
ms.assetid: 7b2d49f2-b91c-4aee-a52b-6cc49bed03af
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: cfb768065cc0aa2aaa7aed0f996b18e46f1da7ba
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574906"
---
# <a name="cross-db-ownership-chaining-server-configuration-option"></a><span data-ttu-id="bcaec-102">Opção cross db ownership chaining de configuração de servidor</span><span class="sxs-lookup"><span data-stu-id="bcaec-102">cross db ownership chaining Server Configuration Option</span></span>
  <span data-ttu-id="bcaec-103">Use a opção **cross db ownership chaining** para configurar o encadeamento de propriedades de bancos de dados em uma instância do [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bcaec-103">Use the **cross db ownership chaining** option to configure cross-database ownership chaining for an instance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="bcaec-104">Essa opção de servidor permite que você controle o encadeamento de propriedade no nível do banco de dados ou em todos os bancos de dados:</span><span class="sxs-lookup"><span data-stu-id="bcaec-104">This server option allows you to control cross-database ownership chaining at the database level or to allow cross-database ownership chaining for all databases:</span></span>  
  
-   <span data-ttu-id="bcaec-105">Quando **cross db ownership chaining** estiver desativado (0) para a instância, o encadeamento de propriedades de bancos de dados estará desabilitado para todos os bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="bcaec-105">When **cross db ownership chaining** is off (0) for the instance, cross-database ownership chaining is disabled for all databases.</span></span>  
  
-   <span data-ttu-id="bcaec-106">Quando **cross db ownership chaining** estiver ativado (1) para a instância, estará ativado para todos os bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="bcaec-106">When **cross db ownership chaining** is on (1) for the instance, cross-database ownership chaining is on for all databases.</span></span>  
  
-   <span data-ttu-id="bcaec-107">Você pode definir o encadeamento de propriedades de banco de dados para bancos de dados individuais com a cláusula SET da instrução ALTER DATABASE.</span><span class="sxs-lookup"><span data-stu-id="bcaec-107">You can set cross-database ownership chaining for individual databases using the SET clause of the ALTER DATABASE statement.</span></span> <span data-ttu-id="bcaec-108">Se você estiver criando um novo banco de dados, poderá definir a opção cross db ownership chaining para o novo banco de dados com a instrução CREATE DATABASE.</span><span class="sxs-lookup"><span data-stu-id="bcaec-108">If you are creating a new database, you can set the cross-database ownership chaining option for the new database using the CREATE DATABASE statement.</span></span>  
  
     <span data-ttu-id="bcaec-109">A definição da opção **cross db ownership chaining** como 1 não é recomendada, a menos que todos os bancos de dados hospedados pela instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] precisem participar do encadeamento de propriedades de bancos de dados e que você esteja ciente das implicações de segurança dessa configuração.</span><span class="sxs-lookup"><span data-stu-id="bcaec-109">Setting **cross db ownership chaining** to 1 is not recommended unless all of the databases hosted by the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] must participate in cross-database ownership chaining and you are aware of the security implications of this setting.</span></span>  
  
## <a name="controlling-cross-database-ownership-chaining"></a><span data-ttu-id="bcaec-110">Controlando o encadeamento de propriedades de banco de dados</span><span class="sxs-lookup"><span data-stu-id="bcaec-110">Controlling Cross-Database Ownership Chaining</span></span>  
 <span data-ttu-id="bcaec-111">Antes de ativar ou desativar o encadeamento de propriedades de banco de dados, considere o seguinte:</span><span class="sxs-lookup"><span data-stu-id="bcaec-111">Before turning cross-database ownership chaining on or off, consider the following:</span></span>  
  
-   <span data-ttu-id="bcaec-112">É necessário ser um membro da função de servidor fixa **sysadmin** para ativar ou desativar o encadeamento de propriedades de bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="bcaec-112">You must be a member of the **sysadmin** fixed server role to turn cross-database ownership chaining on or off.</span></span>  
  
-   <span data-ttu-id="bcaec-113">Antes de desativar o encadeamento de propriedades de banco de dados em um servidor de produção, teste completamente todos os aplicativos, inclusive aplicativos de terceiros, para assegurar que as alterações não afetem a funcionalidade do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="bcaec-113">Before turning off cross-database ownership chaining on a production server, fully test all applications, including third-party applications, to ensure that the changes do not affect application functionality.</span></span>  
  
-   <span data-ttu-id="bcaec-114">Você poderá alterar a opção **cross db ownership chaining** enquanto o servidor estiver em execução, se especificar RECONFIGURE com **sp_configure**.</span><span class="sxs-lookup"><span data-stu-id="bcaec-114">You can change the **cross db ownership chaining** option while the server is running if you specify RECONFIGURE with **sp_configure**.</span></span>  
  
-   <span data-ttu-id="bcaec-115">Se houver bancos de dados que exijam o encadeamento de propriedades de bancos de dados, a prática recomendada é desativar a opção **cross db ownership chaining** para a instância usando **sp_configure**e depois ativar o encadeamento de propriedades de bancos de dados para bancos de dados individuais que o exijam usando a instrução ALTER DATABASE.</span><span class="sxs-lookup"><span data-stu-id="bcaec-115">If you have databases that require cross-database ownership chaining, the recommended practice is to turn off the **cross db ownership chaining** option for the instance using **sp_configure**; then turn on cross-database ownership chaining for individual databases that require it using the ALTER DATABASE statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bcaec-116">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="bcaec-116">See Also</span></span>  
 <span data-ttu-id="bcaec-117">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="bcaec-117">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 <span data-ttu-id="bcaec-118">[CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="bcaec-118">[CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span></span>  
 <span data-ttu-id="bcaec-119">[Opções de configuração do servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="bcaec-119">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="bcaec-120">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="bcaec-120">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 [<span data-ttu-id="bcaec-121">RECONFIGURE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="bcaec-121">RECONFIGURE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/language-elements/reconfigure-transact-sql)  
  
  
