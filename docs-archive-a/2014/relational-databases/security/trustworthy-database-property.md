---
title: Propriedade de banco de dados TRUSTWORTHY | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- TRUSTWORTHY database property
ms.assetid: 64b2a53d-4416-4a19-acc0-664a61b45348
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 23391fe48037d4cd7f69aef7df6649949301a0f0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679764"
---
# <a name="trustworthy-database-property"></a><span data-ttu-id="5ec11-102">Propriedade de banco de dados TRUSTWORTHY</span><span class="sxs-lookup"><span data-stu-id="5ec11-102">TRUSTWORTHY Database Property</span></span>
  <span data-ttu-id="5ec11-103">A propriedade de banco de dados TRUSTWORTHY é usada para indicar se a instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] confia no banco de dados e em seu conteúdo.</span><span class="sxs-lookup"><span data-stu-id="5ec11-103">The TRUSTWORTHY database property is used to indicate whether the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] trusts the database and the contents within it.</span></span> <span data-ttu-id="5ec11-104">Por padrão, esta configuração é OFF, mas pode ser definida como ON usando a instrução ALTER DATABASE.</span><span class="sxs-lookup"><span data-stu-id="5ec11-104">By default, this setting is OFF, but can be set to ON by using the ALTER DATABASE statement.</span></span> <span data-ttu-id="5ec11-105">Por exemplo, `ALTER DATABASE AdventureWorks2012 SET TRUSTWORTHY ON;`.</span><span class="sxs-lookup"><span data-stu-id="5ec11-105">For example, `ALTER DATABASE AdventureWorks2012 SET TRUSTWORTHY ON;`.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5ec11-106">Para definir esta opção, é preciso ser um membro da função de servidor fixa **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="5ec11-106">To set this option, you must be a member of the **sysadmin** fixed server role.</span></span>  
  
 <span data-ttu-id="5ec11-107">Essa propriedade pode ser usada para reduzir ameaças que podem ocorrer ao anexar um banco de dados que contenha um dos seguintes objetos:</span><span class="sxs-lookup"><span data-stu-id="5ec11-107">This property can be used to reduce certain threats that can exist as a result of attaching a database that contains one of the following objects:</span></span>  
  
-   <span data-ttu-id="5ec11-108">Assemblies maliciosos com um definição de permissão EXTERNAL_ACCESS ou UNSAFE.</span><span class="sxs-lookup"><span data-stu-id="5ec11-108">Malicious assemblies with an EXTERNAL_ACCESS or UNSAFE permission setting.</span></span> <span data-ttu-id="5ec11-109">Para obter mais informações, consulte [CLR Integration Security](../clr-integration/security/clr-integration-security.md).</span><span class="sxs-lookup"><span data-stu-id="5ec11-109">For more information, see [CLR Integration Security](../clr-integration/security/clr-integration-security.md).</span></span>  
  
-   <span data-ttu-id="5ec11-110">Módulos maliciosos que são definidos para serem executados como usuários com altos privilégios.</span><span class="sxs-lookup"><span data-stu-id="5ec11-110">Malicious modules that are defined to execute as high privileged users.</span></span> <span data-ttu-id="5ec11-111">Para obter mais informações, veja [Cláusula EXECUTE AS &#40;Transact-SQL&#41;](/sql/t-sql/statements/execute-as-clause-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="5ec11-111">For more information, see [EXECUTE AS Clause &#40;Transact-SQL&#41;](/sql/t-sql/statements/execute-as-clause-transact-sql).</span></span>  
  
 <span data-ttu-id="5ec11-112">Essas duas situações exigem um grau específico de privilégios e estão protegidas pelos mecanismos adequados, quando usados no contexto de um banco de dados já anexado a uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5ec11-112">Both of these situations require a specific degree of privileges and are protected against by appropriate mechanisms when they are used in the context of a database that is already attached to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="5ec11-113">No entanto, se o banco de dados estiver off-line, um usuário que tem acesso ao arquivo de banco de dados provavelmente poderá anexá-lo a uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de sua preferência e adicionar conteúdo malicioso ao banco de dados.</span><span class="sxs-lookup"><span data-stu-id="5ec11-113">However, if the database is taken offline, a user that has access to the database file can potentially attach it to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] of his or her choice and add malicious content to the database.</span></span> <span data-ttu-id="5ec11-114">Quando bancos de dados são desanexados e anexados no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], determinadas permissões são definidas nos dados e nos arquivos de log restringindo o acesso aos arquivos de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="5ec11-114">When databases are detached and attached in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], certain permissions are set on the data and log files that restrict access to the database files.</span></span>  
  
 <span data-ttu-id="5ec11-115">Como um banco de dados que é anexado a uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] não é confiável imediatamente, ele não tem permissão para acessar recursos além do escopo do banco de dados, até que seja explicitamente marcado como confiável.</span><span class="sxs-lookup"><span data-stu-id="5ec11-115">Because a database that is attached to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cannot be immediately trusted, the database is not allowed to access resources beyond the scope of the database until the database is explicitly marked trustworthy.</span></span> <span data-ttu-id="5ec11-116">Além disso, os módulos que são criados para acessar recursos fora do banco de dados, e assemblies com as definições de permissão EXTERNAL_ACCESS e UNSAFE, têm requisitos adicionais para uma execução bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="5ec11-116">Also, modules that are designed to access resources outside the database, and assemblies with either the EXTERNAL_ACCESS and UNSAFE permission setting, have additional requirements in order to run successfully.</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="5ec11-117">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="5ec11-117">Related Content</span></span>  
 [<span data-ttu-id="5ec11-118">Central de segurança do Mecanismo de Banco de Dados do SQL Server e Banco de Dados SQL do Azure</span><span class="sxs-lookup"><span data-stu-id="5ec11-118">Security Center for SQL Server Database Engine and Azure SQL Database</span></span>](security-center-for-sql-server-database-engine-and-azure-sql-database.md)  
  
 [<span data-ttu-id="5ec11-119">ALTER DATABASE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="5ec11-119">ALTER DATABASE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-database-transact-sql)  
  
  
