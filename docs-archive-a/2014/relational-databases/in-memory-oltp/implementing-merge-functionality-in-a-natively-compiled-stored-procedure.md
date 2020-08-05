---
title: Implementando a funcionalidade de MESCLAgem | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: d4bcdc36-3302-4abc-9b35-64ec2b920986
author: rothja
ms.author: jroth
ms.openlocfilehash: 8c2e2d3f0796396c0f3f451215f1fd685979a842
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572563"
---
# <a name="implementing-merge-functionality"></a><span data-ttu-id="1da2a-102">Implementando a funcionalidade MERGE</span><span class="sxs-lookup"><span data-stu-id="1da2a-102">Implementing MERGE Functionality</span></span>
  <span data-ttu-id="1da2a-103">Um banco de dados pode precisar executar uma inserção ou uma atualização, dependendo de uma linha específica já existir no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="1da2a-103">A database may need to perform either an insert of an update, depending on whether a particular row already exists in the database.</span></span>  
  
 <span data-ttu-id="1da2a-104">Sem usar a instrução `MERGE`, veja a seguir uma abordagem que pode ser usada no [!INCLUDE[tsql](../../includes/tsql-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="1da2a-104">Without using the `MERGE` statement, the following is one approach you can use in [!INCLUDE[tsql](../../includes/tsql-md.md)]:</span></span>  
  
```sql  
UPDATE mytable SET col=@somevalue WHERE myPK = @parm  
IF @@ROWCOUNT = 0  
    INSERT mytable (columns) VALUES (@parm, @other values)  
```  
  
 <span data-ttu-id="1da2a-105">Outro método do [!INCLUDE[tsql](../../includes/tsql-md.md)] para implementar uma mesclagem:</span><span class="sxs-lookup"><span data-stu-id="1da2a-105">Another [!INCLUDE[tsql](../../includes/tsql-md.md)] method to implement a merge:</span></span>  
  
```sql  
IF EXISTS (SELECT 1 FROM mytable WHERE myPK = @parm)  
    UPDATE....  
ELSE  
    INSERT  
```  
  
 <span data-ttu-id="1da2a-106">Para um procedimento armazenado nativamente compilado</span><span class="sxs-lookup"><span data-stu-id="1da2a-106">For a natively compiled stored procedure</span></span>  
  
```sql  
DECLARE @i  int  = 0  -- or whatever your PK data type is  
UPDATE mytable SET @i=myPK, othercolums = other values WHERE myPK = @parm  
IF @i = 0  
   INSERT....  
```  
  
## <a name="see-also"></a><span data-ttu-id="1da2a-107">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="1da2a-107">See Also</span></span>  
 <span data-ttu-id="1da2a-108">[Problemas de migração para procedimentos armazenados compilados nativamente](migration-issues-for-natively-compiled-stored-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="1da2a-108">[Migration Issues for Natively Compiled Stored Procedures](migration-issues-for-natively-compiled-stored-procedures.md) </span></span>  
 [<span data-ttu-id="1da2a-109">Construções do Transact-SQL sem suporte pelo OLTP na memória</span><span class="sxs-lookup"><span data-stu-id="1da2a-109">Transact-SQL Constructs Not Supported by In-Memory OLTP</span></span>](transact-sql-constructs-not-supported-by-in-memory-oltp.md)  
  
  
