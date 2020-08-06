---
title: Comunicando-se com SQL Server (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client ODBC driver, communicating with SQL Server
- ODBC applications, communicating with SQL Server
- ODBC, communicating with SQL Server
ms.assetid: cca3dcf0-2a7e-465a-84de-7ce055360eb6
author: rothja
ms.author: jroth
ms.openlocfilehash: c41ac2dcce9c5bdbdd351148d16bcaa8f067d22f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684210"
---
# <a name="communicating-with-sql-server-odbc"></a><span data-ttu-id="a00d5-102">Comunicando-se com o SQL Server (ODBC)</span><span class="sxs-lookup"><span data-stu-id="a00d5-102">Communicating with SQL Server (ODBC)</span></span>
  <span data-ttu-id="a00d5-103">Para que um aplicativo ODBC se comunique com uma instância do [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , ele deve alocar identificadores de ambiente e conexão e conectar-se à fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="a00d5-103">For an ODBC application to communicate with an instance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], it must allocate environment and connection handles and connect to the data source.</span></span> <span data-ttu-id="a00d5-104">Depois que uma conexão é estabelecida, o aplicativo pode enviar consultas ao servidor e processar quaisquer conjuntos de resultados.</span><span class="sxs-lookup"><span data-stu-id="a00d5-104">After a connection is established, the application can send queries to the server and process any result sets.</span></span> <span data-ttu-id="a00d5-105">Quando o aplicativo conclui o uso da fonte de dados, ele se desconecta da fonte de dados e libera o identificador de conexão.</span><span class="sxs-lookup"><span data-stu-id="a00d5-105">When the application has finished using the data source, it disconnects from the data source and frees the connection handle.</span></span> <span data-ttu-id="a00d5-106">Depois de liberar todos os identificadores de conexão, o aplicativo libera o identificador de ambiente.</span><span class="sxs-lookup"><span data-stu-id="a00d5-106">When the application has freed all its connection handles, it frees the environment handle.</span></span>  
  
 <span data-ttu-id="a00d5-107">Um aplicativo pode se conectar a qualquer número de fontes de dados.</span><span class="sxs-lookup"><span data-stu-id="a00d5-107">An application can connect to any number of data sources.</span></span> <span data-ttu-id="a00d5-108">O aplicativo pode usar uma combinação de drivers e fontes de dados, o mesmo driver e uma combinação de fontes de dados ou inclusive o mesmo driver e várias conexões com a mesma fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="a00d5-108">The application can use a combination of drivers and data sources, the same driver and a combination of data sources, or even the same driver and multiple connections to the same data source.</span></span>  
  
 <span data-ttu-id="a00d5-109">Você pode baixar [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] exemplos de ODBC de cliente nativo na página de [Downloads de SQL Server](https://go.microsoft.com/fwlink/?LinkId=62796) no msdn.</span><span class="sxs-lookup"><span data-stu-id="a00d5-109">You can download [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC samples from the [SQL Server Downloads](https://go.microsoft.com/fwlink/?LinkId=62796) page on MSDN.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a00d5-110">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="a00d5-110">In This Section</span></span>  
  
-   [<span data-ttu-id="a00d5-111">Alocando um identificador de ambiente</span><span class="sxs-lookup"><span data-stu-id="a00d5-111">Allocating an Environment Handle</span></span>](allocating-an-environment-handle.md)  
  
-   [<span data-ttu-id="a00d5-112">Alocando um identificador de conexão</span><span class="sxs-lookup"><span data-stu-id="a00d5-112">Allocating a Connection Handle</span></span>](allocating-a-connection-handle.md)  
  
-   [<span data-ttu-id="a00d5-113">fontes de dados ODBC do SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="a00d5-113">SQL Server Native Client ODBC Data Sources</span></span>](../../integration-services/connection-manager/data-sources.md)  
  
-   [<span data-ttu-id="a00d5-114">Conectando-se a uma fonte de dados &#40;&#41;ODBC</span><span class="sxs-lookup"><span data-stu-id="a00d5-114">Connecting to a Data Source &#40;ODBC&#41;</span></span>](connecting-to-a-data-source-odbc.md)  
  
-   [<span data-ttu-id="a00d5-115">Desconectando uma fonte de dados</span><span class="sxs-lookup"><span data-stu-id="a00d5-115">Disconnecting from a Data Source</span></span>](disconnecting-from-a-data-source.md)  
  
## <a name="see-also"></a><span data-ttu-id="a00d5-116">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a00d5-116">See Also</span></span>  
 <span data-ttu-id="a00d5-117">[SQL Server Native Client &#40;ODBC&#41;](../native-client/odbc/sql-server-native-client-odbc.md) </span><span class="sxs-lookup"><span data-stu-id="a00d5-117">[SQL Server Native Client &#40;ODBC&#41;](../native-client/odbc/sql-server-native-client-odbc.md) </span></span>  
 [<span data-ttu-id="a00d5-118">SQLSetEnvAttr</span><span class="sxs-lookup"><span data-stu-id="a00d5-118">SQLSetEnvAttr</span></span>](../native-client-odbc-api/sqlsetenvattr.md)  
  
  
