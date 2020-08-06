---
title: Considerações sobre segurança para extensões | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- security [Reporting Services], extensions
- extensions [Reporting Services], security
- permissions [Reporting Services], extensions
ms.assetid: 58cbdfeb-1105-4a7d-a3b8-b897ff95f367
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: e7819f4d6de2003c9982d33ab00cfa0d4030aa36
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583382"
---
# <a name="security-considerations-for-extensions"></a><span data-ttu-id="bacbd-102">Considerações de segurança para extensões</span><span class="sxs-lookup"><span data-stu-id="bacbd-102">Security Considerations for Extensions</span></span>
  <span data-ttu-id="bacbd-103">Todos aplicativo que se destinam ao CLR (Common Language Runtime) devem interagir com o sistema de segurança CLR.</span><span class="sxs-lookup"><span data-stu-id="bacbd-103">Every application that targets the common language runtime (CLR) must interact with the CLR security system.</span></span> <span data-ttu-id="bacbd-104">Quando tal aplicativo é executado, é automaticamente avaliado e recebe um conjunto de permissões do CLR.</span><span class="sxs-lookup"><span data-stu-id="bacbd-104">When such an application runs, it is automatically evaluated and given a set of permissions by the CLR.</span></span> <span data-ttu-id="bacbd-105">Dependendo das permissões que o aplicativo receber, ele continuará sua execução ou vai gerar uma exceção de segurança.</span><span class="sxs-lookup"><span data-stu-id="bacbd-105">Depending on the permissions that the application receives, it either continues running or generates a security exception.</span></span> <span data-ttu-id="bacbd-106">As configurações e as diretrizes locais de segurança dos arquivos de configuração de política de segurança para um determinado servidor de relatório definem as permissões de código recebidas por um assembly.</span><span class="sxs-lookup"><span data-stu-id="bacbd-106">The local security settings and policies in the security policy configuration files for a particular report server define the code permissions that an assembly receives.</span></span>  
  
 <span data-ttu-id="bacbd-107">Antes de solicitar permissões, você precisa estar ciente dos recursos e das operações protegidas que o seu código de extensão planeja usar, além de saber que permissões protegem esses recursos e operações.</span><span class="sxs-lookup"><span data-stu-id="bacbd-107">Before requesting permissions, you need to be aware of the resources and protected operations your extension code is planning to use, and you also need to know which permissions protect those resources and operations.</span></span> <span data-ttu-id="bacbd-108">Além disso, você precisa manter o controle sobre qualquer recurso acessado por qualquer método de biblioteca de classes chamado pelos componentes de extensão.</span><span class="sxs-lookup"><span data-stu-id="bacbd-108">In addition, you need to keep track of any resources accessed by any class library methods that are called by the extension components.</span></span> <span data-ttu-id="bacbd-109">Para obter mais informações, consulte "Solicitando permissões" no Guia do desenvolvedor do [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bacbd-109">For more information, see "Requesting Permissions" in the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] Developer's Guide.</span></span>  
  
 <span data-ttu-id="bacbd-110">As extensões implantadas em um servidor de relatório devem ser executadas como totalmente confiáveis, o que significa que a extensão precisa fazer parte de um grupo de códigos com o conjunto de permissões **FullTrust**.</span><span class="sxs-lookup"><span data-stu-id="bacbd-110">Extensions deployed to a report server must run as fully trusted, meaning that your extension needs to be part of a code group that is granted the **FullTrust** permission set.</span></span> <span data-ttu-id="bacbd-111">Isso também significa que a sua extensão poderá ter acesso a certos recursos e operações de servidor disponíveis por meio do CLR, dependendo do usuário autenticado para um determinado relatório.</span><span class="sxs-lookup"><span data-stu-id="bacbd-111">This also means that your extension may have access to certain server resources and operations available through the CLR depending on the user that is being authenticated for a particular report.</span></span> <span data-ttu-id="bacbd-112">Para obter mais informações sobre grupos de códigos e extensões, consulte [Segurança de acesso do código no Reporting Services](secure-development/code-access-security-in-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="bacbd-112">For more information about code groups and extensions, see [Code Access Security in Reporting Services](secure-development/code-access-security-in-reporting-services.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="bacbd-113">O [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] impõe a segurança [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] para todas as suas extensões.</span><span class="sxs-lookup"><span data-stu-id="bacbd-113">[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] enforces [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] security for all of its extensions.</span></span>  
  
 <span data-ttu-id="bacbd-114">As condições a seguir se aplicam à implantação de processamento de dados, à entrega, à renderização e às extensões de segurança do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="bacbd-114">The following conditions apply to the deployment of data processing, delivery, rendering, and security extensions in [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="bacbd-115">Somente o administrador local tem permissão para implantar uma extensão.</span><span class="sxs-lookup"><span data-stu-id="bacbd-115">Only the local administrator has permission to deploy an extension.</span></span>  
  
-   <span data-ttu-id="bacbd-116">Somente os usuários com as permissões de leitura/gravação apropriadas podem alterar os arquivos de configuração para o componente do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] que está sendo estendido.</span><span class="sxs-lookup"><span data-stu-id="bacbd-116">Only users with the appropriate read/write permissions can change the configuration files for the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] component that is being extended.</span></span>  
  
-   <span data-ttu-id="bacbd-117">Somente os usuários privilegiados têm permissão para editar os arquivos de política de segurança e para habilitar a segurança de acesso a código para uma extensão.</span><span class="sxs-lookup"><span data-stu-id="bacbd-117">Only privileged users have permission to edit the security policy files and enable code access security for an extension.</span></span>  
  
 <span data-ttu-id="bacbd-118">Para obter mais informações sobre a segurança de acesso do código no [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], consulte [Desenvolvimento seguro &#40;Reporting Services&#41;](secure-development/secure-development-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="bacbd-118">For more information about code access security in [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], see [Secure Development &#40;Reporting Services&#41;](secure-development/secure-development-reporting-services.md).</span></span>  
  
 <span data-ttu-id="bacbd-119">Para obter mais informações sobre segurança [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], consulte "Segurança do .NET Framework" no seu Guia do desenvolvedor do [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bacbd-119">For more information about [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] security, see ".NET Framework Security" in your [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] Developer's Guide.</span></span>  
  
## <a name="initialization-of-extension-assemblies"></a><span data-ttu-id="bacbd-120">Inicialização de assemblies de extensão</span><span class="sxs-lookup"><span data-stu-id="bacbd-120">Initialization of Extension Assemblies</span></span>  
 <span data-ttu-id="bacbd-121">Quando as extensões são carregadas na memória pela primeira vez pelo servidor de relatório, usam as credenciais da conta de serviço, já que alguns assemblies de extensão exigem permissões específicas para o acesso a recursos do sistema, para ler arquivos de configuração e para carregar outros assemblies dependentes.</span><span class="sxs-lookup"><span data-stu-id="bacbd-121">When extensions are first loaded into memory by the report server, they use the service account credentials, because some extension assemblies require specific permissions to access system resources, to read configuration files, and to load other, dependent assemblies.</span></span> <span data-ttu-id="bacbd-122">Após o carregamento de um assembly e de sua inicialização, no entanto, todas as chamadas subsequentes a assemblies de extensão usarão as credenciais da conta do usuário conectado no momento.</span><span class="sxs-lookup"><span data-stu-id="bacbd-122">After an assembly has been loaded and initialized, however, all subsequent calls to extension assemblies use the credentials of the user account that is currently logged on.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bacbd-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="bacbd-123">See Also</span></span>  
 <span data-ttu-id="bacbd-124">[Extensões do Reporting Services](reporting-services-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="bacbd-124">[Reporting Services Extensions](reporting-services-extensions.md) </span></span>  
 [<span data-ttu-id="bacbd-125">Biblioteca de extensões do Reporting Services</span><span class="sxs-lookup"><span data-stu-id="bacbd-125">Reporting Services Extension Library</span></span>](reporting-services-extension-library.md)  
  
  
