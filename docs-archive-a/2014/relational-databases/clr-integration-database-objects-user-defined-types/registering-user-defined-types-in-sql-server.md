---
title: Registrando tipos definidos pelo usuário no SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
dev_langs:
- TSQL
helpviewer_keywords:
- UDTs [CLR integration], maintaining
- user-defined types [CLR integration], maintaining
- dependencies [CLR integration]
- deploying user-defined types [CLR integration]
- CurrencyConversion function
- user-defined types [CLR integration], deploying
- Transact-SQL deploying UDTs
- assemblies [CLR integration], user-defined types
- cross-database UDT support
- CREATE ASSEMBLY statement
- DROP TYPE statement
- Currency UDT
- CREATE TYPE statement
- registering user-defined types
- UDTs [CLR integration], deploying
- removing user-defined types
- user-defined types [CLR integration], registering
- ALTER ASSEMBLY statement
- UDTs [CLR integration], registering
- ADD FILE clause
ms.assetid: f7da3e92-e407-4f0b-b3a3-f214e442b37d
author: rothja
ms.author: jroth
ms.openlocfilehash: 7d24f7948e093335eff708f3c4a8a7361cfc156f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570716"
---
# <a name="registering-user-defined-types-in-sql-server"></a><span data-ttu-id="25677-102">Registrando tipos definidos pelo usuário no SQL Server</span><span class="sxs-lookup"><span data-stu-id="25677-102">Registering User-Defined Types in SQL Server</span></span>
  <span data-ttu-id="25677-103">Para usar um UDT (tipo definido pelo usuário) no [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , você deve registrá-lo.</span><span class="sxs-lookup"><span data-stu-id="25677-103">In order to use a user-defined type (UDT) in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], you must register it.</span></span> <span data-ttu-id="25677-104">O registro de um UDT envolve o registro do assembly e a criação do tipo no banco de dados em que deseja usá-lo.</span><span class="sxs-lookup"><span data-stu-id="25677-104">Registering a UDT involves registering the assembly and creating the type in the database in which you wish to use it.</span></span> <span data-ttu-id="25677-105">Os UDTs têm escopo em um único banco de dados e não podem ser usados em vários bancos de dados, a menos que o assembly e a UDT idênticos sejam registrados em cada banco de dados.</span><span class="sxs-lookup"><span data-stu-id="25677-105">UDTs are scoped to a single database, and cannot be used in multiple databases unless the identical assembly and UDT are registered with each database.</span></span> <span data-ttu-id="25677-106">Quando o assembly do UDT é registrado e o tipo é criado, você pode usar a UDT no [!INCLUDE[tsql](../../includes/tsql-md.md)] e em código de cliente.</span><span class="sxs-lookup"><span data-stu-id="25677-106">Once the UDT assembly is registered and the type created, you can use the UDT in [!INCLUDE[tsql](../../includes/tsql-md.md)] and in client code.</span></span> <span data-ttu-id="25677-107">Para obter mais informações, veja [Tipos CLR definidos pelo usuário](clr-user-defined-types.md).</span><span class="sxs-lookup"><span data-stu-id="25677-107">For more information, see [CLR User-Defined Types](clr-user-defined-types.md).</span></span>  
  
## <a name="using-visual-studio-to-deploy-udts"></a><span data-ttu-id="25677-108">Usando o Visual Studio para implantar UDTs</span><span class="sxs-lookup"><span data-stu-id="25677-108">Using Visual Studio to Deploy UDTs</span></span>  
 <span data-ttu-id="25677-109">O modo mais fácil de implantar seu UDT é usar o [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="25677-109">The easiest way to deploy your UDT is by using [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Studio.</span></span> <span data-ttu-id="25677-110">Para cenários de implantação mais complexos e mais flexibilidade, entretanto, use o [!INCLUDE[tsql](../../includes/tsql-md.md)] como discutido posteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="25677-110">For more complex deployment scenarios and the greatest flexibility, however, use [!INCLUDE[tsql](../../includes/tsql-md.md)] as discussed later in this topic.</span></span>  
  
 <span data-ttu-id="25677-111">Siga estas etapas para criar e implantar um UDT usando o Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="25677-111">Follow these steps to create and deploy a UDT using Visual Studio:</span></span>  
  
1.  <span data-ttu-id="25677-112">Crie um novo projeto de **banco de dados** nos nós de linguagem **Visual Basic** ou **Visual C#** .</span><span class="sxs-lookup"><span data-stu-id="25677-112">Create a new **Database** project in the **Visual Basic** or **Visual C#** language nodes.</span></span>  
  
2.  <span data-ttu-id="25677-113">Acrescente uma referência ao banco de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que conterá a UDT.</span><span class="sxs-lookup"><span data-stu-id="25677-113">Add a reference to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database that will contain the UDT.</span></span>  
  
3.  <span data-ttu-id="25677-114">Adicione uma classe de **tipo definida pelo usuário** .</span><span class="sxs-lookup"><span data-stu-id="25677-114">Add a **User-Defined Type** class.</span></span>  
  
4.  <span data-ttu-id="25677-115">Escreva o código para implementar a UDT.</span><span class="sxs-lookup"><span data-stu-id="25677-115">Write code to implement the UDT.</span></span>  
  
5.  <span data-ttu-id="25677-116">No menu **Compilar** , selecione **implantar**.</span><span class="sxs-lookup"><span data-stu-id="25677-116">From the **Build** menu, select **Deploy**.</span></span> <span data-ttu-id="25677-117">O assembly será registrado e o tipo será criado no banco de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="25677-117">This registers the assembly and creates the type in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database.</span></span>  
  
## <a name="using-transact-sql-to-deploy-udts"></a><span data-ttu-id="25677-118">Usando o Transact-SQL para implantar UDTs</span><span class="sxs-lookup"><span data-stu-id="25677-118">Using Transact-SQL to Deploy UDTs</span></span>  
 <span data-ttu-id="25677-119">A sintaxe CREATE ASSEMBLY do [!INCLUDE[tsql](../../includes/tsql-md.md)] é usada para registrar o assembly no banco de dados no qual você deseja usar a UDT.</span><span class="sxs-lookup"><span data-stu-id="25677-119">The [!INCLUDE[tsql](../../includes/tsql-md.md)] CREATE ASSEMBLY syntax is used to register the assembly in the database in which you wish to use the UDT.</span></span> <span data-ttu-id="25677-120">Ele é armazenado internamente em tabelas do sistema do banco de dados, e não externamente, no sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="25677-120">It is stored internally in database system tables, not externally in the file system.</span></span> <span data-ttu-id="25677-121">Se a UDT for dependente de assembly externos, eles também deverão ser carregados no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="25677-121">If the UDT is dependent on external assemblies, they too must be loaded into the database.</span></span> <span data-ttu-id="25677-122">A instrução CREATE TYPE é usada para criar a UDT no banco de dados no qual será usada.</span><span class="sxs-lookup"><span data-stu-id="25677-122">The CREATE TYPE statement is used to create the UDT in the database in which it is to be used.</span></span> <span data-ttu-id="25677-123">Para obter mais informações, consulte [criar ASSEMBLY &#40;Transact-sql&#41;](/sql/t-sql/statements/create-assembly-transact-sql) e [criar tipo &#40;&#41;do Transact-SQL ](/sql/t-sql/statements/create-type-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="25677-123">For more information, see [CREATE ASSEMBLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-assembly-transact-sql) and [CREATE TYPE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-type-transact-sql).</span></span>  
  
### <a name="using-create-assembly"></a><span data-ttu-id="25677-124">Usando CREATE ASSEMBLY</span><span class="sxs-lookup"><span data-stu-id="25677-124">Using CREATE ASSEMBLY</span></span>  
 <span data-ttu-id="25677-125">A sintaxe CREATE ASSEMBLY registra o assembly no banco de dados no qual você deseja usar a UDT.</span><span class="sxs-lookup"><span data-stu-id="25677-125">The CREATE ASSEMBLY syntax registers the assembly in the database in which you wish to use the UDT.</span></span> <span data-ttu-id="25677-126">Quando o assembly é registrado, não possui dependências.</span><span class="sxs-lookup"><span data-stu-id="25677-126">Once the assembly is registered, it has no dependencies.</span></span>  
  
 <span data-ttu-id="25677-127">Não é permitido criar várias versões do mesmo assembly em um determinado banco de dados.</span><span class="sxs-lookup"><span data-stu-id="25677-127">Creating multiple versions of the same assembly in a given database is not allowed.</span></span> <span data-ttu-id="25677-128">Entretanto, é possível criar várias versões do mesmo assembly com base em cultura em um determinado banco de dados.</span><span class="sxs-lookup"><span data-stu-id="25677-128">However, it is possible to create multiple versions of the same assembly based on culture in a given database.</span></span> <span data-ttu-id="25677-129">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] diferencia várias versões de cultura de um assembly por nomes diferentes dos registrados na instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="25677-129">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] distinguishes multiple culture versions of an assembly by different names as registered in the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="25677-130">Para obter mais informações, consulte “Criando e usando assemblies de nome forte”, no SDK do .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="25677-130">For more information, see "Creating and Using Strong-Named Assemblies" in the .NET Framework SDK.</span></span>  
  
 <span data-ttu-id="25677-131">Quando CREATE ASSEMBLY for executada com o conjunto de permissões SAFE ou EXTERNAL_ACCESS, o assembly será marcado para garantir que seja verificável e fortemente tipado.</span><span class="sxs-lookup"><span data-stu-id="25677-131">When CREATE ASSEMBLY is executed with the SAFE or EXTERNAL_ACCESS permission sets, the assembly is checked to make sure that it is verifiable and type safe.</span></span> <span data-ttu-id="25677-132">Se você omitir a especificação de um conjunto de permissões, SAFE será considerado.</span><span class="sxs-lookup"><span data-stu-id="25677-132">If you omit specifying a permission set, SAFE is assumed.</span></span> <span data-ttu-id="25677-133">Códigos com o conjunto de permissões UNSAFE não serão marcados.</span><span class="sxs-lookup"><span data-stu-id="25677-133">Code with the UNSAFE permission set is not checked.</span></span> <span data-ttu-id="25677-134">Para obter mais informações sobre conjuntos de permissões de assembly, confira [Criando assemblies](../../relational-databases/clr-integration/assemblies-designing.md).</span><span class="sxs-lookup"><span data-stu-id="25677-134">For more information about assembly permission sets, see [Designing Assemblies](../../relational-databases/clr-integration/assemblies-designing.md).</span></span>  
  
#### <a name="example"></a><span data-ttu-id="25677-135">Exemplo</span><span class="sxs-lookup"><span data-stu-id="25677-135">Example</span></span>  
 <span data-ttu-id="25677-136">A instrução a seguir [!INCLUDE[tsql](../../includes/tsql-md.md)] registra o assembly de ponto no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] no banco de dados **AdventureWorks** , com o conjunto de permissões seguro.</span><span class="sxs-lookup"><span data-stu-id="25677-136">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement registers the Point assembly in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in the **AdventureWorks** database, with the SAFE permission set.</span></span> <span data-ttu-id="25677-137">Se a cláusula WITH PERMISSION_SET for omitida, o assembly será registrado com o conjunto de permissões SAFE.</span><span class="sxs-lookup"><span data-stu-id="25677-137">If the WITH PERMISSION_SET clause is omitted, the assembly is registered with the SAFE permission set.</span></span>  
  
```  
USE AdventureWorks;  
CREATE ASSEMBLY Point  
FROM '\\ShareName\Projects\Point\bin\Point.dll'   
WITH PERMISSION_SET = SAFE;  
```  
  
 <span data-ttu-id="25677-138">A instrução a seguir [!INCLUDE[tsql](../../includes/tsql-md.md)] registra o assembly usando *<argumento assembly_bits>* na cláusula FROM.</span><span class="sxs-lookup"><span data-stu-id="25677-138">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement registers the assembly using *<assembly_bits>* argument in the FROM clause.</span></span> <span data-ttu-id="25677-139">Este valor `varbinary` representa o arquivo como um fluxo de bytes.</span><span class="sxs-lookup"><span data-stu-id="25677-139">This `varbinary` value represents the file as a stream of bytes.</span></span>  
  
```  
USE AdventureWorks;  
CREATE ASSEMBLY Point  
FROM 0xfeac4 ... 21ac78  
```  
  
### <a name="using-create-type"></a><span data-ttu-id="25677-140">Usando CREATE TYPE</span><span class="sxs-lookup"><span data-stu-id="25677-140">Using CREATE TYPE</span></span>  
 <span data-ttu-id="25677-141">Quando o assembly é carregado no banco de dados, você pode criar o tipo que usa a instrução do [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="25677-141">Once the assembly is loaded into the database, you can then create the type using the [!INCLUDE[tsql](../../includes/tsql-md.md)] CREATE TYPE statement.</span></span> <span data-ttu-id="25677-142">Isto acrescenta o tipo à lista de tipos disponíveis para esse banco de dados.</span><span class="sxs-lookup"><span data-stu-id="25677-142">This adds the type to the list of available types for that database.</span></span> <span data-ttu-id="25677-143">O tipo tem escopo de banco de dados e só pode ser usado no banco de dados no qual foi criado.</span><span class="sxs-lookup"><span data-stu-id="25677-143">The type has database scope and the type can only be used in the database in which it was created.</span></span> <span data-ttu-id="25677-144">Se a UDT já existir no banco de dados, a instrução de CREATE TYPE falhará com um erro.</span><span class="sxs-lookup"><span data-stu-id="25677-144">If the UDT already exists in the database, the CREATE TYPE statement fails with an error.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="25677-145">A sintaxe CREATE TYPE também é usada para criar tipos de dados de alias do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e tem o objetivo de substituir `sp_addtype` como uma forma de criar tipos de dados de alias.</span><span class="sxs-lookup"><span data-stu-id="25677-145">The CREATE TYPE syntax is also used for creating native [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] alias data types, and is intended to replace `sp_addtype` as a means of creating alias data types.</span></span> <span data-ttu-id="25677-146">Alguns argumentos opcionais da sintaxe CREATE TYPE se referem à criação de UDTs e não são aplicáveis à criação de tipos de dados de alias (como um tipo de base).</span><span class="sxs-lookup"><span data-stu-id="25677-146">Some of the optional arguments in the CREATE TYPE syntax refer to creating UDTs, and are not applicable to creating alias data types (such as base type).</span></span>  
  
 <span data-ttu-id="25677-147">Para obter mais informações, consulte [criar tipo &#40;&#41;Transact-SQL ](/sql/t-sql/statements/create-type-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="25677-147">For more information, see [CREATE TYPE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-type-transact-sql).</span></span>  
  
#### <a name="example"></a><span data-ttu-id="25677-148">Exemplo</span><span class="sxs-lookup"><span data-stu-id="25677-148">Example</span></span>  
 <span data-ttu-id="25677-149">A instrução [!INCLUDE[tsql](../../includes/tsql-md.md)] a seguir cria o tipo `Point`.</span><span class="sxs-lookup"><span data-stu-id="25677-149">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement creates the `Point` type.</span></span> <span data-ttu-id="25677-150">O nome externo é especificado usando a sintaxe de nomenclatura de duas partes de *AssemblyName*. *UDTName*.</span><span class="sxs-lookup"><span data-stu-id="25677-150">The EXTERNAL NAME is specified using the two-part naming syntax of *AssemblyName*.*UDTName*.</span></span>  
  
```  
CREATE TYPE dbo.Point   
EXTERNAL NAME Point.[Point];  
```  
  
## <a name="removing-a-udt-from-the-database"></a><span data-ttu-id="25677-151">Removendo uma UDT do banco de dados</span><span class="sxs-lookup"><span data-stu-id="25677-151">Removing a UDT from the Database</span></span>  
 <span data-ttu-id="25677-152">A instrução de DROP TYPE remove uma UDT do banco de dados atual.</span><span class="sxs-lookup"><span data-stu-id="25677-152">The DROP TYPE statement removes a UDT from the current database.</span></span> <span data-ttu-id="25677-153">Quando uma UDT é descartada, você pode usar a instrução de DROP ASSEMBLY para descartar o assembly do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="25677-153">Once a UDT is dropped, you can use the DROP ASSEMBLY statement to drop the assembly from the database.</span></span>  
  
 <span data-ttu-id="25677-154">A instrução de DROP TYPE não é executada nas seguintes situações:</span><span class="sxs-lookup"><span data-stu-id="25677-154">The DROP TYPE statement does not execute in the following situations:</span></span>  
  
-   <span data-ttu-id="25677-155">Tabelas no banco de dados que contêm colunas definidas usando a UDT.</span><span class="sxs-lookup"><span data-stu-id="25677-155">Tables in the database that contain columns defined using the UDT.</span></span>  
  
-   <span data-ttu-id="25677-156">Funções, procedimentos armazenados ou gatilhos que usam variáveis ou parâmetros da UDT, criadas no banco de dados com a cláusula WITH SCHEMABINDING.</span><span class="sxs-lookup"><span data-stu-id="25677-156">Functions, stored procedures, or triggers that use variables or parameters of the UDT, created in the database with the WITH SCHEMABINDING clause.</span></span>  
  
### <a name="example"></a><span data-ttu-id="25677-157">Exemplo</span><span class="sxs-lookup"><span data-stu-id="25677-157">Example</span></span>  
 <span data-ttu-id="25677-158">O [!INCLUDE[tsql](../../includes/tsql-md.md)] a seguir deve ser executado nesta ordem:</span><span class="sxs-lookup"><span data-stu-id="25677-158">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] must execute in the following order.</span></span> <span data-ttu-id="25677-159">Primeiro, a tabela que referencia a UDT `Point` deve ser descartada, depois o tipo e, finalmente, o assembly.</span><span class="sxs-lookup"><span data-stu-id="25677-159">First the table which references the `Point` UDT must be dropped, then the type, and finally the assembly.</span></span>  
  
```  
DROP TABLE dbo.Points;  
DROP TYPE dbo.Point;  
DROP ASSEMBLY Point;  
```  
  
### <a name="finding-udt-dependencies"></a><span data-ttu-id="25677-160">Localizando dependências do UDT</span><span class="sxs-lookup"><span data-stu-id="25677-160">Finding UDT Dependencies</span></span>  
 <span data-ttu-id="25677-161">Se houver objetos dependentes, como tabelas com definições de coluna de UDT, a instrução DROP TYPE falhará.</span><span class="sxs-lookup"><span data-stu-id="25677-161">If there are dependent objects, such as tables with UDT column definitions, the DROP TYPE statement fails.</span></span> <span data-ttu-id="25677-162">Ela também falhará se houver funções, procedimentos armazenados ou gatilhos criados no banco de dados usando a cláusula WITH SCHEMABINDING, se essas rotinas usarem variáveis ou parâmetros do tipo definido pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="25677-162">It also fails if there are functions, stored procedures, or triggers created in the database using the WITH SCHEMABINDING clause, if these routines use variables or parameters of the user-defined type.</span></span> <span data-ttu-id="25677-163">Você deve descartar todos os objetos dependentes primeiro e, em seguida, executar a instrução DROP TYPE.</span><span class="sxs-lookup"><span data-stu-id="25677-163">You must first drop all dependent objects, and then execute the DROP TYPE statement.</span></span>  
  
 <span data-ttu-id="25677-164">A consulta a seguir [!INCLUDE[tsql](../../includes/tsql-md.md)] localiza todas as colunas e parâmetros que usam um UDT no banco de dados **AdventureWorks** .</span><span class="sxs-lookup"><span data-stu-id="25677-164">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] query locates all of the columns and parameters that use a UDT in the **AdventureWorks** database.</span></span>  
  
```  
USE Adventureworks;  
SELECT o.name AS major_name, o.type_desc AS major_type_desc  
     , c.name AS minor_name, c.type_desc AS minor_type_desc  
     , at.assembly_class  
  FROM (  
        SELECT object_id, name, user_type_id, 'SQL_COLUMN' AS type_desc  
          FROM sys.columns  
     UNION ALL  
        SELECT object_id, name, user_type_id, 'SQL_PROCEDURE_PARAMETER'  
          FROM sys.parameters  
     ) AS c  
  JOIN sys.objects AS o  
    ON o.object_id = c.object_id  
  JOIN sys.assembly_types AS at  
    ON at.user_type_id = c.user_type_id;  
```  
  
## <a name="maintaining-udts"></a><span data-ttu-id="25677-165">Mantendo UDTs</span><span class="sxs-lookup"><span data-stu-id="25677-165">Maintaining UDTs</span></span>  
 <span data-ttu-id="25677-166">Não é possível modificar um UDT quando ele for criado em um banco de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], embora você possa alterar o assembly em que o tipo é baseado. </span><span class="sxs-lookup"><span data-stu-id="25677-166">You cannot modify a UDT once it is created in a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database, although you can alter the assembly on which the type is based.</span></span> <span data-ttu-id="25677-167">Na maioria dos casos, você deve remover a UDT do banco de dados com a instrução DROP TYPE do [!INCLUDE[tsql](../../includes/tsql-md.md)], fazer alterações no assembly subjacente e recarregar usando a instrução ALETER ASSEMBLY. </span><span class="sxs-lookup"><span data-stu-id="25677-167">In most cases, you must remove the UDT from the database with the [!INCLUDE[tsql](../../includes/tsql-md.md)] DROP TYPE statement, make changes to the underlying assembly, and reload it using the ALTER ASSEMBLY statement.</span></span> <span data-ttu-id="25677-168">Em seguida, será necessário recriar a UDT e todos os objetos dependentes.</span><span class="sxs-lookup"><span data-stu-id="25677-168">You then need to re-create the UDT and any dependent objects.</span></span>  
  
### <a name="example"></a><span data-ttu-id="25677-169">Exemplo</span><span class="sxs-lookup"><span data-stu-id="25677-169">Example</span></span>  
 <span data-ttu-id="25677-170">A instrução ALTER ASSEMBLY é usada depois que você faz alterações no código-fonte no assembly do seu UDT e o recompila.</span><span class="sxs-lookup"><span data-stu-id="25677-170">The ALTER ASSEMBLY statement is used after you have made changes to the source code in your UDT assembly and recompiled it.</span></span> <span data-ttu-id="25677-171">Ele copia o arquivo .dll no servidor e o associa novamente ao novo assembly.</span><span class="sxs-lookup"><span data-stu-id="25677-171">It copies the .dll file to the server and rebinds to the new assembly.</span></span> <span data-ttu-id="25677-172">Para obter a sintaxe completa, consulte [ALTER ASSEMBLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-assembly-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="25677-172">For the complete syntax, see [ALTER ASSEMBLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-assembly-transact-sql).</span></span>  
  
 <span data-ttu-id="25677-173">A instrução ALTER ASSEMBLY do [!INCLUDE[tsql](../../includes/tsql-md.md)] a seguir recarregar o assembly Point.dll do local especificado no disco.</span><span class="sxs-lookup"><span data-stu-id="25677-173">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] ALTER ASSEMBLY statement reloads the Point.dll assembly from the specified location on disk.</span></span>  
  
```  
ALTER ASSEMBLY Point  
FROM '\\Projects\Point\bin\Point.dll'  
```  
  
### <a name="using-alter-assembly-to-add-source-code"></a><span data-ttu-id="25677-174">Usando ALTER ASSEMBLY para adicionar código-fonte</span><span class="sxs-lookup"><span data-stu-id="25677-174">Using ALTER ASSEMBLY to Add Source Code</span></span>  
 <span data-ttu-id="25677-175">A cláusula ADD FILE na sintaxe ALTER ASSEMBLY não está presente em CREATE ASSEMBLY.</span><span class="sxs-lookup"><span data-stu-id="25677-175">The ADD FILE clause in the ALTER ASSEMBLY syntax is not present in CREATE ASSEMBLY.</span></span> <span data-ttu-id="25677-176">Você pode usá-la para adicionar código-fonte ou outros arquivos associados a um assembly.</span><span class="sxs-lookup"><span data-stu-id="25677-176">You can use it to add source code or any other files associated with an assembly.</span></span> <span data-ttu-id="25677-177">Os arquivos serão copiados dos seus locais originais e armazenados em tabelas do sistema do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="25677-177">The files are copied from their original locations and stored in system tables in the database.</span></span> <span data-ttu-id="25677-178">Isso garante que você sempre tenha código-fonte ou outros arquivos à mão, se precisar recriar ou documentar a versão atual do UDT.</span><span class="sxs-lookup"><span data-stu-id="25677-178">This ensures that you always have source code or other files on hand should you ever need to re-create or document the current version of the UDT.</span></span>  
  
 <span data-ttu-id="25677-179">A [!INCLUDE[tsql](../../includes/tsql-md.md)] instrução ALTER assembly a seguir adiciona o código-fonte da classe Point.cs para o `Point` UDT.</span><span class="sxs-lookup"><span data-stu-id="25677-179">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] ALTER ASSEMBLY statement adds the Point.cs class source code for the `Point` UDT.</span></span> <span data-ttu-id="25677-180">O texto contendo o arquivo Point.cs será copiado e armazenado no banco de dados com o nome "PointSource".</span><span class="sxs-lookup"><span data-stu-id="25677-180">This copies the text contained in the Point.cs file and stores it in the database under the name "PointSource".</span></span>  
  
```  
ALTER ASSEMBLY Point  
ADD FILE FROM '\\Projects\Point\Point.cs' AS PointSource;  
```  
  
 <span data-ttu-id="25677-181">As informações do assembly são armazenadas na tabela **Sys. assembly_files** no banco de dados em que o assembly foi instalado.</span><span class="sxs-lookup"><span data-stu-id="25677-181">Assembly information is stored in the **sys.assembly_files** table in the database where the assembly has been installed.</span></span> <span data-ttu-id="25677-182">A tabela **Sys. assembly_files** contém as colunas a seguir.</span><span class="sxs-lookup"><span data-stu-id="25677-182">The **sys.assembly_files** table contains the following columns.</span></span>  
  
 <span data-ttu-id="25677-183">**assembly_id**</span><span class="sxs-lookup"><span data-stu-id="25677-183">**assembly_id**</span></span>  
 <span data-ttu-id="25677-184">O identificador definido para o assembly.</span><span class="sxs-lookup"><span data-stu-id="25677-184">The identifier defined for the assembly.</span></span> <span data-ttu-id="25677-185">Este número é atribuído a todos os objetos relacionados ao mesmo assembly.</span><span class="sxs-lookup"><span data-stu-id="25677-185">This number is assigned to all objects relating to the same assembly.</span></span>  
  
 <span data-ttu-id="25677-186">**name**</span><span class="sxs-lookup"><span data-stu-id="25677-186">**name**</span></span>  
 <span data-ttu-id="25677-187">O nome do objeto.</span><span class="sxs-lookup"><span data-stu-id="25677-187">The name of the object.</span></span>  
  
 <span data-ttu-id="25677-188">**file_id**</span><span class="sxs-lookup"><span data-stu-id="25677-188">**file_id**</span></span>  
 <span data-ttu-id="25677-189">Um número que identifica cada objeto, com o primeiro objeto associado a um determinado **assembly_id** dado o valor de 1.</span><span class="sxs-lookup"><span data-stu-id="25677-189">A number identifying each object, with the first object associated with a given **assembly_id** being given the value of 1.</span></span> <span data-ttu-id="25677-190">Se houver vários objetos associados ao mesmo **assembly_id**, cada valor de **file_id** subsequente será incrementado em 1.</span><span class="sxs-lookup"><span data-stu-id="25677-190">If there are multiple objects associated with the same **assembly_id**, then each subsequent **file_id** value is incremented by 1.</span></span>  
  
 <span data-ttu-id="25677-191">**content**</span><span class="sxs-lookup"><span data-stu-id="25677-191">**content**</span></span>  
 <span data-ttu-id="25677-192">A representação hexadecimal do assembly ou arquivo.</span><span class="sxs-lookup"><span data-stu-id="25677-192">The hexadecimal representation of the assembly or file.</span></span>  
  
 <span data-ttu-id="25677-193">Você pode usar a função CAST ou CONVERT para converter o conteúdo da coluna de **conteúdo** em texto legível.</span><span class="sxs-lookup"><span data-stu-id="25677-193">You can use the CAST or CONVERT function to convert the contents of the **content** column to readable text.</span></span> <span data-ttu-id="25677-194">A consulta a seguir converte o conteúdo do arquivo Point.cs a texto legível usando o nome da cláusula WHERE para restringir o conjunto de resultados definido a uma única linha.</span><span class="sxs-lookup"><span data-stu-id="25677-194">The following query converts the contents of the Point.cs file to readable text, using the name in the WHERE clause to restrict the result set to a single row.</span></span>  
  
```  
SELECT CAST(content AS varchar(8000))   
  FROM sys.assembly_files   
  WHERE name='PointSource';  
```  
  
 <span data-ttu-id="25677-195">Se você copiar e colar os resultados em um editor de texto, verá que as quebras de linha e os espaços que existiam no original foram preservados.</span><span class="sxs-lookup"><span data-stu-id="25677-195">If you copy and paste the results in to a text editor, you will see that the line breaks and spaces that existed in the original have been preserved.</span></span>  
  
## <a name="managing-udts-and-assemblies"></a><span data-ttu-id="25677-196">Gerenciando UDTs e assemblies</span><span class="sxs-lookup"><span data-stu-id="25677-196">Managing UDTs and Assemblies</span></span>  
 <span data-ttu-id="25677-197">Ao planejar a implementação de UDTs, considere quais métodos são necessários no assembly do UDT propriamente dito e quais métodos devem ser criados em assemblies separados e implementados como funções definidas pelo usuário ou procedimentos armazenados.</span><span class="sxs-lookup"><span data-stu-id="25677-197">When planning your implementation of UDTs, consider which methods are needed in the UDT assembly itself, and which methods should be created in separate assemblies and implemented as user-defined functions or stored procedures.</span></span> <span data-ttu-id="25677-198">Separar métodos em assemblies à parte permite atualizar o código sem afetar os dados que podem ser armazenados em uma coluna de UDT na tabela.</span><span class="sxs-lookup"><span data-stu-id="25677-198">Separating methods into separate assemblies allows you to update code without affecting data that may be stored in a UDT column in a table.</span></span> <span data-ttu-id="25677-199">A modificação dos assemblies de UDT sem descartar colunas de UDT e outros objetos dependentes só é possível quando a nova definição puder ler os valores iniciais e a assinatura do tipo não for alterada.</span><span class="sxs-lookup"><span data-stu-id="25677-199">You can modify UDT assemblies without dropping UDT columns and other dependent objects only when the new definition can read the former values and the signature of the type does not change.</span></span>  
  
 <span data-ttu-id="25677-200">Separar o código de procedimento que pode ser alterado do código necessário para implementar a UDT simplifica muito a manutenção.</span><span class="sxs-lookup"><span data-stu-id="25677-200">Separating procedural code that may change from the code required to implement the UDT greatly simplifies maintenance.</span></span> <span data-ttu-id="25677-201">Incluir somente do código necessário para que a UDT funcione e manter suas definições de UDT o mais simples possível reduzem o risco da necessidade de descarte do próprio UDT do banco de dados para revisões de código ou correção de bug.</span><span class="sxs-lookup"><span data-stu-id="25677-201">Including only code that is necessary for the UDT to function, and keeping your UDT definitions as simple as possible, reduces the risk that the UDT itself may need to be dropped from the database for code revisions or bug fixes.</span></span>  
  
### <a name="the-currency-udt-and-currency-conversion-function"></a><span data-ttu-id="25677-202">A função Conversão de moeda e conversão de UDT</span><span class="sxs-lookup"><span data-stu-id="25677-202">The Currency UDT and Currency Conversion Function</span></span>  
 <span data-ttu-id="25677-203">A **moeda** UDT no banco de dados de exemplo **AdventureWorks** fornece um exemplo útil da maneira recomendada para estruturar um UDT e suas funções associadas.</span><span class="sxs-lookup"><span data-stu-id="25677-203">The **Currency** UDT in the **AdventureWorks** sample database provides a useful example of the recommended way to structure a UDT and its associated functions.</span></span> <span data-ttu-id="25677-204">O UDT de **moeda** é usado para lidar com o dinheiro com base no sistema monetário de uma cultura específica e permite o armazenamento de diferentes tipos de moeda, como dólares, euros e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="25677-204">The **Currency** UDT is used for handling money based on the monetary system of a particular culture, and allows for storage of different currency types, such as dollars, euros, and so forth.</span></span> <span data-ttu-id="25677-205">A classe do UDT expõe o nome da cultura como uma cadeia de caracteres e o valor de dinheiro como um tipo de dados `decimal`.</span><span class="sxs-lookup"><span data-stu-id="25677-205">The UDT class exposes a culture name as a string, and an amount of money as a `decimal` data type.</span></span> <span data-ttu-id="25677-206">Todos os métodos de serialização necessários são contidos no assembly que define a classe.</span><span class="sxs-lookup"><span data-stu-id="25677-206">All of the necessary serialization methods are contained within the assembly defining the class.</span></span> <span data-ttu-id="25677-207">A função que implementa a conversão de moeda de uma cultura para outra é implementada como uma função externa chamada **ConvertCurrency**, e essa função está localizada em um assembly separado.</span><span class="sxs-lookup"><span data-stu-id="25677-207">The function that implements currency conversion from one culture to another is implemented as an external function named **ConvertCurrency**, and this function is located in a separate assembly.</span></span> <span data-ttu-id="25677-208">A função **ConvertCurrency** faz seu trabalho recuperando a taxa de conversão de uma tabela no banco de dados **AdventureWorks** .</span><span class="sxs-lookup"><span data-stu-id="25677-208">The **ConvertCurrency** function does its work by retrieving the conversion rate from a table in the **AdventureWorks** database.</span></span> <span data-ttu-id="25677-209">Se a origem das taxas de conversão precisar ser alterada ou se houver outras alterações no código existente, o assembly poderá ser facilmente modificado sem afetar o UDT da **moeda** .</span><span class="sxs-lookup"><span data-stu-id="25677-209">If the source of the conversion rates should ever change, or if there should be any other changes to the existing code, the assembly can be easily modified without affecting the **Currency** UDT.</span></span>  
  
 <span data-ttu-id="25677-210">A listagem de código para as funções UDT e **ConvertCurrency** de **moeda** pode ser encontrada instalando os exemplos de Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="25677-210">The code listing for the **Currency** UDT and **ConvertCurrency** functions can be found by installing the common language runtime (CLR) samples.</span></span>  
  
### <a name="using-udts-across-databases"></a><span data-ttu-id="25677-211">Usando UDTs nos bancos de dados</span><span class="sxs-lookup"><span data-stu-id="25677-211">Using UDTs Across Databases</span></span>  
 <span data-ttu-id="25677-212">Por definição, os UDTs têm escopo em um único banco de dados.</span><span class="sxs-lookup"><span data-stu-id="25677-212">UDTs are by definition scoped to a single database.</span></span> <span data-ttu-id="25677-213">Por isso, um UDT definido em um banco de dados não pode ser usado em uma definição de coluna de outro banco de dados.</span><span class="sxs-lookup"><span data-stu-id="25677-213">Therefore, a UDT defined in one database cannot be used in a column definition in another database.</span></span> <span data-ttu-id="25677-214">Para usar UDTs em vários bancos de dados, você deve executar as instruções CREATE ASSEMBLY e CREATE TYPE em cada banco de dados em assemblies idênticos.</span><span class="sxs-lookup"><span data-stu-id="25677-214">In order to use UDTs in multiple databases, you must execute the CREATE ASSEMBLY and CREATE TYPE statements in each database on identical assemblies.</span></span> <span data-ttu-id="25677-215">Os assemblies são considerados idênticos se tiverem os mesmos nome, nome forte, cultura, versão, conjunto de permissões e conteúdo binário.</span><span class="sxs-lookup"><span data-stu-id="25677-215">Assemblies are considered identical if they have the same name, strong name, culture, version, permission set, and binary contents.</span></span>  
  
 <span data-ttu-id="25677-216">Quando a UDT for registrado e estiver acessível nos dois bancos de dados, você poderá converter o valor de UDT de um banco de dados para o outro.</span><span class="sxs-lookup"><span data-stu-id="25677-216">Once the UDT is registered and accessible in both databases, you can convert a UDT value from one database for use in another.</span></span> <span data-ttu-id="25677-217">UDTs idênticos podem ser usados por bancos de dados nos seguintes cenários:</span><span class="sxs-lookup"><span data-stu-id="25677-217">Identical UDTs can be used across databases in the following scenarios:</span></span>  
  
-   <span data-ttu-id="25677-218">Chamar um procedimento armazenado definido em bancos de dados diferentes.</span><span class="sxs-lookup"><span data-stu-id="25677-218">Calling stored procedure defined in different databases.</span></span>  
  
-   <span data-ttu-id="25677-219">Consultar tabelas definidas em bancos de dados diferentes.</span><span class="sxs-lookup"><span data-stu-id="25677-219">Querying tables defined in different databases.</span></span>  
  
-   <span data-ttu-id="25677-220">Selecionar dados de UDT de uma coluna de UDT da tabela do banco de dados inserindo-a em um segundo banco de dados com coluna de UDT idêntica.</span><span class="sxs-lookup"><span data-stu-id="25677-220">Selecting UDT data from one database table UDT column and inserting it into a second database with an identical UDT column.</span></span>  
  
 <span data-ttu-id="25677-221">Nessas situações, qualquer conversão necessária do servidor ocorre automaticamente.</span><span class="sxs-lookup"><span data-stu-id="25677-221">In these situations, any conversion required by the server occurs automatically.</span></span> <span data-ttu-id="25677-222">Você não pode executar as conversões que usam explicitamente as funções CAST ou CONVERT do [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="25677-222">You are not able to perform the conversions explicitly using the [!INCLUDE[tsql](../../includes/tsql-md.md)] CAST or CONVERT functions.</span></span>  
  
 <span data-ttu-id="25677-223">Observe que você não precisa realizar nenhuma ação para usar UDTs quando [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] o cria tabelas de trabalho no banco de dados do sistema **tempdb** .</span><span class="sxs-lookup"><span data-stu-id="25677-223">Note that you do not need to take any action for using UDTs when [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] creates work tables in the **tempdb** system database.</span></span> <span data-ttu-id="25677-224">Isso inclui a manipulação de cursores, variáveis de tabela e funções com valor de tabela definidas pelo usuário que incluem UDTs e que usam de forma transparente o **tempdb**.</span><span class="sxs-lookup"><span data-stu-id="25677-224">This includes the handling of cursors, table variables, and user-defined table-valued functions that include UDTs and that transparently make use of **tempdb**.</span></span> <span data-ttu-id="25677-225">No entanto, se você criar explicitamente uma tabela temporária em **tempdb** que define uma coluna UDT, o UDT deverá ser registrado em **tempdb** da mesma maneira que para um banco de dados de usuário.</span><span class="sxs-lookup"><span data-stu-id="25677-225">However, if you explicitly create a temporary table in **tempdb** that defines a UDT column, then the UDT must be registered in **tempdb** the same way as for a user database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25677-226">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="25677-226">See Also</span></span>  
 [<span data-ttu-id="25677-227">Tipos definido pelo usuário CLR</span><span class="sxs-lookup"><span data-stu-id="25677-227">CLR User-Defined Types</span></span>](clr-user-defined-types.md)  
  
  
