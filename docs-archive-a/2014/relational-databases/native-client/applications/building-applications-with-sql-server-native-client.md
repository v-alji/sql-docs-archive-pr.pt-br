---
title: Criando aplicativos com SQL Server Native Client | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- data access [SQL Server Native Client], building applications
- SQLNCLI, building applications
- applications [SQL Server Native Client]
- SQL Server Native Client, building applications
ms.assetid: 254a2b48-f0e3-43b5-a48d-3d666c2a779f
author: rothja
ms.author: jroth
ms.openlocfilehash: d08fe1042ab1a79f6b48648f5a774b4fbac49ead
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575081"
---
# <a name="building-applications-with-sql-server-native-client"></a><span data-ttu-id="89445-102">Criando aplicativos com o SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="89445-102">Building Applications with SQL Server Native Client</span></span>
  <span data-ttu-id="89445-103">Durante o desenvolvimento de um aplicativo que usa a biblioteca do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client, surgem vários problemas.</span><span class="sxs-lookup"><span data-stu-id="89445-103">When developing an application that uses the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client library, there are a number of issues that come into play.</span></span> <span data-ttu-id="89445-104">Os tópicos desta seção abordam muitos desses problemas, inclusive a atualização do MDAC para o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client, o uso dos arquivos de cabeçalho e biblioteca do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client, além de uma visão geral das várias cadeias de caracteres de conexão que podem ser usadas com o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="89445-104">The topics in this section discuss many of these issues including upgrading from MDAC to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client, using the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client header and library files, and an overview of the various connection strings that can be used with [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="89445-105">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="89445-105">In This Section</span></span>  
 [<span data-ttu-id="89445-106">Instalando o SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="89445-106">Installing SQL Server Native Client</span></span>](installing-sql-server-native-client.md)  
 <span data-ttu-id="89445-107">Aborda como o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client é instalado, os locais em que vários componentes são instalados e como desinstalar o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="89445-107">Discusses how [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client is installed, the locations that various components are installed to, and how to uninstall [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span></span>  
  
 [<span data-ttu-id="89445-108">Componentes do SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="89445-108">Components of SQL Server Native Client</span></span>](components-of-sql-server-native-client.md)  
 <span data-ttu-id="89445-109">Aborda os componentes que compõem o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client, inclusive biblioteca, recurso, ajuda e arquivos de cabeçalho.</span><span class="sxs-lookup"><span data-stu-id="89445-109">Discusses the components that make up [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client including library, resource, help, and header files.</span></span>  
  
 [<span data-ttu-id="89445-110">Usando palavras-chave da cadeia de conexão com o SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="89445-110">Using Connection String Keywords with SQL Server Native Client</span></span>](using-connection-string-keywords-with-sql-server-native-client.md)  
 <span data-ttu-id="89445-111">Aborda os vários tipos de cadeias de conexão que podem ser usados durante a conexão com um banco de dados por [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="89445-111">Discusses the various types of connection strings that can be used when connecting to a database through [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span></span>  
  
 [<span data-ttu-id="89445-112">Usando os arquivos de biblioteca e de cabeçalho do SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="89445-112">Using the SQL Server Native Client Header and Library Files</span></span>](using-the-sql-server-native-client-header-and-library-files.md)  
 <span data-ttu-id="89445-113">Aborda como usar os arquivos de cabeçalho e de biblioteca do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client em um aplicativo.</span><span class="sxs-lookup"><span data-stu-id="89445-113">Discusses how to use the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client header and library files within an application.</span></span>  
  
 [<span data-ttu-id="89445-114">Atualizando um aplicativo do MDAC para o SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="89445-114">Updating an Application to SQL Server Native Client from MDAC</span></span>](updating-an-application-to-sql-server-native-client-from-mdac.md)  
 <span data-ttu-id="89445-115">Discute as diferenças entre o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client e o MDAC, e os problemas que devem ser considerados ao atualizar do MDAC para o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="89445-115">Discusses the differences between [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client and MDAC and issues that should be considered when upgrading from MDAC to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span></span>  
  
 [<span data-ttu-id="89445-116">Atualizando um aplicativo do SQL Server Native Client 2005</span><span class="sxs-lookup"><span data-stu-id="89445-116">Updating an Application from SQL Server 2005 Native Client</span></span>](updating-an-application-from-sql-server-2005-native-client.md)  
 <span data-ttu-id="89445-117">Aborda problemas que devem ser considerados ao fazer a atualização do [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] Native Client para o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client no [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)].</span><span class="sxs-lookup"><span data-stu-id="89445-117">Discusses issues that should be considered when upgrading from [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] Native Client to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client in [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)].</span></span>  
  
 [<span data-ttu-id="89445-118">Usando o ADO com SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="89445-118">Using ADO with SQL Server Native Client</span></span>](using-ado-with-sql-server-native-client.md)  
 <span data-ttu-id="89445-119">Aborda como o ADO pode usar o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client para acessar e usar a funcionalidade do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="89445-119">Discusses how ADO can use [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client to access and use [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] functionality.</span></span>  
  
 [<span data-ttu-id="89445-120">Políticas de suporte do SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="89445-120">Support Policies for SQL Server Native Client</span></span>](support-policies-for-sql-server-native-client.md)  
 <span data-ttu-id="89445-121">Aborda como vários componentes de acesso a dados podem ser usados com versões diferentes do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="89445-121">Discusses how various data-access components can be used with different versions of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span></span>  
  
 [<span data-ttu-id="89445-122">Connecting to an Azure SQL Database Using SQL Server Native Client (Conectando a um Banco de Dados SQL do Azure usando o SQL Server Native Client)</span><span class="sxs-lookup"><span data-stu-id="89445-122">Connecting to an Azure SQL Database Using SQL Server Native Client</span></span>](connecting-to-a-windows-azure-sql-database-using-sql-server-native-client.md)  
 <span data-ttu-id="89445-123">Discute como conectar-se a um [!INCLUDE[ssSDS](../../../includes/sssds-md.md)] usando o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="89445-123">Discusses how to connect to a [!INCLUDE[ssSDS](../../../includes/sssds-md.md)] using [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89445-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="89445-124">See Also</span></span>  
 <span data-ttu-id="89445-125">[Programação de SQL Server Native Client](../sql-server-native-client-programming.md) </span><span class="sxs-lookup"><span data-stu-id="89445-125">[SQL Server Native Client Programming](../sql-server-native-client-programming.md) </span></span>  
 <span data-ttu-id="89445-126">[Tópicos de instruções sobre ODBC](../../native-client-odbc-how-to/odbc-how-to-topics.md) </span><span class="sxs-lookup"><span data-stu-id="89445-126">[ODBC How-to Topics](../../native-client-odbc-how-to/odbc-how-to-topics.md) </span></span>  
 [<span data-ttu-id="89445-127">Tópicos de instruções do OLE DB</span><span class="sxs-lookup"><span data-stu-id="89445-127">OLE DB How-to Topics</span></span>](../../native-client-ole-db-how-to/ole-db-how-to-topics.md)  
  
  
