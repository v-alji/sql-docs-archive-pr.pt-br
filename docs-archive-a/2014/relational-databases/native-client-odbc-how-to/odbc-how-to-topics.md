---
title: Tópicos de instruções sobre ODBC | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
ms.assetid: 151f2066-1c37-410f-88f4-b27dfca66031
author: rothja
ms.author: jroth
ms.openlocfilehash: cfeb120b9fa1fedb5358b5e12dabed7835f9a6b2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684189"
---
# <a name="odbc-how-to-topics"></a><span data-ttu-id="79603-102">Tópicos de instruções sobre ODBC</span><span class="sxs-lookup"><span data-stu-id="79603-102">ODBC How-to Topics</span></span>
  <span data-ttu-id="79603-103">Para usar o driver ODBC do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , você deve ser capaz de criar fontes de dados ODBC e garantir que o servidor tenha a versão correta dos procedimentos armazenados do catálogo.</span><span class="sxs-lookup"><span data-stu-id="79603-103">To use the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ODBC driver, you must be able to create ODBC data sources and ensure that the server has the correct version of the catalog stored procedures.</span></span> <span data-ttu-id="79603-104">Para codificar um aplicativo do SQL Server, você deve saber como alocar identificadores ODBC, definir atributos, se conectar a uma instância do SQL Server, executar consultas e processar resultados.</span><span class="sxs-lookup"><span data-stu-id="79603-104">To code an ODBC application that uses SQL Server, you must know how to allocate ODBC handles, set attributes, connect to an instance of SQL Server, execute queries, and process results.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="79603-105">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="79603-105">In This Section</span></span>  
  
-   [<span data-ttu-id="79603-106">Tópicos de instrução sobre a configuração do driver ODBC do SQL Server</span><span class="sxs-lookup"><span data-stu-id="79603-106">Configuring the SQL Server ODBC Driver How-to Topics</span></span>](../../database-engine/dev-guide/configuring-the-sql-server-odbc-driver-how-to-topics.md)  
  
-   [<span data-ttu-id="79603-107">Alocar identificadores e conectar-se ao SQL Server &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="79603-107">Allocate Handles and Connect to SQL Server &#40;ODBC&#41;</span></span>](allocate-handles-and-connect-to-sql-server-odbc.md)  
  
-   [<span data-ttu-id="79603-108">Tópicos de instruções sobre como executar consultas &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="79603-108">Executing Queries How-to Topics &#40;ODBC&#41;</span></span>](execute-queries/executing-queries-how-to-topics-odbc.md)  
  
-   [<span data-ttu-id="79603-109">Tópicos de instruções sobre o processamento de resultados &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="79603-109">Processing Results How-to Topics &#40;ODBC&#41;</span></span>](../../database-engine/dev-guide/processing-results-how-to-topics-odbc.md)  
  
-   [<span data-ttu-id="79603-110">Tópicos de instruções sobre o uso de cursores &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="79603-110">Using Cursors How-to Topics &#40;ODBC&#41;</span></span>](cursors/using-cursors-how-to-topics-odbc.md)  
  
-   [<span data-ttu-id="79603-111">Usar o Microsoft Coordenador de Transações Distribuídas &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="79603-111">Use Microsoft Distributed Transaction Coordinator &#40;ODBC&#41;</span></span>](use-microsoft-distributed-transaction-coordinator-odbc.md)  
  
-   [<span data-ttu-id="79603-112">Tópicos de instruções sobre como executar procedimentos armazenados &#40;&#41;ODBC</span><span class="sxs-lookup"><span data-stu-id="79603-112">Running Stored Procedures How-to Topics &#40;ODBC&#41;</span></span>](../../database-engine/dev-guide/running-stored-procedures-how-to-topics-odbc.md)  
  
-   [<span data-ttu-id="79603-113">Tópicos de instruções sobre como gerenciar colunas de texto e imagem &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="79603-113">Managing text and image Columns How-to Topics &#40;ODBC&#41;</span></span>](../../database-engine/dev-guide/managing-text-and-image-columns-how-to-topics-odbc.md)  
  
-   [<span data-ttu-id="79603-114">Tópicos de instruções de desempenho do driver ODBC de criação de perfil &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="79603-114">Profiling ODBC Driver Performance How-to Topics &#40;ODBC&#41;</span></span>](profiling-odbc-driver-performance-odbc.md)  
  
-   [<span data-ttu-id="79603-115">Processar erros de ODBC &#40;&#41;ODBC</span><span class="sxs-lookup"><span data-stu-id="79603-115">Process ODBC Errors &#40;ODBC&#41;</span></span>](process-odbc-errors-odbc.md)  
  
-   [<span data-ttu-id="79603-116">Tópicos de instruções sobre cópia em massa com o SQL Server ODBC Driver &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="79603-116">Bulk Copying with the SQL Server ODBC Driver How-to Topics &#40;ODBC&#41;</span></span>](bulk-copy/bulk-copying-with-the-sql-server-odbc-driver-how-to-topics-odbc.md)  
  
## <a name="see-also"></a><span data-ttu-id="79603-117">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="79603-117">See Also</span></span>  
 [<span data-ttu-id="79603-118">SQL Server Native Client &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="79603-118">SQL Server Native Client &#40;ODBC&#41;</span></span>](../native-client/odbc/sql-server-native-client-odbc.md)  
  
  
