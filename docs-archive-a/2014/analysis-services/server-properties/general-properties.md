---
title: Propriedades gerais | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- IdleConnectionTimeout property
- InstanceVisible property
- TempDir property
- AdminTimeout property
- MinIdleSessionTimeout property
- MaxIdleSessionTimeout property
- IdleOrphanSessionTimeout property
- BackupDir property
- CommitTimeout property
- ExternalCommandTimeout property
- Enabled property
- ForceCommitTimeout property
- Port property
- CoordinatorShutdownMode property
- ServerTimeout property
- AllowedBrowsingFolders property
- CoordinatorCancelCount property
- DataDir property
- CoordinatorQueryMaxThreads property
- CoordinatorExecutionMode property
- ExternalConnectionTimeout property
- CollationName property
- EnableFast1033Locale property
- CoordinatorBuildMaxThreads property
- Language property
- StatisticsStoreSize property
- RepositoryConnectionString property
ms.assetid: 88a8117c-396a-469f-a62d-c6f262504021
author: minewiskan
ms.author: owend
ms.openlocfilehash: ca746a1bb57e84cf0f6a8f47622b118c7180eb1c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87686395"
---
# <a name="general-properties"></a><span data-ttu-id="73a7f-102">Propriedades gerais</span><span class="sxs-lookup"><span data-stu-id="73a7f-102">General Properties</span></span>
  [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="73a7f-103">oferece suporte às propriedades do servidor listadas nas tabelas a seguir.</span><span class="sxs-lookup"><span data-stu-id="73a7f-103">supports the server properties listed in the following tables.</span></span> <span data-ttu-id="73a7f-104">Este tópico documenta essas propriedades de servidor no arquivo msmdsrv.ini que não são incluídas em uma seção específica, como Segurança, Rede ou ThreadPool.</span><span class="sxs-lookup"><span data-stu-id="73a7f-104">This topic documents those server properties in the msmdsrv.ini file that are not otherwise included in a specific section, such as Security, Network, or ThreadPool.</span></span> <span data-ttu-id="73a7f-105">Para obter mais informações sobre as propriedades de servidor adicionais e como defini-las, consulte [Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="73a7f-105">For more information about additional server properties and how to set them, see [Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md).</span></span>  
  
 <span data-ttu-id="73a7f-106">**Aplica-se a:** modo de servidor Multidimensional e de Tabela, a menos que indicado em contrário</span><span class="sxs-lookup"><span data-stu-id="73a7f-106">**Applies to:** Multidimensional and Tabular server mode, unless noted otherwise</span></span>  
  
## <a name="non-specific-category"></a><span data-ttu-id="73a7f-107">Categoria não específica</span><span class="sxs-lookup"><span data-stu-id="73a7f-107">Non-Specific Category</span></span>  
 `AdminTimeout`  
 <span data-ttu-id="73a7f-108">Uma propriedade de inteiro de 32 bits assinada que define o tempo limite do administrador em segundos.</span><span class="sxs-lookup"><span data-stu-id="73a7f-108">A signed 32-bit integer property that defines the administrator timeout in seconds.</span></span> <span data-ttu-id="73a7f-109">Essa é uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="73a7f-109">This is an advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 <span data-ttu-id="73a7f-110">O valor padrão dessa propriedade é zero (0), que indica que não há tempo limite.</span><span class="sxs-lookup"><span data-stu-id="73a7f-110">The default value for this property is zero (0), which indicates there is no timeout.</span></span>  
  
 `AllowedBrowsingFolders`  
 <span data-ttu-id="73a7f-111">Uma propriedade de cadeia de caracteres que especifica em uma lista delimitada as pastas que podem ser procuradas ao salvar, abrir e localizar arquivos em caixas de diálogo do Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="73a7f-111">A string property that specifies in a delimited list the folders that can be browsed when saving, opening, and finding files in Analysis Services dialog boxes.</span></span> <span data-ttu-id="73a7f-112">A conta de serviço do Analysis Services deve ter permissões de leitura e gravação em qualquer pasta adicionada à lista.</span><span class="sxs-lookup"><span data-stu-id="73a7f-112">The Analysis Services service account must have read and write permissions to any folders that you add to the list.</span></span>  
  
 `BackupDir`  
 <span data-ttu-id="73a7f-113">Uma propriedade de cadeia de caracteres que identifica o nome do diretório em que os arquivos de backup são armazenados por padrão, no caso de um caminho não ser especificado como parte do comando de backup.</span><span class="sxs-lookup"><span data-stu-id="73a7f-113">A string property that identifies the name of the directory where backup files are stored by default, in the event a path is not specified as part of the Backup command.</span></span>  
  
 `CollationName`  
 <span data-ttu-id="73a7f-114">Uma propriedade de cadeia de caracteres que identifica a ordenação do servidor.</span><span class="sxs-lookup"><span data-stu-id="73a7f-114">A string property that identifies the server collation.</span></span> <span data-ttu-id="73a7f-115">Para obter mais informações, consulte [Idiomas e ordenações &#40;Analysis Services&#41;](../languages-and-collations-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="73a7f-115">For more information, see [Languages and Collations &#40;Analysis Services&#41;](../languages-and-collations-analysis-services.md).</span></span>  
  
 `CommitTimeout`  
 <span data-ttu-id="73a7f-116">Uma propriedade integer que especifica quanto tempo (em milissegundos) o servidor aguardará para adquirir um bloqueio de gravação visando confirmar uma transação.</span><span class="sxs-lookup"><span data-stu-id="73a7f-116">An integer property that specifies how long (in milliseconds) the server will wait to acquire a write lock for the purpose of committing a transaction.</span></span> <span data-ttu-id="73a7f-117">Um período de espera costuma ser necessário porque o servidor precisa aguardar que outros bloqueios sejam liberados para usar um bloqueio de gravação que confirme a transação.</span><span class="sxs-lookup"><span data-stu-id="73a7f-117">A waiting period is often required because the server must wait for other locks to be released before it can take a write lock that commits the transaction.</span></span>  
  
 <span data-ttu-id="73a7f-118">O valor padrão para esta propriedade é zero (0), o que indica que o servidor aguardará indefinidamente.</span><span class="sxs-lookup"><span data-stu-id="73a7f-118">The default value for this property is zero (0), which indicates that the server will wait indefinitely.</span></span> <span data-ttu-id="73a7f-119">Para obter mais informações sobre propriedades relacionadas a bloqueio, consulte [Guia de Operações do SQL Server 2008 R2 Analysis Services](https://go.microsoft.com/fwlink/?LinkID=225539).</span><span class="sxs-lookup"><span data-stu-id="73a7f-119">For more information about lock-related properties, see [SQL Server 2008 R2 Analysis Services Operations Guide](https://go.microsoft.com/fwlink/?LinkID=225539).</span></span>  
  
 `CoordinatorBuildMaxThreads`  
 <span data-ttu-id="73a7f-120">Uma propriedade de inteiro de 32 bits assinada que define o número máximo de threads alocados à criação de índices de partição.</span><span class="sxs-lookup"><span data-stu-id="73a7f-120">A signed 32-bit integer property that defines the maximum number of threads allocated to building partition indexes.</span></span> <span data-ttu-id="73a7f-121">Aumente esse valor para acelerar a indexação da partição, pelo uso da memória.</span><span class="sxs-lookup"><span data-stu-id="73a7f-121">Increase this value in order to speed-up partition indexing, at the cost of memory usage.</span></span> <span data-ttu-id="73a7f-122">Para obter mais informações sobre esta propriedade, consulte [Guia de Operações do SQL Server 2008 R2 Analysis Services](https://go.microsoft.com/fwlink/?LinkID=225539).</span><span class="sxs-lookup"><span data-stu-id="73a7f-122">For more information about this property, see [SQL Server 2008 R2 Analysis Services Operations Guide](https://go.microsoft.com/fwlink/?LinkID=225539).</span></span>  
  
 `CoordinatorCancelCount`  
 <span data-ttu-id="73a7f-123">Uma propriedade de inteiro de 32 bits assinada que define com que frequência o servidor deve verificar se um evento de cancelamento ocorreu (com base na contagem de iterações internas).</span><span class="sxs-lookup"><span data-stu-id="73a7f-123">A signed 32-bit integer property that defines how frequently the server should check whether a Cancel event occurred (based on internal iteration count).</span></span> <span data-ttu-id="73a7f-124">Diminua esse número para verificar cancelamentos frequentemente pelo desempenho geral.</span><span class="sxs-lookup"><span data-stu-id="73a7f-124">Decrease this number in order to check for Cancel more frequently, at the expense of general performance.</span></span>  
  
 <span data-ttu-id="73a7f-125">`CoordinatorCancelCount` é ignorado no modo de servidor de tabela.</span><span class="sxs-lookup"><span data-stu-id="73a7f-125">`CoordinatorCancelCount` is ignored in tabular server mode.</span></span>  
  
 `CoordinatorExecutionMode`  
 <span data-ttu-id="73a7f-126">Uma propriedade de inteiro de 32 bits assinada que define o número máximo de operações paralelas que o servidor tentará, incluindo operações de processamento e consulta.</span><span class="sxs-lookup"><span data-stu-id="73a7f-126">A signed 32-bit integer property that defines the maximum number of parallel operations the server will attempt, including processing and querying operations.</span></span> <span data-ttu-id="73a7f-127">Zero (0) indica que o servidor decidirá, com base em um algoritmo interno.</span><span class="sxs-lookup"><span data-stu-id="73a7f-127">Zero (0) indicates that the server will decide, based on an internal algorithm.</span></span> <span data-ttu-id="73a7f-128">Um número positivo indica o número máximo de operações no total.</span><span class="sxs-lookup"><span data-stu-id="73a7f-128">A positive number indicates the maximum number of operations in total.</span></span> <span data-ttu-id="73a7f-129">Um número negativo, com o sinal invertido, indica o número máximo de operações por processador.</span><span class="sxs-lookup"><span data-stu-id="73a7f-129">A negative number, with the sign reversed, indicates the maximum number of operations per processor.</span></span>  
  
 <span data-ttu-id="73a7f-130">`CoordinatorExecutionMode` é ignorado no modo de servidor de tabela.</span><span class="sxs-lookup"><span data-stu-id="73a7f-130">`CoordinatorExecutionMode` is ignored in tabular server mode.</span></span>  
  
 <span data-ttu-id="73a7f-131">O valor padrão dessa propriedade é -4, que indica que o servidor está limitado a 4 operações paralelas por processador.</span><span class="sxs-lookup"><span data-stu-id="73a7f-131">The default value for this property is -4, which indicates the server is limited to 4 parallel operations per processor.</span></span> <span data-ttu-id="73a7f-132">Para obter mais informações sobre esta propriedade, consulte [Guia de Operações do SQL Server 2008 R2 Analysis Services](https://go.microsoft.com/fwlink/?LinkID=225539).</span><span class="sxs-lookup"><span data-stu-id="73a7f-132">For more information about this property, see [SQL Server 2008 R2 Analysis Services Operations Guide](https://go.microsoft.com/fwlink/?LinkID=225539).</span></span>  
  
 `CoordinatorQueryMaxThreads`  
 <span data-ttu-id="73a7f-133">Uma propriedade de inteiro de 32 bits assinada que define o número máximo de threads por segmento da partição durante a resolução da consulta.</span><span class="sxs-lookup"><span data-stu-id="73a7f-133">A signed 32-bit integer property that defines the maximum number of threads per partition segment during query resolution.</span></span> <span data-ttu-id="73a7f-134">Quanto menor o número de usuários simultâneos, mais alto o valor pode ser, devido ao uso da memória.</span><span class="sxs-lookup"><span data-stu-id="73a7f-134">The fewer the number of concurrent users, the higher this value can be, at the cost of memory.</span></span> <span data-ttu-id="73a7f-135">Inversamente, pode ser necessário baixar o valor se houver um grande número de usuários simultâneos.</span><span class="sxs-lookup"><span data-stu-id="73a7f-135">Conversely, it may need to be lowered if there are a large number of concurrent users.</span></span>  
  
 `CoordinatorShutdownMode`  
 <span data-ttu-id="73a7f-136">Uma propriedade booliana que define modo de desligamento de coordenador.</span><span class="sxs-lookup"><span data-stu-id="73a7f-136">A Boolean property that defines coordinator shutdown mode.</span></span> <span data-ttu-id="73a7f-137">Essa é uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="73a7f-137">This is an advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `DataDir`  
 <span data-ttu-id="73a7f-138">Uma propriedade de cadeia de caracteres que identifica o nome do diretório onde os dados são armazenados.</span><span class="sxs-lookup"><span data-stu-id="73a7f-138">A string property that identifies the name of the directory where data is stored.</span></span>  
  
 `DeploymentMode`  
 <span data-ttu-id="73a7f-139">Determina o contexto operacional de uma instância de servidor do Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="73a7f-139">Determines the operational context of an Analysis Services server instance.</span></span> <span data-ttu-id="73a7f-140">Essa propriedade é conhecida como ' modo de servidor ' em caixas de diálogo, mensagens e documentação.</span><span class="sxs-lookup"><span data-stu-id="73a7f-140">This property is referred to as 'server mode' in dialog boxes, messages, and documentation.</span></span> <span data-ttu-id="73a7f-141">Esta propriedade é configurada pela Instalação do SQL Server com base no modo de servidor selecionado ao instalar o Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="73a7f-141">This property is configured by SQL Server Setup based on the server mode you selected when installing Analysis Services.</span></span> <span data-ttu-id="73a7f-142">Esta propriedade deve ser considerada apenas interna, sempre usando o valor especificado pela Instalação.</span><span class="sxs-lookup"><span data-stu-id="73a7f-142">This property should be considered internal only, always using the value specified by Setup.</span></span>  
  
 <span data-ttu-id="73a7f-143">Os valores válidos para essa propriedade incluem os seguintes:</span><span class="sxs-lookup"><span data-stu-id="73a7f-143">Valid values for this property include the following:</span></span>  
  
|<span data-ttu-id="73a7f-144">Valor</span><span class="sxs-lookup"><span data-stu-id="73a7f-144">Value</span></span>|<span data-ttu-id="73a7f-145">Descrição</span><span class="sxs-lookup"><span data-stu-id="73a7f-145">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="73a7f-146">0</span><span class="sxs-lookup"><span data-stu-id="73a7f-146">0</span></span>|<span data-ttu-id="73a7f-147">Este é o valor padrão.</span><span class="sxs-lookup"><span data-stu-id="73a7f-147">This is the default value.</span></span> <span data-ttu-id="73a7f-148">Ele especifica o modo multidimensional, usado para atender bancos de dados multidimensionais que usam o armazenamento MOLAP, HOLAP e ROLAP, bem como modelos de mineração de dados.</span><span class="sxs-lookup"><span data-stu-id="73a7f-148">It specifies multidimensional mode, used to service multidimensional databases that use MOLAP, HOLAP, and ROLAP storage, as well as data mining models.</span></span>|  
|<span data-ttu-id="73a7f-149">1</span><span class="sxs-lookup"><span data-stu-id="73a7f-149">1</span></span>|<span data-ttu-id="73a7f-150">Especifica instâncias do Analysis Services que foram instaladas como parte de um PowerPivot para implantação do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="73a7f-150">Specifies Analysis Services instances that were installed as part of a PowerPivot for SharePoint deployment.</span></span> <span data-ttu-id="73a7f-151">Não altere a propriedade de modo de implantação da instância do Analysis Services que faz parte de uma instalação do PowerPivot para SharePoint.</span><span class="sxs-lookup"><span data-stu-id="73a7f-151">Do not change the deployment mode property of Analysis Services instance that is part of a PowerPivot for SharePoint installation.</span></span> <span data-ttu-id="73a7f-152">Dados PowerPivot não serão mais executados no servidor se você alterar o modo.</span><span class="sxs-lookup"><span data-stu-id="73a7f-152">PowerPivot data will no longer run on the server if you change the mode.</span></span>|  
|<span data-ttu-id="73a7f-153">2</span><span class="sxs-lookup"><span data-stu-id="73a7f-153">2</span></span>|<span data-ttu-id="73a7f-154">Especifica o modo de Tabela usado para hospedar bancos de dados modelo de tabela que usam o armazenamento na memória ou o armazenamento DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="73a7f-154">Specifies Tabular mode used for hosting tabular model databases that use in-memory storage or DirectQuery storage.</span></span>|  
  
 <span data-ttu-id="73a7f-155">Cada modo é exclusivo do outro.</span><span class="sxs-lookup"><span data-stu-id="73a7f-155">Each mode is exclusive of the other.</span></span> <span data-ttu-id="73a7f-156">Um servidor que é configurado para o modo de tabela não pode executar bancos de dados do Analysis Services que contêm cubos e dimensões.</span><span class="sxs-lookup"><span data-stu-id="73a7f-156">A server that is configured for tabular mode cannot run Analysis Services databases that contain cubes and dimensions.</span></span> <span data-ttu-id="73a7f-157">Se o hardware subjacente der suporte a isso, você poderá instalar várias instâncias do Analysis Services no mesmo computador e configurar cada instância para usar um modo de implantação diferente.</span><span class="sxs-lookup"><span data-stu-id="73a7f-157">If the underlying computer hardware can support it, you can install multiple instances of Analysis Services on the same computer and configure each instance to use a different deployment mode.</span></span> <span data-ttu-id="73a7f-158">Lembre-se de que o Analysis Services é um aplicativo que utiliza vários recursos.</span><span class="sxs-lookup"><span data-stu-id="73a7f-158">Remember that Analysis Services is a resource intensive application.</span></span> <span data-ttu-id="73a7f-159">A implantação de várias instâncias no mesmo sistema é recomendada somente para servidores high-end.</span><span class="sxs-lookup"><span data-stu-id="73a7f-159">Deploying multiple instances on the same system is recommended only for high-end servers.</span></span>  
  
 `EnableFast1033Locale`  
 <span data-ttu-id="73a7f-160">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="73a7f-160">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `ExternalCommandTimeout`  
 <span data-ttu-id="73a7f-161">Uma propriedade integer que define o tempo limite, em segundos, para comandos emitidos para servidores externos, incluindo fontes de dados relacionais e servidores externos do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="73a7f-161">An integer property that defines the timeout, in seconds, for commands issued to external servers, including relational data sources and external [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] servers.</span></span>  
  
 <span data-ttu-id="73a7f-162">O valor padrão desta propriedade é 3600 (segundos).</span><span class="sxs-lookup"><span data-stu-id="73a7f-162">The default value for this property is 3600 (seconds).</span></span>  
  
 `ExternalConnectionTimeout`  
 <span data-ttu-id="73a7f-163">Uma propriedade de número inteiro que define o tempo limite, em segundos, para criar conexões a servidores externos, incluindo fontes de dados relacionais e servidores externos do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="73a7f-163">An integer property that defines the timeout, in seconds, for creating connections to external servers, including relational data sources and external [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] servers.</span></span> <span data-ttu-id="73a7f-164">Esta propriedade é ignorada quando o tempo limite de uma conexão é especificado na cadeia de conexão.</span><span class="sxs-lookup"><span data-stu-id="73a7f-164">This property is ignored if a connection timeout is specified on the connection string.</span></span>  
  
 <span data-ttu-id="73a7f-165">O valor padrão desta propriedade é 60 (segundos).</span><span class="sxs-lookup"><span data-stu-id="73a7f-165">The default value for this property is 60 (seconds).</span></span>  
  
 `ForceCommitTimeout`  
 <span data-ttu-id="73a7f-166">Uma propriedade integer que especifica quanto tempo, em milissegundos, uma operação de confirmação de gravação deve aguardar para cancelar outros comandos que precederam o comando atual, inclusive consultas em andamento.</span><span class="sxs-lookup"><span data-stu-id="73a7f-166">An integer property that specifies how long, in milliseconds, a write commit operation should wait before canceling other commands that preceded the current command, including queries in progress.</span></span> <span data-ttu-id="73a7f-167">Isso permite que a transação de confirmação prossiga, cancelando operações de menor prioridade, como consultas.</span><span class="sxs-lookup"><span data-stu-id="73a7f-167">This allows the commit transaction to proceed by canceling lower priority operations, such as queries.</span></span>  
  
 <span data-ttu-id="73a7f-168">O valor padrão desta propriedade é 30 segundos (30000 milissegundos), o que indica que outros comandos serão forçados a atingir o tempo limite até que a transação de confirmação tenha aguardado por 30 segundos.</span><span class="sxs-lookup"><span data-stu-id="73a7f-168">The default value for this property is 30 seconds (30000 milliseconds), which indicates that other commands will not be forced to timeout until the commit transaction has been waiting for 30 seconds.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="73a7f-169">Consultas e processos cancelados por este evento relatarão a seguinte mensagem de erro: "`Server: The operation has been cancelled`"</span><span class="sxs-lookup"><span data-stu-id="73a7f-169">Queries and processes cancelled by this event will report the following error message: "`Server: The operation has been cancelled`"</span></span>  
  
 <span data-ttu-id="73a7f-170">Para obter mais informações sobre esta propriedade, consulte [Guia de Operações do SQL Server 2008 R2 Analysis Services](https://go.microsoft.com/fwlink/?LinkID=225539).</span><span class="sxs-lookup"><span data-stu-id="73a7f-170">For more information about this property, see [SQL Server 2008 R2 Analysis Services Operations Guide](https://go.microsoft.com/fwlink/?LinkID=225539).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="73a7f-171">`ForceCommitTimeout` é aplicado para comandos de processamento de cubo e para operações de writeback.</span><span class="sxs-lookup"><span data-stu-id="73a7f-171">`ForceCommitTimeout` applies to cube processing commands and to writeback operations.</span></span>  
  
 `IdleConnectionTimeout`  
 <span data-ttu-id="73a7f-172">Uma propriedade integer que especifica um tempo limite, em segundos, para conexões que estão inativas.</span><span class="sxs-lookup"><span data-stu-id="73a7f-172">An integer property that specifies a timeout, in seconds, for connections that are inactive.</span></span>  
  
 <span data-ttu-id="73a7f-173">O valor padrão dessa propriedade é zero (0), que indica que não há tempo limite para conexões ociosas.</span><span class="sxs-lookup"><span data-stu-id="73a7f-173">The default value for this property is zero (0), which indicates that idle connections will not be timed out.</span></span>  
  
 `IdleOrphanSessionTimeout`  
 <span data-ttu-id="73a7f-174">Uma propriedade integer que define por quanto tempo, em segundos, sessões desligadas serão retidas na memória do servidor.</span><span class="sxs-lookup"><span data-stu-id="73a7f-174">An integer property that defines how long, in seconds, orphaned sessions will be retained in server memory.</span></span> <span data-ttu-id="73a7f-175">Uma sessão desligada não tem mais uma conexão associada.</span><span class="sxs-lookup"><span data-stu-id="73a7f-175">An orphaned session is one that no longer has an associated connection.</span></span> <span data-ttu-id="73a7f-176">O padrão é 120 segundos.</span><span class="sxs-lookup"><span data-stu-id="73a7f-176">The default is 120 seconds.</span></span>  
  
 `InstanceVisible`  
 <span data-ttu-id="73a7f-177">Uma propriedade Booliana que indica se a instância do servidor está visível para descobrir solicitações de instância do serviço do Navegador do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="73a7f-177">A Boolean property that indicates whether the server instance is visible to discover instance requests from SQL Server Browser service.</span></span> <span data-ttu-id="73a7f-178">O padrão é True.</span><span class="sxs-lookup"><span data-stu-id="73a7f-178">The default is True.</span></span> <span data-ttu-id="73a7f-179">Se você defini-lo como false, a instância não ficará visível para o Navegador do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="73a7f-179">If you set it to false, the instance is not visible to SQL Server Browser.</span></span>  
  
 `Language`  
 <span data-ttu-id="73a7f-180">Uma propriedade de cadeia de caracteres que define o idioma, inclusive de mensagens de erro e formatação de números.</span><span class="sxs-lookup"><span data-stu-id="73a7f-180">A string property that defines the language, including error messages and number formatting.</span></span> <span data-ttu-id="73a7f-181">Essa propriedade substitui a propriedade CollationName.</span><span class="sxs-lookup"><span data-stu-id="73a7f-181">This property overrides the CollationName property.</span></span>  
  
 <span data-ttu-id="73a7f-182">O valor padrão dessa propriedade é em branco, que indica que a propriedade CollationName define o idioma.</span><span class="sxs-lookup"><span data-stu-id="73a7f-182">The default value for this property is blank, which indicates that the CollationName property defines the language.</span></span>  
  
 `LogDir`  
 <span data-ttu-id="73a7f-183">Uma propriedade de cadeia de caracteres que identifica o nome do diretório que contém os logs de servidor.</span><span class="sxs-lookup"><span data-stu-id="73a7f-183">A string property that identifies the name of the directory that contains server logs.</span></span> <span data-ttu-id="73a7f-184">Essa propriedade só se aplica quando os arquivos do disco são usados para log, em vez de tabelas de banco de dados (o comportamento padrão).</span><span class="sxs-lookup"><span data-stu-id="73a7f-184">This property only applies when disk files are used for logging, as opposed to database tables (the default behavior).</span></span>  
  
 `MaxIdleSessionTimeout`  
 <span data-ttu-id="73a7f-185">Uma propriedade integer que define o tempo limite máximo de sessão inativa, em segundos.</span><span class="sxs-lookup"><span data-stu-id="73a7f-185">An integer property that defines the maximum idle session timeout, in seconds.</span></span> <span data-ttu-id="73a7f-186">O padrão é zero (0), indicando que as sessões nunca expiram. No entanto, as sessões ociosas ainda serão removidas se o servidor estiver sob restrições de recurso.</span><span class="sxs-lookup"><span data-stu-id="73a7f-186">The default is zero (0), indicating that sessions are never timed out. However, idle sessions will still be removed if the server is under resource constraints.</span></span>  
  
 `MinIdleSessionTimeout`  
 <span data-ttu-id="73a7f-187">Uma propriedade integer que define o tempo mínimo, em segundos, para expiração de sessões inativas.</span><span class="sxs-lookup"><span data-stu-id="73a7f-187">An integer property that defines the minimum time, in seconds, that idle sessions will timeout.</span></span> <span data-ttu-id="73a7f-188">O padrão é 2700 segundos.</span><span class="sxs-lookup"><span data-stu-id="73a7f-188">The default is 2700 seconds.</span></span> <span data-ttu-id="73a7f-189">Depois que esse tempo expirar, o servidor poderá encerrar a sessão ociosa, mas só fará isso se houver necessidade de memória.</span><span class="sxs-lookup"><span data-stu-id="73a7f-189">After this time expires, the server is permitted to end the idle session, but will only do so as memory is needed.</span></span>  
  
 `Port`  
 <span data-ttu-id="73a7f-190">Uma propriedade integer que define o número da porta em que o servidor escutará conexões de clientes.</span><span class="sxs-lookup"><span data-stu-id="73a7f-190">An integer property that defines the port number on which server will listen for client connections.</span></span> <span data-ttu-id="73a7f-191">Se não definida, o servidor localizará dinamicamente a primeira porta não usada.</span><span class="sxs-lookup"><span data-stu-id="73a7f-191">If not set, server dynamically finds first unused port.</span></span>  
  
 <span data-ttu-id="73a7f-192">O valor padrão dessa propriedade é zero (0) que, por sua vez, assume a porta 2383 como padrão.</span><span class="sxs-lookup"><span data-stu-id="73a7f-192">The default value for this property is zero (0), which in turn defaults to port 2383.</span></span> <span data-ttu-id="73a7f-193">Para obter mais informações sobre a configuração da porta, consulte [Configure the Windows Firewall to Allow Analysis Services Access](../instances/configure-the-windows-firewall-to-allow-analysis-services-access.md).</span><span class="sxs-lookup"><span data-stu-id="73a7f-193">For more information about port configuration, see [Configure the Windows Firewall to Allow Analysis Services Access](../instances/configure-the-windows-firewall-to-allow-analysis-services-access.md).</span></span>  
  
 `ServerTimeout`  
 <span data-ttu-id="73a7f-194">Um integer que define o tempo limite, em segundos, para consultas.</span><span class="sxs-lookup"><span data-stu-id="73a7f-194">An integer that defines the timeout, in seconds, for queries.</span></span> <span data-ttu-id="73a7f-195">O padrão é 3600 segundos (ou 60 minutos).</span><span class="sxs-lookup"><span data-stu-id="73a7f-195">The default is 3600 seconds (or 60 minutes).</span></span> <span data-ttu-id="73a7f-196">Zero (0) especifica que nenhuma consulta expirará.</span><span class="sxs-lookup"><span data-stu-id="73a7f-196">Zero (0) specifies that no queries will timeout.</span></span>  
  
 `TempDir`  
 <span data-ttu-id="73a7f-197">Uma propriedade de cadeia de caracteres que especifica o local para armazenar arquivos temporários usados durante o processamento, a restauração e outras operações.</span><span class="sxs-lookup"><span data-stu-id="73a7f-197">A string property that specifies the location for storing temporary files used during processing, restoring, and other operations.</span></span> <span data-ttu-id="73a7f-198">O valor padrão desta propriedade é determinado por configuração.</span><span class="sxs-lookup"><span data-stu-id="73a7f-198">The default value for this property is determined by setup.</span></span> <span data-ttu-id="73a7f-199">Se não especificado, o padrão será o diretório de Dados.</span><span class="sxs-lookup"><span data-stu-id="73a7f-199">If not specified, the default is the Data directory.</span></span>  
  
## <a name="requestprioritization-category"></a><span data-ttu-id="73a7f-200">Categoria RequestPrioritization</span><span class="sxs-lookup"><span data-stu-id="73a7f-200">RequestPrioritization Category</span></span>  
 `Enabled`  
 <span data-ttu-id="73a7f-201">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="73a7f-201">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `StatisticsStoreSize`  
 <span data-ttu-id="73a7f-202">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="73a7f-202">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73a7f-203">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="73a7f-203">See Also</span></span>  
 <span data-ttu-id="73a7f-204">[Configurar propriedades do servidor no Analysis Services](server-properties-in-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="73a7f-204">[Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md) </span></span>  
 [<span data-ttu-id="73a7f-205">Determina o Modo de Servidor de uma instância do Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="73a7f-205">Determine the Server Mode of an Analysis Services Instance</span></span>](../instances/determine-the-server-mode-of-an-analysis-services-instance.md)  
  
  
