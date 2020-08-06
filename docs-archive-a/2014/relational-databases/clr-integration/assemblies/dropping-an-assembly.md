---
title: Descartando um assembly | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- removing assemblies
- DROP ASSEMBLY statement
- assemblies [CLR integration], removing
- dropping assemblies
ms.assetid: 03481034-dc91-4488-ab24-ba44243e2690
author: rothja
ms.author: jroth
ms.openlocfilehash: 45d02cbb57459a4c1c11330446021c32dc897353
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87682281"
---
# <a name="dropping-an-assembly"></a><span data-ttu-id="ceedb-102">Descartando um assembly</span><span class="sxs-lookup"><span data-stu-id="ceedb-102">Dropping an Assembly</span></span>
  <span data-ttu-id="ceedb-103">Os assemblies registrados no [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] usando a instrução CREATE ASSEMBLY podem ser excluídos ou descartados quando a funcionalidade que fornecem deixa de ser necessária.</span><span class="sxs-lookup"><span data-stu-id="ceedb-103">Assemblies that have been registered in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] using the CREATE ASSEMBLY statement can be deleted, or dropped, when the functionality they provide is no longer needed.</span></span> <span data-ttu-id="ceedb-104">O descarte de um assembly remove o mesmo e todos os seus arquivos associados como, por exemplo, arquivos de depuração, do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="ceedb-104">Dropping an assembly removes the assembly and all of its associated files, such as debug files, from the database.</span></span> <span data-ttu-id="ceedb-105">Para descartar um assembly, use a instrução DROP ASSEMBLY com a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="ceedb-105">To drop an assembly, use the DROP ASSEMBLY statement with the following syntax:</span></span>  
  
```  
DROP ASSEMBLY MyDotNETAssembly  
```  
  
 <span data-ttu-id="ceedb-106">DROP ASSEMBLY não interfere em nenhum código que referencia o assembly atualmente em execução, mas após a execução de DROP ASSEMBLY, qualquer tentativa de invocar o código do assembly falha.</span><span class="sxs-lookup"><span data-stu-id="ceedb-106">DROP ASSEMBLY does not interfere with any code referencing the assembly that is currently running, but after DROP ASSEMBLY executes, any attempts to invoke the assembly code fail.</span></span>  
  
 <span data-ttu-id="ceedb-107">DROP ASSEMBLY retornará um erro se o assembly for referenciado por outro assembly que exista no banco de dados ou se for usado por funções CLR (Common Language Runtime), procedimentos armazenados, gatilhos, UDTs (tipos definidos pelo usuário) ou UDAs (agregações definidas pelo usuário) no banco de dados atual.</span><span class="sxs-lookup"><span data-stu-id="ceedb-107">DROP ASSEMBLY returns an error if the assembly is referenced by another assembly that exists in the database, or if it is used by common language runtime (CLR) functions, procedures, triggers, user-defined types (UDTs), or user-defined aggregates (UDAs) in the current database.</span></span> <span data-ttu-id="ceedb-108">Primeiro use as instruções DROP AGGREGATE, DROP FUNCTION, DROP PROCEDURE, DROP TRIGGER e DROP TYPE para excluir todos os objetos de banco de dados gerenciados contidos no assembly.</span><span class="sxs-lookup"><span data-stu-id="ceedb-108">First use the DROP AGGREGATE, DROP FUNCTION, DROP PROCEDURE, DROP TRIGGER, and DROP TYPE statements to delete any managed database objects contained in the assembly.</span></span>  
  
## <a name="removing-a-udt-from-the-database"></a><span data-ttu-id="ceedb-109">Removendo uma UDT do banco de dados</span><span class="sxs-lookup"><span data-stu-id="ceedb-109">Removing a UDT from the Database</span></span>  
 <span data-ttu-id="ceedb-110">A instrução de DROP TYPE remove uma UDT do banco de dados atual.</span><span class="sxs-lookup"><span data-stu-id="ceedb-110">The DROP TYPE statement removes a UDT from the current database.</span></span> <span data-ttu-id="ceedb-111">Quando uma UDT é descartada, você pode usar a instrução de DROP ASSEMBLY para descartar o assembly do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="ceedb-111">Once a UDT is dropped, you can use the DROP ASSEMBLY statement to drop the assembly from the database.</span></span>  
  
 <span data-ttu-id="ceedb-112">A instrução DROP TYPE falha caso objetos dependam da UDT, como nas seguintes situações:</span><span class="sxs-lookup"><span data-stu-id="ceedb-112">The DROP TYPE statement fails if objects depend on the UDT, as in the following situations:</span></span>  
  
-   <span data-ttu-id="ceedb-113">Tabelas no banco de dados que contêm colunas definidas usando a UDT.</span><span class="sxs-lookup"><span data-stu-id="ceedb-113">Tables in the database that contain columns defined using the UDT.</span></span>  
  
-   <span data-ttu-id="ceedb-114">Funções, procedimentos armazenados ou gatilhos que usam variáveis ou parâmetros da UDT, criadas no banco de dados com a cláusula WITH SCHEMABINDING.</span><span class="sxs-lookup"><span data-stu-id="ceedb-114">Functions, stored procedures, or triggers that use variables or parameters of the UDT, created in the database with the WITH SCHEMABINDING clause.</span></span>  
  
### <a name="finding-udt-dependencies"></a><span data-ttu-id="ceedb-115">Localizando dependências do UDT</span><span class="sxs-lookup"><span data-stu-id="ceedb-115">Finding UDT Dependencies</span></span>  
 <span data-ttu-id="ceedb-116">Você deve descartar todos os objetos dependentes primeiro e, em seguida, executar a instrução DROP TYPE.</span><span class="sxs-lookup"><span data-stu-id="ceedb-116">You must first drop all dependent objects, and then execute the DROP TYPE statement.</span></span> <span data-ttu-id="ceedb-117">A consulta a seguir [!INCLUDE[tsql](../../../includes/tsql-md.md)] localiza todas as colunas e parâmetros que usam um UDT no banco de dados **AdventureWorks** .</span><span class="sxs-lookup"><span data-stu-id="ceedb-117">The following [!INCLUDE[tsql](../../../includes/tsql-md.md)] query locates all of the columns and parameters that use a UDT in the **AdventureWorks** database.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ceedb-118">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ceedb-118">See Also</span></span>  
 <span data-ttu-id="ceedb-119">[Gerenciando assemblies de integração CLR](managing-clr-integration-assemblies.md) </span><span class="sxs-lookup"><span data-stu-id="ceedb-119">[Managing CLR Integration Assemblies](managing-clr-integration-assemblies.md) </span></span>  
 <span data-ttu-id="ceedb-120">[Alterando um assembly](altering-an-assembly.md) </span><span class="sxs-lookup"><span data-stu-id="ceedb-120">[Altering an Assembly](altering-an-assembly.md) </span></span>  
 <span data-ttu-id="ceedb-121">[Criando um assembly](creating-an-assembly.md) </span><span class="sxs-lookup"><span data-stu-id="ceedb-121">[Creating an Assembly](creating-an-assembly.md) </span></span>  
 <span data-ttu-id="ceedb-122">[Descartar AGREGAção &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-aggregate-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ceedb-122">[DROP AGGREGATE &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-aggregate-transact-sql) </span></span>  
 <span data-ttu-id="ceedb-123">[DROP FUNCTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-function-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ceedb-123">[DROP FUNCTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-function-transact-sql) </span></span>  
 <span data-ttu-id="ceedb-124">[Descartar procedimento &#40;&#41;Transact-SQL](/sql/t-sql/statements/drop-procedure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ceedb-124">[DROP PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-procedure-transact-sql) </span></span>  
 <span data-ttu-id="ceedb-125">[DROP TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-trigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ceedb-125">[DROP TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-trigger-transact-sql) </span></span>  
 [<span data-ttu-id="ceedb-126">DROP TYPE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ceedb-126">DROP TYPE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/drop-type-transact-sql)  
  
  
