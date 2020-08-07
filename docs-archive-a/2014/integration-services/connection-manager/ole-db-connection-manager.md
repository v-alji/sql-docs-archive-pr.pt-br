---
title: Gerenciador de conexões OLE DB | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- OLE DB connection manager
- data sources [Integration Services], connections
- connection managers [Integration Services], OLE DB
- connections [Integration Services], OLE DB
ms.assetid: 91e3622e-4b1a-439a-80c7-a00b90d66979
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5431de956a1039c2978688982792f190b0abc544
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575269"
---
# <a name="ole-db-connection-manager"></a><span data-ttu-id="d2d70-102">gerenciador de conexões OLE DB</span><span class="sxs-lookup"><span data-stu-id="d2d70-102">OLE DB Connection Manager</span></span>
  <span data-ttu-id="d2d70-103">Um gerenciador de conexões OLE DB permite que um pacote se conecte a uma fonte de dados usando um provedor OLE DB.</span><span class="sxs-lookup"><span data-stu-id="d2d70-103">An OLE DB connection manager enables a package to connect to a data source by using an OLE DB provider.</span></span> <span data-ttu-id="d2d70-104">Por exemplo, um gerenciador de conexões OLE DB que se conecta ao [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pode usar o provedor OLE DB da [!INCLUDE[msCoName](../../includes/msconame-md.md)] para [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d2d70-104">For example, an OLE DB connection manager that connects to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] can use the [!INCLUDE[msCoName](../../includes/msconame-md.md)] OLE DB Provider for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d2d70-105">O provedor de OLEDB do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client 11.0 não dá suporte às novas palavras-chave de cadeia de conexão (MultiSubnetFailover=True) para clustering de failover de várias sub-redes.</span><span class="sxs-lookup"><span data-stu-id="d2d70-105">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client 11.0 OLEDB provider does not support the new connection string key words (MultiSubnetFailover=True) for Multi-Subnet Failover Clustering.</span></span> <span data-ttu-id="d2d70-106">Para obter mais informações, consulte as [notas de versão SQL Server](https://go.microsoft.com/fwlink/?LinkId=247824) e a postagem do blog, [failover de várias sub-redes AlwaysOn e SSIS](https://www.mattmasson.com/2012/03/alwayson-multi-subnet-failover-and-ssis/), em www.mattmasson.com.</span><span class="sxs-lookup"><span data-stu-id="d2d70-106">For more information, see the [SQL Server Release  Notes](https://go.microsoft.com/fwlink/?LinkId=247824) and the blog post, [AlwaysOn Multi-Subnet Failover and SSIS](https://www.mattmasson.com/2012/03/alwayson-multi-subnet-failover-and-ssis/), on www.mattmasson.com.</span></span>  
  
 <span data-ttu-id="d2d70-107">Várias [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] tarefas e componentes de fluxo de dados usam um Gerenciador de conexões OLE DB.</span><span class="sxs-lookup"><span data-stu-id="d2d70-107">Several [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] tasks and data flow components use an OLE DB connection manager.</span></span> <span data-ttu-id="d2d70-108">Por exemplo, a fonte e o destino do OLE DB usam esse gerenciador de conexões para extrair e carregar dados e a tarefa Executar SQL pode usar esse gerenciador de conexões para se conectar a um banco de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para executar consultas.</span><span class="sxs-lookup"><span data-stu-id="d2d70-108">For example, the OLE DB source and OLE DB destination use this connection manager to extract and load data, and the Execute SQL task can use this connection manager to connect to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database to run queries.</span></span>  
  
 <span data-ttu-id="d2d70-109">O gerenciador de conexões OLE DB também é usado para acessar fontes de dados OLE DB em tarefas personalizadas gravadas em código não gerenciado que usa uma linguagem como C++.</span><span class="sxs-lookup"><span data-stu-id="d2d70-109">The OLE DB connection manager is also used to access OLE DB data sources in custom tasks written in unmanaged code that uses a language such as C++.</span></span>  
  
 <span data-ttu-id="d2d70-110">Quando você adiciona um gerenciador de conexões OLE DB a um pacote, o [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] cria um gerenciador de conexões que resolverá uma conexão OLE DB em tempo de execução, define as propriedades do gerenciador de conexões e adiciona o gerenciador de conexões à coleção do `Connections` no pacote.</span><span class="sxs-lookup"><span data-stu-id="d2d70-110">When you add an OLE DB connection manager to a package, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] creates a connection manager that will resolve to an OLE DB connection at run time, sets the connection manager properties, and adds the connection manager to the `Connections` collection on the package.</span></span>  
  
 <span data-ttu-id="d2d70-111">A propriedade `ConnectionManagerType` do gerenciador de conexões é definida como `OLEDB`.</span><span class="sxs-lookup"><span data-stu-id="d2d70-111">The `ConnectionManagerType` property of the connection manager is set to `OLEDB`.</span></span>  
  
 <span data-ttu-id="d2d70-112">O gerenciador de conexões OLE DB pode ser configurado das seguintes maneiras:</span><span class="sxs-lookup"><span data-stu-id="d2d70-112">The OLE DB connection manager can be configured in the following ways:</span></span>  
  
-   <span data-ttu-id="d2d70-113">Forneça uma cadeia de conexão específica configurada para atender aos requisitos do provedor selecionado.</span><span class="sxs-lookup"><span data-stu-id="d2d70-113">Provide a specific connection string configured to meet the requirements of the selected provider.</span></span>  
  
-   <span data-ttu-id="d2d70-114">Dependendo do provedor, inclua o nome da fonte de dados à qual efetuar a conexão.</span><span class="sxs-lookup"><span data-stu-id="d2d70-114">Depending on the provider, include the name of the data source to connect to.</span></span>  
  
-   <span data-ttu-id="d2d70-115">Forneça credenciais de segurança apropriadas para o provedor selecionado.</span><span class="sxs-lookup"><span data-stu-id="d2d70-115">Provide security credentials as appropriate for the selected provider.</span></span>  
  
-   <span data-ttu-id="d2d70-116">Indique se a conexão criada a partir do gerenciador de conexões será retida em tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="d2d70-116">Indicate whether the connection that is created from the connection manager is retained at run time.</span></span>  
  
## <a name="logging"></a><span data-ttu-id="d2d70-117">Registrando em log</span><span class="sxs-lookup"><span data-stu-id="d2d70-117">Logging</span></span>  
 <span data-ttu-id="d2d70-118">Você pode registrar as chamadas que o gerenciador de conexões OLE DB faz aos provedores de dados externos.</span><span class="sxs-lookup"><span data-stu-id="d2d70-118">You can log the calls that the OLE DB connection manager makes to external data providers.</span></span> <span data-ttu-id="d2d70-119">É possível usar esse recurso de registro para solucionar problemas de conexões que o gerenciador de conexões OLE DB cria para as fontes de dados externas.</span><span class="sxs-lookup"><span data-stu-id="d2d70-119">You can use this logging capability to troubleshoot the connections that the OLE DB connection manager makes to external data sources.</span></span> <span data-ttu-id="d2d70-120">Para registrar as chamadas que o Gerenciador de conexões do OLE DB faz aos provedores de dados externos, habilite o log de pacote e selecione o evento de **diagnóstico** no nível do pacote.</span><span class="sxs-lookup"><span data-stu-id="d2d70-120">To log the calls that the OLE DB connection manager makes to external data providers, enable package logging and select the **Diagnostic** event at the package level.</span></span> <span data-ttu-id="d2d70-121">Para obter mais informações, consulte [Solucionando problemas de ferramentas para execução de pacotes](../troubleshooting/troubleshooting-tools-for-package-execution.md).</span><span class="sxs-lookup"><span data-stu-id="d2d70-121">For more information, see [Troubleshooting Tools for Package Execution](../troubleshooting/troubleshooting-tools-for-package-execution.md).</span></span>  
  
## <a name="configuration-of-the-oledb-connection-manager"></a><span data-ttu-id="d2d70-122">Configuração do gerenciador de conexões OLEDB</span><span class="sxs-lookup"><span data-stu-id="d2d70-122">Configuration of the OLEDB Connection Manager</span></span>  
 <span data-ttu-id="d2d70-123">Você pode definir propriedades pelo Designer do [!INCLUDE[ssIS](../../includes/ssis-md.md)] ou programaticamente.</span><span class="sxs-lookup"><span data-stu-id="d2d70-123">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span> <span data-ttu-id="d2d70-124">Para obter mais informações sobre as propriedades que podem ser definidas no Designer do [!INCLUDE[ssIS](../../includes/ssis-md.md)] , consulte [Configurar Gerenciador de Conexões OLE DB](../configure-ole-db-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="d2d70-124">For more information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, see [Configure OLE DB Connection Manager](../configure-ole-db-connection-manager.md).</span></span> <span data-ttu-id="d2d70-125">Para obter mais informações sobre como configurar um gerenciador de conexões programaticamente, consulte a documentação da classe **T:Microsoft.SqlServer.Dts.Runtime.ConnectionManager** no Guia do Desenvolvedor.</span><span class="sxs-lookup"><span data-stu-id="d2d70-125">For information about configuring a connection manager programmatically, see the documentation for **T:Microsoft.SqlServer.Dts.Runtime.ConnectionManager** class in the Developer Guide.</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="d2d70-126">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="d2d70-126">Related Content</span></span>  
  
-   <span data-ttu-id="d2d70-127">Artigo wiki, [SSIS com conectores Oracle](https://go.microsoft.com/fwlink/?LinkId=220670) no social.technet.Microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="d2d70-127">Wiki article, [SSIS with Oracle Connectors](https://go.microsoft.com/fwlink/?LinkId=220670) on social.technet.microsoft.com.</span></span>  
  
-   <span data-ttu-id="d2d70-128">Artigo técnico, [Connection Strings for OLE DB Providers](https://go.microsoft.com/fwlink/?LinkId=220744)(Cadeias de conexão para provedores de OLE DB), em carlprothman.net.</span><span class="sxs-lookup"><span data-stu-id="d2d70-128">Technical article, [Connection Strings for OLE DB Providers](https://go.microsoft.com/fwlink/?LinkId=220744), on carlprothman.net.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2d70-129">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d2d70-129">See Also</span></span>  
 <span data-ttu-id="d2d70-130">[Origem de OLE DB](../data-flow/ole-db-source.md) </span><span class="sxs-lookup"><span data-stu-id="d2d70-130">[OLE DB Source](../data-flow/ole-db-source.md) </span></span>  
 <span data-ttu-id="d2d70-131">[Destino OLE DB](../data-flow/ole-db-destination.md) </span><span class="sxs-lookup"><span data-stu-id="d2d70-131">[OLE DB Destination](../data-flow/ole-db-destination.md) </span></span>  
 <span data-ttu-id="d2d70-132">[Tarefa Executar SQL](../control-flow/execute-sql-task.md) </span><span class="sxs-lookup"><span data-stu-id="d2d70-132">[Execute SQL Task](../control-flow/execute-sql-task.md) </span></span>  
 [<span data-ttu-id="d2d70-133">Conexões do SSIS &#40;Integration Services&#41;</span><span class="sxs-lookup"><span data-stu-id="d2d70-133">Integration Services &#40;SSIS&#41; Connections</span></span>](integration-services-ssis-connections.md)  
  
  
