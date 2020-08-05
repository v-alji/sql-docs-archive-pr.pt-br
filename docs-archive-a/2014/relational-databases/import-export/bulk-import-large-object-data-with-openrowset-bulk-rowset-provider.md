---
title: Importação em massa de dados de objeto grande usando o provedor de conjunto de linhas OPENROWSET em massa (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- SINGLE_NCLOB option
- bulk rowset providers [SQL Server]
- bulk importing [SQL Server], data formats
- OPENROWSET function, bulk importing large data
- SINGLE_CLOB option
- data formats [SQL Server], large-object data
- large data, bulk imports
- SINGLE_BLOB option
ms.assetid: 171cdd5c-1e47-4bd7-b99a-4f0fd4e10526
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 0f43aa2fa5e7f7ef0b2c8f1f6e5e6ff28e02f9f1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573000"
---
# <a name="bulk-import-large-object-data-by-using-the-openrowset-bulk-rowset-provider-sql-server"></a><span data-ttu-id="c3d00-102">Importando em massa dados de objeto grande usando o provedor de conjunto de linhas em massa OPENROWSET (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="c3d00-102">Bulk Import Large-Object Data by using the OPENROWSET Bulk Rowset Provider (SQL Server)</span></span>
  <span data-ttu-id="c3d00-103">O Provedor de Conjunto de Linhas em Massa OPENROWSET do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] permite a importação em massa de um arquivo de dados como dados de objeto grande.</span><span class="sxs-lookup"><span data-stu-id="c3d00-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] OPENROWSET Bulk Rowset Provider enables you to bulk import a data file as large-object data.</span></span>  
  
 <span data-ttu-id="c3d00-104">Os tipos de dados de objeto grande com suporte no Provedor de Conjuntos de Linhas em Massa OPENROWSET são **varbinary**(max) ou **image**, **varchar**(max) ou **text**e **nvarchar**(max) ou **ntext**.</span><span class="sxs-lookup"><span data-stu-id="c3d00-104">The large-object data types supported by OPENROWSET Bulk Rowset Provider are **varbinary**(max) or **image**, **varchar**(max) or **text**, and **nvarchar**(max) or **ntext**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c3d00-105">Os tipos de dados **image**, **text** e **ntext** foram preteridos.</span><span class="sxs-lookup"><span data-stu-id="c3d00-105">The **image**, **text** and **ntext** data types are deprecated.</span></span>  
  
 <span data-ttu-id="c3d00-106">A cláusula OPENROWSET BULK oferece suporte a três opções que importam o conteúdo de um arquivo de dados como um conjunto de linhas com linha e coluna únicas.</span><span class="sxs-lookup"><span data-stu-id="c3d00-106">The OPENROWSET BULK clause supports three options for importing the contents of a data file as a single-row, single-column rowset.</span></span> <span data-ttu-id="c3d00-107">Você pode especificar uma dessas opções de objeto grande, em vez de usar um arquivo de formato.</span><span class="sxs-lookup"><span data-stu-id="c3d00-107">You can specify one of these large-object options instead of using a format file.</span></span> <span data-ttu-id="c3d00-108">Essas opções são as seguintes:</span><span class="sxs-lookup"><span data-stu-id="c3d00-108">These options are as follows:</span></span>  
  
 <span data-ttu-id="c3d00-109">SINGLE_BLOB</span><span class="sxs-lookup"><span data-stu-id="c3d00-109">SINGLE_BLOB</span></span>  
 <span data-ttu-id="c3d00-110">Lê o conteúdo de *data_file* como uma linha única, retorna o conteúdo como um conjunto de linhas de coluna única do tipo **varbinary(max)** .</span><span class="sxs-lookup"><span data-stu-id="c3d00-110">Reads the contents of *data_file* as a single-row, returns the contents as a single-column rowset of type **varbinary(max)**.</span></span>  
  
 <span data-ttu-id="c3d00-111">SINGLE_CLOB</span><span class="sxs-lookup"><span data-stu-id="c3d00-111">SINGLE_CLOB</span></span>  
 <span data-ttu-id="c3d00-112">Lê os conteúdos do arquivo de dados especificado como caracteres, retorna os conteúdos como um conjunto de linhas de linha única e coluna única do tipo **varchar(max)** , usando a ordenação do banco de dados atual, como um text ou documento do [!INCLUDE[msCoName](../../includes/msconame-md.md)] Word.</span><span class="sxs-lookup"><span data-stu-id="c3d00-112">Reads the contents of the specified data file as characters, returns the contents as a single-row, single-column rowset of type **varchar(max)**, using the collation of the current database; such as a text or [!INCLUDE[msCoName](../../includes/msconame-md.md)] Word document.</span></span>  
  
 <span data-ttu-id="c3d00-113">SINGLE_NCLOB</span><span class="sxs-lookup"><span data-stu-id="c3d00-113">SINGLE_NCLOB</span></span>  
 <span data-ttu-id="c3d00-114">Lê os conteúdos do arquivo de dados especificados como Unicode, retorna os conteúdos como um conjunto de linhas de linha única e coluna única do tipo **nvarchar(max)** , usando a ordenação do banco de dados atual.</span><span class="sxs-lookup"><span data-stu-id="c3d00-114">Reads the contents of the specified data file as Unicode, returns the contents as a single-row, single-column rowset of type **nvarchar(max)**, using the collation of the current database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3d00-115">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c3d00-115">See Also</span></span>  
 <span data-ttu-id="c3d00-116">[Importar dados em massa usando BULK INSERT ou OPENROWSET&#40;BULK...&#41; &#40;SQL Server&#41;](import-bulk-data-by-using-bulk-insert-or-openrowset-bulk-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="c3d00-116">[Import Bulk Data by Using BULK INSERT or OPENROWSET&#40;BULK...&#41; &#40;SQL Server&#41;](import-bulk-data-by-using-bulk-insert-or-openrowset-bulk-sql-server.md) </span></span>  
 <span data-ttu-id="c3d00-117">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c3d00-117">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="c3d00-118">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c3d00-118">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span></span>  
 <span data-ttu-id="c3d00-119">[Manter valores nulos ou use os valores padrão durante a importação em massa &#40;SQL Server&#41;](keep-nulls-or-use-default-values-during-bulk-import-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="c3d00-119">[Keep Nulls or Use Default Values During Bulk Import &#40;SQL Server&#41;](keep-nulls-or-use-default-values-during-bulk-import-sql-server.md) </span></span>  
 <span data-ttu-id="c3d00-120">[Utilitário bcp](../../tools/bcp-utility.md) </span><span class="sxs-lookup"><span data-stu-id="c3d00-120">[bcp Utility](../../tools/bcp-utility.md) </span></span>  
 [<span data-ttu-id="c3d00-121">BULK INSERT &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="c3d00-121">BULK INSERT &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/bulk-insert-transact-sql)  
  
  
