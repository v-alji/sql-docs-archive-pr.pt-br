---
title: Edições e componentes do SQL Server 2014 | Microsoft Docs
ms.custom: ''
ms.date: 05/24/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
helpviewer_keywords:
- Enterprise Edition [SQL Server]
- Developer Edition [SQL Server]
- 32-bit vs. 64-bit editions [SQL Server]
- default components
- Workgroup Edition [SQL Server]
- Internet servers [SQL Server]
- installing SQL Server, components
- Setup [SQL Server], components
- SQL Server, editions
- SQL Server, components
- client/server applications [SQL Server]
- editions [SQL Server]
- versions [SQL Server]
- Setup [SQL Server], editions
- SQL Server Installation Wizard
- components [SQL Server]
- Standard Edition [SQL Server]
- 64-bit edition [SQL Server]
- IIS [SQL Server]
- installing SQL Server, editions
- editions [SQL Server], about edition options
- Setup [SQL Server]
ms.assetid: e5186f02-dd91-47d0-8fa4-de3f41c76903
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: ba357d09a50912d8b2ffff8dec948df06a24c3d0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573607"
---
# <a name="editions-and-components-of-sql-server-2014"></a><span data-ttu-id="116f7-102">Edições e componentes do SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="116f7-102">Editions and Components of SQL Server 2014</span></span>
  <span data-ttu-id="116f7-103">Os requisitos de instalação variam de acordo com as necessidades do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="116f7-103">Installation requirements vary based on your application needs.</span></span> <span data-ttu-id="116f7-104">As diferentes edições do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] acomodam desempenho, runtime e requisitos de preço exclusivos para organizações e indivíduos.</span><span class="sxs-lookup"><span data-stu-id="116f7-104">The different editions of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] accommodate the unique performance, runtime, and price requirements of organizations and individuals.</span></span> <span data-ttu-id="116f7-105">Os componentes do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] que você instala dependem também dos seus requisitos específicos.</span><span class="sxs-lookup"><span data-stu-id="116f7-105">The [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] components that you install also depend on your specific requirements.</span></span> <span data-ttu-id="116f7-106">As seções a seguir ajudarão você a entender como fazer a melhor escolha entre as edições e os componentes disponíveis no [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="116f7-106">The following sections help you understand how to make the best choice among the editions and components available in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="principal-editions-of-sscurrent"></a><span data-ttu-id="116f7-107">Principais edições do [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)]</span><span class="sxs-lookup"><span data-stu-id="116f7-107">Principal Editions of [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)]</span></span>  
 <span data-ttu-id="116f7-108">A tabela a seguir descreve as edições principais do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="116f7-108">The following table describes the principal editions of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="116f7-109">Para obter mais informações, consulte [Features Supported by the Editions of SQL Server 2014](../getting-started/features-supported-by-the-editions-of-sql-server-2014.md)</span><span class="sxs-lookup"><span data-stu-id="116f7-109">For more information, see [Features Supported by the Editions of SQL Server 2014](../getting-started/features-supported-by-the-editions-of-sql-server-2014.md)</span></span>  
  
|[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] <span data-ttu-id="116f7-110">edição</span><span class="sxs-lookup"><span data-stu-id="116f7-110">edition</span></span>|<span data-ttu-id="116f7-111">Definição</span><span class="sxs-lookup"><span data-stu-id="116f7-111">Definition</span></span>|  
|---------------------------------------|----------------|  
|<span data-ttu-id="116f7-112">Enterprise (64 bits e 32 bits)</span><span class="sxs-lookup"><span data-stu-id="116f7-112">Enterprise (64-bit and 32-bit)</span></span>|<span data-ttu-id="116f7-113">A oferta premium, a edição [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] Enterprise fornece recursos de datacenter abrangentes de alta tecnologia com desempenho incrivelmente rápido, virtualização ilimitada e business intelligence de ponta a ponta – oferecendo altos níveis de serviço para cargas de trabalho críticas e acesso a visões de dados para usuários finais.</span><span class="sxs-lookup"><span data-stu-id="116f7-113">The premium offering, [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] Enterprise edition delivers comprehensive high-end datacenter capabilities with blazing-fast performance, unlimited virtualization, and end-to-end business intelligence - enabling high service levels for mission-critical workloads and end user access to data insights.</span></span>|  
|<span data-ttu-id="116f7-114">Business Intelligence (64 bits e 32 bits)</span><span class="sxs-lookup"><span data-stu-id="116f7-114">Business Intelligence (64-bit and 32-bit)</span></span>|<span data-ttu-id="116f7-115">A edição [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] Business Intelligence fornece uma plataforma abrangente que permite que as empresas criem e implantem soluções BI seguras, flexíveis e gerenciáveis.</span><span class="sxs-lookup"><span data-stu-id="116f7-115">[!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] Business Intelligence edition delivers comprehensive platform empowering organizations to build and deploy secure, scalable and manageable BI solutions.</span></span> <span data-ttu-id="116f7-116">Ele oferece funcionalidade empolgante, como visualização e exploração de dados baseada em navegador; recursos poderosos de mashup de dados e gerenciamento de integração aprimorado.</span><span class="sxs-lookup"><span data-stu-id="116f7-116">It offers exciting functionality such as browser based data exploration and visualization; powerful data mash-up capabilities, and enhanced integration management.</span></span>|  
|<span data-ttu-id="116f7-117">Standard (64 bits e 32 bits)</span><span class="sxs-lookup"><span data-stu-id="116f7-117">Standard (64-bit and 32-bit)</span></span>|<span data-ttu-id="116f7-118">A edição [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] Standard fornece gerenciamento de dados básicos e bancos de dados de business intelligence para departamentos e pequenas empresas executarem seus aplicativos e dá suporte a ferramentas de desenvolvimento comuns para rede local e em nuvem – permitindo o gerenciamento eficiente de bancos de dados com mínimos recursos de TI.</span><span class="sxs-lookup"><span data-stu-id="116f7-118">[!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] Standard edition delivers basic data management and business intelligence database for departments and small organizations to run their applications and supports common development tools for on-premise and cloud - enabling effective database management with minimal IT resources.</span></span>|  
  
## <a name="specialized-editions-of-sscurrent"></a><span data-ttu-id="116f7-119">Edições especializadas do [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)]</span><span class="sxs-lookup"><span data-stu-id="116f7-119">Specialized Editions of [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)]</span></span>  
 <span data-ttu-id="116f7-120">As edições especializadas do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] são destinadas às cargas de trabalho comerciais.</span><span class="sxs-lookup"><span data-stu-id="116f7-120">Specialized editions of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] are targeted for business workloads.</span></span> <span data-ttu-id="116f7-121">A tabela a seguir descreve as edições especializadas do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="116f7-121">The following table describes the specialized editions of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
|[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] <span data-ttu-id="116f7-122">edição</span><span class="sxs-lookup"><span data-stu-id="116f7-122">edition</span></span>|<span data-ttu-id="116f7-123">Descrição</span><span class="sxs-lookup"><span data-stu-id="116f7-123">Description</span></span>|  
|---------------------------------------|-----------------|  
|<span data-ttu-id="116f7-124">Web (64 bits e 32 bits)</span><span class="sxs-lookup"><span data-stu-id="116f7-124">Web (64-bit and 32-bit)</span></span>|<span data-ttu-id="116f7-125">A edição[!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] Web é uma opção de baixo custo total de propriedade para hospedagem de sites e VAPs da Web que fornece recursos de escalabilidade, economia e capacidade de gerenciamento para propriedades da Web de pequeno a grande porte.</span><span class="sxs-lookup"><span data-stu-id="116f7-125">[!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] Web edition is a low total-cost-of-ownership option for Web hosters and Web VAPs to provide scalability, affordability, and manageability capabilities for small to large scale Web properties.</span></span>|  
  
## <a name="breadth-editions-of-sscurrent"></a><span data-ttu-id="116f7-126">Edições de amplitude do [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)]</span><span class="sxs-lookup"><span data-stu-id="116f7-126">Breadth Editions of [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)]</span></span>  
 <span data-ttu-id="116f7-127">As edições de amplitude do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] foram criadas para cenários de cliente específicos e são oferecidas GRATUITAMENTE ou a um custo irrisório.</span><span class="sxs-lookup"><span data-stu-id="116f7-127">Breadth editions of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] are engineered for specific customer scenarios and are offered FREE or at a very nominal cost.</span></span> <span data-ttu-id="116f7-128">A tabela a seguir descreve as edições de amplitude do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="116f7-128">The following table describes the breadth editions of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
|[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] <span data-ttu-id="116f7-129">edição</span><span class="sxs-lookup"><span data-stu-id="116f7-129">edition</span></span>|<span data-ttu-id="116f7-130">Descrição</span><span class="sxs-lookup"><span data-stu-id="116f7-130">Description</span></span>|  
|---------------------------------------|-----------------|  
|<span data-ttu-id="116f7-131">Developer (64 bits e 32 bits)</span><span class="sxs-lookup"><span data-stu-id="116f7-131">Developer (64-bit and 32-bit)</span></span>|<span data-ttu-id="116f7-132">A edição[!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] Developer permite que os desenvolvedores criem qualquer tipo de aplicativo com base no [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="116f7-132">[!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] Developer edition lets developers build any kind of application on top of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="116f7-133">Ele inclui todas as funcionalidades da edição Enterprise, mas é licenciado para ser usado como um sistema de teste e desenvolvimento, e não como um servidor de produção.</span><span class="sxs-lookup"><span data-stu-id="116f7-133">It includes all the functionality of Enterprise edition, but is licensed for use as a development and test system, not as a production server.</span></span> <span data-ttu-id="116f7-134">O [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Developer é uma opção ideal para pessoas que criam e testam aplicativos.</span><span class="sxs-lookup"><span data-stu-id="116f7-134">[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Developer is an ideal choice for people who build and test applications.</span></span>|  
|<span data-ttu-id="116f7-135">Edições Express (64 e 32 bits)</span><span class="sxs-lookup"><span data-stu-id="116f7-135">Express (64-bit and 32-bit) editions</span></span>|<span data-ttu-id="116f7-136">A edição [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] Express é o banco de dados básico gratuito, ideal para conhecer e criar aplicativos de desktop e plicativos controlados por dados de pequenos servidores.</span><span class="sxs-lookup"><span data-stu-id="116f7-136">[!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] Express edition is the entry-level, free database and is ideal for learning and building desktop and small server data-driven applications.</span></span> <span data-ttu-id="116f7-137">É a melhor escolha para fornecedores de software independente, desenvolvedores e interessados que criam aplicativos cliente.</span><span class="sxs-lookup"><span data-stu-id="116f7-137">It is the best choice for independent software vendors, developers, and hobbyists building client applications.</span></span> <span data-ttu-id="116f7-138">Se precisar de recursos mais avançados de banco de dados, o [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Express pode ser perfeitamente atualizado para versões mais sofisticadas do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="116f7-138">If you need more advanced database features, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Express can be seamlessly upgraded to other higher end versions of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="116f7-139">O[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Express LocalDB, uma versão leve do Express que tem todos os seus recursos de programação, embora seja executado no modo de usuário, e tenha uma instalação rápida e sem nenhuma configuração e uma lista curta de pré-requisitos.</span><span class="sxs-lookup"><span data-stu-id="116f7-139">[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Express LocalDB, a lightweight version of Express that has all of its programmability features, yet runs in user mode and has a fast, zero-configuration installation and a short list of prerequisites.</span></span>|  
  
## <a name="using-ssnoversion-with-an-internet-server"></a><span data-ttu-id="116f7-140">Usando o [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] com um servidor de Internet</span><span class="sxs-lookup"><span data-stu-id="116f7-140">Using [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] with an Internet Server</span></span>  
 <span data-ttu-id="116f7-141">Em um servidor de Internet, como um servidor que executa o IIS (Serviços de Informações da Internet), você instalará normalmente as ferramentas cliente do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="116f7-141">On an Internet server, such as a server that is running Internet Information Services (IIS), you will typically install the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] client tools.</span></span> <span data-ttu-id="116f7-142">Essas ferramentas incluem os componentes cliente de conectividade usados por um aplicativo que se conecta a uma instância do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="116f7-142">Client tools include the client connectivity components used by an application connecting to an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="116f7-143">Apesar de ser possível instalar uma instância do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] em um computador que executa o IIS, isso é feito normalmente apenas para pequenos sites da Web que possuem um único computador servidor.</span><span class="sxs-lookup"><span data-stu-id="116f7-143">Although you can install an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] on a computer that is running IIS, this is typically done only for small Web sites that have a single server computer.</span></span> <span data-ttu-id="116f7-144">A maioria dos sites da Web possui sistemas IIS de camada intermediária em um servidor ou em clusters de servidores e bancos de dados em um servidor diferente ou em uma federação de servidores.</span><span class="sxs-lookup"><span data-stu-id="116f7-144">Most Web sites have their middle-tier IIS systems on one server or a cluster of servers, and their databases on a separate server or federation of servers.</span></span>  
  
## <a name="using-ssnoversion-with-clientserver-applications"></a><span data-ttu-id="116f7-145">Usando o [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] com aplicativos cliente/servidor</span><span class="sxs-lookup"><span data-stu-id="116f7-145">Using [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] with Client/Server Applications</span></span>  
 <span data-ttu-id="116f7-146">Você pode instalar apenas os componentes cliente do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] em um computador que esteja executando aplicativos cliente/servidor que se conectam diretamente a uma instância do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="116f7-146">You can install just the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] client components on a computer that is running client/server applications that connect directly to an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="116f7-147">A instalação dos componentes cliente é também uma boa opção se você administra uma instância do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] em um servidor de banco de dados ou se planeja desenvolver aplicativos no [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="116f7-147">A client components installation is also a good option if you administer an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] on a database server, or if you plan to develop [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] applications.</span></span>  
  
 <span data-ttu-id="116f7-148">A opção de ferramentas cliente instala os seguintes recursos do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] : componentes compatíveis com versões anteriores, [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], componentes de conectividade, ferramentas de gerenciamento, Software Development Kit e componentes dos Manuais Online do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="116f7-148">The client tools option installs the following [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] features: backward compatibility components, [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], connectivity components, management tools, software development kit, and [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Books Online components.</span></span> <span data-ttu-id="116f7-149">Para obter mais informações, consulte [instalar SQL Server 2014 do assistente de instalação &#40;&#41;de ](../database-engine/install-windows/install-sql-server-from-the-installation-wizard-setup.md)instalação.</span><span class="sxs-lookup"><span data-stu-id="116f7-149">For more information, see [Install SQL Server 2014 from the Installation Wizard &#40;Setup&#41;](../database-engine/install-windows/install-sql-server-from-the-installation-wizard-setup.md).</span></span>  
  
## <a name="deciding-among-ssnoversion-components"></a><span data-ttu-id="116f7-150">Decidindo entre os componentes do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="116f7-150">Deciding Among [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Components</span></span>  
 <span data-ttu-id="116f7-151">Use a página Seleção de Recursos do Assistente de Instalação do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] para selecionar os componentes a serem incluídos em uma instalação do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="116f7-151">Use the Feature Selection page of the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Installation Wizard to select the components to include in an installation of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="116f7-152">Por padrão, nenhum dos recursos na árvore está selecionado.</span><span class="sxs-lookup"><span data-stu-id="116f7-152">By default, none of the features in the tree are selected.</span></span>  
  
 <span data-ttu-id="116f7-153">Use as informações nas tabelas a seguir para determinar o conjunto de recursos mais adequado às suas necessidades.</span><span class="sxs-lookup"><span data-stu-id="116f7-153">Use the information in the following tables to determine the set of features that best fits your needs.</span></span>  
  
|<span data-ttu-id="116f7-154">Componentes de servidor</span><span class="sxs-lookup"><span data-stu-id="116f7-154">Server components</span></span>|<span data-ttu-id="116f7-155">Descrição</span><span class="sxs-lookup"><span data-stu-id="116f7-155">Description</span></span>|  
|-----------------------|-----------------|  
|[!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)]|[!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)]<span data-ttu-id="116f7-156">inclui o [!INCLUDE[ssDE](../includes/ssde-md.md)] , o serviço principal para armazenar, processar e proteger dados, replicação, pesquisa de texto completo, ferramentas para gerenciar dados XML e relacionais e o [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS) Server.</span><span class="sxs-lookup"><span data-stu-id="116f7-156">includes the [!INCLUDE[ssDE](../includes/ssde-md.md)], the core service for storing, processing, and securing data, replication, full-text search, tools for managing relational and XML data, and the [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS) server.</span></span>|  
|[!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)]|[!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] <span data-ttu-id="116f7-157">inclui as ferramentas para criação e gerenciamento de aplicativos OLAP (processamento analítico online) e de mineração de dados.</span><span class="sxs-lookup"><span data-stu-id="116f7-157">includes the tools for creating and managing online analytical processing (OLAP) and data mining applications.</span></span>|  
|[!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)]|<span data-ttu-id="116f7-158">O[!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] inclui componentes de servidor e cliente por criar, gerenciar e implantar relatórios tabulares, de matriz, gráficos e de forma livre.</span><span class="sxs-lookup"><span data-stu-id="116f7-158">[!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] includes server and client components for creating, managing, and deploying tabular, matrix, graphical, and free-form reports.</span></span> <span data-ttu-id="116f7-159">O[!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] também é uma plataforma extensível que você pode usar para desenvolver aplicativos de relatório.</span><span class="sxs-lookup"><span data-stu-id="116f7-159">[!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] is also an extensible platform that you can use to develop report applications.</span></span>|  
|[!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]|[!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] <span data-ttu-id="116f7-160">é um conjunto de ferramentas gráficas e objetos programáveis para mover, copiar e transformar dados.</span><span class="sxs-lookup"><span data-stu-id="116f7-160">is a set of graphical tools and programmable objects for moving, copying, and transforming data.</span></span> <span data-ttu-id="116f7-161">Ele também inclui o componente [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS) para o [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="116f7-161">It also includes the [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS) component for [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span></span>|  
|[!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]|<span data-ttu-id="116f7-162">O[!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] (MDS) é a solução do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] para gerenciamento de dados mestre.</span><span class="sxs-lookup"><span data-stu-id="116f7-162">[!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] (MDS) is the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] solution for master data management.</span></span> <span data-ttu-id="116f7-163">O MDS pode ser configurado para gerenciar qualquer domínio (produtos, clientes, contas) e inclui hierarquias, segurança granular, transações, controle de versão de dados e regras de negócio, bem como um [!INCLUDE[ssMDSXLS](../includes/ssmdsxls-md.md)] que pode ser usado para gerenciar dados.</span><span class="sxs-lookup"><span data-stu-id="116f7-163">MDS can be configured to manage any domain (products, customers, accounts) and includes hierarchies, granular security, transactions, data versioning, and business rules, as well as an [!INCLUDE[ssMDSXLS](../includes/ssmdsxls-md.md)] that can be used to manage data.</span></span>|  
  
|<span data-ttu-id="116f7-164">Ferramentas de gerenciamento</span><span class="sxs-lookup"><span data-stu-id="116f7-164">Management tools</span></span>|<span data-ttu-id="116f7-165">Descrição</span><span class="sxs-lookup"><span data-stu-id="116f7-165">Description</span></span>|  
|----------------------|-----------------|  
|[!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]|<span data-ttu-id="116f7-166">O[!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] é um ambiente integrado para acessar, configurar, gerenciar, administrar e desenvolver os componentes do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="116f7-166">[!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] is an integrated environment to access, configure, manage, administer, and develop components of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="116f7-167">O[!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] permite que os desenvolvedores e administradores de todos os níveis utilizem o [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="116f7-167">[!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] lets developers and administrators of all skill levels use [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>|  
|[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] <span data-ttu-id="116f7-168">Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="116f7-168">Configuration Manager</span></span>|<span data-ttu-id="116f7-169">O[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Configuration Manager fornece gerenciamento básico de configuração para serviços, protocolos do servidor, protocolos do cliente e aliases do cliente do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="116f7-169">[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Configuration Manager provides basic configuration management for [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] services, server protocols, client protocols, and client aliases.</span></span>|  
|[!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)]|[!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] <span data-ttu-id="116f7-170">fornece uma interface gráfica do usuário para monitorar uma instância do [!INCLUDE[ssDE](../includes/ssde-md.md)] ou do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="116f7-170">provides a graphical user interface to monitor an instance of the [!INCLUDE[ssDE](../includes/ssde-md.md)] or [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span>|  
|[!INCLUDE[ssDE](../includes/ssde-md.md)] <span data-ttu-id="116f7-171">Orientador de Otimização</span><span class="sxs-lookup"><span data-stu-id="116f7-171">Tuning Advisor</span></span>|<span data-ttu-id="116f7-172">O Orientador de Otimização do[!INCLUDE[ssDE](../includes/ssde-md.md)] ajuda a criar conjuntos de índices, exibições indexadas e partições ideais.</span><span class="sxs-lookup"><span data-stu-id="116f7-172">[!INCLUDE[ssDE](../includes/ssde-md.md)] Tuning Advisor helps create optimal sets of indexes, indexed views, and partitions.</span></span>|  
|<span data-ttu-id="116f7-173">Cliente Data Quality</span><span class="sxs-lookup"><span data-stu-id="116f7-173">Data Quality Client</span></span>|<span data-ttu-id="116f7-174">Fornece uma interface gráfica do usuário altamente simples e intuitiva para se conectar ao servidor DQS e executar operações de limpeza de dados.</span><span class="sxs-lookup"><span data-stu-id="116f7-174">Provides a highly simple and intuitive graphical user interface to connect to the DQS server, and perform data cleansing operations.</span></span> <span data-ttu-id="116f7-175">Ele também permite monitorar centralmente várias atividades executadas durante a operação de limpeza de dados.</span><span class="sxs-lookup"><span data-stu-id="116f7-175">It also allows you to centrally monitor various activities performed during the data cleansing operation.</span></span>|  
|[!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]|<span data-ttu-id="116f7-176">O[!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)] oferece um IDE para criar soluções para os componentes de Business Intelligence: [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)]e [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="116f7-176">[!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)] provides an IDE for building solutions for the Business Intelligence components: [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)], and [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span></span><br /><br /> <span data-ttu-id="116f7-177">(Antes chamado de Business Intelligence Development Studio).</span><span class="sxs-lookup"><span data-stu-id="116f7-177">(Formerly called Business Intelligence Development Studio).</span></span><br /><br /> <span data-ttu-id="116f7-178">O[!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)] também inclui "Projetos de banco de dados" que oferecem um ambiente integrado para desenvolvedores de banco de dados realizarem seu trabalho de design de banco de dados para qualquer plataforma [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] (no local e fora do local) no Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="116f7-178">[!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)] also includes "Database Projects", which provides an integrated environment for database developers to carry out all their database design work for any [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] platform (both on and off premise) within Visual Studio.</span></span> <span data-ttu-id="116f7-179">Os desenvolvedores de banco de dados podem usar o Gerenciador de Servidores aprimorado no Visual Studio para criar ou editar facilmente objetos de banco de dados e dados, ou executar consultas.</span><span class="sxs-lookup"><span data-stu-id="116f7-179">Database developers can use the enhanced Server Explorer in Visual Studio to easily create or edit database objects and data, or execute queries.</span></span>|  
|<span data-ttu-id="116f7-180">Componentes de conectividade</span><span class="sxs-lookup"><span data-stu-id="116f7-180">Connectivity Components</span></span>|<span data-ttu-id="116f7-181">Instala componentes para comunicação entre clientes e servidores, e bibliotecas de rede para DB-Library, ODBC e OLE DB.</span><span class="sxs-lookup"><span data-stu-id="116f7-181">Installs components for communication between clients and servers, and network libraries for DB-Library, ODBC, and OLE DB.</span></span>|  
  
|<span data-ttu-id="116f7-182">Documentação</span><span class="sxs-lookup"><span data-stu-id="116f7-182">Documentation</span></span>|<span data-ttu-id="116f7-183">Descrição</span><span class="sxs-lookup"><span data-stu-id="116f7-183">Description</span></span>|  
|-------------------|-----------------|  
|[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] <span data-ttu-id="116f7-184">Manuais Online</span><span class="sxs-lookup"><span data-stu-id="116f7-184">Books Online</span></span>|<span data-ttu-id="116f7-185">Documentação principal do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="116f7-185">Core documentation for [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="116f7-186">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="116f7-186">See Also</span></span>  
 <span data-ttu-id="116f7-187">[Planejando uma instalação do SQL Server](install/planning-a-sql-server-installation.md) </span><span class="sxs-lookup"><span data-stu-id="116f7-187">[Planning a SQL Server Installation](install/planning-a-sql-server-installation.md) </span></span>  
 [<span data-ttu-id="116f7-188">Instale o SQL Server 2014 do assistente de instalação &#40;a instalação&#41;</span><span class="sxs-lookup"><span data-stu-id="116f7-188">Install SQL Server 2014 from the Installation Wizard &#40;Setup&#41;</span></span>](../database-engine/install-windows/install-sql-server-from-the-installation-wizard-setup.md)  
  
  