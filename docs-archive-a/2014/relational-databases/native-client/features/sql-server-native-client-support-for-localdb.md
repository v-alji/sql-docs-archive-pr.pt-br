---
title: Suporte de SQL Server Native Client para LocalDB | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
ms.assetid: 127569d1-a9f7-49bf-a561-c084986a8871
author: rothja
ms.author: jroth
ms.openlocfilehash: b08ea46e8db1b665280116a439b95748f69d03ef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571364"
---
# <a name="sql-server-native-client-support-for-localdb"></a><span data-ttu-id="15912-102">Suporte do SQL Server Native Client para LocalDB</span><span class="sxs-lookup"><span data-stu-id="15912-102">SQL Server Native Client Support for LocalDB</span></span>
  <span data-ttu-id="15912-103">A partir do [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)], uma versão leve do SQL Server, denominada LocalDB, será disponibilizada.</span><span class="sxs-lookup"><span data-stu-id="15912-103">Beginning in [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)], a lightweight version of SQL Server, called LocalDB, will be available.</span></span> <span data-ttu-id="15912-104">Este tópico descreve como conectar-se a um banco de dados em uma instância do LocalDB.</span><span class="sxs-lookup"><span data-stu-id="15912-104">This topic discusses how to connect to a database in a LocalDB instance.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="15912-105">Comentários</span><span class="sxs-lookup"><span data-stu-id="15912-105">Remarks</span></span>  
 <span data-ttu-id="15912-106">Para obter mais informações sobre o LocalDB, inclusive como instalá-lo e configurar sua instância do LocalDB, consulte:</span><span class="sxs-lookup"><span data-stu-id="15912-106">For more information about LocalDB, including how to install LocalDB and configure your LocalDB instance, see:</span></span>  
  
-   [<span data-ttu-id="15912-107">Referência de LocalDB do SQL Server Express</span><span class="sxs-lookup"><span data-stu-id="15912-107">SQL Server Express LocalDB Reference</span></span>](../../sql-server-express-localdb-reference.md)  
  
-   [<span data-ttu-id="15912-108">SQL Server 2014 Express LocalDB</span><span class="sxs-lookup"><span data-stu-id="15912-108">SQL Server 2014 Express LocalDB</span></span>](../../../database-engine/configure-windows/sql-server-2016-express-localdb.md)  
  
 <span data-ttu-id="15912-109">Para resumir, o LocalDB permite:</span><span class="sxs-lookup"><span data-stu-id="15912-109">To summarize, LocalDB allows you to:</span></span>  
  
-   <span data-ttu-id="15912-110">Usar `sqllocaldb.exe i` para descobrir o nome da instância padrão.</span><span class="sxs-lookup"><span data-stu-id="15912-110">Use `sqllocaldb.exe i` to discover the name of the default instance.</span></span>  
  
-   <span data-ttu-id="15912-111">Usar a palavra-chave da cadeia de conexão `AttachDBFilename` para especificar o arquivo de banco de dados que o servidor deve anexar.</span><span class="sxs-lookup"><span data-stu-id="15912-111">Use the `AttachDBFilename` connection string keyword to specify which database file the server should attach.</span></span> <span data-ttu-id="15912-112">Ao usar `AttachDBFilename` , se você não especificar o nome do banco de dados com a palavra-chave String de conexão de **banco** de dados, o banco de dados será removido da instância de LocalDB quando o aplicativo for fechado.</span><span class="sxs-lookup"><span data-stu-id="15912-112">When using `AttachDBFilename`, if you do not specify the name of the database with the **Database** connection string keyword, the database will be removed from the LocalDB instance when the application closes.</span></span>  
  
-   <span data-ttu-id="15912-113">Especifique uma instância do LocalDB em sua cadeia de conexão:</span><span class="sxs-lookup"><span data-stu-id="15912-113">Specify a LocalDB instance in your connection string:</span></span>  
  
```  
SERVER=(localdb)\v11.0  
```  
  
 <span data-ttu-id="15912-114">Se necessário, você pode criar uma instância do LocalDB com sqllocaldb.exe.</span><span class="sxs-lookup"><span data-stu-id="15912-114">If necessary, you can create a LocalDB instance with sqllocaldb.exe.</span></span> <span data-ttu-id="15912-115">Você também pode usar sqlcmd.exe para adicionar e modificar bancos de dados em uma instância do LocalDB.</span><span class="sxs-lookup"><span data-stu-id="15912-115">You can also use sqlcmd.exe to add and modify databases in a LocalDB instance.</span></span> <span data-ttu-id="15912-116">Por exemplo, `sqlcmd -S (localdb)\v11.0`.</span><span class="sxs-lookup"><span data-stu-id="15912-116">For example, `sqlcmd -S (localdb)\v11.0`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15912-117">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="15912-117">See Also</span></span>  
 [<span data-ttu-id="15912-118">Recursos do SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="15912-118">SQL Server Native Client Features</span></span>](sql-server-native-client-features.md)  
  
  
