---
title: Gerenciador de Conexões ODBC | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- connections [Integration Services], ODBC
- ODBC connection manager
- data sources [Integration Services], connections
- connection managers [Integration Services], ODBC
ms.assetid: e8c77aa7-6772-485e-918e-cef9eeb18c58
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e1069e31f3f8ffaf14dde091d913ff6d9f8fa7cc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572635"
---
# <a name="odbc-connection-manager"></a><span data-ttu-id="98056-102">gerenciador de conexões ODBC</span><span class="sxs-lookup"><span data-stu-id="98056-102">ODBC Connection Manager</span></span>
  <span data-ttu-id="98056-103">Um gerenciador de conexões ODBC permite que um pacote se conecte com vários sistemas de gerenciamento de banco de dados que usam a especificação ODBC (Conectividade Aberta de Banco de Dados).</span><span class="sxs-lookup"><span data-stu-id="98056-103">An ODBC connection manager enables a package to connect to a variety of database management systems using the Open Database Connectivity specification (ODBC).</span></span>  
  
 <span data-ttu-id="98056-104">Quando você adiciona uma conexão ODBC a um pacote e define as propriedades do Gerenciador de conexões, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] o cria um Gerenciador de conexões e adiciona o Gerenciador de conexões à `Connections` coleção do pacote.</span><span class="sxs-lookup"><span data-stu-id="98056-104">When you add an ODBC connection to a package and set the connection manager properties, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] creates a connection manager and adds the connection manager to the `Connections` collection of the package.</span></span> <span data-ttu-id="98056-105">No tempo de execução, o gerenciador de conexões é resolvido como uma conexão física ODBC.</span><span class="sxs-lookup"><span data-stu-id="98056-105">At run time the connection manager is resolved as a physical ODBC connection.</span></span>  
  
 <span data-ttu-id="98056-106">A propriedade `ConnectionManagerType` do gerenciador de conexões é definida como `ODBC`.</span><span class="sxs-lookup"><span data-stu-id="98056-106">The `ConnectionManagerType` property of the connection manager is set to `ODBC`.</span></span>  
  
 <span data-ttu-id="98056-107">Você pode configurar um gerenciador de conexões ODBC das seguintes formas:</span><span class="sxs-lookup"><span data-stu-id="98056-107">You can configure the ODBC connection manager in the following ways:</span></span>  
  
-   <span data-ttu-id="98056-108">Forneça uma cadeia de caracteres de conexão que faça referência a um usuário ou a um nome de fonte de dados do sistema.</span><span class="sxs-lookup"><span data-stu-id="98056-108">Provide a connection string that references a user or system data source name.</span></span>  
  
-   <span data-ttu-id="98056-109">Especifique o servidor a ser conectado.</span><span class="sxs-lookup"><span data-stu-id="98056-109">Specify the server to connect to.</span></span>  
  
-   <span data-ttu-id="98056-110">Indique se a conexão é retida no tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="98056-110">Indicate whether the connection is retained at run time.</span></span>  
  
## <a name="configuration-of-the-odbc-connection-manager"></a><span data-ttu-id="98056-111">Configuração do gerenciador de conexões ODBC</span><span class="sxs-lookup"><span data-stu-id="98056-111">Configuration of the ODBC Connection Manager</span></span>  
 <span data-ttu-id="98056-112">Você pode definir propriedades pelo Designer do [!INCLUDE[ssIS](../../includes/ssis-md.md)] ou programaticamente.</span><span class="sxs-lookup"><span data-stu-id="98056-112">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="98056-113">Para obter mais informações sobre as propriedades que podem ser definidas no Designer [!INCLUDE[ssIS](../../includes/ssis-md.md)] , clique em um dos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="98056-113">For more information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click one of the following topic:</span></span>  
  
-   [<span data-ttu-id="98056-114">Referência da interface do usuário do Gerenciador de Conexões ODBC</span><span class="sxs-lookup"><span data-stu-id="98056-114">ODBC Connection Manager UI Reference</span></span>](../odbc-connection-manager-ui-reference.md)  
  
 <span data-ttu-id="98056-115">Para obter informações sobre como configurar um gerenciador de conexões programaticamente, consulte <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> e [Adicionando conexões programaticamente](../building-packages-programmatically/adding-connections-programmatically.md).</span><span class="sxs-lookup"><span data-stu-id="98056-115">For information about configuring a connection manager programmatically, see <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> and [Adding Connections Programmatically](../building-packages-programmatically/adding-connections-programmatically.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98056-116">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="98056-116">See Also</span></span>  
 [<span data-ttu-id="98056-117">Conexões do SSIS &#40;Integration Services&#41;</span><span class="sxs-lookup"><span data-stu-id="98056-117">Integration Services &#40;SSIS&#41; Connections</span></span>](integration-services-ssis-connections.md)  
  
  
