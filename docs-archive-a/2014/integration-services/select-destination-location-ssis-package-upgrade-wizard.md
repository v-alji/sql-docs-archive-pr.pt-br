---
title: Selecionar local de destino (Assistente de atualização de pacotes SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.is.upgradewizard.selectdestinationlocation.f1
ms.assetid: 89274a71-0ffe-4889-84df-f5a7d78459ef
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9411157434c3dbb9fb033f7b63b5e6041fd8f75d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583718"
---
# <a name="select-destination-location-ssis-package-upgrade-wizard"></a><span data-ttu-id="9abd5-102">Selecionar Local de Destino (Assistente de Atualização de Pacotes SSIS)</span><span class="sxs-lookup"><span data-stu-id="9abd5-102">Select Destination Location (SSIS Package Upgrade Wizard)</span></span>
  <span data-ttu-id="9abd5-103">Use a página **Selecionar Local de Destino** para especificar o destino no qual os pacotes atualizados serão salvos.</span><span class="sxs-lookup"><span data-stu-id="9abd5-103">Use the **Select Destination Location** page to specify the destination to which to save the upgraded packages.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9abd5-104">Essa página só está disponível quando o Assistente de Atualização de Pacotes do [!INCLUDE[ssIS](../includes/ssis-md.md)] é executado por meio do [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] ou no prompt de comando.</span><span class="sxs-lookup"><span data-stu-id="9abd5-104">This page is only available when you run the [!INCLUDE[ssIS](../includes/ssis-md.md)] Package Upgrade Wizard from [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] or at the command prompt.</span></span>  
  
 <span data-ttu-id="9abd5-105">**Para executar o Assistente de Atualização de Pacotes SSIS**</span><span class="sxs-lookup"><span data-stu-id="9abd5-105">**To run the SSIS Package Upgrade Wizard**</span></span>  
  
-   [<span data-ttu-id="9abd5-106">Atualizar pacotes do Integration Services usando o Assistente de Atualização de Pacote SSIS</span><span class="sxs-lookup"><span data-stu-id="9abd5-106">Upgrade Integration Services Packages Using the SSIS Package Upgrade Wizard</span></span>](install-windows/upgrade-integration-services-packages-using-the-ssis-package-upgrade-wizard.md)  
  
## <a name="static-options"></a><span data-ttu-id="9abd5-107">Opções estáticas</span><span class="sxs-lookup"><span data-stu-id="9abd5-107">Static Options</span></span>  
 <span data-ttu-id="9abd5-108">**Salvar no local de origem**</span><span class="sxs-lookup"><span data-stu-id="9abd5-108">**Save to source location**</span></span>  
 <span data-ttu-id="9abd5-109">Salve os pacotes atualizados ao mesmo local especificado na página **Selecionar Local de Origem** do assistente.</span><span class="sxs-lookup"><span data-stu-id="9abd5-109">Save the upgraded packages to the same location as specified on the **Select Source Location** page of the wizard.</span></span>  
  
 <span data-ttu-id="9abd5-110">Se os pacotes originais estiverem armazenados no sistema de arquivos e você desejar que o assistente faça backup desses pacotes, selecione a opção **Salvar no local de origem** .</span><span class="sxs-lookup"><span data-stu-id="9abd5-110">If the original packages are stored in the file system and you want the wizard to back up those packages, select the **Save to source location** option.</span></span> <span data-ttu-id="9abd5-111">Para obter mais informações, consulte [Atualizar pacotes do Integration Services usando o Assistente de Atualização de Pacote SSIS](install-windows/upgrade-integration-services-packages-using-the-ssis-package-upgrade-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="9abd5-111">For more information, see [Upgrade Integration Services Packages Using the SSIS Package Upgrade Wizard](install-windows/upgrade-integration-services-packages-using-the-ssis-package-upgrade-wizard.md).</span></span>  
  
 <span data-ttu-id="9abd5-112">**Selecionar novo local de destino**</span><span class="sxs-lookup"><span data-stu-id="9abd5-112">**Select new destination location**</span></span>  
 <span data-ttu-id="9abd5-113">Salve os pacotes atualizados no local de destino especificado nesta página.</span><span class="sxs-lookup"><span data-stu-id="9abd5-113">Save the upgraded packages to the destination location that is specified on this page.</span></span>  
  
 <span data-ttu-id="9abd5-114">**Origem do pacote**</span><span class="sxs-lookup"><span data-stu-id="9abd5-114">**Package source**</span></span>  
 <span data-ttu-id="9abd5-115">Especifique onde os pacotes de atualização serão armazenados.</span><span class="sxs-lookup"><span data-stu-id="9abd5-115">Specify where the upgrade packages are to be stored.</span></span> <span data-ttu-id="9abd5-116">Os valores dessa opção estão relacionados na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="9abd5-116">This option has the values listed in the following table.</span></span>  
  
|<span data-ttu-id="9abd5-117">Valor</span><span class="sxs-lookup"><span data-stu-id="9abd5-117">Value</span></span>|<span data-ttu-id="9abd5-118">Descrição</span><span class="sxs-lookup"><span data-stu-id="9abd5-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="9abd5-119">**Sistema de Arquivos**</span><span class="sxs-lookup"><span data-stu-id="9abd5-119">**File System**</span></span>|<span data-ttu-id="9abd5-120">Indica que os pacotes atualizados serão salvos em uma pasta no computador local.</span><span class="sxs-lookup"><span data-stu-id="9abd5-120">Indicates that the upgraded packages are to be saved to a folder on the local computer.</span></span>|  
|<span data-ttu-id="9abd5-121">**Armazenamento de Pacotes SSIS**</span><span class="sxs-lookup"><span data-stu-id="9abd5-121">**SSIS Package Store**</span></span>|<span data-ttu-id="9abd5-122">Indica que os pacotes atualizados serão salvos no armazenamento de pacotes do Integration Services.</span><span class="sxs-lookup"><span data-stu-id="9abd5-122">Indicates that the upgraded packages are to be saved to the Integration Services package store.</span></span> <span data-ttu-id="9abd5-123">O repositório de pacotes consiste no conjunto de pastas do sistema de arquivos gerenciado pelo serviço do Integration Services.</span><span class="sxs-lookup"><span data-stu-id="9abd5-123">The package store consists of the set of file system folders that the Integration Services service manages.</span></span> <span data-ttu-id="9abd5-124">Para obter mais informações, consulte [Gerenciamento de pacotes &#40;Serviço SSIS&#41;](service/package-management-ssis-service.md).</span><span class="sxs-lookup"><span data-stu-id="9abd5-124">For more information, see [Package Management &#40;SSIS Service&#41;](service/package-management-ssis-service.md).</span></span><br /><br /> <span data-ttu-id="9abd5-125">Selecione esse valor para exibir as opções dinâmicas de **Origem do pacote** correspondentes.</span><span class="sxs-lookup"><span data-stu-id="9abd5-125">Selecting this value displays the corresponding **Package source** dynamics options.</span></span>|  
|<span data-ttu-id="9abd5-126">**Microsoft SQL Server**</span><span class="sxs-lookup"><span data-stu-id="9abd5-126">**Microsoft SQL Server**</span></span>|<span data-ttu-id="9abd5-127">Indica que os pacotes atualizados serão salvos em uma instância existente do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9abd5-127">Indicates that the upgraded packages are to be saved to an existing instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span><br /><br /> <span data-ttu-id="9abd5-128">Selecione esse valor para exibir as opções dinâmicas de **Origem do pacote** correspondentes.</span><span class="sxs-lookup"><span data-stu-id="9abd5-128">Selecting this value displays the corresponding dynamic **Package source** dynamic options.</span></span>|  
  
 <span data-ttu-id="9abd5-129">**Pasta**</span><span class="sxs-lookup"><span data-stu-id="9abd5-129">**Folder**</span></span>  
 <span data-ttu-id="9abd5-130">Digite o nome de uma pasta na qual os pacotes atualizados serão salvos ou clique em **Procurar** e localize a pasta.</span><span class="sxs-lookup"><span data-stu-id="9abd5-130">Type the name of a folder to which the upgraded packages will be saved, or click **Browse** and locate the folder.</span></span>  
  
 <span data-ttu-id="9abd5-131">**Procurar**</span><span class="sxs-lookup"><span data-stu-id="9abd5-131">**Browse**</span></span>  
 <span data-ttu-id="9abd5-132">Procure para localizar a pasta na qual os pacotes atualizados serão salvos.</span><span class="sxs-lookup"><span data-stu-id="9abd5-132">Browse to locate the folder to which the upgraded packages will be saved.</span></span>  
  
## <a name="package-source-dynamic-options"></a><span data-ttu-id="9abd5-133">Opções dinâmicas de Origem do pacote</span><span class="sxs-lookup"><span data-stu-id="9abd5-133">Package Source Dynamic Options</span></span>  
  
### <a name="package-source--ssis-package-store"></a><span data-ttu-id="9abd5-134">Origem do pacote = Repositório de Pacotes SSIS</span><span class="sxs-lookup"><span data-stu-id="9abd5-134">Package source = SSIS Package Store</span></span>  
 <span data-ttu-id="9abd5-135">**Servidor**</span><span class="sxs-lookup"><span data-stu-id="9abd5-135">**Server**</span></span>  
 <span data-ttu-id="9abd5-136">Digite o nome do servidor onde os pacotes de atualização serão salvos ou selecione um servidor na lista.</span><span class="sxs-lookup"><span data-stu-id="9abd5-136">Type the name of the server to which the upgrade packages will be saved, or select a server in the list.</span></span>  
  
### <a name="package-source--microsoft-sql-server"></a><span data-ttu-id="9abd5-137">Origem do pacote = Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="9abd5-137">Package source = Microsoft SQL Server</span></span>  
 <span data-ttu-id="9abd5-138">**Servidor**</span><span class="sxs-lookup"><span data-stu-id="9abd5-138">**Server**</span></span>  
 <span data-ttu-id="9abd5-139">Digite o nome do servidor onde os pacotes de atualização serão salvos ou selecione esse servidor na lista.</span><span class="sxs-lookup"><span data-stu-id="9abd5-139">Type the name of the server to which the upgrade packages will be saved, or select this server in the list.</span></span>  
  
 <span data-ttu-id="9abd5-140">**Usar autenticação do Windows**</span><span class="sxs-lookup"><span data-stu-id="9abd5-140">**Use Windows authentication**</span></span>  
 <span data-ttu-id="9abd5-141">Selecione para usar a Autenticação do Windows para estabelecer conexão com o servidor.</span><span class="sxs-lookup"><span data-stu-id="9abd5-141">Select to use Windows Authentication to connect to the server.</span></span>  
  
 <span data-ttu-id="9abd5-142">**Usar autenticação SQL Server**</span><span class="sxs-lookup"><span data-stu-id="9abd5-142">**Use SQL Server authentication**</span></span>  
 <span data-ttu-id="9abd5-143">Selecione para usar a Autenticação do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] para estabelecer conexão com o servidor.</span><span class="sxs-lookup"><span data-stu-id="9abd5-143">Select to use [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication to connect to the server.</span></span> <span data-ttu-id="9abd5-144">Se você usar a Autenticação do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , será preciso fornecer um nome de usuário e uma senha.</span><span class="sxs-lookup"><span data-stu-id="9abd5-144">If you use [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication, you must provide a user name and password.</span></span>  
  
 <span data-ttu-id="9abd5-145">**Nome de usuário**</span><span class="sxs-lookup"><span data-stu-id="9abd5-145">**User name**</span></span>  
 <span data-ttu-id="9abd5-146">Digite o nome de usuário a ser usado quando a Autenticação do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] for usada para estabelecer conexão com o servidor.</span><span class="sxs-lookup"><span data-stu-id="9abd5-146">Type the user name to be used when using [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication to connect to the server.</span></span>  
  
 <span data-ttu-id="9abd5-147">**Senha**</span><span class="sxs-lookup"><span data-stu-id="9abd5-147">**Password**</span></span>  
 <span data-ttu-id="9abd5-148">Digite a senha a ser usada quando a Autenticação do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] for usada para estabelecer conexão com o servidor.</span><span class="sxs-lookup"><span data-stu-id="9abd5-148">Type the password to be used when using [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication to connect to the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9abd5-149">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9abd5-149">See Also</span></span>  
 [<span data-ttu-id="9abd5-150">Atualizar pacotes do Integration Services</span><span class="sxs-lookup"><span data-stu-id="9abd5-150">Upgrade Integration Services Packages</span></span>](install-windows/upgrade-integration-services-packages.md)  
  
  
