---
title: SQL Server Native Client fontes de dados ODBC | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- ODBC data sources, about data sources
- ODBC data sources, names
- data sources [SQL Server Native Client]
- names [ODBC]
- ODBC applications, data sources
- SQL Server Native Client ODBC driver, data sources
- ODBC data sources
ms.assetid: a6a50fd0-d439-43fd-b76f-16ec02f478c5
author: rothja
ms.author: jroth
ms.openlocfilehash: 6960118e13f0843640b18056bda655726cbbbd29
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573947"
---
# <a name="sql-server-native-client-odbc-data-sources"></a><span data-ttu-id="7f905-102">fontes de dados ODBC do SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="7f905-102">SQL Server Native Client ODBC Data Sources</span></span>
  <span data-ttu-id="7f905-103">Um DSN (nome da fonte de dados) do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] identifica uma fonte de dados ODBC que contém todas as informações de que um aplicativo ODBC precisa para se conectar a um banco de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] em um servidor específico.</span><span class="sxs-lookup"><span data-stu-id="7f905-103">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data source name (DSN) identifies an ODBC data source containing all of the information that an ODBC application needs to connect to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database on a specific server.</span></span> <span data-ttu-id="7f905-104">Há duas maneiras de definir um nome da fonte de dados ODBC:</span><span class="sxs-lookup"><span data-stu-id="7f905-104">There are two ways you can define an ODBC data source name:</span></span>  
  
-   <span data-ttu-id="7f905-105">Em um computador cliente, abra Ferramentas administrativas no painel de controle e clique duas vezes em **fontes de dados (ODBC)**.</span><span class="sxs-lookup"><span data-stu-id="7f905-105">On a client computer, open Administrative Tools in Control Panel, and double-click **Data Sources (ODBC)**.</span></span> <span data-ttu-id="7f905-106">O Administrador de Fonte de Dados ODBC será aberto e poderá ser usado para criar um DSN.</span><span class="sxs-lookup"><span data-stu-id="7f905-106">This will open the ODBC Data Source Administrator, which you can use to create a DSN.</span></span>  
  
-   <span data-ttu-id="7f905-107">Em um aplicativo ODBC, chame [SQLConfigDataSource](../native-client-odbc-api/sqlconfigdatasource.md).</span><span class="sxs-lookup"><span data-stu-id="7f905-107">In an ODBC application, call [SQLConfigDataSource](../native-client-odbc-api/sqlconfigdatasource.md).</span></span>  
  
 <span data-ttu-id="7f905-108">Uma fonte de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] contém:</span><span class="sxs-lookup"><span data-stu-id="7f905-108">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data source contains:</span></span>  
  
-   <span data-ttu-id="7f905-109">O nome da fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="7f905-109">The name of the data source.</span></span>  
  
-   <span data-ttu-id="7f905-110">Quaisquer informações necessárias para se conectar a uma instância específica do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7f905-110">Any information needed to connect to a specific instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="7f905-111">O banco de dados padrão a ser usado em uma instância específica do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (opcional).</span><span class="sxs-lookup"><span data-stu-id="7f905-111">The default database to use on a specific instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (optional).</span></span>  
  
-   <span data-ttu-id="7f905-112">Configurações como quais opções ANSI serão usadas, se as estatísticas de desempenho serão registradas ou não e assim por diante (opcional).</span><span class="sxs-lookup"><span data-stu-id="7f905-112">Settings such as which ANSI options to use, whether to log performance statistics, and so on (optional).</span></span>  
  
 <span data-ttu-id="7f905-113">Não é necessário um aplicativo ODBC para se conectar através de uma fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="7f905-113">An ODBC application is not required to connect through a data source.</span></span> <span data-ttu-id="7f905-114">Entretanto, o aplicativo precisa fornecer as mesmas informações de conectividade para uma função de conexão ODBC que de outro modo o driver encontraria em um DSN.</span><span class="sxs-lookup"><span data-stu-id="7f905-114">However, the application must provide the same connectivity information to an ODBC connect function that the driver would otherwise find in a DSN.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f905-115">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7f905-115">See Also</span></span>  
 [<span data-ttu-id="7f905-116">Comunicando-se com SQL Server &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="7f905-116">Communicating with SQL Server &#40;ODBC&#41;</span></span>](communicating-with-sql-server-odbc.md)  
  
  
