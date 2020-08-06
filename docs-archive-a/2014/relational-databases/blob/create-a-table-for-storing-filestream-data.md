---
title: Criar uma tabela para armazenar dados FILESTREAM | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: filestream
ms.topic: conceptual
helpviewer_keywords:
- FILESTREAM [SQL Server], table storage
ms.assetid: 029c3059-5c83-43e2-a859-9027031b7de1
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 484d7b58ce949df79dc7e17ee4dc7307b70c0154
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680480"
---
# <a name="create-a-table-for-storing-filestream-data"></a><span data-ttu-id="01b94-102">Criar uma tabela para armazenar dados FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="01b94-102">Create a Table for Storing FILESTREAM Data</span></span>
  <span data-ttu-id="01b94-103">Este tópico mostra como criar uma tabela para armazenar dados FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="01b94-103">This topic shows how to create a table for storing FILESTREAM data.</span></span>  
  
 <span data-ttu-id="01b94-104">Quando o banco de dados tiver um grupo de arquivos FILESTREAM, será possível criar ou modificar tabelas para armazenar dados FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="01b94-104">When the database has a FILESTREAM filegroup, you can create or modify tables to store FILESTREAM data.</span></span> <span data-ttu-id="01b94-105">Para especificar que uma coluna contém dados FILESTREAM, crie a coluna `varbinary(max)` e adicione o atributo FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="01b94-105">To specify that a column contains FILESTREAM data, you create a `varbinary(max)` column and add the FILESTREAM attribute.</span></span>  
  
### <a name="to-create-a-table-to-store-filestream-data"></a><span data-ttu-id="01b94-106">Para criar uma tabela para armazenar dados FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="01b94-106">To create a table to store FILESTREAM data</span></span>  
  
1.  <span data-ttu-id="01b94-107">No [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], clique em **Nova Consulta** para exibir o Editor de Consultas.</span><span class="sxs-lookup"><span data-stu-id="01b94-107">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], click **New Query** to display the Query Editor.</span></span>  
  
2.  <span data-ttu-id="01b94-108">Copie o código [!INCLUDE[tsql](../../includes/tsql-md.md)] do exemplo a seguir no Editor de Consultas.</span><span class="sxs-lookup"><span data-stu-id="01b94-108">Copy the [!INCLUDE[tsql](../../includes/tsql-md.md)] code from the following example into the Query Editor.</span></span> <span data-ttu-id="01b94-109">Este código [!INCLUDE[tsql](../../includes/tsql-md.md)] cria uma tabela habilitada para FILESTREAM chamada Registros.</span><span class="sxs-lookup"><span data-stu-id="01b94-109">This [!INCLUDE[tsql](../../includes/tsql-md.md)] code creates a FILESTREAM-enabled table called Records.</span></span>  
  
3.  <span data-ttu-id="01b94-110">Para criar a tabela, clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="01b94-110">To create the table, click **Execute**.</span></span>  
  
## <a name="example"></a><span data-ttu-id="01b94-111">Exemplo</span><span class="sxs-lookup"><span data-stu-id="01b94-111">Example</span></span>  
 <span data-ttu-id="01b94-112">O exemplo de código a seguir mostra como criar uma tabela chamada `Records`.</span><span class="sxs-lookup"><span data-stu-id="01b94-112">The following code example shows how to create a table that is named `Records`.</span></span> <span data-ttu-id="01b94-113">A coluna `Id` é uma coluna `ROWGUIDCOL` exigida para usar dados de FILESTREAM com APIs de Win32.</span><span class="sxs-lookup"><span data-stu-id="01b94-113">The `Id` column is a `ROWGUIDCOL` column and is required to use FILESTREAM data with Win32 APIs.</span></span> <span data-ttu-id="01b94-114">A coluna `SerialNumber` é uma coluna `UNIQUE INTEGER`.</span><span class="sxs-lookup"><span data-stu-id="01b94-114">The `SerialNumber` column is a `UNIQUE INTEGER`.</span></span> <span data-ttu-id="01b94-115">A coluna `Chart` é uma coluna `FILESTREAM` usada para armazenar `Chart` no sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="01b94-115">The `Chart` column is a `FILESTREAM` column and is used to store the `Chart` in the file system.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="01b94-116">Este tópico requer o banco de dados Archive que foi criado em [Criar um banco de dados habilitado para FILESTREAM](create-a-filestream-enabled-database.md).</span><span class="sxs-lookup"><span data-stu-id="01b94-116">This example refers to the Archive database that is created in [Create a FILESTREAM-Enabled Database](create-a-filestream-enabled-database.md).</span></span>  
  
 [!code-sql[FILESTREAM#FS_CreateTable](../../snippets/tsql/SQL15/tsql/filestream/transact-sql/filestream.sql#fs_createtable)]  
  
## <a name="see-also"></a><span data-ttu-id="01b94-117">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="01b94-117">See Also</span></span>  
 <span data-ttu-id="01b94-118">[CREATE TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-table-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="01b94-118">[CREATE TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-table-transact-sql) </span></span>  
 [<span data-ttu-id="01b94-119">ALTER TABLE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="01b94-119">ALTER TABLE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-table-transact-sql)  
  
  
