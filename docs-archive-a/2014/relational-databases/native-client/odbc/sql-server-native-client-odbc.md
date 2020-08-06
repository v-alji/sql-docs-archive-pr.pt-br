---
title: SQL Server Native Client (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQLNCLI, ODBC
- SQL Server Native Client ODBC driver, about SQL Server Native Client ODBC driver
- data access [SQL Server Native Client], ODBC
- SQL Server Native Client ODBC driver
- ODBC
- SQL Server Native Client, ODBC
- ODBC, about SQL Server Native Client ODBC driver
ms.assetid: 811d5ba3-a2b8-48c0-adbc-8c91f041f458
author: rothja
ms.author: jroth
ms.openlocfilehash: 16c73966e318ed1e7d326fa77f56195ebbd830df
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681629"
---
# <a name="sql-server-native-client-odbc"></a><span data-ttu-id="f09ba-102">SQL Server Native Client (ODBC)</span><span class="sxs-lookup"><span data-stu-id="f09ba-102">SQL Server Native Client (ODBC)</span></span>
  <span data-ttu-id="f09ba-103">O ODBC é uma definição padrão de uma API (interface de programação de aplicativo) usada para acessar dados em bancos de dados relacionais ou ISAM (método de acesso sequencial indexado).</span><span class="sxs-lookup"><span data-stu-id="f09ba-103">ODBC is a standard definition of an application programming interface (API) used to access data in relational or indexed sequential access method (ISAM) databases.</span></span> <span data-ttu-id="f09ba-104">O [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] oferece suporte ao ODBC por meio do driver ODBC do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client, como uma das APIs nativas para escrever aplicativos C e C++ que se comunicam com o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f09ba-104">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] supports ODBC, via the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver, as one of the native APIs for writing C and C++ applications that communicate with [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="f09ba-105">Os programas do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] escritos usando o driver ODBC do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client se comunicam com o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] por meio de chamadas de função C.</span><span class="sxs-lookup"><span data-stu-id="f09ba-105">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] programs that are written using the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver communicate with [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] through C function calls.</span></span> <span data-ttu-id="f09ba-106">As versões específicas do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] das funções ODBC são implementadas no driver ODBC do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="f09ba-106">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]-specific versions of the ODBC functions are implemented in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver.</span></span> <span data-ttu-id="f09ba-107">O driver passa instruções SQL para o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] e retorna os resultados das instruções ao aplicativo.</span><span class="sxs-lookup"><span data-stu-id="f09ba-107">The driver passes SQL statements to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] and returns the results of the statements to the application.</span></span>  
  
 <span data-ttu-id="f09ba-108">O driver ODBC do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client está em conformidade com a especificação do Microsoft Win32 ODBC 3.51.</span><span class="sxs-lookup"><span data-stu-id="f09ba-108">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver complies with the Microsoft Win32 ODBC 3.51 specification.</span></span> <span data-ttu-id="f09ba-109">O driver dá suporte a aplicativos escritos usando versões anteriores do ODBC da forma definida na especificação do ODBC 3.51.</span><span class="sxs-lookup"><span data-stu-id="f09ba-109">The driver supports applications written using earlier versions of ODBC in the manner defined in the ODBC 3.51 specification.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f09ba-110">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="f09ba-110">In This Section</span></span>  
  
-   [<span data-ttu-id="f09ba-111">Nomes de fonte de dados e sistemas operacionais de 64 bits</span><span class="sxs-lookup"><span data-stu-id="f09ba-111">Data Source Names and 64-Bit Operating Systems</span></span>](data-source-names-and-64-bit-operating-systems.md)  
  
-   [<span data-ttu-id="f09ba-112">Criando um aplicativo de driver ODBC do SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="f09ba-112">Creating a SQL Server Native Client ODBC Driver Application</span></span>](creating-a-driver-application.md)  
  
-   [<span data-ttu-id="f09ba-113">Comunicando-se com SQL Server &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="f09ba-113">Communicating with SQL Server &#40;ODBC&#41;</span></span>](../../native-client-odbc-communication/communicating-with-sql-server-odbc.md)  
  
-   [<span data-ttu-id="f09ba-114">Executando consultas &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="f09ba-114">Executing Queries &#40;ODBC&#41;</span></span>](../../native-client-odbc-queries/executing-queries-odbc.md)  
  
-   [<span data-ttu-id="f09ba-115">Processando resultados &#40;&#41;ODBC</span><span class="sxs-lookup"><span data-stu-id="f09ba-115">Processing Results &#40;ODBC&#41;</span></span>](../../native-client-odbc-results/processing-results-odbc.md)  
  
-   [<span data-ttu-id="f09ba-116">Usando cursores &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="f09ba-116">Using Cursors &#40;ODBC&#41;</span></span>](../../native-client-odbc-cursors/using-cursors-odbc.md)  
  
-   [<span data-ttu-id="f09ba-117">Executando transações &#40;&#41;ODBC</span><span class="sxs-lookup"><span data-stu-id="f09ba-117">Performing Transactions &#40;ODBC&#41;</span></span>](../../../database-engine/dev-guide/performing-transactions-odbc.md)  
  
-   [<span data-ttu-id="f09ba-118">Tratando de erros e mensagens</span><span class="sxs-lookup"><span data-stu-id="f09ba-118">Handling Errors and Messages</span></span>](../../native-client-odbc-error-messages/handling-errors-and-messages.md)  
  
-   [<span data-ttu-id="f09ba-119">Executando procedimentos armazenados</span><span class="sxs-lookup"><span data-stu-id="f09ba-119">Running Stored Procedures</span></span>](../../native-client-odbc-stored-procedures/running-stored-procedures.md)  
  
-   [<span data-ttu-id="f09ba-120">Usando funções de catálogo</span><span class="sxs-lookup"><span data-stu-id="f09ba-120">Using Catalog Functions</span></span>](using-catalog-functions.md)  
  
-   [<span data-ttu-id="f09ba-121">Executando operações de cópia em massa &#40;&#41;ODBC</span><span class="sxs-lookup"><span data-stu-id="f09ba-121">Performing Bulk Copy Operations &#40;ODBC&#41;</span></span>](../../native-client-odbc-bulk-copy-operations/performing-bulk-copy-operations-odbc.md)  
  
-   [<span data-ttu-id="f09ba-122">Gerenciando colunas de texto e imagem</span><span class="sxs-lookup"><span data-stu-id="f09ba-122">Managing Text and Image Columns</span></span>](../../native-client-odbc-text-image-columns/managing-text-and-image-columns.md)  
  
-   [<span data-ttu-id="f09ba-123">Criando perfil de desempenho do driver ODBC</span><span class="sxs-lookup"><span data-stu-id="f09ba-123">Profiling ODBC Driver Performance</span></span>](profiling-odbc-driver-performance.md)  
  
-   [<span data-ttu-id="f09ba-124">Parâmetros com valor de tabela &#40;&#41;ODBC</span><span class="sxs-lookup"><span data-stu-id="f09ba-124">Table-Valued Parameters &#40;ODBC&#41;</span></span>](../../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md)  
  
-   [<span data-ttu-id="f09ba-125">Melhorias de data e hora &#40;&#41;ODBC</span><span class="sxs-lookup"><span data-stu-id="f09ba-125">Date and Time Improvements &#40;ODBC&#41;</span></span>](../../native-client-odbc-date-time/date-and-time-improvements-odbc.md)  
  
-   [<span data-ttu-id="f09ba-126">Tipos de CLR grandes definidos pelo usuário &#40;&#41;ODBC</span><span class="sxs-lookup"><span data-stu-id="f09ba-126">Large CLR User-Defined Types &#40;ODBC&#41;</span></span>](large-clr-user-defined-types-odbc.md)  
  
-   [<span data-ttu-id="f09ba-127">Suporte a FILESTREAM &#40;&#41;ODBC</span><span class="sxs-lookup"><span data-stu-id="f09ba-127">FILESTREAM Support &#40;ODBC&#41;</span></span>](filestream-support-odbc.md)  
  
-   [<span data-ttu-id="f09ba-128">SPNs &#40;Nomes da Entidade de Serviço&#41; em conexões de cliente &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="f09ba-128">Service Principal Names &#40;SPNs&#41; in Client Connections &#40;ODBC&#41;</span></span>](service-principal-names-spns-in-client-connections-odbc.md)  
  
-   [<span data-ttu-id="f09ba-129">Colunas esparsas dão suporte a&#41;&#40;ODBC</span><span class="sxs-lookup"><span data-stu-id="f09ba-129">Sparse Columns Support &#40;ODBC&#41;</span></span>](sparse-columns-support-odbc.md)  
  
-   [<span data-ttu-id="f09ba-130">Referência de&#41; &#40;ODBC do SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="f09ba-130">SQL Server Native Client &#40;ODBC&#41; Reference</span></span>](../../../database-engine/dev-guide/sql-server-native-client-odbc-reference.md)  
  
-   [<span data-ttu-id="f09ba-131">Tópicos de instruções sobre ODBC</span><span class="sxs-lookup"><span data-stu-id="f09ba-131">ODBC How-to Topics</span></span>](../../native-client-odbc-how-to/odbc-how-to-topics.md)  
  
## <a name="see-also"></a><span data-ttu-id="f09ba-132">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f09ba-132">See Also</span></span>  
 <span data-ttu-id="f09ba-133">[Programação de SQL Server Native Client](../sql-server-native-client-programming.md) </span><span class="sxs-lookup"><span data-stu-id="f09ba-133">[SQL Server Native Client Programming](../sql-server-native-client-programming.md) </span></span>  
 [<span data-ttu-id="f09ba-134">Instalando o SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="f09ba-134">Installing SQL Server Native Client</span></span>](../applications/installing-sql-server-native-client.md)  
  
  
