---
title: Criando um aplicativo de driver ODBC SQL Server Native Client | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- ODBC, architecture
- SQL Server Native Client ODBC driver, creating applications
- ODBC function calls
- ODBC, header files
- ODBC applications
- ODBC applications, creating
- SQL Server Native Client ODBC driver, extensions
- applications [SQL Server Native Client]
- SQL Server Native Client ODBC driver, ODBC architecture
- extensions [ODBC]
- ODBC, driver extensions
- function calls [ODBC]
ms.assetid: c83c36e2-734e-4960-bc7e-92235910bc6f
author: rothja
ms.author: jroth
ms.openlocfilehash: c8a1719f8b60885810d9b2f8a1f1023a7ffe6e47
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684161"
---
# <a name="creating-a-sql-server-native-client-odbc-driver-application"></a><span data-ttu-id="73477-102">Criando um aplicativo de driver ODBC do SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="73477-102">Creating a SQL Server Native Client ODBC Driver Application</span></span>
  <span data-ttu-id="73477-103">A arquitetura ODBC tem quatro componentes que executam as funções a seguir.</span><span class="sxs-lookup"><span data-stu-id="73477-103">ODBC architecture has four components that perform the following functions.</span></span>  
  
|<span data-ttu-id="73477-104">Componente</span><span class="sxs-lookup"><span data-stu-id="73477-104">Component</span></span>|<span data-ttu-id="73477-105">Função</span><span class="sxs-lookup"><span data-stu-id="73477-105">Function</span></span>|  
|---------------|--------------|  
|<span data-ttu-id="73477-106">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="73477-106">Application</span></span>|<span data-ttu-id="73477-107">Chama funções ODBC para se comunicar com uma fonte de dados ODBC, envia instruções SQL e processa os conjuntos de resultados.</span><span class="sxs-lookup"><span data-stu-id="73477-107">Calls ODBC functions to communicate with an ODBC data source, submits SQL statements, and processes result sets.</span></span>|  
|<span data-ttu-id="73477-108">Gerenciador de Driver</span><span class="sxs-lookup"><span data-stu-id="73477-108">Driver Manager</span></span>|<span data-ttu-id="73477-109">Gerencia a comunicação entre um aplicativo e todos os drivers ODBC usados por ele.</span><span class="sxs-lookup"><span data-stu-id="73477-109">Manages communication between an application and all ODBC drivers used by the application.</span></span>|  
|<span data-ttu-id="73477-110">Driver</span><span class="sxs-lookup"><span data-stu-id="73477-110">Driver</span></span>|<span data-ttu-id="73477-111">Processa todas as chamadas de funções ODBC do aplicativo, conecta-se a uma fonte de dados, passa instruções SQL do aplicativo para a fonte de dados e retorna os resultados para o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="73477-111">Processes all ODBC function calls from the application, connects to a data source, passes SQL statements from the application to the data source, and returns results to the application.</span></span> <span data-ttu-id="73477-112">Se necessário, o driver converte SQL ODBC do aplicativo em SQL nativo usado pela fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="73477-112">If necessary, the driver translates ODBC SQL from the application to native SQL used by the data source.</span></span>|  
|<span data-ttu-id="73477-113">Fonte de dados</span><span class="sxs-lookup"><span data-stu-id="73477-113">Data source</span></span>|<span data-ttu-id="73477-114">Contém todas as informações necessárias a um driver para acessar uma instância específica de dados em um DBMS.</span><span class="sxs-lookup"><span data-stu-id="73477-114">Contains all information a driver needs to access a specific instance of data in a DBMS.</span></span>|  
  
 <span data-ttu-id="73477-115">Um aplicativo que usa o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] driver ODBC do Native Client para se comunicar com uma instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] executa as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="73477-115">An application that uses the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver to communicate with an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] performs the following tasks:</span></span>  
  
-   <span data-ttu-id="73477-116">Conecta-se com uma fonte de dados</span><span class="sxs-lookup"><span data-stu-id="73477-116">Connects with a data source</span></span>  
  
-   <span data-ttu-id="73477-117">Envia instruções SQL para a fonte de dados</span><span class="sxs-lookup"><span data-stu-id="73477-117">Sends SQL statements to the data source</span></span>  
  
-   <span data-ttu-id="73477-118">Processa os resultados das instruções da fonte de dados</span><span class="sxs-lookup"><span data-stu-id="73477-118">Processes the results of statements from the data source</span></span>  
  
-   <span data-ttu-id="73477-119">Processa erros e mensagens</span><span class="sxs-lookup"><span data-stu-id="73477-119">Processes errors and messages</span></span>  
  
-   <span data-ttu-id="73477-120">Finaliza a conexão com a fonte de dados</span><span class="sxs-lookup"><span data-stu-id="73477-120">Terminates the connection to the data source</span></span>  
  
 <span data-ttu-id="73477-121">Um aplicativo mais complexo escrito para o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] driver ODBC do Native Client também pode executar as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="73477-121">A more complex application written for the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver might also perform the following tasks:</span></span>  
  
-   <span data-ttu-id="73477-122">Usar cursores para controlar o local em um conjunto de resultados</span><span class="sxs-lookup"><span data-stu-id="73477-122">Use cursors to control location in a result set</span></span>  
  
-   <span data-ttu-id="73477-123">Solicitar operações de confirmação ou reversão para o controle de transações</span><span class="sxs-lookup"><span data-stu-id="73477-123">Request commit or rollback operations for transaction control</span></span>  
  
-   <span data-ttu-id="73477-124">Executar transações distribuídas que envolvem dois ou mais servidores</span><span class="sxs-lookup"><span data-stu-id="73477-124">Perform distributed transactions involving two or more servers</span></span>  
  
-   <span data-ttu-id="73477-125">Executar procedimentos armazenados no servidor remoto</span><span class="sxs-lookup"><span data-stu-id="73477-125">Run stored procedures on the remote server</span></span>  
  
-   <span data-ttu-id="73477-126">Chamar funções de catálogo para perguntar sobre os atributos de um conjunto de resultados</span><span class="sxs-lookup"><span data-stu-id="73477-126">Call catalog functions to inquire about the attributes of a result set</span></span>  
  
-   <span data-ttu-id="73477-127">Executar operações de cópia em massa</span><span class="sxs-lookup"><span data-stu-id="73477-127">Perform bulk copy operations</span></span>  
  
-   <span data-ttu-id="73477-128">Gerenciar operações de dados grandes (**varchar (max)**, **nvarchar (max)** e **varbinary (max)** )</span><span class="sxs-lookup"><span data-stu-id="73477-128">Manage large data (**varchar(max)**, **nvarchar(max)**, and **varbinary(max)** columns) operations</span></span>  
  
-   <span data-ttu-id="73477-129">Usar lógica de reconexão para facilitar o failover quando o espelhamento de banco de dados é configurado</span><span class="sxs-lookup"><span data-stu-id="73477-129">Use reconnection logic to facilitate failover when database mirroring is configured</span></span>  
  
-   <span data-ttu-id="73477-130">Registrar dados de desempenho e consultas de execução demorada</span><span class="sxs-lookup"><span data-stu-id="73477-130">Log performance data and long-running queries</span></span>  
  
 <span data-ttu-id="73477-131">Para fazer chamadas de função ODBC, um aplicativo C ou C++ deve incluir os arquivos de cabeçalhos sql.h, sqlext.h e sqltypes.h.</span><span class="sxs-lookup"><span data-stu-id="73477-131">To make ODBC function calls, a C or C++ application must include the sql.h, sqlext.h, and sqltypes.h header files.</span></span> <span data-ttu-id="73477-132">Para fazer chamadas às funções de API do instalador ODBC, um aplicativo deve incluir o arquivo de cabeçalho odbcinst.h.</span><span class="sxs-lookup"><span data-stu-id="73477-132">To make calls to the ODBC installer API functions, an application must include the odbcinst.h header file.</span></span> <span data-ttu-id="73477-133">Um aplicativo ODBC Unicode deve incluir o arquivo de cabeçalho sqlucode.h.</span><span class="sxs-lookup"><span data-stu-id="73477-133">A Unicode ODBC application must include the sqlucode.h header file.</span></span> <span data-ttu-id="73477-134">Os aplicativos ODBC devem ser vinculados ao arquivo odbc32.lib.</span><span class="sxs-lookup"><span data-stu-id="73477-134">ODBC applications must be linked with the odbc32.lib file.</span></span> <span data-ttu-id="73477-135">Os aplicativos ODBC que chamam as funções de API do instalador ODBC devem ser vinculados ao arquivo odbccp32.lib.</span><span class="sxs-lookup"><span data-stu-id="73477-135">ODBC applications that call the ODBC installer API functions must be linked with the odbccp32.lib file.</span></span> <span data-ttu-id="73477-136">Esses arquivos são incluídos no SDK da Plataforma Windows.</span><span class="sxs-lookup"><span data-stu-id="73477-136">These files are included in the Windows Platform SDK.</span></span>  
  
 <span data-ttu-id="73477-137">Muitos drivers ODBC, incluindo o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] driver ODBC do Native Client, oferecem extensões ODBC específicas do driver.</span><span class="sxs-lookup"><span data-stu-id="73477-137">Many ODBC drivers, including the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver, offer driver-specific ODBC extensions.</span></span> <span data-ttu-id="73477-138">Para aproveitar as [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] extensões específicas do driver ODBC do Native Client, um aplicativo deve incluir o arquivo de cabeçalho sqlncli. h.</span><span class="sxs-lookup"><span data-stu-id="73477-138">To take advantage of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver-specific extensions, an application should include the sqlncli.h header file.</span></span> <span data-ttu-id="73477-139">Esse arquivo de cabeçalho contém:</span><span class="sxs-lookup"><span data-stu-id="73477-139">This header file contains:</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]<span data-ttu-id="73477-140">Atributos de conexão específicos do driver ODBC do Native Client.</span><span class="sxs-lookup"><span data-stu-id="73477-140">Native Client ODBC driver-specific connection attributes.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]<span data-ttu-id="73477-141">Atributos de instrução específicos do driver ODBC do Native Client.</span><span class="sxs-lookup"><span data-stu-id="73477-141">Native Client ODBC driver-specific statement attributes.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]<span data-ttu-id="73477-142">Atributos de coluna específicos do driver ODBC do Native Client.</span><span class="sxs-lookup"><span data-stu-id="73477-142">Native Client ODBC driver-specific column attributes.</span></span>  
  
-   <span data-ttu-id="73477-143">Tipos de dados específicos do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="73477-143">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]-specific data types.</span></span>  
  
-   <span data-ttu-id="73477-144">Tipos de dados definidos pelo usuário específicos do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="73477-144">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]-specific user-defined data types.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]<span data-ttu-id="73477-145">Tipos específicos de [SQLGetInfo](../../native-client-odbc-api/sqlgetinfo.md) do driver ODBC do Native Client.</span><span class="sxs-lookup"><span data-stu-id="73477-145">Native Client ODBC driver-specific [SQLGetInfo](../../native-client-odbc-api/sqlgetinfo.md) types.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]<span data-ttu-id="73477-146">Campos de diagnóstico de driver ODBC do Native Client.</span><span class="sxs-lookup"><span data-stu-id="73477-146">Native Client ODBC driver diagnostics fields.</span></span>  
  
-   <span data-ttu-id="73477-147">Códigos de função dinâmica de diagnóstico específicos do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="73477-147">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]-specific diagnostic dynamic function codes.</span></span>  
  
-   <span data-ttu-id="73477-148">Definições de tipos C/C++ para tipos de dados C nativos específicos do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (retornados quando as colunas são associadas ao tipo de dados C, SQL_C_BINARY).</span><span class="sxs-lookup"><span data-stu-id="73477-148">C/C++ type definitions for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]-specific native C data types (returned when columns bound to C data type SQL_C_BINARY).</span></span>  
  
-   <span data-ttu-id="73477-149">Definição de tipo para a estrutura de dados de SQLPERF.</span><span class="sxs-lookup"><span data-stu-id="73477-149">Type definition for the SQLPERF data structure.</span></span>  
  
-   <span data-ttu-id="73477-150">Macros e protótipos de cópia em massa para oferecer suporte ao uso de APIs de cópia em massa através de uma conexão ODBC.</span><span class="sxs-lookup"><span data-stu-id="73477-150">Bulk copy macros and prototypes to support bulk copy API usage through an ODBC connection.</span></span>  
  
-   <span data-ttu-id="73477-151">Chame as funções de API de metadados de consulta distribuída para listas de servidores vinculados e seus catálogos.</span><span class="sxs-lookup"><span data-stu-id="73477-151">Call the distributed query metadata API functions for lists of linked servers and their catalogs.</span></span>  
  
 <span data-ttu-id="73477-152">Qualquer aplicativo ODBC C ou C++ que usa o recurso de cópia em massa do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] driver ODBC do Native Client deve ser vinculado ao arquivo sqlncli11. lib.</span><span class="sxs-lookup"><span data-stu-id="73477-152">Any C or C++ ODBC application that uses the bulk copy feature of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver must be linked with the sqlncli11.lib file.</span></span> <span data-ttu-id="73477-153">Aplicativos que chamam as funções de API de metadados de consulta distribuída também devem ser vinculados ao sqlncli11.lib.</span><span class="sxs-lookup"><span data-stu-id="73477-153">Applications calling the distributed query metadata API functions must also be linked with sqlncli11.lib.</span></span> <span data-ttu-id="73477-154">Os arquivos sqlncli. h e sqlncli11. lib são distribuídos como parte das [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Ferramentas do desenvolvedor.</span><span class="sxs-lookup"><span data-stu-id="73477-154">The sqlncli.h and sqlncli11.lib files are distributed as part of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] developer's tools.</span></span> <span data-ttu-id="73477-155">Os diretórios Include e Lib do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] devem estar nos caminhos INCLUDE e LIB do compilador conforme o exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="73477-155">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Include and Lib directories should be in the compiler's INCLUDE and LIB paths as in the following:</span></span>  
  
```  
LIB=c:\Program Files\Microsoft Data Access SDK 2.8\Libs\x86\lib;C:\Program Files\Microsoft SQL Server\100\Tools\SDK\Lib;  
INCLUDE=c:\Program Files\Microsoft Data Access SDK 2.8\inc;C:\Program Files\Microsoft SQL Server\100\Tools\SDK\Include;  
```  
  
 <span data-ttu-id="73477-156">Uma decisão de design que deve ser tomada no início do processo de criação de um aplicativo é se ele precisa ter várias chamadas ODBC pendentes ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="73477-156">One design decision made early in the process of building an application is whether the application needs to have multiple ODBC calls outstanding at the same time.</span></span> <span data-ttu-id="73477-157">Há dois métodos de suporte a várias chamadas ODBC simultâneas, que são descritos nos próximos tópicos desta seção.</span><span class="sxs-lookup"><span data-stu-id="73477-157">There are two methods for supporting multiple concurrent ODBC calls, which are described in the remaining topics in this section.</span></span> <span data-ttu-id="73477-158">Para obter mais informações, consulte a [referência do programador de ODBC](https://go.microsoft.com/fwlink/?LinkId=45250).</span><span class="sxs-lookup"><span data-stu-id="73477-158">For more information, see the [ODBC Programmer's Reference](https://go.microsoft.com/fwlink/?LinkId=45250).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="73477-159">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="73477-159">In This Section</span></span>  
  
-   [<span data-ttu-id="73477-160">Modo assíncrono e SQLCancel</span><span class="sxs-lookup"><span data-stu-id="73477-160">Asynchronous Mode and SQLCancel</span></span>](../../native-client-odbc-api/sqlcancel.md)  
  
-   [<span data-ttu-id="73477-161">Aplicativos multi-threaded</span><span class="sxs-lookup"><span data-stu-id="73477-161">Multithreaded Applications</span></span>](creating-a-driver-application-multithreaded-applications.md)  
  
## <a name="see-also"></a><span data-ttu-id="73477-162">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="73477-162">See Also</span></span>  
 [<span data-ttu-id="73477-163">SQL Server Native Client &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="73477-163">SQL Server Native Client &#40;ODBC&#41;</span></span>](sql-server-native-client-odbc.md)  
  
  
