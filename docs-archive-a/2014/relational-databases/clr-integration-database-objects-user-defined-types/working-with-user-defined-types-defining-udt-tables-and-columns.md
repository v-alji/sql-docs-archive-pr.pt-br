---
title: Definindo colunas e tabelas UDT | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
dev_langs:
- TSQL
helpviewer_keywords:
- user-defined types [CLR integration], columns
- UDTs [CLR integration], columns
- columns [CLR integration]
- user-defined types [CLR integration], tables
- tables [CLR integration]
- UDTs [CLR integration], tables
- UDTs [CLR integration], indexes
- user-defined types [CLR integration], indexes
- indexes [CLR integration]
ms.assetid: aea495f4-ce26-4952-b019-38f012625f3f
author: rothja
ms.author: jroth
ms.openlocfilehash: aa9596629ed8b4877b1793fa0c56956c52989499
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87584158"
---
# <a name="defining-udt-tables-and-columns"></a><span data-ttu-id="8e6c9-102">Definindo tabelas e colunas UDT</span><span class="sxs-lookup"><span data-stu-id="8e6c9-102">Defining UDT Tables and Columns</span></span>
  <span data-ttu-id="8e6c9-103">Depois que o assembly que contém a definição de UDT (tipo definido pelo usuário) tiver sido registrado em um [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] banco de dados, ele poderá ser usado em uma definição de coluna.</span><span class="sxs-lookup"><span data-stu-id="8e6c9-103">Once the assembly containing the user-defined type (UDT) definition has been registered in a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database, it can be used in a column definition.</span></span>  
  
## <a name="creating-tables-with-udts"></a><span data-ttu-id="8e6c9-104">Criando tabelas com UDTs</span><span class="sxs-lookup"><span data-stu-id="8e6c9-104">Creating Tables with UDTs</span></span>  
 <span data-ttu-id="8e6c9-105">Não há nenhuma sintaxe especial para criar uma coluna UDT em uma tabela.</span><span class="sxs-lookup"><span data-stu-id="8e6c9-105">There is no special syntax for creating a UDT column in a table.</span></span> <span data-ttu-id="8e6c9-106">Você pode usar o nome do UDT em uma definição de coluna como se ele fosse um dos tipos de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] intrínsecos.</span><span class="sxs-lookup"><span data-stu-id="8e6c9-106">You can use the name of the UDT in a column definition as though it were one of the intrinsic [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data types.</span></span> <span data-ttu-id="8e6c9-107">A instrução CREATE TABLE a seguir [!INCLUDE[tsql](../../includes/tsql-md.md)] cria uma tabela chamada **Points**, com uma coluna chamada **ID,** que é definida como uma `int` coluna de identidade e a chave primária da tabela.</span><span class="sxs-lookup"><span data-stu-id="8e6c9-107">The following CREATE TABLE [!INCLUDE[tsql](../../includes/tsql-md.md)] statement creates a table named **Points**, with a column named **ID,** which is defined as an `int` identity column and \ the primary key for the table.</span></span> <span data-ttu-id="8e6c9-108">A segunda coluna é nome **PointValue**, com um tipo de dados de **Point**.</span><span class="sxs-lookup"><span data-stu-id="8e6c9-108">The second column is named **PointValue**, with a data type of **Point**.</span></span> <span data-ttu-id="8e6c9-109">O nome do esquema usado neste exemplo é **dbo**.</span><span class="sxs-lookup"><span data-stu-id="8e6c9-109">The schema name used in this example is **dbo**.</span></span> <span data-ttu-id="8e6c9-110">Observe que você precisa ter as permissões necessárias para especificar um nome de esquema.</span><span class="sxs-lookup"><span data-stu-id="8e6c9-110">Note that you must have the necessary permissions to specify a schema name.</span></span> <span data-ttu-id="8e6c9-111">Se você omitir o nome do esquema, será usado o esquema padrão do usuário de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="8e6c9-111">If you omit the schema name, the default schema for the database user is used.</span></span>  
  
```  
CREATE TABLE dbo.Points   
(ID int IDENTITY(1,1) PRIMARY KEY, PointValue Point)  
```  
  
## <a name="creating-indexes-on-udt-columns"></a><span data-ttu-id="8e6c9-112">Criando índices em colunas UDT</span><span class="sxs-lookup"><span data-stu-id="8e6c9-112">Creating Indexes on UDT Columns</span></span>  
 <span data-ttu-id="8e6c9-113">Há duas opções para indexar uma coluna UDT:</span><span class="sxs-lookup"><span data-stu-id="8e6c9-113">There are two options for indexing a UDT column:</span></span>  
  
-   <span data-ttu-id="8e6c9-114">Indexar o valor cheio.</span><span class="sxs-lookup"><span data-stu-id="8e6c9-114">Index the full value.</span></span> <span data-ttu-id="8e6c9-115">Neste caso, se o UDT tiver ordem binária, você poderá criar um índice de toda a coluna UDT usando a instrução [!INCLUDE[tsql](../../includes/tsql-md.md)] CREATE INDEX.</span><span class="sxs-lookup"><span data-stu-id="8e6c9-115">In this case, if the UDT is binary ordered, you can create an index over the entire UDT column by using the CREATE INDEX [!INCLUDE[tsql](../../includes/tsql-md.md)] statement.</span></span>  
  
-   <span data-ttu-id="8e6c9-116">Indexar expressões UDT.</span><span class="sxs-lookup"><span data-stu-id="8e6c9-116">Index UDT expressions.</span></span> <span data-ttu-id="8e6c9-117">Você pode criar índices em colunas computadas persistidas das expressões UDT.</span><span class="sxs-lookup"><span data-stu-id="8e6c9-117">You can create indexes on persisted computed columns over UDT expressions.</span></span> <span data-ttu-id="8e6c9-118">A expressão UDT pode ser um campo, um método ou uma propriedade de um UDT.</span><span class="sxs-lookup"><span data-stu-id="8e6c9-118">The UDT expression can be a field, method, or property of a UDT.</span></span> <span data-ttu-id="8e6c9-119">A expressão deve ser determinística e não deve acessar dados.</span><span class="sxs-lookup"><span data-stu-id="8e6c9-119">The expression must be deterministic and must not perform data access.</span></span>  
  
 <span data-ttu-id="8e6c9-120">Para obter mais informações, consulte [tipos CLR definidos pelo usuário](clr-user-defined-types.md) e [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="8e6c9-120">For more information, see [CLR User-Defined Types](clr-user-defined-types.md) and [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e6c9-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8e6c9-121">See Also</span></span>  
 [<span data-ttu-id="8e6c9-122">Trabalhando com tipos de dados definidos pelo usuário no SQL Server</span><span class="sxs-lookup"><span data-stu-id="8e6c9-122">Working with User-Defined Types in SQL Server</span></span>](working-with-user-defined-types-in-sql-server.md)  
  
  
