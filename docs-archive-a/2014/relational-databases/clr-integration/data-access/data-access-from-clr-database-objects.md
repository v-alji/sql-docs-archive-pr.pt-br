---
title: Acesso a dados de objetos de banco de dados CLR | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- common language runtime [SQL Server], data access
- routines [CLR integration]
- data access [CLR integration]
- ADO.NET [CLR integration]
- internal data access [CLR integration]
- common language runtime [SQL Server], ADO.NET
- database objects [CLR integration], data access
- managed code [SQL Server], database objects
- .NET Data Access Provider for SQL Server [CLR integration]
- managed code [SQL Server], data access
- SqlClient provider
- in-process data access providers [CLR integration]
ms.assetid: 9a0f4dee-71c1-42e9-a85e-52382807010f
author: rothja
ms.author: jroth
ms.openlocfilehash: d229d490a9f3a7bc6f613259ee0535218de47975
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582460"
---
# <a name="data-access-from-clr-database-objects"></a><span data-ttu-id="6fb56-102">Acesso aos dados dos objetos de banco de dados CLR</span><span class="sxs-lookup"><span data-stu-id="6fb56-102">Data Access from CLR Database Objects</span></span>
  <span data-ttu-id="6fb56-103">Uma rotina Common Language Runtime (CLR) pode acessar facilmente os dados armazenados na instância do [!INCLUDE[msCoName](../../../includes/ssnoversion-md.md)] na qual ele é executado, bem como os dados armazenados em instâncias remotas.</span><span class="sxs-lookup"><span data-stu-id="6fb56-103">A common language runtime (CLR) routine may easily access data stored in the instance of [!INCLUDE[msCoName](../../../includes/ssnoversion-md.md)] in which it runs, as well as data stored in remote instances.</span></span> <span data-ttu-id="6fb56-104">Os dados específicos que a rotina pode acessar são determinados pelo contexto de usuário no qual o código está sendo executado.</span><span class="sxs-lookup"><span data-stu-id="6fb56-104">Which particular data the routine can access is determined by the user context in which the code is running.</span></span> <span data-ttu-id="6fb56-105">Acesse dados de dentro de um objeto CLR Database usando o .NET Framework Provedor de Dados para [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] dados de aplicativos de cliente gerenciado e de camada intermediária.</span><span class="sxs-lookup"><span data-stu-id="6fb56-105">Access data from within a CLR database object by using the .NET Framework Data Provider for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] data from managed client and middle-tier applications.</span></span> <span data-ttu-id="6fb56-106">Por causa disto, você pode aproveitar seu conhecimento do ADO.NET e do `SqlClient` em aplicativos cliente e de camada intermediária.</span><span class="sxs-lookup"><span data-stu-id="6fb56-106">Because of this, you can leverage your knowledge of ADO.NET and `SqlClient` in client and middle-tier applications.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6fb56-107">Os métodos de tipos definidos pelo usuário e as funções definidas pelo usuário não são permitidos para executar o acesso a dados por padrão.</span><span class="sxs-lookup"><span data-stu-id="6fb56-107">User-defined type methods and user-defined functions are not allowed to perform data access by default.</span></span> <span data-ttu-id="6fb56-108">Você deve definir a propriedade `DataAccess` de `SqlMethodAttribute` ou de `SqlFunctionAttribute` como `DataAccessKind.Read` para habilitar o acesso a dados somente leitura de métodos de UDT (Tipo Definido pelo Usuário) ou de funções definidas pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="6fb56-108">You must set the `DataAccess` property of `SqlMethodAttribute` or `SqlFunctionAttribute` to `DataAccessKind.Read` to enable read-only data access from user-defined type (UDT) methods or user-defined functions.</span></span> <span data-ttu-id="6fb56-109">As operações de modificação de dados não são permitidas de UDTs ou de funções definidas pelo usuário e lançam exceções em tempo de execução, se houver alguma tentativa.</span><span class="sxs-lookup"><span data-stu-id="6fb56-109">Data modification operations are not allowed from UDTs or user-defined functions, and throws exceptions at execution time if attempted.</span></span>  
  
 <span data-ttu-id="6fb56-110">Esta seção aborda apenas as diferenças funcionais e comportamentais específicas ao acessar dados de um objeto de banco de dados de CLR.</span><span class="sxs-lookup"><span data-stu-id="6fb56-110">This section discusses only the specific functional and behavioral differences when accessing data from within a CLR database object.</span></span> <span data-ttu-id="6fb56-111">Para obter mais informações sobre os recursos e a funcionalidade do ADO.NET, consulte a documentação do ADO.NET incluída no SDK do .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6fb56-111">For more information about the features and functionality of ADO.NET, see the ADO.NET documentation included in the .NET Framework SDK.</span></span>  
  
 <span data-ttu-id="6fb56-112">A tabela a seguir lista os tópicos desta seção.</span><span class="sxs-lookup"><span data-stu-id="6fb56-112">The following table lists the topics in this section.</span></span>  
  
 [<span data-ttu-id="6fb56-113">Conexão de contexto</span><span class="sxs-lookup"><span data-stu-id="6fb56-113">Context Connection</span></span>](context-connection.md)  
 <span data-ttu-id="6fb56-114">Descreve a conexão de contexto com o SQL Server.</span><span class="sxs-lookup"><span data-stu-id="6fb56-114">Describes the context connection to SQL Server.</span></span>  
  
 [<span data-ttu-id="6fb56-115">Representação e credenciais para conexões</span><span class="sxs-lookup"><span data-stu-id="6fb56-115">Impersonation and Credentials for Connections</span></span>](impersonation-and-credentials-for-connections.md)  
 <span data-ttu-id="6fb56-116">Descreve as conexões de representação e as credenciais de conexão.</span><span class="sxs-lookup"><span data-stu-id="6fb56-116">Describes impersonating connections and connection credentials.</span></span>  
  
 [<span data-ttu-id="6fb56-117">Extensões específicas em processo do SQL Server para o ADO.NET</span><span class="sxs-lookup"><span data-stu-id="6fb56-117">SQL Server In-Process Specific Extensions to ADO.NET</span></span>](../../clr-integration-data-access-in-process-ado-net/sql-server-in-process-specific-extensions-to-ado-net.md)  
 <span data-ttu-id="6fb56-118">Aborda os processos `SqlPipe`, `SqlContext`, `SqlTriggerContext` e `SqlDataRecord` específicos em andamento.</span><span class="sxs-lookup"><span data-stu-id="6fb56-118">Discusses the in-process specific `SqlPipe`, `SqlContext`, `SqlTriggerContext`, and `SqlDataRecord` objects.</span></span>  
  
 [<span data-ttu-id="6fb56-119">Integração CLR e transações</span><span class="sxs-lookup"><span data-stu-id="6fb56-119">CLR Integration and Transactions</span></span>](../../native-client-ole-db-transactions/transactions.md)  
 <span data-ttu-id="6fb56-120">Descreve como a nova estrutura de transação fornecida no namespace System.Transactions se integra ao ADO.NET e a integração CLR do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6fb56-120">Describes how the new transaction framework provided in the System.Transactions namespace integrates with ADO.NET and [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] CLR integration.</span></span>  
  
 [<span data-ttu-id="6fb56-121">Serialização XML de objetos de banco de dados CLR</span><span class="sxs-lookup"><span data-stu-id="6fb56-121">XML Serialization from CLR Database Objects</span></span>](../../../database-engine/dev-guide/xml-serialization-from-clr-database-objects.md)  
 <span data-ttu-id="6fb56-122">Explica como habilitar cenários de serialização XML de objetos de banco de dados de CLR dentro do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6fb56-122">Explains how to enable XML serialization scenarios of CLR database objects inside [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
  
