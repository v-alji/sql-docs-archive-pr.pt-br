---
title: Coleta de dados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- data collection [SQL Server]
ms.assetid: 0cc1f95c-5815-4d78-8868-a900be15e674
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 6efa08a0cd9a92690ceac212b005f1f5607d4e5e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570715"
---
# <a name="data-collection"></a><span data-ttu-id="16cbe-102">Coleta de dados</span><span class="sxs-lookup"><span data-stu-id="16cbe-102">Data Collection</span></span>
  <span data-ttu-id="16cbe-103">O Coletor de Dados é um componente do [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] que coleta diferentes conjuntos de dados.</span><span class="sxs-lookup"><span data-stu-id="16cbe-103">The Data Collector is a component of [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] that collects different sets of data.</span></span> <span data-ttu-id="16cbe-104">A coleta de dados é executada constantemente ou em uma agenda definida pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="16cbe-104">Data collection either runs constantly or on a user-defined schedule.</span></span> <span data-ttu-id="16cbe-105">O coletor de dados armazena os dados coletados em um banco de dados relacional conhecido como data warehouse de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="16cbe-105">The data collector stores the collected data in a relational database known as the management data warehouse.</span></span>

## <a name="benefits-of-data-collector"></a><span data-ttu-id="16cbe-106">Benefícios do Coletor de Dados</span><span class="sxs-lookup"><span data-stu-id="16cbe-106">Benefits of Data Collector</span></span>
 <span data-ttu-id="16cbe-107">O coletor de dados é um componente importante da plataforma de coleta de dados para o [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] e para as ferramentas fornecidas pelo [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="16cbe-107">The data collector is a core component of the data collection platform for [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] and the tools that are provided by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="16cbe-108">O coletor de dados fornece um ponto central para coleta de dados em seus servidores de banco de dados e aplicativos.</span><span class="sxs-lookup"><span data-stu-id="16cbe-108">The data collector provides one central point for data collection across your database servers and applications.</span></span> <span data-ttu-id="16cbe-109">Esse ponto de coleta pode obter dados de várias fontes e não se limita apenas aos dados de desempenho, ao contrário do Rastreamento do SQL.</span><span class="sxs-lookup"><span data-stu-id="16cbe-109">This collection point can obtain data from a variety of sources and is not limited to performance data, unlike SQL Trace.</span></span>

 <span data-ttu-id="16cbe-110">O coletor de dados permite ajustar o escopo da coleta de dados para se adéquem a seus ambientes de teste e de produção.</span><span class="sxs-lookup"><span data-stu-id="16cbe-110">The data collector enables you to adjust the scope of data collection to suit your test and production environments.</span></span> <span data-ttu-id="16cbe-111">O coletor de dados também usa o data warehouse, um banco de dados relacional que permite gerenciar os dados coletados configurando diferentes períodos de retenção dos dados.</span><span class="sxs-lookup"><span data-stu-id="16cbe-111">The data collector also uses a data warehouse, a relational database that enables you to manage the data that you collect by setting different retention periods for your data.</span></span>

 <span data-ttu-id="16cbe-112">O coletor de dados oferece suporte ao ajuste dinâmico para coleta de dados e é extensível via API.</span><span class="sxs-lookup"><span data-stu-id="16cbe-112">The data collector supports dynamic tuning for data collection and is extensible through its API.</span></span> <span data-ttu-id="16cbe-113">Para obter mais informações, consulte [Data Collector Programming](../../database-engine/dev-guide/data-collector-programming.md).</span><span class="sxs-lookup"><span data-stu-id="16cbe-113">For more information, see [Data Collector Programming](../../database-engine/dev-guide/data-collector-programming.md).</span></span>

 <span data-ttu-id="16cbe-114">A ilustração a seguir mostra como o coletor de dados se adapta à estratégia geral de coleta e gerenciamento de dados no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="16cbe-114">The following illustration shows how the data collector fits in the overall strategy for data collection and data management in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span>

 <span data-ttu-id="16cbe-115">![A função do coletor de dados no gerenciamento de dados](../../database-engine/media/datacollectorroleindatastrategy.gif "A função do coletor de dados no gerenciamento de dados")</span><span class="sxs-lookup"><span data-stu-id="16cbe-115">![The Data Collector's Role in Data Management](../../database-engine/media/datacollectorroleindatastrategy.gif "The Data Collector's Role in Data Management")</span></span>

## <a name="data-collector-concepts"></a><span data-ttu-id="16cbe-116">Conceitos do Coletor de Dados</span><span class="sxs-lookup"><span data-stu-id="16cbe-116">Data Collector Concepts</span></span>
 <span data-ttu-id="16cbe-117">O coletor de dados é integrado ao [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent e ao [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], e os utiliza extensivamente.</span><span class="sxs-lookup"><span data-stu-id="16cbe-117">The data collector is integrated with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent and [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], and uses both extensively.</span></span> <span data-ttu-id="16cbe-118">Antes de trabalhar com o coletor de dados, você precisa entender determinados conceitos relacionados a cada um desses componentes do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="16cbe-118">Before you work with the data collector, you should therefore understand certain concepts related to each of these [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] components.</span></span>

 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="16cbe-119">O Agente é usado para programar e executar trabalhos de coleta.</span><span class="sxs-lookup"><span data-stu-id="16cbe-119">Agent is used to schedule and run collection jobs.</span></span> <span data-ttu-id="16cbe-120">Você precisa entender os seguintes conceitos:</span><span class="sxs-lookup"><span data-stu-id="16cbe-120">You should understand the following concepts:</span></span>

-   <span data-ttu-id="16cbe-121">Trabalho</span><span class="sxs-lookup"><span data-stu-id="16cbe-121">Job</span></span>

-   <span data-ttu-id="16cbe-122">Etapa de trabalho</span><span class="sxs-lookup"><span data-stu-id="16cbe-122">Job step</span></span>

-   <span data-ttu-id="16cbe-123">Agenda do trabalho</span><span class="sxs-lookup"><span data-stu-id="16cbe-123">Job schedule</span></span>

-   <span data-ttu-id="16cbe-124">Subsistema</span><span class="sxs-lookup"><span data-stu-id="16cbe-124">Subsystem</span></span>

-   <span data-ttu-id="16cbe-125">Contas Proxy</span><span class="sxs-lookup"><span data-stu-id="16cbe-125">Proxy accounts</span></span>

 <span data-ttu-id="16cbe-126">Para obter mais informações, consulte [Tarefas de administração automatizadas &#40;SQL Server Agent&#41;](../../ssms/agent/sql-server-agent.md).</span><span class="sxs-lookup"><span data-stu-id="16cbe-126">For more information, see [Automated Administration Tasks &#40;SQL Server Agent&#41;](../../ssms/agent/sql-server-agent.md).</span></span>

 <span data-ttu-id="16cbe-127">O [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] ([!INCLUDE[ssIS](../../includes/ssis-md.md)]) é usado para executar pacotes que coletam dados de provedores de dados individuais.</span><span class="sxs-lookup"><span data-stu-id="16cbe-127">[!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] ([!INCLUDE[ssIS](../../includes/ssis-md.md)]) is used to execute packages that collect data from individual data providers.</span></span> <span data-ttu-id="16cbe-128">Você precisa estar familiarizado com as seguintes ferramentas e conceitos do [!INCLUDE[ssIS](../../includes/ssis-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="16cbe-128">You should be familiar with the following [!INCLUDE[ssIS](../../includes/ssis-md.md)] tools and concepts:</span></span>

-   <span data-ttu-id="16cbe-129">Pacote [!INCLUDE[ssIS](../../includes/ssis-md.md)]</span><span class="sxs-lookup"><span data-stu-id="16cbe-129">[!INCLUDE[ssIS](../../includes/ssis-md.md)] package</span></span>

-   <span data-ttu-id="16cbe-130">Configuração do pacote [!INCLUDE[ssIS](../../includes/ssis-md.md)]</span><span class="sxs-lookup"><span data-stu-id="16cbe-130">[!INCLUDE[ssIS](../../includes/ssis-md.md)] package configuration</span></span>

 <span data-ttu-id="16cbe-131">Para obter mais informações, consulte [Integration Services &#40;SSIS&#41; Pacotes](../../integration-services/integration-services-ssis-packages.md).</span><span class="sxs-lookup"><span data-stu-id="16cbe-131">For more information, see [Integration Services &#40;SSIS&#41; Packages](../../integration-services/integration-services-ssis-packages.md).</span></span>

## <a name="data-collector-terminology"></a><span data-ttu-id="16cbe-132">Terminologia do Coletor de Dados</span><span class="sxs-lookup"><span data-stu-id="16cbe-132">Data Collector Terminology</span></span>
 <span data-ttu-id="16cbe-133">Direcione uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)] em uma edição do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que dê suporte à coleta de dados.</span><span class="sxs-lookup"><span data-stu-id="16cbe-133">target An instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] in an edition of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that supports Data Collection.</span></span> <span data-ttu-id="16cbe-134">Para obter mais informações sobre as edições com suporte, consulte a seção "gerenciabilidade" dos [recursos com suporte nas edições do SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="16cbe-134">For more information about supported editions, see the "Manageability" section of [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span>

 <span data-ttu-id="16cbe-135">Uma *raiz de destino* define uma subárvore na hierarquia de destino.</span><span class="sxs-lookup"><span data-stu-id="16cbe-135">A *target root* defines a subtree in the target hierarchy.</span></span> <span data-ttu-id="16cbe-136">Um *conjunto de destinos* é o grupo de destinos resultante da aplicação de um filtro a uma subárvore definida por uma raiz de destino.</span><span class="sxs-lookup"><span data-stu-id="16cbe-136">A *target set* is the group of targets that results from applying a filter to a subtree defined by a target root.</span></span> <span data-ttu-id="16cbe-137">Uma raiz de destino pode ser um banco de dados, uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]ou uma instância do computador.</span><span class="sxs-lookup"><span data-stu-id="16cbe-137">A target root can be a database, an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], or a computer instance.</span></span>

 <span data-ttu-id="16cbe-138">tipo de destino o tipo de destino, que tem determinadas características e comportamento.</span><span class="sxs-lookup"><span data-stu-id="16cbe-138">target type The type of target, which has certain characteristics and behavior.</span></span> <span data-ttu-id="16cbe-139">Por exemplo, um destino de instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tem características diferentes das de um destino de banco de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="16cbe-139">For example, a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance target has different characteristics than a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database target.</span></span>

 <span data-ttu-id="16cbe-140">provedor de dados uma fonte de dados conhecida, específica para um tipo de destino que fornece dados para um tipo de coletor.</span><span class="sxs-lookup"><span data-stu-id="16cbe-140">data provider A known data source, specific to a target type, that provides data to a collector type.</span></span>

 <span data-ttu-id="16cbe-141">coletor digite um wrapper lógico em volta dos [!INCLUDE[ssIS](../../includes/ssis-md.md)] pacotes que fornecem o mecanismo real para coletar dados e carregá-los no data warehouse de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="16cbe-141">collector type A logical wrapper around the [!INCLUDE[ssIS](../../includes/ssis-md.md)] packages that provide the actual mechanism for collecting data and uploading it to the management data warehouse.</span></span>

 <span data-ttu-id="16cbe-142">item de coleção uma instância de um tipo de coletor.</span><span class="sxs-lookup"><span data-stu-id="16cbe-142">collection item An instance of a collector type.</span></span> <span data-ttu-id="16cbe-143">Um item de coleta é criado com um conjunto específico de propriedades de entrada e uma frequência de coleta.</span><span class="sxs-lookup"><span data-stu-id="16cbe-143">A collection item is created with a specific set of input properties and a collection frequency.</span></span>

 <span data-ttu-id="16cbe-144">conjunto de coleta um grupo de itens de coleta.</span><span class="sxs-lookup"><span data-stu-id="16cbe-144">collection set A group of collection items.</span></span> <span data-ttu-id="16cbe-145">Um conjunto de coleta é uma unidade de coleta de dados com o qual um usuário pode interagir através da interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="16cbe-145">A collection set is a unit of data collection that a user can interact with through the user interface.</span></span>

 <span data-ttu-id="16cbe-146">modo de coleta da maneira como os dados são coletados e armazenados.</span><span class="sxs-lookup"><span data-stu-id="16cbe-146">collection mode The manner in which the data is collected and stored.</span></span> <span data-ttu-id="16cbe-147">O modo de coleta pode ser em cache ou não cache.</span><span class="sxs-lookup"><span data-stu-id="16cbe-147">Collection mode can be cached or non-cached.</span></span> <span data-ttu-id="16cbe-148">O modo cache dá suporte à coleta contínua, enquanto que o modo não cache destina-se à coleta sob demanda ou a um instantâneo de coleta.</span><span class="sxs-lookup"><span data-stu-id="16cbe-148">Cached mode supports continuous collection, whereas non-cached mode is intended for on-demand collection or a collection snapshot.</span></span>

 <span data-ttu-id="16cbe-149">o data warehouse de gerenciamento de um banco de dados relacional usado para armazenar o dado coletado.</span><span class="sxs-lookup"><span data-stu-id="16cbe-149">management data warehouse A relational database used to store collected data.</span></span>

 <span data-ttu-id="16cbe-150">A ilustração a seguir mostra as dependências e as relações entre os componentes do coletor de dados.</span><span class="sxs-lookup"><span data-stu-id="16cbe-150">The following illustration shows the dependencies and relationships between data collector components.</span></span>

 <span data-ttu-id="16cbe-151">![Dependências funcionais do coletor de dados](../../database-engine/media/dc-functional-dependencies.gif "Dependências funcionais do coletor de dados")</span><span class="sxs-lookup"><span data-stu-id="16cbe-151">![Data collector functional dependencies](../../database-engine/media/dc-functional-dependencies.gif "Data collector functional dependencies")</span></span>

 <span data-ttu-id="16cbe-152">Como mostrado na ilustração, o provedor de dados é externo ao coletor de dados e, por definição, tem uma relação implícita com o destino.</span><span class="sxs-lookup"><span data-stu-id="16cbe-152">As shown in the illustration, the data provider is external to the data collector and by definition has an implicit relationship with the target.</span></span> <span data-ttu-id="16cbe-153">O provedor de dados é específico para um destino específico (por exemplo, um serviço do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] como o mecanismo relacional) e fornece dados como exibições do sistema no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], contadores de Desempenho do Sistema e provedores WMI, que podem ser consumidos pelo coletor de dados.</span><span class="sxs-lookup"><span data-stu-id="16cbe-153">The data provider is specific to a particular target (for example, a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service such as the relational engine) and provides data such as system views in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], Performance Monitor counters, and WMI providers, that can be consumed by the data collector.</span></span>

 <span data-ttu-id="16cbe-154">O tipo de coletor é específico a um tipo de destino, baseado na associação lógica de um provedor de dados a um tipo de destino.</span><span class="sxs-lookup"><span data-stu-id="16cbe-154">The collector type is specific to a target type, based on the logical association of a data provider to a target type.</span></span> <span data-ttu-id="16cbe-155">O tipo de coletor define como os dados são coletados de um provedor de dados específico (usando parâmetros esquematizados) e especifica o esquema de armazenamento de dados.</span><span class="sxs-lookup"><span data-stu-id="16cbe-155">The collector type defines how data is collected from a specific data provider (by using schematized parameters) and specifies the data storage schema.</span></span> <span data-ttu-id="16cbe-156">São necessários o esquema de provedor de dados e o esquema de armazenamento de dados para armazenar os dados coletados.</span><span class="sxs-lookup"><span data-stu-id="16cbe-156">The data provider schema and storage schema are required in order to store the data that is collected.</span></span> <span data-ttu-id="16cbe-157">O tipo de coletor também fornece o local do data warehouse de gerenciamento, que pode ser no computador que está executando a coleta de dados ou em um computador diferente.</span><span class="sxs-lookup"><span data-stu-id="16cbe-157">The collector type also provides the location of the management data warehouse, which can reside on the computer running data collection or on a different computer.</span></span>

 <span data-ttu-id="16cbe-158">Um item de coleta, mostrado na ilustração, é uma instância de um tipo de coletor específico, com parâmetros de entrada, como o esquema XML do tipo de coletor.</span><span class="sxs-lookup"><span data-stu-id="16cbe-158">A collection item, shown in the illustration, is an instance of a specific collector type, parameterized with input parameters, such as the XML schema for the collector type.</span></span> <span data-ttu-id="16cbe-159">Todos os itens de coleta devem funcionar na mesma raiz de destino ou em uma raiz de destino vazia.</span><span class="sxs-lookup"><span data-stu-id="16cbe-159">All collection items must operate on the same target root or on an empty target root.</span></span> <span data-ttu-id="16cbe-160">Isso habilita o coletor de dados a combinar tipos de coletor do sistema operacional ou de uma raiz de destino específica, mas não de raízes de destino diferentes.</span><span class="sxs-lookup"><span data-stu-id="16cbe-160">This enables the data collector to combine collector types from the operating system or from a specific target root, but not from different target roots.</span></span>

 <span data-ttu-id="16cbe-161">Um item de coleta tem uma frequência de coleta definida que determina a frequência com que os instantâneos de valores são feitos.</span><span class="sxs-lookup"><span data-stu-id="16cbe-161">A collection item has a collection frequency defined that determines how often snapshots of values are taken.</span></span> <span data-ttu-id="16cbe-162">Embora seja um bloco de construção para um conjunto de coleta, um item de coleta não existe isoladamente.</span><span class="sxs-lookup"><span data-stu-id="16cbe-162">Although it is a building block for a collection set, a collection item cannot exist on its own.</span></span>

 <span data-ttu-id="16cbe-163">Os conjuntos de coleta são definidos e implantados em uma instância de servidor e podem ser executados independentemente um do outro.</span><span class="sxs-lookup"><span data-stu-id="16cbe-163">Collection sets are defined and deployed on a server instance and can be run independently of each other.</span></span> <span data-ttu-id="16cbe-164">Cada conjunto de coleta pode ser se aplicado a um destino que corresponda aos tipos de destino de todos os tipos de coletor que fazem de um conjunto de coleta.</span><span class="sxs-lookup"><span data-stu-id="16cbe-164">Each collection set can be applied to a target that matches the target types of all the collector types that are part of a collection set.</span></span> <span data-ttu-id="16cbe-165">O conjunto de coleta é executado por um trabalho ou trabalhos do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent, e os dados são carregados no data warehouse de gerenciamento em uma agenda predefinida.</span><span class="sxs-lookup"><span data-stu-id="16cbe-165">The collection set is run by a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job or jobs, and data is uploaded to the management data warehouse on a predefined schedule.</span></span>

 <span data-ttu-id="16cbe-166">Todos os dados coletados por instâncias diferentes dentro do conjunto de coleta são carregados no data warehouse de gerenciamento na mesma agenda.</span><span class="sxs-lookup"><span data-stu-id="16cbe-166">All the data collected by different instances within the collection set is uploaded to the management data warehouse on the same schedule.</span></span> <span data-ttu-id="16cbe-167">Essa agenda é definida como uma agenda compartilhada do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent e pode ser usada por mais de um conjunto de coleta.</span><span class="sxs-lookup"><span data-stu-id="16cbe-167">This schedule is defined as a shared [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent schedule and can be used by more than one collection set.</span></span> <span data-ttu-id="16cbe-168">Um conjunto de coleta é ativado ou desativado como uma entidade única; os itens de coleta não podem ser ativados ou desativados individualmente.</span><span class="sxs-lookup"><span data-stu-id="16cbe-168">A collection set is turned on or turned off as a single entity; collection items cannot be turned on or turned off individually.</span></span>

 <span data-ttu-id="16cbe-169">Ao criar ou atualizar um conjunto de coleta, você pode configurar o modo de coleta para coletar dados e carregá-los no data warehouse de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="16cbe-169">When you create or update a collection set, you can configure the collection mode for collecting data and uploading it to the management data warehouse.</span></span> <span data-ttu-id="16cbe-170">O tipo de agendamento é determinado pelo tipo de coleta: em cache ou não cache.</span><span class="sxs-lookup"><span data-stu-id="16cbe-170">The type of scheduling is determined by the type of collection: cached or non-cached.</span></span> <span data-ttu-id="16cbe-171">Se a coleta for em cache, a coleta e o carregamento de dados serão executados como trabalhos separados.</span><span class="sxs-lookup"><span data-stu-id="16cbe-171">If the collection is cached, data collection and upload each run on a separate job.</span></span> <span data-ttu-id="16cbe-172">A coleta é executada segundo uma agenda que inicia quando o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent é iniciado e executado na frequência especificada no item de coleta.</span><span class="sxs-lookup"><span data-stu-id="16cbe-172">Collection runs on a schedule that starts when the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent starts and it runs on the frequency specified in the collection item.</span></span> <span data-ttu-id="16cbe-173">O carregamento é executado de acordo com a agenda especificada pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="16cbe-173">Upload runs according to the schedule specified by the user.</span></span>

 <span data-ttu-id="16cbe-174">Na coleta não cache, a coleta e o carregamento de dados são executados em um único trabalho, mas em duas etapas.</span><span class="sxs-lookup"><span data-stu-id="16cbe-174">Under non-cached collection, data collection and upload both run on a single job, but in two steps.</span></span> <span data-ttu-id="16cbe-175">A primeira etapa é a coleta, a segunda etapa é o carregamento.</span><span class="sxs-lookup"><span data-stu-id="16cbe-175">Step one is collection, step two is upload.</span></span> <span data-ttu-id="16cbe-176">Nenhuma agenda é necessária para a coleta sob demanda.</span><span class="sxs-lookup"><span data-stu-id="16cbe-176">No schedule is required for on-demand collection.</span></span>

 <span data-ttu-id="16cbe-177">Depois que um conjunto de coleta é habilitado, a coleta de dados pode ser iniciada, de acordo com uma agenda ou sob demanda.</span><span class="sxs-lookup"><span data-stu-id="16cbe-177">After a collection set is enabled, data collection can start, either according to a schedule or on demand.</span></span> <span data-ttu-id="16cbe-178">Quando a coleta de dados iniciar, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent gera um processo para o coletor de dados, que em troca carrega os pacotes do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] no conjunto de coleta.</span><span class="sxs-lookup"><span data-stu-id="16cbe-178">When data collection starts, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent spawns a process for the data collector, which in turn loads the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages for the collection set.</span></span> <span data-ttu-id="16cbe-179">Os itens de coleta que representam tipos de coleta reúnem dados dos provedores de dados apropriados nos destinos especificados.</span><span class="sxs-lookup"><span data-stu-id="16cbe-179">The collection items, which represent collection types, gather data from the appropriate data providers on the specified targets.</span></span> <span data-ttu-id="16cbe-180">Quando o ciclo de coleta termina, os dados são carregados no data warehouse de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="16cbe-180">When the collection cycle ends, this data is uploaded to the management data warehouse.</span></span>

## <a name="data-collector-tasks"></a><span data-ttu-id="16cbe-181">Tarefas do Coletor de Dados</span><span class="sxs-lookup"><span data-stu-id="16cbe-181">Data Collector Tasks</span></span>

|<span data-ttu-id="16cbe-182">Descrição da tarefa</span><span class="sxs-lookup"><span data-stu-id="16cbe-182">Task Description</span></span>|<span data-ttu-id="16cbe-183">Tópico</span><span class="sxs-lookup"><span data-stu-id="16cbe-183">Topic</span></span>|
|----------------------|-----------|
|<span data-ttu-id="16cbe-184">Descreve como gerenciar diferentes aspectos da coleta de dados; por exemplo, habilitar ou desabilitar a coleta de dados, alterar a configuração de um conjunto de coleta ou exibir dados no data warehouse de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="16cbe-184">Describes how to manage different aspects of data collection, such as enabling or disabling data collection, changing a collection set configuration, or viewing data in the management data warehouse.</span></span>|[<span data-ttu-id="16cbe-185">Gerenciar coleta de dados</span><span class="sxs-lookup"><span data-stu-id="16cbe-185">Manage Data Collection</span></span>](manage-data-collection.md)|
|<span data-ttu-id="16cbe-186">Descreve como usar os relatórios para obter informações sobre o monitoramento da capacidade do sistema e a solução de problemas de desempenho do sistema.</span><span class="sxs-lookup"><span data-stu-id="16cbe-186">Describes how to use reports to obtain information for monitoring system capacity and troubleshooting system performance.</span></span>|[<span data-ttu-id="16cbe-187">Relatórios do conjunto de coleta de dados do sistema</span><span class="sxs-lookup"><span data-stu-id="16cbe-187">System Data Collection Set Reports</span></span>](system-data-collection-set-reports.md)|
|<span data-ttu-id="16cbe-188">Descreve como usar o Data Warehouse de Gerenciamento para coletar dados de um servidor que seja o destino da coleta de dados.</span><span class="sxs-lookup"><span data-stu-id="16cbe-188">Describes how to use the Management Data Warehouse to collect data from a server that is a data collection target.</span></span>|[<span data-ttu-id="16cbe-189">Data warehouse de gerenciamento</span><span class="sxs-lookup"><span data-stu-id="16cbe-189">Management Data Warehouse</span></span>](management-data-warehouse.md)|

