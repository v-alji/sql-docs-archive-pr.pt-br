---
title: Permissões de pasta e arquivo (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- security [Master Data Services], file and folder
- folders [Master Data Services]
- files [Master Data Services]
ms.assetid: 6402d81d-7349-47b1-95ca-99b0c0f4f373
author: lrtoyou1223
ms.author: lle
robots: noindex,nofollow
ms.openlocfilehash: 6dc356e074574a4c520b1f4de2f41db0e983c4df
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680531"
---
# <a name="folder-and-file-permissions-master-data-services"></a><span data-ttu-id="f2dc9-102">Permissões de pasta e arquivo (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="f2dc9-102">Folder and File Permissions (Master Data Services)</span></span>
  <span data-ttu-id="f2dc9-103">Quando você instala o [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], as pastas e arquivos são instalados no sistema de arquivos no caminho de instalação especificado para recursos compartilhados do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f2dc9-103">When you install [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], folders and files are installed in the file system at the installation path you specify for [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] shared features.</span></span> <span data-ttu-id="f2dc9-104">Se você usar o caminho de instalação padrão para [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] recursos compartilhados, o caminho de instalação do [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] é *unidade*: \Program Files\Microsoft SQL Server\120\Master Data Services.</span><span class="sxs-lookup"><span data-stu-id="f2dc9-104">If you use the default installation path for [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] shared features, the installation path for [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] is *drive*:\Program Files\Microsoft SQL Server\120\Master Data Services.</span></span> <span data-ttu-id="f2dc9-105">Embora seja possível alterar o caminho de instalação de recursos compartilhados, considere as permissões que são herdadas da pasta pai e as permissões que são definidas explicitamente para o [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f2dc9-105">Although you can change the shared features installation path, be aware of permissions that are inherited from the parent folder and permissions that are explicitly set for [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)].</span></span>  
  
## <a name="inherited-permissions"></a><span data-ttu-id="f2dc9-106">Permissões herdadas</span><span class="sxs-lookup"><span data-stu-id="f2dc9-106">Inherited Permissions</span></span>  
 <span data-ttu-id="f2dc9-107">A pasta **Microsoft SQL Server** , a pasta **Master Data Services** e a maioria das subpastas e arquivos herda permissões da pasta pai especificada na Instalação do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f2dc9-107">The **Microsoft SQL Server** folder, the **Master Data Services** folder, and most subfolders and files inherit permissions from the parent folder specified in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Setup.</span></span> <span data-ttu-id="f2dc9-108">Se você escolher o local de instalação padrão, a pasta pai da qual as permissões são herdadas será *drive*:\Program Files.</span><span class="sxs-lookup"><span data-stu-id="f2dc9-108">If you choose the default installation location, the parent folder that permissions are inherited from is *drive*:\Program Files.</span></span> <span data-ttu-id="f2dc9-109">A tabela a seguir descreve as permissões padrão para **Arquivos de Programas**.</span><span class="sxs-lookup"><span data-stu-id="f2dc9-109">The following table describes the default permissions for **Program Files**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f2dc9-110">Se você modificar as permissões padrão de **Arquivos de Programas**ou escolher outro local de instalação, as pastas e arquivos do [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] herdarão as permissões da respectiva pasta pai e as permissões poderão diferir das que são descritas na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="f2dc9-110">If you modify default permissions for **Program Files**, or you choose a different installation location, the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] folders and files inherit permissions from their parent folder accordingly, and the permissions might differ from those described in the following table.</span></span>  
  
###### <a name="program-files-default-permissions"></a><span data-ttu-id="f2dc9-111">Permissões padrão de Arquivos de Programas</span><span class="sxs-lookup"><span data-stu-id="f2dc9-111">Program Files Default Permissions</span></span>  
  
|<span data-ttu-id="f2dc9-112">Nome do grupo ou conta</span><span class="sxs-lookup"><span data-stu-id="f2dc9-112">Group or account name</span></span>|<span data-ttu-id="f2dc9-113">Permissões</span><span class="sxs-lookup"><span data-stu-id="f2dc9-113">Permissions</span></span>|  
|---------------------------|-----------------|  
|<span data-ttu-id="f2dc9-114">CREATOR OWNER</span><span class="sxs-lookup"><span data-stu-id="f2dc9-114">CREATOR OWNER</span></span>|<span data-ttu-id="f2dc9-115">Permissões especiais</span><span class="sxs-lookup"><span data-stu-id="f2dc9-115">Special permissions</span></span>|  
|<span data-ttu-id="f2dc9-116">SYSTEM</span><span class="sxs-lookup"><span data-stu-id="f2dc9-116">SYSTEM</span></span>|<span data-ttu-id="f2dc9-117">Permissões especiais</span><span class="sxs-lookup"><span data-stu-id="f2dc9-117">Special permissions</span></span>|  
|<span data-ttu-id="f2dc9-118">Administradores</span><span class="sxs-lookup"><span data-stu-id="f2dc9-118">Administrators</span></span>|<span data-ttu-id="f2dc9-119">Permissões especiais</span><span class="sxs-lookup"><span data-stu-id="f2dc9-119">Special permissions</span></span>|  
|<span data-ttu-id="f2dc9-120">Usuários</span><span class="sxs-lookup"><span data-stu-id="f2dc9-120">Users</span></span>|<span data-ttu-id="f2dc9-121">Ler & executar, listar conteúdo da pasta, leitura</span><span class="sxs-lookup"><span data-stu-id="f2dc9-121">Read & execute, List folder contents, Read</span></span>|  
|<span data-ttu-id="f2dc9-122">TrustedInstaller</span><span class="sxs-lookup"><span data-stu-id="f2dc9-122">TrustedInstaller</span></span>|<span data-ttu-id="f2dc9-123">Listar conteúdo de pasta, permissões especiais</span><span class="sxs-lookup"><span data-stu-id="f2dc9-123">List folder contents, Special permissions</span></span>|  
  
## <a name="explicit-permissions"></a><span data-ttu-id="f2dc9-124">Permissões explícitas</span><span class="sxs-lookup"><span data-stu-id="f2dc9-124">Explicit Permissions</span></span>  
 <span data-ttu-id="f2dc9-125">A pasta **MDSTempDir** e o arquivo Web.config do [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] (na pasta **WebApplication** ) não herdam permissões.</span><span class="sxs-lookup"><span data-stu-id="f2dc9-125">The **MDSTempDir** folder and the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] Web.config file (in the **WebApplication** folder) do not inherit permissions.</span></span> <span data-ttu-id="f2dc9-126">Eles têm permissões que são definidas explicitamente quando você instala o [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], independentemente do caminho de instalação escolhido.</span><span class="sxs-lookup"><span data-stu-id="f2dc9-126">They have permissions that are set explicitly when you install [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], regardless of the installation path you choose.</span></span> <span data-ttu-id="f2dc9-127">Não modifique essas permissões.</span><span class="sxs-lookup"><span data-stu-id="f2dc9-127">Do not modify these permissions.</span></span>  
  
###### <a name="mdstempdir-permissions"></a><span data-ttu-id="f2dc9-128">Permissões de MDSTempDir</span><span class="sxs-lookup"><span data-stu-id="f2dc9-128">MDSTempDir Permissions</span></span>  
  
|<span data-ttu-id="f2dc9-129">Nome do grupo ou conta</span><span class="sxs-lookup"><span data-stu-id="f2dc9-129">Group or account name</span></span>|<span data-ttu-id="f2dc9-130">Permissões</span><span class="sxs-lookup"><span data-stu-id="f2dc9-130">Permissions</span></span>|  
|---------------------------|-----------------|  
|<span data-ttu-id="f2dc9-131">SYSTEM</span><span class="sxs-lookup"><span data-stu-id="f2dc9-131">SYSTEM</span></span>|<span data-ttu-id="f2dc9-132">Modificar, ler & executar, listar conteúdo da pasta, leitura, gravação</span><span class="sxs-lookup"><span data-stu-id="f2dc9-132">Modify, Read & execute, List folder contents, Read, Write</span></span>|  
|<span data-ttu-id="f2dc9-133">Administradores</span><span class="sxs-lookup"><span data-stu-id="f2dc9-133">Administrators</span></span>|<span data-ttu-id="f2dc9-134">Modificar, ler & executar, listar conteúdo da pasta, leitura, gravação</span><span class="sxs-lookup"><span data-stu-id="f2dc9-134">Modify, Read & execute, List folder contents, Read, Write</span></span>|  
|<span data-ttu-id="f2dc9-135">MDS_ServiceAccounts</span><span class="sxs-lookup"><span data-stu-id="f2dc9-135">MDS_ServiceAccounts</span></span>|<span data-ttu-id="f2dc9-136">Modificar, ler & executar, listar conteúdo da pasta, leitura, gravação</span><span class="sxs-lookup"><span data-stu-id="f2dc9-136">Modify, Read & execute, List folder contents, Read, Write</span></span>|  
  
###### <a name="webconfig-permissions"></a><span data-ttu-id="f2dc9-137">Permissões de Web.config</span><span class="sxs-lookup"><span data-stu-id="f2dc9-137">Web.config Permissions</span></span>  
  
|<span data-ttu-id="f2dc9-138">Nome do grupo ou conta</span><span class="sxs-lookup"><span data-stu-id="f2dc9-138">Group or account name</span></span>|<span data-ttu-id="f2dc9-139">Permissões</span><span class="sxs-lookup"><span data-stu-id="f2dc9-139">Permissions</span></span>|  
|---------------------------|-----------------|  
|<span data-ttu-id="f2dc9-140">SYSTEM</span><span class="sxs-lookup"><span data-stu-id="f2dc9-140">SYSTEM</span></span>|<span data-ttu-id="f2dc9-141">Controle completo, modificar, ler & executar, leitura, gravação</span><span class="sxs-lookup"><span data-stu-id="f2dc9-141">Full control, Modify, Read & execute, Read, Write</span></span>|  
|<span data-ttu-id="f2dc9-142">Administradores</span><span class="sxs-lookup"><span data-stu-id="f2dc9-142">Administrators</span></span>|<span data-ttu-id="f2dc9-143">Controle completo, modificar, ler & executar, leitura, gravação</span><span class="sxs-lookup"><span data-stu-id="f2dc9-143">Full control, Modify, Read & execute, Read, Write</span></span>|  
|<span data-ttu-id="f2dc9-144">MDS_ServiceAccounts</span><span class="sxs-lookup"><span data-stu-id="f2dc9-144">MDS_ServiceAccounts</span></span>|<span data-ttu-id="f2dc9-145">Ler & executar, leitura</span><span class="sxs-lookup"><span data-stu-id="f2dc9-145">Read & execute, Read</span></span>|  
  
 <span data-ttu-id="f2dc9-146">Para obter mais informações sobre o conteúdo do arquivo Web.config do [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], consulte [Referência de configuração da Web &#40;Master Data Services&#41;](web-configuration-reference-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="f2dc9-146">For more information about the contents of the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] Web.config file, see [Web Configuration Reference &#40;Master Data Services&#41;](web-configuration-reference-master-data-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2dc9-147">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f2dc9-147">See Also</span></span>  
 [<span data-ttu-id="f2dc9-148">Instalar o Master Data Services</span><span class="sxs-lookup"><span data-stu-id="f2dc9-148">Install Master Data Services</span></span>](install-windows/install-master-data-services.md)  
  
  
