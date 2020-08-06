---
title: Recursos de SQL Server Native Client | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- MDAC [SQL Server]
- SQL Server Native Client ODBC driver, about SQL Server Native Client ODBC driver
- SQLNCLI, about SQL Server Native Client
- data access [SQL Server Native Client], features
ms.assetid: 7bb32865-5afb-41ab-98b4-3fa545ee8953
author: rothja
ms.author: jroth
ms.openlocfilehash: bb4ba07f84848f754519f8f4fa1c3e56485e85a0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571368"
---
# <a name="sql-server-native-client-features"></a><span data-ttu-id="79f39-102">Recursos do SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="79f39-102">SQL Server Native Client Features</span></span>
  <span data-ttu-id="79f39-103">Além de expor os recursos do WDAC (Windows (anteriormente Microsoft) Data Access Components), o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client também implementa vários outros recursos para expor a funcionalidade do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="79f39-103">In addition to exposing features of the Windows (formerly Microsoft) Data Access Components (WDAC), [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client also implements many other features to expose [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] functionality.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="79f39-104">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="79f39-104">In This Section</span></span>  
 [<span data-ttu-id="79f39-105">Alteração de comportamento do driver ODBC ao lidar com conversões de caracteres</span><span class="sxs-lookup"><span data-stu-id="79f39-105">ODBC Driver Behavior Change When Handling Character Conversions</span></span>](odbc-driver-behavior-change-when-handling-character-conversions.md)  
 <span data-ttu-id="79f39-106">Discute uma alteração de comportamento a partir do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 2012 Native Client.</span><span class="sxs-lookup"><span data-stu-id="79f39-106">Discusses a change of behavior beginning in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 2012 Native Client.</span></span>  
  
 [<span data-ttu-id="79f39-107">Usando o espelhamento de banco de dados</span><span class="sxs-lookup"><span data-stu-id="79f39-107">Using Database Mirroring</span></span>](using-database-mirroring.md)  
 <span data-ttu-id="79f39-108">Discute como [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] o Native Client dá suporte ao uso de bancos de dados espelhados, que é a capacidade de manter uma cópia, ou espelho, de um [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] banco de dados em um servidor em espera.</span><span class="sxs-lookup"><span data-stu-id="79f39-108">Discusses how [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client supports the use of mirrored databases, which is the ability to keep a copy, or mirror, of a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] database on a standby server.</span></span>  
  
 [<span data-ttu-id="79f39-109">Executando operações assíncronas</span><span class="sxs-lookup"><span data-stu-id="79f39-109">Performing Asynchronous Operations</span></span>](performing-asynchronous-operations.md)  
 <span data-ttu-id="79f39-110">Aborda como o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client oferece suporte a operações assíncronas, o que possibilita o retorno imediato sem bloqueio no thread que fez a chamada.</span><span class="sxs-lookup"><span data-stu-id="79f39-110">Discusses how [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client supports asynchronous operations, which is the ability to return immediately without blocking on the calling thread.</span></span>  
  
 [<span data-ttu-id="79f39-111">Usando MARS &#40;Multiple Active Result Sets&#41;</span><span class="sxs-lookup"><span data-stu-id="79f39-111">Using Multiple Active Result Sets &#40;MARS&#41;</span></span>](using-multiple-active-result-sets-mars.md)  
 <span data-ttu-id="79f39-112">Aborda como o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client oferece suporte a MARS (vários conjuntos de resultados ativos).</span><span class="sxs-lookup"><span data-stu-id="79f39-112">Discusses how [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client supports multiple active result sets (MARS).</span></span> <span data-ttu-id="79f39-113">Os MARS permitem executar e receber vários conjuntos de resultados por meio de uma única conexão de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="79f39-113">MARS enables you to execute and receive multiple result sets using a single database connection</span></span>  
  
 [<span data-ttu-id="79f39-114">Usando tipos de dados XML</span><span class="sxs-lookup"><span data-stu-id="79f39-114">Using XML Data Types</span></span>](using-xml-data-types.md)  
 <span data-ttu-id="79f39-115">Aborda como o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client oferece suporte ao tipo de dados XML, um tipo de dados baseado em XML que pode ser usado como um tipo de coluna, um tipo de variável, um tipo de parâmetro ou um tipo de retorno de função.</span><span class="sxs-lookup"><span data-stu-id="79f39-115">Discusses how [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client supports the XML data type, which is a XML-based data type that can be used as a column type, variable type, parameter type, or function return type.</span></span>  
  
 [<span data-ttu-id="79f39-116">Usando tipos definidos pelo usuário</span><span class="sxs-lookup"><span data-stu-id="79f39-116">Using User-Defined Types</span></span>](using-user-defined-types.md)  
 <span data-ttu-id="79f39-117">Discute como [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] o Native Client dá suporte a UDT (tipos definidos pelo usuário), que estende o sistema de tipos SQL, permitindo que você armazene objetos e estruturas de dados personalizadas em um banco de dado [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="79f39-117">Discusses how [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client supports User-Defined Types (UDT), which extends the SQL type system by allowing you to store objects and custom data structures in a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] database.</span></span>  
  
 [<span data-ttu-id="79f39-118">Usando tipos de valor grande</span><span class="sxs-lookup"><span data-stu-id="79f39-118">Using Large Value Types</span></span>](using-large-value-types.md)  
 <span data-ttu-id="79f39-119">Aborda como o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client oferece suporte a tipos de dados de valor grande, que são tipos de dados LOB (objeto binário grande).</span><span class="sxs-lookup"><span data-stu-id="79f39-119">Discusses how [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client supports large value data types, which are large object data types (LOB).</span></span>  
  
 [<span data-ttu-id="79f39-120">Alterando senhas programaticamente</span><span class="sxs-lookup"><span data-stu-id="79f39-120">Changing Passwords Programmatically</span></span>](changing-passwords-programmatically.md)  
 <span data-ttu-id="79f39-121">Aborda como o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client oferece suporte ao tratamento de senhas expiradas de forma que as senhas agora possam ser alteradas no cliente sem o envolvimento do administrador.</span><span class="sxs-lookup"><span data-stu-id="79f39-121">Discusses how [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client supports the handling of expired passwords so that passwords can now be changed on the client without administrator involvement.</span></span>  
  
 [<span data-ttu-id="79f39-122">Trabalhando com isolamento de instantâneo</span><span class="sxs-lookup"><span data-stu-id="79f39-122">Working with Snapshot Isolation</span></span>](working-with-snapshot-isolation.md)  
 <span data-ttu-id="79f39-123">Aborda como o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client oferece suporte ao aprimoramento do controle de versão de linha que melhora o desempenho do banco de dados ao evitar cenários de bloqueio de leitor/gravador.</span><span class="sxs-lookup"><span data-stu-id="79f39-123">Discusses how [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client supports the enhancement to row versioning that improves database performance by avoiding reader-writer blocking scenarios.</span></span>  
  
 [<span data-ttu-id="79f39-124">Trabalhando com notificações de consulta</span><span class="sxs-lookup"><span data-stu-id="79f39-124">Working with Query Notifications</span></span>](working-with-query-notifications.md)  
 <span data-ttu-id="79f39-125">Aborda como o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client oferece suporte à notificação do consumidor na modificação do conjunto de linhas.</span><span class="sxs-lookup"><span data-stu-id="79f39-125">Discusses how [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client supports consumer notification on rowset modification.</span></span>  
  
 [<span data-ttu-id="79f39-126">Executando operações de cópia em massa</span><span class="sxs-lookup"><span data-stu-id="79f39-126">Performing Bulk Copy Operations</span></span>](performing-bulk-copy-operations.md)  
 <span data-ttu-id="79f39-127">Discute como [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] o Native Client dá suporte a operações de cópia em massa que permitem a transferência de grandes quantidades de dados para dentro ou para fora de uma [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] tabela ou exibição.</span><span class="sxs-lookup"><span data-stu-id="79f39-127">Discusses how [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client supports bulk copy operations that allow the transfer of large amounts of data into or out of a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] table or view.</span></span>  
  
 [<span data-ttu-id="79f39-128">Usando criptografia sem validação</span><span class="sxs-lookup"><span data-stu-id="79f39-128">Using Encryption Without Validation</span></span>](using-encryption-without-validation.md)  
 <span data-ttu-id="79f39-129">Aborda como usar o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client para criptografar dados enviados para o servidor sem validar o certificado.</span><span class="sxs-lookup"><span data-stu-id="79f39-129">Discusses how to use [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client to encrypt data sent to the server without validating the certificate.</span></span>  
  
 [<span data-ttu-id="79f39-130">Os parâmetros com valor de tabela &#40;SQL Server Native Client&#41;</span><span class="sxs-lookup"><span data-stu-id="79f39-130">Table-Valued Parameters &#40;SQL Server Native Client&#41;</span></span>](table-valued-parameters-sql-server-native-client.md)  
 <span data-ttu-id="79f39-131">Aborda o suporte do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client aos parâmetros com valor de tabela.</span><span class="sxs-lookup"><span data-stu-id="79f39-131">Discusses [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client support for the table-valued parameters.</span></span>  
  
 [<span data-ttu-id="79f39-132">Tipos de dados CLR grandes definidos pelo usuário</span><span class="sxs-lookup"><span data-stu-id="79f39-132">Large CLR User-Defined Types</span></span>](../../clr-integration-database-objects-user-defined-types/clr-user-defined-types.md)  
 <span data-ttu-id="79f39-133">Aborda o suporte a UDTs CLR (Common Language Runtime) grandes.</span><span class="sxs-lookup"><span data-stu-id="79f39-133">Discusses support for large common language runtime (CLR) user-defined types (UDTs).</span></span>  
  
 [<span data-ttu-id="79f39-134">Suporte a FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="79f39-134">FILESTREAM Support</span></span>](filestream-support.md)  
 <span data-ttu-id="79f39-135">Discute [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] o suporte de cliente nativo para o recurso de fluxo de recursos avançado.</span><span class="sxs-lookup"><span data-stu-id="79f39-135">Discusses [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client support for the enhanced FILESTREAM feature.</span></span>  
  
 [<span data-ttu-id="79f39-136">Suporte a SPN &#40;Nome da Entidade de Serviço&#41; em conexões com o cliente</span><span class="sxs-lookup"><span data-stu-id="79f39-136">Service Principal Name &#40;SPN&#41; Support in Client Connections</span></span>](service-principal-name-spn-support-in-client-connections.md)  
 <span data-ttu-id="79f39-137">Aborda como o suporte a SPNs (nomes da entidade de serviço) foi estendido para possibilitar autenticação mútua em todos os protocolos.</span><span class="sxs-lookup"><span data-stu-id="79f39-137">Discusses how support for service principal names (SPNs) has been extended to enable mutual authentication across all protocols.</span></span>  
  
 [<span data-ttu-id="79f39-138">Suporte a colunas esparsas no SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="79f39-138">Sparse Columns Support in SQL Server Native Client</span></span>](sparse-columns-support-in-sql-server-native-client.md)  
 <span data-ttu-id="79f39-139">Aborda o suporte do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client a colunas esparsas.</span><span class="sxs-lookup"><span data-stu-id="79f39-139">Discusses [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client support for sparse columns.</span></span>  
  
 [<span data-ttu-id="79f39-140">Melhorias de data e hora</span><span class="sxs-lookup"><span data-stu-id="79f39-140">Date and Time Improvements</span></span>](date-and-time-improvements.md)  
 <span data-ttu-id="79f39-141">Aborda o suporte adicionado ao [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client para os novos tipos de dados de data e hora.</span><span class="sxs-lookup"><span data-stu-id="79f39-141">Discusses support added to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client for the date and time data types.</span></span>  
  
 [<span data-ttu-id="79f39-142">Descoberta de metadados</span><span class="sxs-lookup"><span data-stu-id="79f39-142">Metadata Discovery</span></span>](metadata-discovery.md)  
 <span data-ttu-id="79f39-143">Discute melhorias de descoberta de metadados que foram feitas no [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)].</span><span class="sxs-lookup"><span data-stu-id="79f39-143">Discusses metadata discovery improvements that were made in [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)].</span></span>  
  
 [<span data-ttu-id="79f39-144">Suporte a UTF-16 no SQL Server Native Client 11.0</span><span class="sxs-lookup"><span data-stu-id="79f39-144">UTF-16 Support in SQL Server Native Client 11.0</span></span>](utf-16-support-in-sql-server-native-client-11-0.md)  
 <span data-ttu-id="79f39-145">Discute uma alteração no comportamento apresentada no [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)].</span><span class="sxs-lookup"><span data-stu-id="79f39-145">Discusses a behavior change introduced in [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)].</span></span> <span data-ttu-id="79f39-146">Se você fornecer um buffer de comprimento fixo ao associar um resultado de coluna ou parâmetro de saída e se o caractere `wchar` gravado no buffer antes da finalização do caractere for um ponto de código alternativo alto de um par alternativo, e se o próximo caractere `wchar` for um ponto de código alternativo baixo, o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client não adicionará o ponto de código alternativo alto ao buffer.</span><span class="sxs-lookup"><span data-stu-id="79f39-146">If you supply a fixed-length buffer when binding a column result or output parameter and if the `wchar` character written into the buffer before the terminating character is a high surrogate code point of a surrogate pair, and if the next `wchar` character is a low surrogate code point, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client will not add the high surrogate code point to the buffer.</span></span>  
  
 [<span data-ttu-id="79f39-147">Suporte do SQL Server Native Client à alta disponibilidade e recuperação de desastre</span><span class="sxs-lookup"><span data-stu-id="79f39-147">SQL Server Native Client Support for High Availability, Disaster Recovery</span></span>](sql-server-native-client-support-for-high-availability-disaster-recovery.md)  
 <span data-ttu-id="79f39-148">Aborda como seu aplicativo pode ser configurado para aproveitar os recursos de alta disponibilidade e de recuperação de desastre adicionados no [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)].</span><span class="sxs-lookup"><span data-stu-id="79f39-148">Discusses how your application can be configured to take advantage of the high-availability, disaster recovery features added in [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)].</span></span>  
  
 [<span data-ttu-id="79f39-149">Acessar informações de diagnóstico nos logs de eventos estendidos</span><span class="sxs-lookup"><span data-stu-id="79f39-149">Accessing Diagnostic Information in the Extended Events Log</span></span>](accessing-diagnostic-information-in-the-extended-events-log.md)  
 <span data-ttu-id="79f39-150">Discute os aprimoramentos do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client e o rastreamento de dados que fornece acesso a informações de diagnóstico no buffer de anel e no log de XEvents.</span><span class="sxs-lookup"><span data-stu-id="79f39-150">Discusses enhancements to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client and data tracing that gives you access to diagnostic information in the ring buffer and XEvents log.</span></span>  
  
 [<span data-ttu-id="79f39-151">Suporte do SQL Server Native Client para LocalDB</span><span class="sxs-lookup"><span data-stu-id="79f39-151">SQL Server Native Client Support for LocalDB</span></span>](sql-server-native-client-support-for-localdb.md)  
 <span data-ttu-id="79f39-152">Discute o suporte do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ao recurso LocalDB.</span><span class="sxs-lookup"><span data-stu-id="79f39-152">Discusses [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client support for the LocalDB feature.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79f39-153">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="79f39-153">See Also</span></span>  
 <span data-ttu-id="79f39-154">[Programação de SQL Server Native Client](../sql-server-native-client-programming.md) </span><span class="sxs-lookup"><span data-stu-id="79f39-154">[SQL Server Native Client Programming](../sql-server-native-client-programming.md) </span></span>  
 <span data-ttu-id="79f39-155">[Tópicos de instruções sobre ODBC](../../native-client-odbc-how-to/odbc-how-to-topics.md) </span><span class="sxs-lookup"><span data-stu-id="79f39-155">[ODBC How-to Topics](../../native-client-odbc-how-to/odbc-how-to-topics.md) </span></span>  
 <span data-ttu-id="79f39-156">[Tópicos de instruções sobre OLE DB](../../native-client-ole-db-how-to/ole-db-how-to-topics.md) </span><span class="sxs-lookup"><span data-stu-id="79f39-156">[OLE DB How-to Topics](../../native-client-ole-db-how-to/ole-db-how-to-topics.md) </span></span>  
 [<span data-ttu-id="79f39-157">Instalando o SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="79f39-157">Installing SQL Server Native Client</span></span>](../applications/installing-sql-server-native-client.md)  
  
  
