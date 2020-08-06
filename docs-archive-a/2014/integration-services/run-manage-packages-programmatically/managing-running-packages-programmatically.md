---
title: Gerenciar pacotes em execução programaticamente | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- packages [Integration Services], managing
- running packages [Integration Services]
ms.assetid: 0e91f4ac-6f29-40d7-8c28-9b82e4802c35
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 95c5f9c28b407631764d64523b37a6295870542a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684800"
---
# <a name="managing-running-packages-programmatically"></a><span data-ttu-id="6974a-102">Gerenciando pacotes em execução programaticamente</span><span class="sxs-lookup"><span data-stu-id="6974a-102">Managing Running Packages Programmatically</span></span>
  <span data-ttu-id="6974a-103">Ao trabalhar programaticamente com pacotes [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], determine quais pacotes estão em execução no momento.</span><span class="sxs-lookup"><span data-stu-id="6974a-103">As you work programmatically with [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages, you may want to determine which packages are currently running.</span></span> <span data-ttu-id="6974a-104">A classe <xref:Microsoft.SqlServer.Dts.Runtime.Application> do namespace <xref:Microsoft.SqlServer.Dts.Runtime> fornece métodos e classes que atendem a esses requisitos.</span><span class="sxs-lookup"><span data-stu-id="6974a-104">The <xref:Microsoft.SqlServer.Dts.Runtime.Application> class of the <xref:Microsoft.SqlServer.Dts.Runtime> namespace provides methods and classes to satisfy these requirements.</span></span>  
  
 <span data-ttu-id="6974a-105">Para obter mais informações sobre o monitoramento de pacotes, consulte [Gerenciamento de Pacotes &#40;Serviço SSIS&#41;](../service/package-management-ssis-service.md).</span><span class="sxs-lookup"><span data-stu-id="6974a-105">For more information about monitoring packages, see [Package Management &#40;SSIS Service&#41;](../service/package-management-ssis-service.md).</span></span>  
  
 <span data-ttu-id="6974a-106">Todos os métodos discutidos neste tópico exigem uma referência ao assembly `Microsoft.SqlServer.ManagedDTS`.</span><span class="sxs-lookup"><span data-stu-id="6974a-106">All the methods discussed in this topic require a reference to the `Microsoft.SqlServer.ManagedDTS` assembly.</span></span> <span data-ttu-id="6974a-107">Após adicionar a referência em um novo projeto, importe o namespace <xref:Microsoft.SqlServer.Dts.Runtime> com uma instrução `using` ou `Imports`.</span><span class="sxs-lookup"><span data-stu-id="6974a-107">After you add the reference in a new project, import the <xref:Microsoft.SqlServer.Dts.Runtime> namespace with a `using` or `Imports` statement.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="6974a-108">Os métodos da classe <xref:Microsoft.SqlServer.Dts.Runtime.Application> para funcionar com o Repositório de Pacotes do SSIS dão suporte apenas a “.”, localhost ou ao nome do servidor local.</span><span class="sxs-lookup"><span data-stu-id="6974a-108">The methods of the <xref:Microsoft.SqlServer.Dts.Runtime.Application> class for working with the SSIS Package Store support only ".", localhost, or the server name for the local server.</span></span> <span data-ttu-id="6974a-109">Você não pode usar "(local)".</span><span class="sxs-lookup"><span data-stu-id="6974a-109">You cannot use "(local)".</span></span>  
  
## <a name="determining-which-packages-are-currently-running"></a><span data-ttu-id="6974a-110">Determinando quais pacotes estão em execução atualmente</span><span class="sxs-lookup"><span data-stu-id="6974a-110">Determining Which Packages Are Currently Running</span></span>  
 <span data-ttu-id="6974a-111">Para determinar quais pacotes estão em execução atualmente no servidor especificado, chame o método <xref:Microsoft.SqlServer.Dts.Runtime.Application.GetRunningPackages%2A>.</span><span class="sxs-lookup"><span data-stu-id="6974a-111">To determine which packages are currently running on the specified server, call the <xref:Microsoft.SqlServer.Dts.Runtime.Application.GetRunningPackages%2A> method.</span></span> <span data-ttu-id="6974a-112">Esse método retorna uma coleção <xref:Microsoft.SqlServer.Dts.Runtime.RunningPackages> de objetos <xref:Microsoft.SqlServer.Dts.Runtime.RunningPackage>.</span><span class="sxs-lookup"><span data-stu-id="6974a-112">This method returns a <xref:Microsoft.SqlServer.Dts.Runtime.RunningPackages> collection of <xref:Microsoft.SqlServer.Dts.Runtime.RunningPackage> objects.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6974a-113">Administradores consultam todos os pacotes que estão em execução atualmente no computador; outros usuários só verificam os pacotes iniciados por eles.</span><span class="sxs-lookup"><span data-stu-id="6974a-113">Administrators see all packages that are currently executing on the computer; other users see only those packages that they have launched.</span></span>  
  
## <a name="working-with-running-packages"></a><span data-ttu-id="6974a-114">Trabalhando com pacotes em execução</span><span class="sxs-lookup"><span data-stu-id="6974a-114">Working with Running Packages</span></span>  
 <span data-ttu-id="6974a-115">Depois de determinar quais pacotes estão em execução no momento, você poderá recuperar informações sobre os pacotes e solicitar que um pacote seja interrompido.</span><span class="sxs-lookup"><span data-stu-id="6974a-115">After you have determined which packages are currently running, you can retrieve information about the packages and request that a package be stopped.</span></span>  
  
### <a name="getting-information-about-a-running-package"></a><span data-ttu-id="6974a-116">Obtendo informações sobre um pacote em execução</span><span class="sxs-lookup"><span data-stu-id="6974a-116">Getting Information about a Running Package</span></span>  
 <span data-ttu-id="6974a-117">Ao iterar na coleção <xref:Microsoft.SqlServer.Dts.Runtime.RunningPackages>, você pode utilizar as propriedades do objeto <xref:Microsoft.SqlServer.Dts.Runtime.RunningPackage> para localizar um pacote ou para obter informações adicionais sobre os pacotes em execução:</span><span class="sxs-lookup"><span data-stu-id="6974a-117">As you iterate through the <xref:Microsoft.SqlServer.Dts.Runtime.RunningPackages> collection, you can use the properties of the <xref:Microsoft.SqlServer.Dts.Runtime.RunningPackage> object to locate a package or to obtain additional information about the packages that are running:</span></span>  
  
-   <xref:Microsoft.SqlServer.Dts.Runtime.RunningPackage.ExecutionDuration%2A>  
  
-   <xref:Microsoft.SqlServer.Dts.Runtime.RunningPackage.ExecutionStartTime%2A>  
  
-   <xref:Microsoft.SqlServer.Dts.Runtime.RunningPackage.InstanceID%2A>  
  
-   <xref:Microsoft.SqlServer.Dts.Runtime.RunningPackage.PackageDescription%2A>  
  
-   <xref:Microsoft.SqlServer.Dts.Runtime.RunningPackage.PackageID%2A>  
  
-   <xref:Microsoft.SqlServer.Dts.Runtime.RunningPackage.PackageName%2A>  
  
-   <xref:Microsoft.SqlServer.Dts.Runtime.RunningPackage.UserName%2A>  
  
### <a name="stopping-a-running-package"></a><span data-ttu-id="6974a-118">Interrompendo um pacote em execução</span><span class="sxs-lookup"><span data-stu-id="6974a-118">Stopping a Running Package</span></span>  
 <span data-ttu-id="6974a-119">Você pode chamar o método <xref:Microsoft.SqlServer.Dts.Runtime.RunningPackage.Stop%2A> de um objeto <xref:Microsoft.SqlServer.Dts.Runtime.RunningPackage> para solicitar que o pacote seja interrompido.</span><span class="sxs-lookup"><span data-stu-id="6974a-119">You can call the <xref:Microsoft.SqlServer.Dts.Runtime.RunningPackage.Stop%2A> method of a <xref:Microsoft.SqlServer.Dts.Runtime.RunningPackage> object to request that the package be stopped.</span></span> <span data-ttu-id="6974a-120">Pode haver um atraso entre a hora em que uma solicitação de interrupção é emitida e a hora em que o pacote é realmente interrompido.</span><span class="sxs-lookup"><span data-stu-id="6974a-120">There may be a delay between the time that a stop request is issued and the time that the package actually stops.</span></span>  
  
<span data-ttu-id="6974a-121">![Ícone de Integration Services (pequeno)](../media/dts-16.gif "Ícone do Integration Services (pequeno)")  **Mantenha-se atualizado com Integration Services**</span><span class="sxs-lookup"><span data-stu-id="6974a-121">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="6974a-122">Para obter os downloads, artigos, exemplos e vídeos mais recentes da Microsoft, assim como soluções selecionadas pela comunidade, visite a página do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] no MSDN:</span><span class="sxs-lookup"><span data-stu-id="6974a-122">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="6974a-123">Visite a página do Integration Services no MSDN</span><span class="sxs-lookup"><span data-stu-id="6974a-123">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="6974a-124">Para receber uma notificação automática dessas atualizações, assine os RSS feeds disponíveis na página.</span><span class="sxs-lookup"><span data-stu-id="6974a-124">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6974a-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6974a-125">See Also</span></span>  
 <span data-ttu-id="6974a-126">[Gerenciamento de Pacotes &#40;serviço SSIS&#41;](../service/package-management-ssis-service.md) </span><span class="sxs-lookup"><span data-stu-id="6974a-126">[Package Management &#40;SSIS Service&#41;](../service/package-management-ssis-service.md) </span></span>  
 [<span data-ttu-id="6974a-127">Enumerando pacotes disponíveis programaticamente</span><span class="sxs-lookup"><span data-stu-id="6974a-127">Enumerating Available Packages Programmatically</span></span>](../run-manage-packages-programmatically/enumerating-available-packages-programmatically.md)  
  
  
