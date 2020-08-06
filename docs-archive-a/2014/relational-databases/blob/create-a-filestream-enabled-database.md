---
title: Criar um banco de dados habilitado para FILESTREAM | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: filestream
ms.topic: conceptual
helpviewer_keywords:
- FILESTREAM [SQL Server], FILESTREAM-enabled databases
ms.assetid: 0fc16356-76f7-44b8-a58b-f0b7c43694ec
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 0fe6e5bc6e4f60bc0703482f3bf4d761104b3c5f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680965"
---
# <a name="create-a-filestream-enabled-database"></a><span data-ttu-id="745ae-102">Criar um banco de dados habilitado para FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="745ae-102">Create a FILESTREAM-Enabled Database</span></span>
  <span data-ttu-id="745ae-103">Este tópico mostra como criar um banco de dados que oferece suporte a FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="745ae-103">This topic shows how to create a database that supports FILESTREAM.</span></span> <span data-ttu-id="745ae-104">Como o FILESTREAM usa um tipo especial de grupo de arquivos, ao criar o banco de dados, será preciso especificar a cláusula CONTAINS FILESTREAM para pelo menos um grupo de arquivos.</span><span class="sxs-lookup"><span data-stu-id="745ae-104">Because FILESTREAM uses a special type of filegroup, when you create the database, you must specify the CONTAINS FILESTREAM clause for at least one filegroup.</span></span>  
  
 <span data-ttu-id="745ae-105">Um grupo de arquivos FILESTREAM pode conter mais de um arquivo.</span><span class="sxs-lookup"><span data-stu-id="745ae-105">A FILESTREAM filegroup can contain more than one file.</span></span> <span data-ttu-id="745ae-106">Para ver um exemplo de código que demonstra como criar um grupo de arquivos FILESTREAM que contém vários arquivos, consulte [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="745ae-106">For a code example that demonstrates how to create a FILESTREAM filegroup that contains multiple files, see [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql).</span></span>  
  
### <a name="to-create-a-filestream-enabled-database"></a><span data-ttu-id="745ae-107">Para criar um banco de dados habilitado para FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="745ae-107">To create a FILESTREAM-enabled database</span></span>  
  
1.  <span data-ttu-id="745ae-108">No [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], clique em **Nova Consulta** para exibir o Editor de Consultas.</span><span class="sxs-lookup"><span data-stu-id="745ae-108">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], click **New Query** to display the Query Editor.</span></span>  
  
2.  <span data-ttu-id="745ae-109">Copiar o [!INCLUDE[tsql](../../includes/tsql-md.md)] código cria um banco de dados habilitado para FILESTREAM chamado arquivo morto.</span><span class="sxs-lookup"><span data-stu-id="745ae-109">Copy the [!INCLUDE[tsql](../../includes/tsql-md.md)] code creates a FILESTREAM-enabled database called Archive.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="745ae-110">Para este script, o diretório C:\Data deve existir.</span><span class="sxs-lookup"><span data-stu-id="745ae-110">For this script, the directory C:\Data must exist.</span></span>  
  
3.  <span data-ttu-id="745ae-111">Para construir o banco de dados, clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="745ae-111">To build the database, click **Execute**.</span></span>  
  
## <a name="example"></a><span data-ttu-id="745ae-112">Exemplo</span><span class="sxs-lookup"><span data-stu-id="745ae-112">Example</span></span>  
 <span data-ttu-id="745ae-113">O exemplo de código a seguir cria um banco de dados chamado `Archive`.</span><span class="sxs-lookup"><span data-stu-id="745ae-113">The following code example creates a database that is named `Archive`.</span></span> <span data-ttu-id="745ae-114">O banco de dados contém três grupos de arquivos: `PRIMARY`, `Arch1`e `FileStreamGroup1`.</span><span class="sxs-lookup"><span data-stu-id="745ae-114">The database contains three filegroups: `PRIMARY`, `Arch1`, and `FileStreamGroup1`.</span></span> <span data-ttu-id="745ae-115">`PRIMARY` e `Arch1` são grupos de arquivos normais que não podem conter dados FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="745ae-115">`PRIMARY` and `Arch1` are regular filegroups that cannot contain FILESTREAM data.</span></span> <span data-ttu-id="745ae-116">`FileStreamGroup1` é o grupo de arquivos `FILESTREAM` .</span><span class="sxs-lookup"><span data-stu-id="745ae-116">`FileStreamGroup1` is the `FILESTREAM` filegroup.</span></span>  
  
```sql  
CREATE DATABASE Archive   
ON  
PRIMARY ( NAME = Arch1,  
    FILENAME = 'c:\data\archdat1.mdf'),  
FILEGROUP FileStreamGroup1 CONTAINS FILESTREAM( NAME = Arch3,  
    FILENAME = 'c:\data\filestream1')  
LOG ON  ( NAME = Archlog1,  
    FILENAME = 'c:\data\archlog1.ldf')  
GO  
```  
  
 <span data-ttu-id="745ae-117">Para um grupo de arquivos `FILESTREAM` , `FILENAME` faz referência a um caminho.</span><span class="sxs-lookup"><span data-stu-id="745ae-117">For a `FILESTREAM` filegroup, `FILENAME` refers to a path.</span></span> <span data-ttu-id="745ae-118">O caminho até a última pasta deve existir e a última pasta não deve existir.</span><span class="sxs-lookup"><span data-stu-id="745ae-118">The path up to the last folder must exist, and the last folder must not exist.</span></span> <span data-ttu-id="745ae-119">Neste exemplo, `c:\data` deve existir.</span><span class="sxs-lookup"><span data-stu-id="745ae-119">In this example, `c:\data` must exist.</span></span> <span data-ttu-id="745ae-120">Entretanto, a subpasta `filestream1` não pode existir quando você executar a instrução `CREATE DATABASE` .</span><span class="sxs-lookup"><span data-stu-id="745ae-120">However, the `filestream1` subfolder cannot exist when you execute the `CREATE DATABASE` statement.</span></span> <span data-ttu-id="745ae-121">Para saber mais sobre a sintaxe, consulte [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="745ae-121">For more information about the syntax, see [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql).</span></span>  
  
 <span data-ttu-id="745ae-122">Após executar o exemplo anterior, um arquivo filestream.hdr e uma pasta $FSLOG devem aparecer na pasta c:\Data\filestream1.</span><span class="sxs-lookup"><span data-stu-id="745ae-122">After you run the previous example, a filestream.hdr file and an $FSLOG folder appears in the c:\Data\filestream1 folder.</span></span> <span data-ttu-id="745ae-123">O arquivo filestream.hdr é um arquivo de cabeçalho para o contêiner FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="745ae-123">The filestream.hdr file is a header file for the FILESTREAM container.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="745ae-124">O arquivo filestream.hdr é um arquivo de sistema importante.</span><span class="sxs-lookup"><span data-stu-id="745ae-124">The filestream.hdr file is an important system file.</span></span> <span data-ttu-id="745ae-125">Ele contém informações de cabeçalho FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="745ae-125">It contains FILESTREAM header information.</span></span> <span data-ttu-id="745ae-126">Não remova nem modifique esse arquivo.</span><span class="sxs-lookup"><span data-stu-id="745ae-126">Do not remove or modify this file.</span></span>  
  
 <span data-ttu-id="745ae-127">Em bancos de dados existentes, você pode usar a instrução [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql) para adicionar um grupo de arquivos FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="745ae-127">For existing databases, you can use the [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql) statement to add a FILESTREAM filegroup.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="745ae-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="745ae-128">See Also</span></span>  
 <span data-ttu-id="745ae-129">[CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="745ae-129">[CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span></span>  
 [<span data-ttu-id="745ae-130">ALTER DATABASE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="745ae-130">ALTER DATABASE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-database-transact-sql)  
  
  
