---
title: Componentes do servidor do mecanismo OLAP | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- Analysis Services, architecture
- ports [Analysis Services]
- XML/A listener
- server architecture [Analysis Services]
ms.assetid: 5193c976-9dcd-459c-abba-8c3c44e7a7f2
author: minewiskan
ms.author: owend
ms.openlocfilehash: b60d721a69213ad52536830b49b40d6bb82a3811
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684935"
---
# <a name="olap-engine-server-components"></a><span data-ttu-id="69fb9-102">Componentes do servidor de mecanismo OLAP</span><span class="sxs-lookup"><span data-stu-id="69fb9-102">OLAP Engine Server Components</span></span>
  <span data-ttu-id="69fb9-103">O componente de servidor do [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] é o **msmdsrv.exe** aplicativo, que é executado como um serviço do Windows.</span><span class="sxs-lookup"><span data-stu-id="69fb9-103">The server component of [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] is the **msmdsrv.exe** application, which runs as a Windows service.</span></span> <span data-ttu-id="69fb9-104">Esse aplicativo consiste em componentes de segurança, um componente de ouvinte do XML for Analysis (XMLA), um componente de processador de consulta e vários outros componentes internos que executam as seguintes funções:</span><span class="sxs-lookup"><span data-stu-id="69fb9-104">This application consists of security components, an XML for Analysis (XMLA) listener component, a query processor component and numerous other internal components that perform the following functions:</span></span>

-   <span data-ttu-id="69fb9-105">Análise de instruções recebidas dos clientes</span><span class="sxs-lookup"><span data-stu-id="69fb9-105">Parsing statements received from clients</span></span>

-   <span data-ttu-id="69fb9-106">Gerenciamento de metadados</span><span class="sxs-lookup"><span data-stu-id="69fb9-106">Managing metadata</span></span>

-   <span data-ttu-id="69fb9-107">Tratamento de transações</span><span class="sxs-lookup"><span data-stu-id="69fb9-107">Handling transactions</span></span>

-   <span data-ttu-id="69fb9-108">Processamento de cálculos</span><span class="sxs-lookup"><span data-stu-id="69fb9-108">Processing calculations</span></span>

-   <span data-ttu-id="69fb9-109">Armazenagem de dimensões e dados de célula</span><span class="sxs-lookup"><span data-stu-id="69fb9-109">Storing dimension and cell data</span></span>

-   <span data-ttu-id="69fb9-110">Criação de agregações</span><span class="sxs-lookup"><span data-stu-id="69fb9-110">Creating aggregations</span></span>

-   <span data-ttu-id="69fb9-111">Programação de consultas</span><span class="sxs-lookup"><span data-stu-id="69fb9-111">Scheduling queries</span></span>

-   <span data-ttu-id="69fb9-112">Cache de objetos</span><span class="sxs-lookup"><span data-stu-id="69fb9-112">Caching objects</span></span>

-   <span data-ttu-id="69fb9-113">Gerenciamento de recursos do servidor</span><span class="sxs-lookup"><span data-stu-id="69fb9-113">Managing server resources</span></span>

## <a name="architectural-diagram"></a><span data-ttu-id="69fb9-114">Diagrama de arquitetura</span><span class="sxs-lookup"><span data-stu-id="69fb9-114">Architectural Diagram</span></span>
 <span data-ttu-id="69fb9-115">Uma instância do [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] executada como serviço e comunicação autônomos com o serviço ocorre por meio do XMLA, usando HTTP ou TCP.</span><span class="sxs-lookup"><span data-stu-id="69fb9-115">An [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] instance runs as a stand-alone service and communication with the service occurs through XML for Analysis (XMLA), by using either HTTP or TCP.</span></span> <span data-ttu-id="69fb9-116">AMO é uma camada entre o aplicativo de usuário e a instância do [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="69fb9-116">AMO is a layer between the user application and the [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] instance.</span></span> <span data-ttu-id="69fb9-117">Essa camada fornece acesso a objetos administrativos do [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="69fb9-117">This layer provides access to [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] administrative objects.</span></span> <span data-ttu-id="69fb9-118">AMO é uma biblioteca de classe que recebe comandos de um aplicativo cliente e os converte em mensagens de XMLA para a instância do [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="69fb9-118">AMO is a class library that takes commands from a client application and converts those commands into XMLA messages for the [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] instance.</span></span> <span data-ttu-id="69fb9-119">AMO apresenta objetos de instância do [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] como classes para o aplicativo de usuário final, com membros de método que executam comandos e membros de propriedade que mantêm os dados para os objetos [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="69fb9-119">AMO presents [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] instance objects as classes to the end user application, with method members that run commands and property members that hold the data for the [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] objects.</span></span>

 <span data-ttu-id="69fb9-120">A ilustração a seguir mostra a arquitetura de componentes do [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)], inclusive todos os elementos principais executados dentro da instância do [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] e todos os componentes de usuário que interagem com a instância.</span><span class="sxs-lookup"><span data-stu-id="69fb9-120">The following illustration shows the [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] components architecture, including all major elements running within the [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] instance and all user components that interact with the instance.</span></span> <span data-ttu-id="69fb9-121">A ilustração também mostra que o único modo de acessar a instância é usando o ouvinte do XML for Analysis (XMLA) ou usando HTTP ou TCP.</span><span class="sxs-lookup"><span data-stu-id="69fb9-121">The illustration also shows that the only way to access the instance is by using the XML for Analysis (XMLA) Listener, either by using HTTP or TCP.</span></span>

 <span data-ttu-id="69fb9-122">![Diagrama da arquitetura de sistema do Analysis Services](../../../analysis-services/dev-guide/media/analysisservicessystemarchitecture.gif "Diagrama da arquitetura de sistema do Analysis Services")</span><span class="sxs-lookup"><span data-stu-id="69fb9-122">![Analysis Services System Architecture Diagram](../../../analysis-services/dev-guide/media/analysisservicessystemarchitecture.gif "Analysis Services System Architecture Diagram")</span></span>

## <a name="xmla-listener"></a><span data-ttu-id="69fb9-123">Ouvinte XMLA</span><span class="sxs-lookup"><span data-stu-id="69fb9-123">XMLA Listener</span></span>
 <span data-ttu-id="69fb9-124">O componente ouvinte XMLA processa todas as comunicações de XMLA entre o [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] e seus clientes.</span><span class="sxs-lookup"><span data-stu-id="69fb9-124">The XMLA listener component handles all XMLA communications between [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] and its clients.</span></span> <span data-ttu-id="69fb9-125">A [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] `Port` definição de configuração no arquivo de msmdsrv.ini pode ser usada para especificar uma porta na qual uma [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] instância escuta.</span><span class="sxs-lookup"><span data-stu-id="69fb9-125">The [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] `Port` configuration setting in the msmdsrv.ini file can be used to specify a port on which an [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] instance listens.</span></span> <span data-ttu-id="69fb9-126">Um valor 0 nesse arquivo indica que o [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] ouve na porta padrão.</span><span class="sxs-lookup"><span data-stu-id="69fb9-126">A value of 0 in this file indicates that [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] listen on the default port.</span></span> <span data-ttu-id="69fb9-127">A menos que especificado de outro modo, o [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] usa as seguintes portas TCP padrão:</span><span class="sxs-lookup"><span data-stu-id="69fb9-127">Unless otherwise specified, [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] uses the following default TCP ports:</span></span>

|<span data-ttu-id="69fb9-128">Porta</span><span class="sxs-lookup"><span data-stu-id="69fb9-128">Port</span></span>|<span data-ttu-id="69fb9-129">Descrição</span><span class="sxs-lookup"><span data-stu-id="69fb9-129">Description</span></span>|
|----------|-----------------|
|<span data-ttu-id="69fb9-130">2383</span><span class="sxs-lookup"><span data-stu-id="69fb9-130">2383</span></span>|<span data-ttu-id="69fb9-131">Instância padrão do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="69fb9-131">Default instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span></span>|
|<span data-ttu-id="69fb9-132">2382</span><span class="sxs-lookup"><span data-stu-id="69fb9-132">2382</span></span>|<span data-ttu-id="69fb9-133">Redirecionador para outras instâncias do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="69fb9-133">Redirector for other instances of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span></span>|
|<span data-ttu-id="69fb9-134">Atribuído dinamicamente na inicialização do servidor</span><span class="sxs-lookup"><span data-stu-id="69fb9-134">Dynamically assigned at server startup</span></span>|<span data-ttu-id="69fb9-135">Instância nomeada do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="69fb9-135">Named instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span></span>|

 <span data-ttu-id="69fb9-136">Consulte [Configurar o Firewall do Windows para permitir acesso Analysis Services](../../instances/configure-the-windows-firewall-to-allow-analysis-services-access.md) para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="69fb9-136">See [Configure the Windows Firewall to Allow Analysis Services Access](../../instances/configure-the-windows-firewall-to-allow-analysis-services-access.md) for more details.</span></span>

## <a name="see-also"></a><span data-ttu-id="69fb9-137">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="69fb9-137">See Also</span></span>
 <span data-ttu-id="69fb9-138">[As regras de nomenclatura de objeto &#40;Analysis Services&#41;](object-naming-rules-analysis-services.md) [arquitetura física &#40;Analysis Services-dados multidimensionais&#41;](understanding-microsoft-olap-physical-architecture.md) [arquitetura lógica &#40;Analysis Services de dados multidimensionais&#41;](../olap-logical/understanding-microsoft-olap-logical-architecture.md)</span><span class="sxs-lookup"><span data-stu-id="69fb9-138">[Object Naming Rules &#40;Analysis Services&#41;](object-naming-rules-analysis-services.md) [Physical Architecture &#40;Analysis Services - Multidimensional Data&#41;](understanding-microsoft-olap-physical-architecture.md) [Logical Architecture &#40;Analysis Services - Multidimensional Data&#41;](../olap-logical/understanding-microsoft-olap-logical-architecture.md)</span></span>


