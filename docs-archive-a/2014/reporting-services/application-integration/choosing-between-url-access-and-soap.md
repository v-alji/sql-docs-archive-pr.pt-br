---
title: Escolhendo entre o acesso à URL e SOAP | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- SOAP [Reporting Services], vs. URL access
- Report Server Web service, application integration
- URL access [Reporting Services], vs. SOAP
- Web service [Reporting Services], application integration
ms.assetid: bccdc243-4366-4ce5-8e63-3dd6c463fa52
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 8075d92c51960c36d52d1a6ed5dc742a943177ff
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569229"
---
# <a name="choosing-between-url-access-and-soap"></a><span data-ttu-id="800d2-102">Optando entre acesso à URL e SOAP</span><span class="sxs-lookup"><span data-stu-id="800d2-102">Choosing Between URL Access and SOAP</span></span>
  <span data-ttu-id="800d2-103">A integração do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] a aplicativos personalizados pode ser desafiadora.</span><span class="sxs-lookup"><span data-stu-id="800d2-103">Integrating [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] into custom applications can be challenging.</span></span> <span data-ttu-id="800d2-104">No entanto, o desafio não é a complexidade do modelo de programação ou das APIs, mas as muitas maneiras possíveis de integrá-los.</span><span class="sxs-lookup"><span data-stu-id="800d2-104">The challenge, however, is not the complexity of the programming model or APIs, but the many possible ways to integrate it.</span></span> <span data-ttu-id="800d2-105">O [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] foi criado a partir do zero como uma plataforma de desenvolvedor e, portanto, é compilado tendo em mente a flexibilidade da programação.</span><span class="sxs-lookup"><span data-stu-id="800d2-105">[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] was designed from the ground up as a developer platform, and as such, it is built with programming flexibility in mind.</span></span> <span data-ttu-id="800d2-106">Com a flexibilidade vem a necessidade de tomar decisões importantes sobre como integrar a navegação de relatórios e a funcionalidade de gerenciamento do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] aos seus aplicativos comerciais existentes.</span><span class="sxs-lookup"><span data-stu-id="800d2-106">With flexibility comes the need to make important decisions about integrating [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] report navigation and management functionality into your existing business applications.</span></span>

 <span data-ttu-id="800d2-107">![Cenários de programação de Reporting Services](../../../2014/reporting-services/media/bk-ext-04.gif "Cenários de programação do Reporting Services") A programação de Reporting Services dá suporte a uma ampla gama de cenários.</span><span class="sxs-lookup"><span data-stu-id="800d2-107">![Reporting Services programming scenarios](../../../2014/reporting-services/media/bk-ext-04.gif "Reporting Services programming scenarios") Reporting Services programming supports a wide range of scenarios.</span></span>

 <span data-ttu-id="800d2-108">Existem dois modos de integrar o [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] a aplicativos personalizados: acesso à URL e a API SOAP do Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="800d2-108">There are two ways to integrate [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] into custom applications: URL access and the Reporting Services SOAP API.</span></span> <span data-ttu-id="800d2-109">A opção utilizada dependerá de vários fatores.</span><span class="sxs-lookup"><span data-stu-id="800d2-109">Which to use depends on several factors.</span></span> <span data-ttu-id="800d2-110">Em alguns casos, a integração do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] aos seus aplicativos comerciais personalizados exigirá que você use o acesso à URL e o SOAP.</span><span class="sxs-lookup"><span data-stu-id="800d2-110">In some cases, integrating [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] into your custom business applications requires a you to use both URL access and SOAP.</span></span> <span data-ttu-id="800d2-111">Você deve fazer as seguintes perguntas:</span><span class="sxs-lookup"><span data-stu-id="800d2-111">You should ask the following questions:</span></span>

-   <span data-ttu-id="800d2-112">Que tipo de funcionalidade de relatório empresarial você ou os seus usuários finais exigem?</span><span class="sxs-lookup"><span data-stu-id="800d2-112">What type of enterprise reporting functionality do you or your end users require?</span></span> <span data-ttu-id="800d2-113">Você precisa de uma maneira simples de abrir relatórios e de navegar neles ou precisa de recursos mais avançados de gerenciamento de servidor de relatório a partir da sua solução comercial personalizada?</span><span class="sxs-lookup"><span data-stu-id="800d2-113">Do you need a simple way to launch and navigate reports, or do you need more advanced report server management features from your custom business solution?</span></span>

-   <span data-ttu-id="800d2-114">Em qual tipo de ambiente os seus usuários operam normalmente?</span><span class="sxs-lookup"><span data-stu-id="800d2-114">In which type of environment do your users typically operate?</span></span> <span data-ttu-id="800d2-115">O seu aplicativo comercial é um aplicativo Web ou um aplicativo do Windows?</span><span class="sxs-lookup"><span data-stu-id="800d2-115">Is your business application a Web application or a Windows application?</span></span> <span data-ttu-id="800d2-116">Como que facilidade os seus usuários finais podem alternar entre um ambiente Win32 e um ambiente da Web?</span><span class="sxs-lookup"><span data-stu-id="800d2-116">How easily can your end users switch from a Win32 environment to a Web environment?</span></span> <span data-ttu-id="800d2-117">De que tipo de controle você precisa sobre o ambiente nos quais os relatórios serão executados e gerenciados?</span><span class="sxs-lookup"><span data-stu-id="800d2-117">What type of control do you need over the environment in which reports are run and managed?</span></span>

 <span data-ttu-id="800d2-118">Depois de responder as perguntas anteriores, você poderá decidir como integrará o [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] à sua infraestrutura de TI.</span><span class="sxs-lookup"><span data-stu-id="800d2-118">Once you have answered the previous questions, you can decide how to integrate [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] into your IT infrastructure.</span></span> <span data-ttu-id="800d2-119">Normalmente, o acesso à URL é o preferido para a exibição e navegação de relatórios individuais.</span><span class="sxs-lookup"><span data-stu-id="800d2-119">Typically, URL access is preferred for viewing and navigating individual reports.</span></span> <span data-ttu-id="800d2-120">O acesso à URL permite que você navegue de forma livre e rápida sem a sobrecarga do serviço Web.</span><span class="sxs-lookup"><span data-stu-id="800d2-120">URL access enables you to freely and quickly navigate reports without the overhead of the Web service.</span></span> <span data-ttu-id="800d2-121">Além disso, o acesso à URL é, atualmente, a única técnica de programação que usa o Visualizador de HTML completo para navegação de relatórios, o que inclui a barra de ferramentas de relatório.</span><span class="sxs-lookup"><span data-stu-id="800d2-121">In addition, URL access is currently the only programming technique that uses the full HTML Viewer for report navigation, which includes the report toolbar.</span></span> <span data-ttu-id="800d2-122">O acesso à URL também oferece um desempenho melhor do que o SOAP porque ignora o marshalling de solicitações SOAP para e do servidor.</span><span class="sxs-lookup"><span data-stu-id="800d2-122">In addition, URL access provides better performance than SOAP because it bypasses the marshalling of SOAP requests to and from the server.</span></span> <span data-ttu-id="800d2-123">Em cenários de integração que exigem acesso rápido e fácil a relatórios com ferramentas internas para exibição e navegação, o acesso à URL é a melhor opção.</span><span class="sxs-lookup"><span data-stu-id="800d2-123">In integration scenarios that require quick and easy access to reports with built-in tools for viewing and navigation, URL access is the better choice.</span></span>

> [!NOTE]
>  <span data-ttu-id="800d2-124">O acesso à URL do servidor de relatório dá suporte ao Visualizador de HTML e à funcionalidade estendida da barra de ferramentas de relatório.</span><span class="sxs-lookup"><span data-stu-id="800d2-124">Report server URL access supports HTML Viewer and the extended functionality of the report toolbar.</span></span> <span data-ttu-id="800d2-125">A API SOAP API não dá suporte a esse tipo de relatório renderizado.</span><span class="sxs-lookup"><span data-stu-id="800d2-125">The SOAP API does not support this type of rendered report.</span></span> <span data-ttu-id="800d2-126">Você precisará criar e desenvolver a sua própria barra de ferramentas de relatório, se renderizar relatórios usando SOAP.</span><span class="sxs-lookup"><span data-stu-id="800d2-126">You need to design and develop your own report toolbar, if you render reports using SOAP.</span></span>

 <span data-ttu-id="800d2-127">Para obter mais informações sobre a barra de ferramentas de relatório, consulte [Visualizador de HTML e a barra de ferramentas de relatório](../html-viewer-and-the-report-toolbar.md).</span><span class="sxs-lookup"><span data-stu-id="800d2-127">For more information about the report toolbar, see [HTML Viewer and the Report Toolbar](../html-viewer-and-the-report-toolbar.md).</span></span>

 <span data-ttu-id="800d2-128">Para obter mais informações sobre o acesso à URL, consulte [acesso à url &#40;&#41;SSRS ](../url-access-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="800d2-128">For more information about URL access, see [URL Access &#40;SSRS&#41;](../url-access-ssrs.md).</span></span>

 <span data-ttu-id="800d2-129">O acesso à URL é útil para a visualização de relatórios, mas não oferece a funcionalidade de gerenciamento de relatórios e de namespaces que pode ser essencial para qualquer cenário de relatórios empresarial.</span><span class="sxs-lookup"><span data-stu-id="800d2-129">URL access is useful for viewing reports, but it does not provide the report and namespace management functionality that can be essential to any enterprise reporting scenario.</span></span> <span data-ttu-id="800d2-130">Nesse caso, a funcionalidade ampla e sofisticada da API SOAP do Reporting Services é recomendada.</span><span class="sxs-lookup"><span data-stu-id="800d2-130">In this case, the broad and rich functionality of the Reporting Services SOAP API is recommended.</span></span> <span data-ttu-id="800d2-131">Com a API SOAP você pode gerenciar e implantar relatórios, criar agendas, configurar propriedades de servidor, gerenciar o namespace de servidor de relatório, criar assinaturas e mais.</span><span class="sxs-lookup"><span data-stu-id="800d2-131">With the SOAP API you can manage and deploy reports, create schedules, configure server properties, manage the report server namespace, create subscriptions, and more.</span></span> <span data-ttu-id="800d2-132">A API SOAP exibe o conjunto completo de funcionalidades de gerenciamento do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="800d2-132">The SOAP API exposes the complete set of management functionality in [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="800d2-133">A API SOAP também pode habilitar a exibição e a navegação de relatórios por meio do método <xref:ReportExecution2005.ReportExecutionService.Render%2A> da API.</span><span class="sxs-lookup"><span data-stu-id="800d2-133">The SOAP API can also enable report viewing and navigation through the <xref:ReportExecution2005.ReportExecutionService.Render%2A> method of the API.</span></span> <span data-ttu-id="800d2-134">No entanto, exibir relatórios por meio da API SOAP não habilita a funcionalidade de exibição interna da barra de ferramentas de relatório, nem manipula automaticamente a interatividade do relatório fornecida pelo acesso à URL.</span><span class="sxs-lookup"><span data-stu-id="800d2-134">However, viewing reports through the SOAP API does not enable the built-in viewing functionality of the report toolbar, nor does it automatically handle the report interactivity that URL access provides.</span></span>

 <span data-ttu-id="800d2-135">Para obter mais informações sobre a API SOAP do Reporting Services, consulte [Serviço Web do Servidor de Relatórios](../report-server-web-service/report-server-web-service.md).</span><span class="sxs-lookup"><span data-stu-id="800d2-135">For more information about the Reporting Services SOAP API, see [Report Server Web Service](../report-server-web-service/report-server-web-service.md).</span></span>

 <span data-ttu-id="800d2-136">Na maioria dos casos, o acesso à URL e as chamadas SOAP serão necessários para que você atenda às suas necessidades de relatórios.</span><span class="sxs-lookup"><span data-stu-id="800d2-136">In the majority of cases, URL access and SOAP calls are both required to meet your reporting needs.</span></span> <span data-ttu-id="800d2-137">SOAP é usado na conexão inicial ao banco de dados do servidor de relatório e na apresentação da lista de relatórios disponível em uma interface do usuário e o acesso à URL é usado para acessar os relatórios individuais e para navegar por eles.</span><span class="sxs-lookup"><span data-stu-id="800d2-137">SOAP is used when initially connecting to the report server database and presenting the available list of reports in a user interface and URL access is used to actually access and navigate individual reports.</span></span>

 <span data-ttu-id="800d2-138">Para obter um exemplo de combinação do acesso de URL com o serviço Web para fornecer relatórios integrados, consulte [Amostras de produto do SQL Server Reporting Services](https://go.microsoft.com/fwlink/?LinkId=177889).</span><span class="sxs-lookup"><span data-stu-id="800d2-138">For an example of combining URL access and the Web service to provide integrated reporting, see [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889).</span></span>

## <a name="see-also"></a><span data-ttu-id="800d2-139">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="800d2-139">See Also</span></span>
 <span data-ttu-id="800d2-140">[Integração do Reporting Services a aplicativos](../../../2014/reporting-services/application-integration/integrating-reporting-services-into-applications.md) que [integram Reporting Services usando](../application-integration/integrating-reporting-services-using-soap.md) a integração SOAP Reporting Services usando referência técnica de [acesso à URL](../application-integration/integrating-reporting-services-using-url-access.md) [&#40;SSRS&#41;](../../../2014/reporting-services/technical-reference-ssrs.md)</span><span class="sxs-lookup"><span data-stu-id="800d2-140">[Integrating Reporting Services into Applications](../../../2014/reporting-services/application-integration/integrating-reporting-services-into-applications.md) [Integrating Reporting Services Using SOAP](../application-integration/integrating-reporting-services-using-soap.md) [Integrating Reporting Services Using URL Access](../application-integration/integrating-reporting-services-using-url-access.md) [Technical Reference &#40;SSRS&#41;](../../../2014/reporting-services/technical-reference-ssrs.md)</span></span>

