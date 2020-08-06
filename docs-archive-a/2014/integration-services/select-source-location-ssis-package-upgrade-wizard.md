---
title: Selecionar local de origem (Assistente de atualização de pacotes SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.is.upgradewizard.selectsourcelocation.f1
ms.assetid: 429f146e-edb4-4401-a225-f2c8468971c5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e24eec77dc87a6215f9d686cf5af964cc244d68d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678844"
---
# <a name="select-source-location-ssis-package-upgrade-wizard"></a><span data-ttu-id="96ea9-102">Selecionar Local de Origem (Assistente de Atualização de Pacotes SSIS)</span><span class="sxs-lookup"><span data-stu-id="96ea9-102">Select Source Location (SSIS Package Upgrade Wizard)</span></span>
  <span data-ttu-id="96ea9-103">Use a página **Selecionar Local de Origem** para especificar a origem a partir da qual os pacotes serão atualizados.</span><span class="sxs-lookup"><span data-stu-id="96ea9-103">Use the **Select Source Location** page to specify the source from which to upgrade packages.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="96ea9-104">Essa página só está disponível quando o Assistente de Atualização de Pacotes do [!INCLUDE[ssIS](../includes/ssis-md.md)] é executado por meio do [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] ou no prompt de comando.</span><span class="sxs-lookup"><span data-stu-id="96ea9-104">This page is only available when you run the [!INCLUDE[ssIS](../includes/ssis-md.md)] Package Upgrade Wizard from [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] or at the command prompt.</span></span>  
  
 <span data-ttu-id="96ea9-105">**Para executar o Assistente de Atualização de Pacotes SSIS**</span><span class="sxs-lookup"><span data-stu-id="96ea9-105">**To run the SSIS Package Upgrade Wizard**</span></span>  
  
-   [<span data-ttu-id="96ea9-106">Atualizar pacotes do Integration Services usando o Assistente de Atualização de Pacote SSIS</span><span class="sxs-lookup"><span data-stu-id="96ea9-106">Upgrade Integration Services Packages Using the SSIS Package Upgrade Wizard</span></span>](install-windows/upgrade-integration-services-packages-using-the-ssis-package-upgrade-wizard.md)  
  
## <a name="static-options"></a><span data-ttu-id="96ea9-107">Opções estáticas</span><span class="sxs-lookup"><span data-stu-id="96ea9-107">Static Options</span></span>  
 <span data-ttu-id="96ea9-108">**Origem do pacote**</span><span class="sxs-lookup"><span data-stu-id="96ea9-108">**Package source**</span></span>  
 <span data-ttu-id="96ea9-109">Selecione o local de armazenamento que contém os pacotes a serem atualizados.</span><span class="sxs-lookup"><span data-stu-id="96ea9-109">Select the storage location that contains the packages to be upgraded.</span></span> <span data-ttu-id="96ea9-110">Os valores dessa opção estão relacionados na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="96ea9-110">This option has the values listed in the following table.</span></span>  
  
|<span data-ttu-id="96ea9-111">Valor</span><span class="sxs-lookup"><span data-stu-id="96ea9-111">Value</span></span>|<span data-ttu-id="96ea9-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="96ea9-112">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="96ea9-113">**Sistema de Arquivos**</span><span class="sxs-lookup"><span data-stu-id="96ea9-113">**File System**</span></span>|<span data-ttu-id="96ea9-114">Indica que os pacotes a serem atualizados estão em uma pasta no computador local.</span><span class="sxs-lookup"><span data-stu-id="96ea9-114">Indicates that the packages to be upgraded are in a folder on the local computer.</span></span><br /><br /> <span data-ttu-id="96ea9-115">Para que o assistente faça backup dos pacotes originais antes de atualizá-los, esses pacotes devem ser armazenados no sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="96ea9-115">To have the wizard back up the original packages before upgrading those packages, the original packages must be stored in the file system.</span></span> <span data-ttu-id="96ea9-116">Para obter mais informações, consulte o tópico de instruções.</span><span class="sxs-lookup"><span data-stu-id="96ea9-116">For more information, see How To Topic.</span></span>|  
|<span data-ttu-id="96ea9-117">**Armazenamento de Pacotes SSIS**</span><span class="sxs-lookup"><span data-stu-id="96ea9-117">**SSIS Package Store**</span></span>|<span data-ttu-id="96ea9-118">Indica que os pacotes a serem atualizados estão no armazenamento de pacotes.</span><span class="sxs-lookup"><span data-stu-id="96ea9-118">Indicates that the packages to be upgraded are in the package store.</span></span> <span data-ttu-id="96ea9-119">O repositório de pacotes consiste no conjunto de pastas do sistema de arquivos gerenciado pelo serviço do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="96ea9-119">The package store consists of the set of file system folders that the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service manages.</span></span> <span data-ttu-id="96ea9-120">Para obter mais informações, consulte [Gerenciamento de pacotes &#40;Serviço SSIS&#41;](service/package-management-ssis-service.md).</span><span class="sxs-lookup"><span data-stu-id="96ea9-120">For more information, see [Package Management &#40;SSIS Service&#41;](service/package-management-ssis-service.md).</span></span><br /><br /> <span data-ttu-id="96ea9-121">Selecione esse valor para exibir as opções dinâmicas de **Origem do pacote** correspondentes.</span><span class="sxs-lookup"><span data-stu-id="96ea9-121">Selecting this value displays the corresponding **Package source** dynamic options.</span></span>|  
|<span data-ttu-id="96ea9-122">**Microsoft SQL Server**</span><span class="sxs-lookup"><span data-stu-id="96ea9-122">**Microsoft SQL Server**</span></span>|<span data-ttu-id="96ea9-123">Indica que os pacotes a serem atualizados são de uma instância existente do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="96ea9-123">Indicates the packages to be upgraded are from an existing instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span><br /><br /> <span data-ttu-id="96ea9-124">Selecione esse valor para exibir as opções dinâmicas de **Origem do pacote** correspondentes.</span><span class="sxs-lookup"><span data-stu-id="96ea9-124">Selecting this value displays the corresponding **Package source** dynamic options.</span></span>|  
  
 <span data-ttu-id="96ea9-125">**Pasta**</span><span class="sxs-lookup"><span data-stu-id="96ea9-125">**Folder**</span></span>  
 <span data-ttu-id="96ea9-126">Digite o nome de uma pasta que contém os pacotes que você quer atualizar ou clique em **Procurar** e localize a pasta.</span><span class="sxs-lookup"><span data-stu-id="96ea9-126">Type the name of a folder that contains the packages you want to upgrade or click **Browse** and locate the folder.</span></span>  
  
 <span data-ttu-id="96ea9-127">**Procurar**</span><span class="sxs-lookup"><span data-stu-id="96ea9-127">**Browse**</span></span>  
 <span data-ttu-id="96ea9-128">Navegue para localizar a pasta que contém os pacotes você deseja atualizar.</span><span class="sxs-lookup"><span data-stu-id="96ea9-128">Browse to locate the folder that contains the packages you want to upgrade.</span></span>  
  
## <a name="package-source-dynamic-options"></a><span data-ttu-id="96ea9-129">Opções dinâmicas de Origem do pacote</span><span class="sxs-lookup"><span data-stu-id="96ea9-129">Package Source Dynamic Options</span></span>  
  
### <a name="package-source--ssis-package-store"></a><span data-ttu-id="96ea9-130">Origem do pacote = Repositório de Pacotes SSIS</span><span class="sxs-lookup"><span data-stu-id="96ea9-130">Package source = SSIS Package Store</span></span>  
 <span data-ttu-id="96ea9-131">**Servidor**</span><span class="sxs-lookup"><span data-stu-id="96ea9-131">**Server**</span></span>  
 <span data-ttu-id="96ea9-132">Digite o nome do servidor que tem os pacotes a serem atualizados ou selecione esse servidor na lista.</span><span class="sxs-lookup"><span data-stu-id="96ea9-132">Type the name of the server that has the packages to be upgraded, or select this server in the list.</span></span>  
  
### <a name="package-source--microsoft-sql-server"></a><span data-ttu-id="96ea9-133">Origem do pacote = Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="96ea9-133">Package source = Microsoft SQL Server</span></span>  
 <span data-ttu-id="96ea9-134">**Servidor**</span><span class="sxs-lookup"><span data-stu-id="96ea9-134">**Server**</span></span>  
 <span data-ttu-id="96ea9-135">Digite o nome do servidor que tem os pacotes a serem atualizados ou selecione esse servidor na lista.</span><span class="sxs-lookup"><span data-stu-id="96ea9-135">Type the name of the server that has the packages to be upgraded, or select this server from the list.</span></span>  
  
 <span data-ttu-id="96ea9-136">**Usar autenticação do Windows**</span><span class="sxs-lookup"><span data-stu-id="96ea9-136">**Use Windows authentication**</span></span>  
 <span data-ttu-id="96ea9-137">Selecione para usar a Autenticação do Windows para estabelecer conexão com o servidor.</span><span class="sxs-lookup"><span data-stu-id="96ea9-137">Select to use Windows Authentication to connect to the server.</span></span>  
  
 <span data-ttu-id="96ea9-138">**Usar autenticação SQL Server**</span><span class="sxs-lookup"><span data-stu-id="96ea9-138">**Use SQL Server authentication**</span></span>  
 <span data-ttu-id="96ea9-139">Selecione para usar a Autenticação do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] para estabelecer conexão com o servidor.</span><span class="sxs-lookup"><span data-stu-id="96ea9-139">Select to use [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication to connect to the server.</span></span> <span data-ttu-id="96ea9-140">Se você usar a Autenticação do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , será preciso fornecer um nome de usuário e uma senha.</span><span class="sxs-lookup"><span data-stu-id="96ea9-140">If you use [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication, you must provide a user name and password.</span></span>  
  
 <span data-ttu-id="96ea9-141">**Nome de usuário**</span><span class="sxs-lookup"><span data-stu-id="96ea9-141">**User name**</span></span>  
 <span data-ttu-id="96ea9-142">Digite o nome de usuário que a Autenticação do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] usará para estabelecer conexão com o servidor.</span><span class="sxs-lookup"><span data-stu-id="96ea9-142">Type the user name that [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication will use to connect to the server.</span></span>  
  
 <span data-ttu-id="96ea9-143">**Senha**</span><span class="sxs-lookup"><span data-stu-id="96ea9-143">**Password**</span></span>  
 <span data-ttu-id="96ea9-144">Digite a senha que a Autenticação do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] usará para estabelecer conexão com o servidor.</span><span class="sxs-lookup"><span data-stu-id="96ea9-144">Type the password that [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication will use to connect to the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96ea9-145">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="96ea9-145">See Also</span></span>  
 [<span data-ttu-id="96ea9-146">Atualizar pacotes do Integration Services</span><span class="sxs-lookup"><span data-stu-id="96ea9-146">Upgrade Integration Services Packages</span></span>](install-windows/upgrade-integration-services-packages.md)  
  
  
