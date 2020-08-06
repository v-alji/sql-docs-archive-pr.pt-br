---
title: Gerenciar funções de pacote programaticamente (Serviço SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- Integration Services packages, roles
- roles [Integration Services]
- packages [Integration Services], roles
ms.assetid: 2e0ca0d5-d4f5-421d-b17d-a48b37b923e5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: dff54f3f90d9e008ae21c83c2a8fdc3f7440a5c3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684799"
---
# <a name="managing-package-roles-programmatically-ssis-service"></a><span data-ttu-id="31132-102">Gerenciando funções de pacote programaticamente (Serviço SSIS)</span><span class="sxs-lookup"><span data-stu-id="31132-102">Managing Package Roles Programmatically (SSIS Service)</span></span>
  <span data-ttu-id="31132-103">Ao trabalhar programaticamente com pacotes do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], talvez você queira determinar quais funções estão disponíveis para aplicar a pacotes ou determinar/definir as funções aplicadas a um único pacote.</span><span class="sxs-lookup"><span data-stu-id="31132-103">As you work programmatically with [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages, you may want to determine which roles are available to apply to packages, or to determine or set the roles applied to an individual package.</span></span> <span data-ttu-id="31132-104">A classe <xref:Microsoft.SqlServer.Dts.Runtime.Application> do namespace <xref:Microsoft.SqlServer.Dts.Runtime> fornece diversos métodos para atender a esses requisitos.</span><span class="sxs-lookup"><span data-stu-id="31132-104">The <xref:Microsoft.SqlServer.Dts.Runtime.Application> class of the <xref:Microsoft.SqlServer.Dts.Runtime> namespace provides a variety of methods to satisfy these requirements.</span></span>

 <span data-ttu-id="31132-105">As funções se aplicam apenas aos pacotes armazenados no banco de dados [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]msdb**do**.</span><span class="sxs-lookup"><span data-stu-id="31132-105">Roles apply only to packages stored in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **msdb** database.</span></span> <span data-ttu-id="31132-106">Para obter mais informações sobre funções de pacote, veja [Funções do Integration Services &#40;Serviço do SSIS&#41;](../security/integration-services-roles-ssis-service.md).</span><span class="sxs-lookup"><span data-stu-id="31132-106">For more information about package roles, see [Integration Services Roles &#40;SSIS Service&#41;](../security/integration-services-roles-ssis-service.md).</span></span>

 <span data-ttu-id="31132-107">Todos os métodos discutidos neste tópico exigem uma referência ao assembly `Microsoft.SqlServer.ManagedDTS`.</span><span class="sxs-lookup"><span data-stu-id="31132-107">All the methods discussed in this topic require a reference to the `Microsoft.SqlServer.ManagedDTS` assembly.</span></span> <span data-ttu-id="31132-108">Depois de adicionar a referência em um novo projeto, importe o namespace <xref:Microsoft.SqlServer.Dts.Runtime> através de uma instrução `using` ou `Imports`.</span><span class="sxs-lookup"><span data-stu-id="31132-108">After you add the reference in a new project, import the <xref:Microsoft.SqlServer.Dts.Runtime> namespace by using a `using` or `Imports` statement.</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="31132-109">Os métodos da classe <xref:Microsoft.SqlServer.Dts.Runtime.Application> para funcionar com o Repositório de Pacotes do SSIS dão suporte apenas a “.”, localhost ou ao nome do servidor local.</span><span class="sxs-lookup"><span data-stu-id="31132-109">The methods of the <xref:Microsoft.SqlServer.Dts.Runtime.Application> class for working with the SSIS Package Store support only ".", localhost, or the server name for the local server.</span></span> <span data-ttu-id="31132-110">Você não pode usar "(local)".</span><span class="sxs-lookup"><span data-stu-id="31132-110">You cannot use "(local)".</span></span>

## <a name="determining-which-roles-are-available"></a><span data-ttu-id="31132-111">Determinando quais funções estão disponíveis</span><span class="sxs-lookup"><span data-stu-id="31132-111">Determining Which Roles Are Available</span></span>
 <span data-ttu-id="31132-112">Para determinar quais funções estão disponíveis para os pacotes armazenados em um servidor específico, chame o método <xref:Microsoft.SqlServer.Dts.Runtime.Application.GetDtsServerRoles%2A> da classe <xref:Microsoft.SqlServer.Dts.Runtime.Application>.</span><span class="sxs-lookup"><span data-stu-id="31132-112">To determine which roles are available for the packages stored on a particular server, call the <xref:Microsoft.SqlServer.Dts.Runtime.Application.GetDtsServerRoles%2A> method of the <xref:Microsoft.SqlServer.Dts.Runtime.Application> class.</span></span>

## <a name="determining-which-roles-are-assigned"></a><span data-ttu-id="31132-113">Determinando quais funções são atribuídas</span><span class="sxs-lookup"><span data-stu-id="31132-113">Determining Which Roles Are Assigned</span></span>
 <span data-ttu-id="31132-114">Para determinar quais funções já foram atribuídas a um pacote específico, chame o método <xref:Microsoft.SqlServer.Dts.Runtime.Application.GetPackageRoles%2A>.</span><span class="sxs-lookup"><span data-stu-id="31132-114">To determine which roles have already been assigned to a particular package, call the <xref:Microsoft.SqlServer.Dts.Runtime.Application.GetPackageRoles%2A> method.</span></span> <span data-ttu-id="31132-115">Para atribuir funções a um pacote, chame o método <xref:Microsoft.SqlServer.Dts.Runtime.Application.SetPackageRoles%2A>.</span><span class="sxs-lookup"><span data-stu-id="31132-115">To assign roles to a package, call the <xref:Microsoft.SqlServer.Dts.Runtime.Application.SetPackageRoles%2A> method.</span></span>

<span data-ttu-id="31132-116">![Ícone de Integration Services (pequeno)](../media/dts-16.gif "Ícone do Integration Services (pequeno)")  **Mantenha-se atualizado com Integration Services**</span><span class="sxs-lookup"><span data-stu-id="31132-116">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="31132-117">Para obter os downloads, artigos, exemplos e vídeos mais recentes da Microsoft, assim como soluções selecionadas pela comunidade, visite a página do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] no MSDN:</span><span class="sxs-lookup"><span data-stu-id="31132-117">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="31132-118">Visite a página do Integration Services no MSDN</span><span class="sxs-lookup"><span data-stu-id="31132-118">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="31132-119">Para receber uma notificação automática dessas atualizações, assine os RSS feeds disponíveis na página.</span><span class="sxs-lookup"><span data-stu-id="31132-119">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>

## <a name="see-also"></a><span data-ttu-id="31132-120">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="31132-120">See Also</span></span>
 [<span data-ttu-id="31132-121">Funções do Integration Services &#40;SSIS Service&#41;</span><span class="sxs-lookup"><span data-stu-id="31132-121">Integration Services Roles &#40;SSIS Service&#41;</span></span>](../security/integration-services-roles-ssis-service.md)


