---
title: Fazer atualizações parciais em dados FILESTREAM | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: filestream
ms.topic: conceptual
helpviewer_keywords:
- FILESTREAM [SQL Server], FSCTL_SQL_FILESTREAM_FETCH_OLD_CONTENT
- FSCTL_SQL_FILESTREAM_FETCH_OLD_CONTENT
ms.assetid: d6f7661e-6c14-4d31-9541-4520ca0f82b2
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 696c1a6421e14568877e24f015e5094395f1051b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684765"
---
# <a name="make-partial-updates-to-filestream-data"></a><span data-ttu-id="ef03e-102">Fazer atualizações parciais em dados do FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="ef03e-102">Make Partial Updates to FILESTREAM Data</span></span>
  <span data-ttu-id="ef03e-103">Um aplicativo usa FSCTL_SQL_FILESTREAM_FETCH_OLD_CONTENT para fazer atualizações parciais em dados de BLOB FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="ef03e-103">An application uses FSCTL_SQL_FILESTREAM_FETCH_OLD_CONTENT to make partial updates to FILESTREAM BLOB data.</span></span> <span data-ttu-id="ef03e-104">A função [DeviceIoControl](https://go.microsoft.com/fwlink/?LinkId=105527) passa esse valor e o identificador que é retornado de [OpenSqlFilestream](access-filestream-data-with-opensqlfilestream.md) para o driver FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="ef03e-104">The [DeviceIoControl](https://go.microsoft.com/fwlink/?LinkId=105527) function passes this value and the handle that is returned from [OpenSqlFilestream](access-filestream-data-with-opensqlfilestream.md) to the FILESTREAM driver.</span></span> <span data-ttu-id="ef03e-105">O driver então força uma cópia de servidor dos dados de FILESTREAM atuais no arquivo referenciado pelo identificador.</span><span class="sxs-lookup"><span data-stu-id="ef03e-105">The driver then forces a server-side copy of the current FILESTREAM data into the file that is referenced by the handle.</span></span> <span data-ttu-id="ef03e-106">Se o aplicativo emite o valor FSCTL_SQL_FILESTREAM_FETCH_OLD_CONTENT depois que o identificador ter sido gravado, a última operação de gravação permanecerá e as operações de gravação anteriores feitas no identificador serão perdidas.</span><span class="sxs-lookup"><span data-stu-id="ef03e-106">If the application issues the FSCTL_SQL_FILESTREAM_FETCH_OLD_CONTENT value after the handle has been written to, the last write operation persists and previous write operations that were made to the handle are lost.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ef03e-107">FILESTREAM usa o [protocolo SMB](https://go.microsoft.com/fwlink/?LinkId=112454) para acesso remoto.</span><span class="sxs-lookup"><span data-stu-id="ef03e-107">FILESTREAM relies on the [SMB protocol](https://go.microsoft.com/fwlink/?LinkId=112454) for remote access.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ef03e-108">Exemplo</span><span class="sxs-lookup"><span data-stu-id="ef03e-108">Example</span></span>  
 <span data-ttu-id="ef03e-109">O exemplo a seguir mostra como usar o valor `FSCTL_SQL_FILESTREAM_FETCH_OLD_CONTENT` para executar uma atualização parcial de um BLOB FILESTREAM inserido.</span><span class="sxs-lookup"><span data-stu-id="ef03e-109">The following example shows you how to use the `FSCTL_SQL_FILESTREAM_FETCH_OLD_CONTENT` value to perform a partial update of an inserted FILESTREAM BLOB.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ef03e-110">Este exemplo requer o banco de dados e a tabela habilitados para FILESTREAM criados em [Criar um banco de dados habilitado para FILESTREAM](create-a-filestream-enabled-database.md) e [Como criar uma tabela para armazenar dados de FILESTREAM](create-a-table-for-storing-filestream-data.md).</span><span class="sxs-lookup"><span data-stu-id="ef03e-110">This example requires the FILESTREAM-enabled database and table that are created in [Create a FILESTREAM-Enabled Database](create-a-filestream-enabled-database.md) and [Create a Table for Storing FILESTREAM Data](create-a-table-for-storing-filestream-data.md).</span></span>  
  
 [!code-cpp[FILESTREAM#FS_CPP_FSCTL](../../snippets/tsql/SQL15/tsql/filestream/cpp/filestream.cpp#fs_cpp_fsctl)]  
  
## <a name="see-also"></a><span data-ttu-id="ef03e-111">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ef03e-111">See Also</span></span>  
 <span data-ttu-id="ef03e-112">[Acessar dados do FILESTREAM com OpenSqlFilestream](access-filestream-data-with-opensqlfilestream.md) </span><span class="sxs-lookup"><span data-stu-id="ef03e-112">[Access FILESTREAM Data with OpenSqlFilestream](access-filestream-data-with-opensqlfilestream.md) </span></span>  
 [<span data-ttu-id="ef03e-113">Criar aplicativos clientes para dados FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="ef03e-113">Create Client Applications for FILESTREAM Data</span></span>](create-client-applications-for-filestream-data.md)  
  
  
