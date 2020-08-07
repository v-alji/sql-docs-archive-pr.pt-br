---
title: Criar classes proxy do serviço Web do Master Data Manager | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
ms.assetid: 8bdab026-a0c0-41f3-9d36-f3919c23247f
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: c4f25d749f829357f6541f14073e654bade27215
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87584170"
---
# <a name="create-master-data-manager-web-service-proxy-classes"></a><span data-ttu-id="48c0e-102">Criar classes proxy do serviço Web do Master Data Manager</span><span class="sxs-lookup"><span data-stu-id="48c0e-102">Create Master Data Manager Web Service Proxy Classes</span></span>
  <span data-ttu-id="48c0e-103">O serviço Web [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] permite a você fazer uso programático dos recursos do [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] de qualquer computador que possa acessar seu site do [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="48c0e-103">The [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web service lets you make programmatic use of the features of [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] from any computer that can access your [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web site.</span></span> <span data-ttu-id="48c0e-104">Antes de começar a gravar código para acessar o serviço Web, você deve gerar classes proxy.</span><span class="sxs-lookup"><span data-stu-id="48c0e-104">Before you can start writing code to access the web service, you must generate proxy classes.</span></span> <span data-ttu-id="48c0e-105">A classe proxy principal que você usa para executar operações de serviço Web é a classe <xref:Microsoft.MasterDataServices.ServiceClient>, que implementa a interface <xref:Microsoft.MasterDataServices.IService>.</span><span class="sxs-lookup"><span data-stu-id="48c0e-105">The main proxy class you use to perform web service operations is the <xref:Microsoft.MasterDataServices.ServiceClient> class, which implements the <xref:Microsoft.MasterDataServices.IService> interface.</span></span>  
  
## <a name="enable-web-service-metadata-publishing"></a><span data-ttu-id="48c0e-106">Habilitar a publicação de metadados de serviço Web</span><span class="sxs-lookup"><span data-stu-id="48c0e-106">Enable Web Service Metadata Publishing</span></span>  
 <span data-ttu-id="48c0e-107">Antes de gerar classes proxy, você deve habilitar a publicação de metadados de serviço Web.</span><span class="sxs-lookup"><span data-stu-id="48c0e-107">Before you can generate proxy classes, you must enable web service metadata publishing.</span></span> <span data-ttu-id="48c0e-108">Siga estas etapas para fazer isso:</span><span class="sxs-lookup"><span data-stu-id="48c0e-108">Follow these steps to do this:</span></span>  
  
1.  <span data-ttu-id="48c0e-109">Abra o arquivo Web.config do [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] em um editor de texto.</span><span class="sxs-lookup"><span data-stu-id="48c0e-109">Open the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] Web.config file in a text editor.</span></span> <span data-ttu-id="48c0e-110">Esse arquivo está na pasta WebApplication, no caminho de instalação do [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="48c0e-110">This file is in the WebApplication folder of the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] installation path.</span></span>  
  
2.  <span data-ttu-id="48c0e-111">Localize a `mdsWsHttpBehavior` seção em **\<serviceBehaviors>** .</span><span class="sxs-lookup"><span data-stu-id="48c0e-111">Find the `mdsWsHttpBehavior` section under **\<serviceBehaviors>**.</span></span> <span data-ttu-id="48c0e-112">Para o **\<serviceMetadata>** elemento, defina `httpGetEnabled` como `true` .</span><span class="sxs-lookup"><span data-stu-id="48c0e-112">For the **\<serviceMetadata>** element, set `httpGetEnabled` to `true`.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="48c0e-113">Entretanto, se quiser habilitar serviços Web sobre protocolo SSL (Secure Sockets Layer), defina `httpsGetEnabled` como `true` na seção `mdsWsHttpBehavior` do arquivo web.config.</span><span class="sxs-lookup"><span data-stu-id="48c0e-113">If you want to enable Web services over Secure Sockets Layer (SSL), set `httpsGetEnabled` to `true` in the `mdsWsHttpBehavior` section of the web.config file.</span></span> <span data-ttu-id="48c0e-114">Você também precisa alterar o `mdsWsHTTPBinding` para que ele seja configurado para SSL, também, e faça um comentário da seção não SSL.</span><span class="sxs-lookup"><span data-stu-id="48c0e-114">You also need to change `mdsWsHTTPBinding` so that it is configured for SSL, as well, and comment out the non-SSL section.</span></span>  
  
3.  <span data-ttu-id="48c0e-115">Salve as alterações no arquivo.</span><span class="sxs-lookup"><span data-stu-id="48c0e-115">Save changes to the file.</span></span>  
  
4.  <span data-ttu-id="48c0e-116">Teste a publicação de metadados navegando para a URL do serviço, por exemplo: http://yourserver/MDS/service/service.svc.</span><span class="sxs-lookup"><span data-stu-id="48c0e-116">Test metadata publishing by browsing to the service URL, for example: http://yourserver/MDS/service/service.svc.</span></span> <span data-ttu-id="48c0e-117">Se a publicação de metadados estiver habilitada, será exibida uma página que começa com</span><span class="sxs-lookup"><span data-stu-id="48c0e-117">If metadata publishing is enabled, a page is displayed that begins with</span></span>   
    <span data-ttu-id="48c0e-118">"Você criou um serviço."</span><span class="sxs-lookup"><span data-stu-id="48c0e-118">"You have created a service."</span></span>  
  
## <a name="creating-proxy-classes-by-using-visual-studio"></a><span data-ttu-id="48c0e-119">Criando classes proxy usando o Visual Studio</span><span class="sxs-lookup"><span data-stu-id="48c0e-119">Creating Proxy Classes by Using Visual Studio</span></span>  
 <span data-ttu-id="48c0e-120">Se você tiver o Visual Studio 2010 instalado, o modo mais simples de gerar classes proxy será adicionar uma **Referência de Serviço** ao seu projeto.</span><span class="sxs-lookup"><span data-stu-id="48c0e-120">If you have Visual Studio 2010 installed, the simplest way to generate proxy classes is to add a **Service Reference** to your project.</span></span> <span data-ttu-id="48c0e-121">O endereço da referência do serviço é a URL do aplicativo Web [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)], com /service/service.svc.</span><span class="sxs-lookup"><span data-stu-id="48c0e-121">The address of the service reference is the URL of the [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web application, appended with /service/service.svc.</span></span> <span data-ttu-id="48c0e-122">Por exemplo: http://yourserver/MDS/service/service.svc.</span><span class="sxs-lookup"><span data-stu-id="48c0e-122">For example: http://yourserver/MDS/service/service.svc.</span></span> <span data-ttu-id="48c0e-123">Para obter mais informações, consulte [Como adicionar, atualizar ou remover uma referência de serviço](https://go.microsoft.com/fwlink/?LinkId=221167).</span><span class="sxs-lookup"><span data-stu-id="48c0e-123">For more information, see [How to: Add, Update, or Remove a Service Reference](https://go.microsoft.com/fwlink/?LinkId=221167).</span></span>  
  
## <a name="creating-proxy-classes-by-using-svcutilexe"></a><span data-ttu-id="48c0e-124">Criando classes proxy usando Svcutil.exe</span><span class="sxs-lookup"><span data-stu-id="48c0e-124">Creating Proxy Classes by Using Svcutil.exe</span></span>  
 <span data-ttu-id="48c0e-125">Você deve ter [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] o ou o [!INCLUDE[msCoName](../../includes/msconame-md.md)] SDK do Windows instalado para ter Svcutil.exe em seu computador.</span><span class="sxs-lookup"><span data-stu-id="48c0e-125">You must have either [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] or the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows SDK installed in order to have Svcutil.exe on your computer.</span></span> <span data-ttu-id="48c0e-126">Se você usar o [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)], deverá usar o prompt de comando do [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] para executar o comando.</span><span class="sxs-lookup"><span data-stu-id="48c0e-126">If you use [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)], you must use the [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] command prompt to run the command.</span></span> <span data-ttu-id="48c0e-127">Para obter mais informações, consulte [Ferramenta de utilitário de metadados ServiceModel (Svcutil.exe)](https://go.microsoft.com/fwlink/?LinkId=165027)[Gerando um cliente WCF de metadados do serviço](https://go.microsoft.com/fwlink/?LinkId=164821).</span><span class="sxs-lookup"><span data-stu-id="48c0e-127">For more information, see [ServiceModel Metadata Utility Tool (Svcutil.exe)](https://go.microsoft.com/fwlink/?LinkId=165027) and [Generating a WCF Client from Service Metadata](https://go.microsoft.com/fwlink/?LinkId=164821).</span></span>  
  
 <span data-ttu-id="48c0e-128">Para criar um conjunto de classes proxy C# usando Svcutil.exe, utilize um comando como o seguinte:</span><span class="sxs-lookup"><span data-stu-id="48c0e-128">To create a set of C# proxy classes by using Svcutil.exe, use a command such as the following:</span></span>  
  
```  
svcutil.exe http://<server_name:port>/<virtual_path>/Service/Service.svc   
/out:<proxy_name>.cs /messageContract /tcv:Version35   
/noconfig /ct:System.Collections.ObjectModel.Collection`1   
/namespace:*,Microsoft.MasterDataServices  
```  
  
 <span data-ttu-id="48c0e-129">Em que:</span><span class="sxs-lookup"><span data-stu-id="48c0e-129">Where:</span></span>  
  
-   <span data-ttu-id="48c0e-130">*server_name*:*port* são o número da porta e o nome do computador que hospeda o [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)].</span><span class="sxs-lookup"><span data-stu-id="48c0e-130">*servername*:*port* are the computer name and port number of the computer that hosts [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)].</span></span>  
  
-   <span data-ttu-id="48c0e-131">*virtual_path* é o caminho virtual do [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] no IIS (Serviços de Informações da Internet).</span><span class="sxs-lookup"><span data-stu-id="48c0e-131">*virtual_path* is the virtual path of [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] in Internet Information Services (IIS).</span></span>  
  
-   <span data-ttu-id="48c0e-132">*proxy_name* é o nome do arquivo proxy gerado.</span><span class="sxs-lookup"><span data-stu-id="48c0e-132">*proxy_name* is the name for the generated proxy file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48c0e-133">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="48c0e-133">See Also</span></span>  
 [<span data-ttu-id="48c0e-134">Operações de serviço Web categorizadas &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="48c0e-134">Categorized Web Service Operations &#40;Master Data Services&#41;</span></span>](categorized-web-service-operations-master-data-services.md)  
  
  
