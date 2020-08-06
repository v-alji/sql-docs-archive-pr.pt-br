---
title: Gerenciar pacotes e pastas programaticamente | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- enumerators [Integration Services]
- packages [Integration Services], managing
- custom enumerators [Integration Services]
ms.assetid: ec59b75d-ba09-44ac-9039-9d593bb462d9
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 695ff4ad020dbdfb2564b4964a55324db4248517
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684797"
---
# <a name="managing-packages-and-folders-programmatically"></a><span data-ttu-id="9bc69-102">Gerenciando pacotes e pastas programaticamente</span><span class="sxs-lookup"><span data-stu-id="9bc69-102">Managing Packages and Folders Programmatically</span></span>
  <span data-ttu-id="9bc69-103">Ao trabalhar de forma programática com pacotes do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], convém determinar se um pacote ou pasta individual existe ou gerenciar as pastas em que os pacotes estão armazenados.</span><span class="sxs-lookup"><span data-stu-id="9bc69-103">As you work programmatically with [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages, you may want to determine whether an individual package or folder exists, or to manage the folders in which packages are stored.</span></span> <span data-ttu-id="9bc69-104">A classe <xref:Microsoft.SqlServer.Dts.Runtime.Application> do namespace <xref:Microsoft.SqlServer.Dts.Runtime> fornece diversos métodos para atender a esses requisitos.</span><span class="sxs-lookup"><span data-stu-id="9bc69-104">The <xref:Microsoft.SqlServer.Dts.Runtime.Application> class of the <xref:Microsoft.SqlServer.Dts.Runtime> namespace provides a variety of methods to satisfy these requirements.</span></span>  
  
##  <a name="determining-whether-a-package-or-folder-exists"></a><a name="exists"></a> <span data-ttu-id="9bc69-105">Determinando se existe um pacote ou pasta</span><span class="sxs-lookup"><span data-stu-id="9bc69-105">Determining Whether a Package or Folder Exists</span></span>  
 <span data-ttu-id="9bc69-106">Para determinar programaticamente se existe um pacote salvo, chame um dos métodos a seguir antes de tentar carregar e executar o pacote:</span><span class="sxs-lookup"><span data-stu-id="9bc69-106">To determine programmatically whether a saved package exists, call one of the following methods before attempting to load and run the package:</span></span>  
  
|<span data-ttu-id="9bc69-107">Local de armazenamento</span><span class="sxs-lookup"><span data-stu-id="9bc69-107">Storage Location</span></span>|<span data-ttu-id="9bc69-108">Método de chamada</span><span class="sxs-lookup"><span data-stu-id="9bc69-108">Method to Call</span></span>|  
|----------------------|--------------------|  
|<span data-ttu-id="9bc69-109">Armazenamento de Pacotes SSIS</span><span class="sxs-lookup"><span data-stu-id="9bc69-109">SSIS Package Store</span></span>|<xref:Microsoft.SqlServer.Dts.Runtime.Application.ExistsOnDtsServer%2A>|  
|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|<xref:Microsoft.SqlServer.Dts.Runtime.Application.ExistsOnSqlServer%2A>|  
  
 <span data-ttu-id="9bc69-110">Para determinar programaticamente se existe uma pasta, chame um dos métodos a seguir antes de tentar listar os pacotes armazenados na pasta:</span><span class="sxs-lookup"><span data-stu-id="9bc69-110">To determine programmatically whether a folder exists, call one of the following methods before attempting to list the packages stored in the folder, :</span></span>  
  
|<span data-ttu-id="9bc69-111">Local de armazenamento</span><span class="sxs-lookup"><span data-stu-id="9bc69-111">Storage Location</span></span>|<span data-ttu-id="9bc69-112">Método de chamada</span><span class="sxs-lookup"><span data-stu-id="9bc69-112">Method to Call</span></span>|  
|----------------------|--------------------|  
|<span data-ttu-id="9bc69-113">Armazenamento de Pacotes SSIS</span><span class="sxs-lookup"><span data-stu-id="9bc69-113">SSIS Package Store</span></span>|<xref:Microsoft.SqlServer.Dts.Runtime.Application.FolderExistsOnDtsServer%2A>|  
|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|<xref:Microsoft.SqlServer.Dts.Runtime.Application.FolderExistsOnSqlServer%2A>|  
  

  
##  <a name="managing-packages-and-folders"></a><a name="managing"></a> <span data-ttu-id="9bc69-114">Gerenciar pacotes e pastas</span><span class="sxs-lookup"><span data-stu-id="9bc69-114">Managing Packages and Folders</span></span>  
 <span data-ttu-id="9bc69-115">A classe <xref:Microsoft.SqlServer.Dts.Runtime.Application> do namespace <xref:Microsoft.SqlServer.Dts.Runtime> fornece métodos adicionais para gerenciar pacotes e as pastas nas quais eles são armazenados.</span><span class="sxs-lookup"><span data-stu-id="9bc69-115">The <xref:Microsoft.SqlServer.Dts.Runtime.Application> class of the <xref:Microsoft.SqlServer.Dts.Runtime> namespace provides additional methods for managing packages and the folders in which they are stored.</span></span>  
  
###  <a name="removing-a-package"></a><a name="managing_rempkg"></a> <span data-ttu-id="9bc69-116">Remover um pacote</span><span class="sxs-lookup"><span data-stu-id="9bc69-116">Removing a Package</span></span>  
 <span data-ttu-id="9bc69-117">Para remover um pacote salvo programaticamente, chame um dos métodos seguintes:</span><span class="sxs-lookup"><span data-stu-id="9bc69-117">To remove a saved package programmatically, call one of the following methods:</span></span>  
  
|<span data-ttu-id="9bc69-118">Local de armazenamento</span><span class="sxs-lookup"><span data-stu-id="9bc69-118">Storage Location</span></span>|<span data-ttu-id="9bc69-119">Método de chamada</span><span class="sxs-lookup"><span data-stu-id="9bc69-119">Method to Call</span></span>|  
|----------------------|--------------------|  
|<span data-ttu-id="9bc69-120">Armazenamento de Pacotes SSIS</span><span class="sxs-lookup"><span data-stu-id="9bc69-120">SSIS Package Store</span></span>|<xref:Microsoft.SqlServer.Dts.Runtime.Application.RemoveFromDtsServer%2A>|  
|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|<xref:Microsoft.SqlServer.Dts.Runtime.Application.RemoveFromSqlServer%2A>|  
  

  
###  <a name="creating-a-folder"></a><a name="managing_create"></a> <span data-ttu-id="9bc69-121">Criar uma pasta</span><span class="sxs-lookup"><span data-stu-id="9bc69-121">Creating a Folder</span></span>  
 <span data-ttu-id="9bc69-122">Para criar uma pasta de armazenamento programaticamente, chame um dos métodos seguintes:</span><span class="sxs-lookup"><span data-stu-id="9bc69-122">To create a storage folder programmatically, call one of the following methods:</span></span>  
  
|<span data-ttu-id="9bc69-123">Local de armazenamento</span><span class="sxs-lookup"><span data-stu-id="9bc69-123">Storage Location</span></span>|<span data-ttu-id="9bc69-124">Método de chamada</span><span class="sxs-lookup"><span data-stu-id="9bc69-124">Method to Call</span></span>|  
|----------------------|--------------------|  
|<span data-ttu-id="9bc69-125">Armazenamento de Pacotes SSIS</span><span class="sxs-lookup"><span data-stu-id="9bc69-125">SSIS Package Store</span></span>|<xref:Microsoft.SqlServer.Dts.Runtime.Application.CreateFolderOnDtsServer%2A>|  
|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|<xref:Microsoft.SqlServer.Dts.Runtime.Application.CreateFolderOnSqlServer%2A>|  
  

  
###  <a name="removing-a-folder"></a><a name="managing_remfldr"></a> <span data-ttu-id="9bc69-126">Remover uma pasta</span><span class="sxs-lookup"><span data-stu-id="9bc69-126">Removing a Folder</span></span>  
 <span data-ttu-id="9bc69-127">Para remover uma pasta de armazenamento programaticamente, chame um dos métodos seguintes:</span><span class="sxs-lookup"><span data-stu-id="9bc69-127">To remove a storage folder programmatically, call one of the following methods:</span></span>  
  
|<span data-ttu-id="9bc69-128">Local de armazenamento</span><span class="sxs-lookup"><span data-stu-id="9bc69-128">Storage Location</span></span>|<span data-ttu-id="9bc69-129">Método de chamada</span><span class="sxs-lookup"><span data-stu-id="9bc69-129">Method to Call</span></span>|  
|----------------------|--------------------|  
|<span data-ttu-id="9bc69-130">Armazenamento de Pacotes SSIS</span><span class="sxs-lookup"><span data-stu-id="9bc69-130">SSIS Package Store</span></span>|<xref:Microsoft.SqlServer.Dts.Runtime.Application.RemoveFolderFromDtsServer%2A>|  
|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|<xref:Microsoft.SqlServer.Dts.Runtime.Application.RemoveFolderFromSqlServer%2A>|  
  
  
  
###  <a name="renaming-a-folder"></a><a name="managing_rename"></a> <span data-ttu-id="9bc69-131">Renomear uma pasta</span><span class="sxs-lookup"><span data-stu-id="9bc69-131">Renaming a Folder</span></span>  
 <span data-ttu-id="9bc69-132">Para renomear uma pasta de armazenamento programaticamente, chame um dos métodos seguintes:</span><span class="sxs-lookup"><span data-stu-id="9bc69-132">To rename a storage folder programmatically, call one of the following methods:</span></span>  
  
|<span data-ttu-id="9bc69-133">Local de armazenamento</span><span class="sxs-lookup"><span data-stu-id="9bc69-133">Storage Location</span></span>|<span data-ttu-id="9bc69-134">Método de chamada</span><span class="sxs-lookup"><span data-stu-id="9bc69-134">Method to Call</span></span>|  
|----------------------|--------------------|  
|<span data-ttu-id="9bc69-135">Armazenamento de Pacotes SSIS</span><span class="sxs-lookup"><span data-stu-id="9bc69-135">SSIS Package Store</span></span>|<xref:Microsoft.SqlServer.Dts.Runtime.Application.RenameFolderOnDtsServer%2A>|  
|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|<xref:Microsoft.SqlServer.Dts.Runtime.Application.RenameFolderOnSqlServer%2A>|  
  

  
<span data-ttu-id="9bc69-136">![Ícone de Integration Services (pequeno)](../media/dts-16.gif "Ícone do Integration Services (pequeno)")  **Mantenha-se atualizado com Integration Services**</span><span class="sxs-lookup"><span data-stu-id="9bc69-136">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="9bc69-137">Para obter os downloads, artigos, exemplos e vídeos mais recentes da Microsoft, assim como soluções selecionadas pela comunidade, visite a página do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] no MSDN:</span><span class="sxs-lookup"><span data-stu-id="9bc69-137">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="9bc69-138">Visite a página do Integration Services no MSDN</span><span class="sxs-lookup"><span data-stu-id="9bc69-138">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="9bc69-139">Para receber uma notificação automática dessas atualizações, assine os RSS feeds disponíveis na página.</span><span class="sxs-lookup"><span data-stu-id="9bc69-139">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9bc69-140">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9bc69-140">See Also</span></span>  
 <span data-ttu-id="9bc69-141">[Gerenciamento de Pacotes &#40;serviço SSIS&#41;](../service/package-management-ssis-service.md) </span><span class="sxs-lookup"><span data-stu-id="9bc69-141">[Package Management &#40;SSIS Service&#41;](../service/package-management-ssis-service.md) </span></span>  
 [<span data-ttu-id="9bc69-142">Enumerando pacotes disponíveis programaticamente</span><span class="sxs-lookup"><span data-stu-id="9bc69-142">Enumerating Available Packages Programmatically</span></span>](../run-manage-packages-programmatically/enumerating-available-packages-programmatically.md)  
  
  
