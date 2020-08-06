---
title: Compatibilidade com o FILESTREAM | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- FILESTREAM [SQL Server], SQL Server Native Client
- SQL Server Native Client [FILESTREAM support]
ms.assetid: 1ad3400d-7fcd-40c9-87ae-f5afc61e0374
author: rothja
ms.author: jroth
ms.openlocfilehash: 18e9a002bfb205e2c0807234550998fe48120d20
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679916"
---
# <a name="filestream-support"></a><span data-ttu-id="3ed6c-102">Suporte a FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="3ed6c-102">FILESTREAM Support</span></span>
  <span data-ttu-id="3ed6c-103">FILESTREAM é uma forma de armazenar e acessar valores altos de binário, por meio do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] ou por acesso direto ao sistema de arquivos do Windows.</span><span class="sxs-lookup"><span data-stu-id="3ed6c-103">FILESTREAM provides a way to store and access large binary values, either through [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] or by direct access to the Windows file system.</span></span> <span data-ttu-id="3ed6c-104">Um valor binário grande é um valor superior a 2 gigabytes (GB).</span><span class="sxs-lookup"><span data-stu-id="3ed6c-104">A large binary value is a value larger than 2 gigabytes (GB).</span></span> <span data-ttu-id="3ed6c-105">Para saber mais sobre a compatibilidade com o FILESTREAM avançado, confira [FILESTREAM &#40;SQL Server&#41;](../../blob/filestream-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="3ed6c-105">For more information about enhanced FILESTREAM support, see [FILESTREAM &#40;SQL Server&#41;](../../blob/filestream-sql-server.md).</span></span>  
  
 <span data-ttu-id="3ed6c-106">Quando uma conexão de banco de dados for aberta, `@@TEXTSIZE` será definido, por padrão, como -1 ("ilimitado").</span><span class="sxs-lookup"><span data-stu-id="3ed6c-106">When a database connection is opened, `@@TEXTSIZE` will be set to -1 ("unlimited"), by default.</span></span>  
  
 <span data-ttu-id="3ed6c-107">Também é possível acessar e atualizar colunas FILESTREAM usando as APIs do sistema de arquivos do Windows.</span><span class="sxs-lookup"><span data-stu-id="3ed6c-107">It is also possible to access and update FILESTREAM columns using Windows file system APIs.</span></span>  
  
 <span data-ttu-id="3ed6c-108">Para obter mais informações, consulte estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="3ed6c-108">For more information, see the following topics:</span></span>  
  
-   [<span data-ttu-id="3ed6c-109">Suporte a FILESTREAM &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="3ed6c-109">FILESTREAM Support &#40;OLE DB&#41;</span></span>](../ole-db/filestream-support-ole-db.md)  
  
-   [<span data-ttu-id="3ed6c-110">Suporte a FILESTREAM &#40;&#41;ODBC</span><span class="sxs-lookup"><span data-stu-id="3ed6c-110">FILESTREAM Support &#40;ODBC&#41;</span></span>](../odbc/filestream-support-odbc.md)  
  
-   [<span data-ttu-id="3ed6c-111">Acessar dados do FILESTREAM com OpenSqlFilestream</span><span class="sxs-lookup"><span data-stu-id="3ed6c-111">Access FILESTREAM Data with OpenSqlFilestream</span></span>](../../blob/access-filestream-data-with-opensqlfilestream.md)  
  
## <a name="querying-for-filestream-columns"></a><span data-ttu-id="3ed6c-112">Consultando colunas FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="3ed6c-112">Querying for FILESTREAM Columns</span></span>  
 <span data-ttu-id="3ed6c-113">Conjuntos de linhas de esquema no OLE DB não relatarão se uma coluna é uma coluna FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="3ed6c-113">Schema rowsets in OLE DB will not report whether a column is a FILESTREAM column.</span></span> <span data-ttu-id="3ed6c-114">ITableDefinition no OLE DB não pode ser usado para criar uma coluna FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="3ed6c-114">ITableDefinition in OLE DB cannot be used to create a FILESTREAM column.</span></span>  
  
 <span data-ttu-id="3ed6c-115">As funções de catálogo, como SQLColumns no ODBC, não relatarão se uma coluna é uma coluna FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="3ed6c-115">Catalog functions such as SQLColumns in ODBC will not report whether a column is a FILESTREAM column.</span></span>  
  
 <span data-ttu-id="3ed6c-116">Para criar colunas FILESTREAM ou detectar quais colunas existentes são colunas FILESTREAM, você pode usar a `is_filestream` coluna da exibição de catálogo [Sys. Columns](/sql/relational-databases/system-catalog-views/sys-columns-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="3ed6c-116">To create FILESTREAM columns or to detect which existing columns are FILESTREAM columns, you can use the `is_filestream` column of the [sys.columns](/sql/relational-databases/system-catalog-views/sys-columns-transact-sql) catalog view.</span></span>  
  
 <span data-ttu-id="3ed6c-117">A seguir, é mostrado um exemplo:</span><span class="sxs-lookup"><span data-stu-id="3ed6c-117">The following is an example:</span></span>  
  
```  
-- Create a table with a FILESTREAM column.  
CREATE TABLE Bob_01 (GuidCol1 uniqueidentifier ROWGUIDCOL NOT NULL UNIQUE DEFAULT NEWID(), IntCol2 int, varbinaryCol3 varbinary(max) FILESTREAM);  
  
-- Find FILESTREAM columns.  
SELECT name FROM sys.columns WHERE is_filestream=1;  
  
-- Determine whether a column is a FILESTREAM column.  
SELECT is_filestream FROM sys.columns WHERE name = 'varbinaryCol3' AND object_id IN (SELECT object_id FROM sys.tables WHERE name='Bob_01');  
```  
  
## <a name="down-level-compatibility"></a><span data-ttu-id="3ed6c-118">Compatibilidade com níveis inferiores</span><span class="sxs-lookup"><span data-stu-id="3ed6c-118">Down-Level Compatibility</span></span>  
 <span data-ttu-id="3ed6c-119">Se o cliente foi compilado usando a versão do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client que foi incluída no [!INCLUDE[ssVersion2005](../../../includes/sscurrent-md.md)] , o `varbinary(max)` comportamento será compatível com o [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3ed6c-119">If your client was compiled using the version of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client that was included with [!INCLUDE[ssVersion2005](../../../includes/sscurrent-md.md)], `varbinary(max)` behavior will be compatible with [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)].</span></span> <span data-ttu-id="3ed6c-120">Ou seja, o tamanho máximo de dados retornados será limitado a 2 GB.</span><span class="sxs-lookup"><span data-stu-id="3ed6c-120">That is, the maximum size of returned data will be limited to 2 GB.</span></span> <span data-ttu-id="3ed6c-121">Para valores de resultado superiores a 2 GB, ocorrerá truncamento e será retornado um aviso de "truncamento à direita de dados de cadeia de caracteres".</span><span class="sxs-lookup"><span data-stu-id="3ed6c-121">For result values larger that 2 GB, truncation will occur and a "string data right truncation" warning will be returned.</span></span>  
  
 <span data-ttu-id="3ed6c-122">Quando a compatibilidade de tipo de dados estiver definida como 80, o comportamento do cliente será consistente com o comportamento de clientes de nível inferior.</span><span class="sxs-lookup"><span data-stu-id="3ed6c-122">When data-type compatibility is set to 80, client behavior will be consistent with down-level client behavior.</span></span>  
  
 <span data-ttu-id="3ed6c-123">Para clientes que usam SQLOLEDB ou outros provedores que foram liberados antes do [!INCLUDE[ssVersion2005](../../../includes/ssnoversion-md.md)] Native Client, `varbinary(max)` serão mapeados para a imagem.</span><span class="sxs-lookup"><span data-stu-id="3ed6c-123">For clients that use SQLOLEDB or other providers that were released before the [!INCLUDE[ssVersion2005](../../../includes/ssnoversion-md.md)] Native Client, `varbinary(max)` will be mapped to image.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ed6c-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="3ed6c-124">See Also</span></span>  
 [<span data-ttu-id="3ed6c-125">Recursos do SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="3ed6c-125">SQL Server Native Client Features</span></span>](sql-server-native-client-features.md)  
  
  
