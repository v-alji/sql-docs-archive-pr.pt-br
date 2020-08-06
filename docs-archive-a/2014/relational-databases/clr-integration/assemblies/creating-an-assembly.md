---
title: Criando um assembly | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- creating assemblies
- UNSAFE assemblies
- CREATE ASSEMBLY statement
- SAFE assemblies
- EXTERNAL_ACCESS assemblies
- assemblies [CLR integration], creating
ms.assetid: a2bc503d-b6b2-4963-8beb-c11c323f18e0
author: rothja
ms.author: jroth
ms.openlocfilehash: 9dea1f8fe57691f05274cac353a1064420309e06
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87682283"
---
# <a name="creating-an-assembly"></a><span data-ttu-id="e837b-102">Criando um assembly</span><span class="sxs-lookup"><span data-stu-id="e837b-102">Creating an Assembly</span></span>
  <span data-ttu-id="e837b-103">Os objetos de banco de dados gerenciado, como os procedimentos armazenados ou gatilhos, são compilados e implantados em unidades chamadas de assembly.</span><span class="sxs-lookup"><span data-stu-id="e837b-103">Managed database objects, such as stored procedures or triggers, are compiled and then deployed in units called an assembly.</span></span> <span data-ttu-id="e837b-104">Os assemblies DLL gerenciados devem ser registrados no [!INCLUDE[msCoName](../../../includes/ssnoversion-md.md)] antes da funcionalidade que o assembly fornece pode ser usado.</span><span class="sxs-lookup"><span data-stu-id="e837b-104">Managed DLL assemblies must be registered in [!INCLUDE[msCoName](../../../includes/ssnoversion-md.md)] before the functionality the assembly provides can be used.</span></span> <span data-ttu-id="e837b-105">Para registrar um assembly em um banco de dados do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], use a instrução CREATE ASSEMBLY.</span><span class="sxs-lookup"><span data-stu-id="e837b-105">To register an assembly in a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] database, use the CREATE ASSEMBLY statement.</span></span> <span data-ttu-id="e837b-106">Este tópico trata sobre como registrar um assembly em um banco de dados usando a instrução CREATE ASSEMBLY e como especificar as configurações de segurança do assembly.</span><span class="sxs-lookup"><span data-stu-id="e837b-106">This topic discusses how to register an assembly in a database using the CREATE ASSEMBLY statement, and how to specify the security settings for the assembly.</span></span>  
  
## <a name="the-create-assembly-statement"></a><span data-ttu-id="e837b-107">A instrução CREATE ASSEMBLY</span><span class="sxs-lookup"><span data-stu-id="e837b-107">The CREATE ASSEMBLY Statement</span></span>  
 <span data-ttu-id="e837b-108">A instrução CREATE ASSEMBLY é usada para criar um assembly em um banco de dados.</span><span class="sxs-lookup"><span data-stu-id="e837b-108">The CREATE ASSEMBLY statement is used to create an assembly in a database.</span></span> <span data-ttu-id="e837b-109">Veja um exemplo:</span><span class="sxs-lookup"><span data-stu-id="e837b-109">Here is an example:</span></span>  
  
```  
CREATE ASSEMBLY SQLCLRTest  
FROM 'C:\MyDBApp\SQLCLRTest.dll';  
```  
  
 <span data-ttu-id="e837b-110">A cláusula FROM especifica o nome do caminho do assembly a ser criado.</span><span class="sxs-lookup"><span data-stu-id="e837b-110">The FROM clause specifies the pathname of the assembly to create.</span></span> <span data-ttu-id="e837b-111">Esse caminho pode ser um caminho UNC (convenção de nomenclatura universal) ou um caminho físico do arquivo que é local no computador.</span><span class="sxs-lookup"><span data-stu-id="e837b-111">This path can either be a Universal Naming Convention (UNC) path or a physical file path that is local to the machine.</span></span>  
  
 <span data-ttu-id="e837b-112">O [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] não permite o registro de versões diferentes de um assembly com nome, cultura e chave pública iguais.</span><span class="sxs-lookup"><span data-stu-id="e837b-112">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] does not allow registering different versions of an assembly with the same name, culture and public key.</span></span>  
  
 <span data-ttu-id="e837b-113">É possível criar assemblies que referenciem outros.</span><span class="sxs-lookup"><span data-stu-id="e837b-113">It is possible to create assemblies that reference other assemblies.</span></span> <span data-ttu-id="e837b-114">Quando um assembly é criado [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , o também cria os assemblies referenciados pelo assembly de nível raiz, se os assemblies referenciados ainda não estiverem criados no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="e837b-114">When an assembly is created in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] also creates the assemblies referenced by the root-level assembly, if the referenced assemblies are not already created into the database.</span></span>  
  
 <span data-ttu-id="e837b-115">Os usuários de banco de dados ou as funções de usuário obtêm permissões para criar, e assim ter propriedade sobre, os assemblies em um banco de dados.</span><span class="sxs-lookup"><span data-stu-id="e837b-115">Database users or user roles are given permissions to create, and thereby own, assemblies in a database.</span></span> <span data-ttu-id="e837b-116">Para criar assemblies, a função ou o usuário de banco de dados deve ter a permissão CREATE ASSEMBLY.</span><span class="sxs-lookup"><span data-stu-id="e837b-116">In order to create assemblies, the database user or role should have the CREATE ASSEMBLY permission.</span></span>  
  
 <span data-ttu-id="e837b-117">Um assembly só poderá ter êxito ao referenciar outros assemblies se:</span><span class="sxs-lookup"><span data-stu-id="e837b-117">An assembly can only succeed in referencing other assemblies if:</span></span>  
  
-   <span data-ttu-id="e837b-118">O assembly chamado ou referenciado tem como proprietário o mesmo usuário ou função.</span><span class="sxs-lookup"><span data-stu-id="e837b-118">The assembly that is called or referenced is owned by the same user or role.</span></span>  
  
-   <span data-ttu-id="e837b-119">O assembly chamado ou referenciado foi criado no mesmo banco de dados.</span><span class="sxs-lookup"><span data-stu-id="e837b-119">The assembly that is called or referenced was created in the same database.</span></span>  
  
## <a name="specifying-security-when-creating-assemblies"></a><span data-ttu-id="e837b-120">Especificando a segurança ao criar assemblies</span><span class="sxs-lookup"><span data-stu-id="e837b-120">Specifying Security When Creating Assemblies</span></span>  
 <span data-ttu-id="e837b-121">Ao criar um assembly em um banco de dados do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], você pode especificar um dos três diferentes níveis de segurança em que o código pode ser executado: `SAFE`, `EXTERNAL_ACCESS` ou `UNSAFE`.</span><span class="sxs-lookup"><span data-stu-id="e837b-121">When creating an assembly into a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] database, you can specify one of three different levels of security in which your code can run: `SAFE`, `EXTERNAL_ACCESS`, or `UNSAFE`.</span></span> <span data-ttu-id="e837b-122">Quando a instrução `CREATE ASSEMBLY` é executada, determinadas verificações são realizadas no assembly do código que podem causar falha no assembly ao se registrar no servidor.</span><span class="sxs-lookup"><span data-stu-id="e837b-122">When the `CREATE ASSEMBLY` statement is run, certain checks are performed on the code assembly which may cause the assembly to fail to register on the server.</span></span> <span data-ttu-id="e837b-123">Para obter mais informações, consulte o exemplo de representação no [codeplex](https://msftengprodsamples.codeplex.com/).</span><span class="sxs-lookup"><span data-stu-id="e837b-123">For more information, see the Impersonation sample on [CodePlex](https://msftengprodsamples.codeplex.com/).</span></span>  
  
 <span data-ttu-id="e837b-124">`SAFE` é o conjunto de permissões padrão e funciona para a maioria dos cenários.</span><span class="sxs-lookup"><span data-stu-id="e837b-124">`SAFE` is the default permission set and works for the majority of scenarios.</span></span> <span data-ttu-id="e837b-125">Para especificar um determinado nível de segurança, modifique a sintaxe da instrução CREATE ASSEMBLY da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="e837b-125">To specify a given security level, you modify the syntax of the CREATE ASSEMBLY statement as follows:</span></span>  
  
```  
CREATE ASSEMBLY SQLCLRTest  
FROM 'C:\MyDBApp\SQLCLRTest.dll'  
WITH PERMISSION_SET = SAFE;  
```  
  
 <span data-ttu-id="e837b-126">Também é possível criar um assembly com o conjunto de permissões `SAFE` simplesmente omitindo a terceira linha de código acima:</span><span class="sxs-lookup"><span data-stu-id="e837b-126">It is also possible to create an assembly with the `SAFE` permission set by simply omitting the third line of code above:</span></span>  
  
```  
CREATE ASSEMBLY SQLCLRTest  
FROM 'C:\MyDBApp\SQLCLRTest.dll';  
```  
  
 <span data-ttu-id="e837b-127">Quando o código de um assembly é executado no conjunto de permissões `SAFE`, ele só pode fazer cálculos e acessar dados no servidor através do provedor gerenciado em processo.</span><span class="sxs-lookup"><span data-stu-id="e837b-127">When code in an assembly runs under the `SAFE` permission set, it can only do computation and data access within the server through the in-process managed provider.</span></span>  
  
### <a name="creating-external_access-and-unsafe-assemblies"></a><span data-ttu-id="e837b-128">Criando assemblies EXTERNAL_ACCESS e UNSAFE</span><span class="sxs-lookup"><span data-stu-id="e837b-128">Creating EXTERNAL_ACCESS and UNSAFE Assemblies</span></span>  
 <span data-ttu-id="e837b-129">O `EXTERNAL_ACCESS` aborda cenários nos quais o código precisa acessar recursos fora do servidor, como arquivos, rede, o Registro e variáveis de ambiente.</span><span class="sxs-lookup"><span data-stu-id="e837b-129">`EXTERNAL_ACCESS` addresses scenarios in which the code needs to access resources outside the server, such as files, network, registry, and environment variables.</span></span> <span data-ttu-id="e837b-130">Sempre que o servidor acessa um recurso externo, ele representa o contexto de segurança do usuário que chama o código gerenciado.</span><span class="sxs-lookup"><span data-stu-id="e837b-130">Whenever the server accesses an external resource, it impersonates the security context of the user calling the managed code.</span></span>  
  
 <span data-ttu-id="e837b-131">A permissão de código `UNSAFE` é usada nas situações em que um assembly não é seguro de modo verificável ou exige acesso adicional a recursos restritos, como a API do Win32 da [!INCLUDE[msCoName](../../../includes/msconame-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e837b-131">`UNSAFE` code permission is for those situations in which an assembly is not verifiably safe or requires additional access to restricted resources, such as the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Win32 API.</span></span>  
  
 <span data-ttu-id="e837b-132">Para criar um assembly `EXTERNAL_ACCESS` ou `UNSAFE` no [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], é necessário atender a uma das duas condições a seguir:</span><span class="sxs-lookup"><span data-stu-id="e837b-132">To create an `EXTERNAL_ACCESS` or `UNSAFE` assembly in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], one of the following two conditions must be met:</span></span>  
  
1.  <span data-ttu-id="e837b-133">O assembly é assinado com nome forte ou com Authenticode usando um certificado.</span><span class="sxs-lookup"><span data-stu-id="e837b-133">The assembly is strong name signed or Authenticode signed with a certificate.</span></span> <span data-ttu-id="e837b-134">Esse nome forte (ou certificado) é criado no [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] como uma chave assimétrica (ou certificado) e tem um logon correspondente com a permissão `EXTERNAL ACCESS ASSEMBLY` (para assemblies de acesso externo) ou a permissão `UNSAFE ASSEMBLY` (para assemblies não seguros).</span><span class="sxs-lookup"><span data-stu-id="e837b-134">This strong name (or certificate) is created inside [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] as an asymmetric key (or certificate), and has a corresponding login with `EXTERNAL ACCESS ASSEMBLY` permission (for external access assemblies) or `UNSAFE ASSEMBLY` permission (for unsafe assemblies).</span></span>  
  
2.  <span data-ttu-id="e837b-135">O proprietário do banco de dados (DBO) tem `EXTERNAL ACCESS ASSEMBLY` `EXTERNAL ACCESS` a permissão (para assemblies) ou `UNSAFE ASSEMBLY` (para `UNSAFE` assemblies) e o banco de dados tem a [propriedade de banco de dados TRUSTWORTHY](../../security/trustworthy-database-property.md) definida como `ON` .</span><span class="sxs-lookup"><span data-stu-id="e837b-135">The database owner (DBO) has `EXTERNAL ACCESS ASSEMBLY` (for `EXTERNAL ACCESS` assemblies) or `UNSAFE ASSEMBLY` (for `UNSAFE` assemblies) permission, and the database has the [TRUSTWORTHY Database Property](../../security/trustworthy-database-property.md) set to `ON`.</span></span>  
  
 <span data-ttu-id="e837b-136">As duas condições listadas acima também são verificadas na hora do carregamento do assembly (que inclui a execução).</span><span class="sxs-lookup"><span data-stu-id="e837b-136">The two conditions listed above are also checked at assembly load time (which includes execution).</span></span> <span data-ttu-id="e837b-137">Pelo menos um das condições precisa ser cumprida para carregar o assembly.</span><span class="sxs-lookup"><span data-stu-id="e837b-137">At least one of the conditions must be met in order to load the assembly.</span></span>  
  
 <span data-ttu-id="e837b-138">É recomendável que a [propriedade de banco](../../security/trustworthy-database-property.md) de dados TRUSTWORTHY em um banco de dados não seja definida somente para `ON` executar Common Language Runtime (CLR) no processo do servidor.</span><span class="sxs-lookup"><span data-stu-id="e837b-138">We recommend that the [TRUSTWORTHY Database Property](../../security/trustworthy-database-property.md) on a database not be set to `ON` only to run common language runtime (CLR) code in the server process.</span></span> <span data-ttu-id="e837b-139">Em vez disso, recomendamos que seja criada uma chave assimétrica do arquivo de assembly no banco de dados mestre.</span><span class="sxs-lookup"><span data-stu-id="e837b-139">Instead, we recommend that an asymmetric key be created from the assembly file in the master database.</span></span> <span data-ttu-id="e837b-140">É necessário criar um logon mapeado para essa chave assimétrica o qual precisa receber a concessão de uma permissão `EXTERNAL ACCESS ASSEMBLY` ou `UNSAFE ASSEMBLY`.</span><span class="sxs-lookup"><span data-stu-id="e837b-140">A login mapped to this asymmetric key must then be created, and the login must be granted `EXTERNAL ACCESS ASSEMBLY` or `UNSAFE ASSEMBLY` permission.</span></span>  
  
 <span data-ttu-id="e837b-141">As instruções a seguir [!INCLUDE[tsql](../../../includes/tsql-md.md)] antes de executar a instrução CREATE assembly.</span><span class="sxs-lookup"><span data-stu-id="e837b-141">The following [!INCLUDE[tsql](../../../includes/tsql-md.md)] statements before running the CREATE ASSEMBLY statement.</span></span>  
  
```  
USE master;   
GO    
  
CREATE ASYMMETRIC KEY SQLCLRTestKey FROM EXECUTABLE FILE = 'C:\MyDBApp\SQLCLRTest.dll'     
CREATE LOGIN SQLCLRTestLogin FROM ASYMMETRIC KEY SQLCLRTestKey     
GRANT EXTERNAL ACCESS ASSEMBLY TO SQLCLRTestLogin;   
GO   
```  
  
> [!NOTE]  
>  <span data-ttu-id="e837b-142">Você deve criar um logon novo para associar com a chave assimétrica.</span><span class="sxs-lookup"><span data-stu-id="e837b-142">You must create a new login to associate with the asymmetric key.</span></span> <span data-ttu-id="e837b-143">Esse logon é usado somente para conceder permissões; não precisa estar associado a um usuário ou usado dentro do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="e837b-143">This login is only used to grant permissions; it does not have to be associated with a user, or used within the application.</span></span>  
  
 <span data-ttu-id="e837b-144">Para criar um assembly `EXTERNAL ACCESS`, o criador precisa ter a permissão `EXTERNAL ACCESS`.</span><span class="sxs-lookup"><span data-stu-id="e837b-144">To create an `EXTERNAL ACCESS` assembly, the creator needs to have `EXTERNAL ACCESS` permission.</span></span> <span data-ttu-id="e837b-145">Isso é especificado ao criar o assembly:</span><span class="sxs-lookup"><span data-stu-id="e837b-145">This is specified when creating the assembly:</span></span>  
  
```  
CREATE ASSEMBLY SQLCLRTest  
FROM 'C:\MyDBApp\SQLCLRTest.dll'  
WITH PERMISSION_SET = EXTERNAL_ACCESS;  
```  
  
 <span data-ttu-id="e837b-146">As instruções a seguir [!INCLUDE[tsql](../../../includes/tsql-md.md)] antes de executar a instrução CREATE assembly.</span><span class="sxs-lookup"><span data-stu-id="e837b-146">The following [!INCLUDE[tsql](../../../includes/tsql-md.md)] statements before running the CREATE ASSEMBLY statement.</span></span>  
  
```  
USE master;   
GO    
  
CREATE ASYMMETRIC KEY SQLCLRTestKey FROM EXECUTABLE FILE = 'C:\MyDBApp\SQLCLRTest.dll';     
CREATE LOGIN SQLCLRTestLogin FROM ASYMMETRIC KEY SQLCLRTestKey ;    
GRANT UNSAFE ASSEMBLY TO SQLCLRTestLogin ;  
GO  
```  
  
 <span data-ttu-id="e837b-147">Para especificar que um assembly é carregado com a permissão `UNSAFE`, especifique o conjunto de permissões `UNSAFE` ao carregar o assembly no servidor:</span><span class="sxs-lookup"><span data-stu-id="e837b-147">To specify that an assembly loads with `UNSAFE` permission, you specify the `UNSAFE` permission set when loading the assembly into the server:</span></span>  
  
```  
CREATE ASSEMBLY SQLCLRTest  
FROM 'C:\MyDBApp\SQLCLRTest.dll'  
WITH PERMISSION_SET = UNSAFE;  
```  
  
 <span data-ttu-id="e837b-148">Para obter mais detalhes sobre as permissões para cada uma das configurações, consulte [segurança da integração CLR](../security/clr-integration-security.md).</span><span class="sxs-lookup"><span data-stu-id="e837b-148">For more details about the permissions for each of the settings, see [CLR Integration Security](../security/clr-integration-security.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e837b-149">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e837b-149">See Also</span></span>  
 <span data-ttu-id="e837b-150">[Gerenciando assemblies de integração CLR](managing-clr-integration-assemblies.md) </span><span class="sxs-lookup"><span data-stu-id="e837b-150">[Managing CLR Integration Assemblies](managing-clr-integration-assemblies.md) </span></span>  
 <span data-ttu-id="e837b-151">[Alterando um assembly](altering-an-assembly.md) </span><span class="sxs-lookup"><span data-stu-id="e837b-151">[Altering an Assembly](altering-an-assembly.md) </span></span>  
 <span data-ttu-id="e837b-152">[Descartando um assembly](dropping-an-assembly.md) </span><span class="sxs-lookup"><span data-stu-id="e837b-152">[Dropping an Assembly](dropping-an-assembly.md) </span></span>  
 <span data-ttu-id="e837b-153">[Segurança de acesso ao código de integração CLR](../security/clr-integration-code-access-security.md) </span><span class="sxs-lookup"><span data-stu-id="e837b-153">[CLR Integration Code Access Security](../security/clr-integration-code-access-security.md) </span></span>  
 <span data-ttu-id="e837b-154">[propriedade TRUSTWORTHY do banco de dados](../../security/trustworthy-database-property.md) </span><span class="sxs-lookup"><span data-stu-id="e837b-154">[TRUSTWORTHY Database Property](../../security/trustworthy-database-property.md) </span></span>  
 [<span data-ttu-id="e837b-155">Permitindo chamadores parcialmente confiáveis</span><span class="sxs-lookup"><span data-stu-id="e837b-155">Allowing Partially Trusted Callers</span></span>](../../../database-engine/dev-guide/allowing-partially-trusted-callers.md)  
  
