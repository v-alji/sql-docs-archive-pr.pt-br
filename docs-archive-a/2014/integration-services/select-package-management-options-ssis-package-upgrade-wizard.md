---
title: Selecionar opções de Gerenciamento de Pacotes (Assistente de atualização de pacotes SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.is.upgradewizard.selectpackagemgtoptions.f1
ms.assetid: 810fc020-51cd-43ed-9f35-af99b4f35947
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b5113ad5a1f6758a75742ca58aef04ce92168649
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583716"
---
# <a name="select-package-management-options-ssis-package-upgrade-wizard"></a><span data-ttu-id="6a951-102">Selecionar Opções de Gerenciamento de Pacotes (Assistente de Atualização de Pacotes SSIS)</span><span class="sxs-lookup"><span data-stu-id="6a951-102">Select Package Management Options (SSIS Package Upgrade Wizard)</span></span>
  <span data-ttu-id="6a951-103">Use a página **Selecionar Opções de Gerenciamento de Pacote** para especificar opções para atualizar pacotes.</span><span class="sxs-lookup"><span data-stu-id="6a951-103">Use the **Select Package Management Options** page to specify options for upgrading packages.</span></span>  
  
 <span data-ttu-id="6a951-104">**Para executar o Assistente de Atualização de Pacotes SSIS**</span><span class="sxs-lookup"><span data-stu-id="6a951-104">**To run the SSIS Package Upgrade Wizard**</span></span>  
  
-   [<span data-ttu-id="6a951-105">Atualizar pacotes do Integration Services usando o Assistente de Atualização de Pacote SSIS</span><span class="sxs-lookup"><span data-stu-id="6a951-105">Upgrade Integration Services Packages Using the SSIS Package Upgrade Wizard</span></span>](install-windows/upgrade-integration-services-packages-using-the-ssis-package-upgrade-wizard.md)  
  
## <a name="options"></a><span data-ttu-id="6a951-106">Opções</span><span class="sxs-lookup"><span data-stu-id="6a951-106">Options</span></span>  
 <span data-ttu-id="6a951-107">**Atualizar cadeias de conexão para usar novos nomes de provedor**</span><span class="sxs-lookup"><span data-stu-id="6a951-107">**Update connection strings to use new provider names**</span></span>  
 <span data-ttu-id="6a951-108">Atualize as cadeias de conexão para usar os nomes dos seguintes provedores da versão atual do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="6a951-108">Update the connection strings to use the names for the following providers for the current release of [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="6a951-109">Provedor OLE DB para [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6a951-109">OLE DB Provider for [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)]</span></span>  
  
-   [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] <span data-ttu-id="6a951-110">Native Client</span><span class="sxs-lookup"><span data-stu-id="6a951-110">Native Client</span></span>  
  
 <span data-ttu-id="6a951-111">O Assistente de Atualização de Pacotes [!INCLUDE[ssIS](../includes/ssis-md.md)] só atualiza cadeias de conexão armazenadas em gerenciadores de conexões.</span><span class="sxs-lookup"><span data-stu-id="6a951-111">The [!INCLUDE[ssIS](../includes/ssis-md.md)] Package Upgrade Wizard updates only connection strings that are stored in connection managers.</span></span> <span data-ttu-id="6a951-112">O assistente não atualiza cadeias de conexão construídas dinamicamente com a linguagem de expressão do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] ou o código de uma tarefa Script.</span><span class="sxs-lookup"><span data-stu-id="6a951-112">The wizard does not update connection strings that are constructed dynamically by using the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] expression language, or by using code in a Script task.</span></span>  
  
 <span data-ttu-id="6a951-113">**Validar pacotes de atualização**</span><span class="sxs-lookup"><span data-stu-id="6a951-113">**Validate upgrade packages**</span></span>  
 <span data-ttu-id="6a951-114">Valide os pacotes de atualização e salve só os pacotes aprovados na validação.</span><span class="sxs-lookup"><span data-stu-id="6a951-114">Validate the upgrade packages and save only those upgrade packages that pass validation.</span></span>  
  
 <span data-ttu-id="6a951-115">Se você não selecionar essa opção, o assistente não validará pacotes de atualização.</span><span class="sxs-lookup"><span data-stu-id="6a951-115">If you do not select this option, the wizard will not validate upgrade packages.</span></span> <span data-ttu-id="6a951-116">Portanto, o assistente salvará todos os pacotes de atualização, independentemente de sua validez.</span><span class="sxs-lookup"><span data-stu-id="6a951-116">Therefore, the wizard will save all upgrade packages, regardless of whether the packages are valid or not.</span></span> <span data-ttu-id="6a951-117">O assistente salva os pacotes de atualização no destino especificado na página **Selecionar Local de Destino** do assistente.</span><span class="sxs-lookup"><span data-stu-id="6a951-117">The wizard saves upgrade packages to the destination that is specified on the **SelectDestination Location** page of the wizard.</span></span>  
  
 <span data-ttu-id="6a951-118">A validação prolonga o processo de atualização.</span><span class="sxs-lookup"><span data-stu-id="6a951-118">Validation adds time to the upgrade process.</span></span> <span data-ttu-id="6a951-119">Recomendamos que você não selecione essa opção para pacotes grandes que provavelmente serão atualizados com êxito.</span><span class="sxs-lookup"><span data-stu-id="6a951-119">We recommend that you do not select this option for large packages that are likely to be upgraded successfully.</span></span>  
  
 <span data-ttu-id="6a951-120">**Criar novas IDs de pacote**</span><span class="sxs-lookup"><span data-stu-id="6a951-120">**Create new package IDs**</span></span>  
 <span data-ttu-id="6a951-121">Crie novas IDs para os pacotes de atualização.</span><span class="sxs-lookup"><span data-stu-id="6a951-121">Create new package IDs for the upgrade packages.</span></span>  
  
 <span data-ttu-id="6a951-122">**Continuar o processo de upgrade quando um upgrade de pacote falhar**</span><span class="sxs-lookup"><span data-stu-id="6a951-122">**Continue upgrade process when a package upgrade fails**</span></span>  
 <span data-ttu-id="6a951-123">Especifique que o Assistente de Atualização de Pacotes [!INCLUDE[ssIS](../includes/ssis-md.md)] deve continuar atualizando os pacotes restantes quando não for possível atualizar um pacote.</span><span class="sxs-lookup"><span data-stu-id="6a951-123">Specify that when a package cannot be upgraded, the [!INCLUDE[ssIS](../includes/ssis-md.md)] Package Upgrade Wizard continues to upgrade the remaining packages.</span></span>  
  
 <span data-ttu-id="6a951-124">**Conflitos de nome de pacote**</span><span class="sxs-lookup"><span data-stu-id="6a951-124">**Package name conflicts**</span></span>  
 <span data-ttu-id="6a951-125">Especifique como o assistente deve manipular pacotes que têm o mesmo nome.</span><span class="sxs-lookup"><span data-stu-id="6a951-125">Specify how the wizard should handle packages that have the same name.</span></span> <span data-ttu-id="6a951-126">Os valores dessa opção estão relacionados na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="6a951-126">This option has the values listed in the following table.</span></span>  
  
 <span data-ttu-id="6a951-127">**Substituir arquivos de pacote existentes**</span><span class="sxs-lookup"><span data-stu-id="6a951-127">**Overwrite existing package files**</span></span>  
 <span data-ttu-id="6a951-128">Substitui o pacote existente pelo pacote de atualização do mesmo nome.</span><span class="sxs-lookup"><span data-stu-id="6a951-128">Replaces the existing package with the upgrade package of the same name.</span></span>  
  
 <span data-ttu-id="6a951-129">**Adicionar sufixos numéricos para fazer upgrade de nomes de pacote**</span><span class="sxs-lookup"><span data-stu-id="6a951-129">**Add numeric suffixes to upgrade package names**</span></span>  
 <span data-ttu-id="6a951-130">Adiciona um sufixo numérico ao nome do pacote de atualização.</span><span class="sxs-lookup"><span data-stu-id="6a951-130">Adds a numeric suffix to the name of the upgrade package.</span></span>  
  
 <span data-ttu-id="6a951-131">**Não fazer upgrade de pacotes**</span><span class="sxs-lookup"><span data-stu-id="6a951-131">**Do not upgrade packages**</span></span>  
 <span data-ttu-id="6a951-132">Interrompe a atualização dos pacotes e exibe um erro quando o assistente é concluído.</span><span class="sxs-lookup"><span data-stu-id="6a951-132">Stops the packages from being upgraded and displays an error when you complete the wizard.</span></span>  
  
 <span data-ttu-id="6a951-133">Essas opções não estão disponíveis quando a opção **Salvar no local de origem** é selecionada na página **Selecionar Local de Destino** do assistente.</span><span class="sxs-lookup"><span data-stu-id="6a951-133">These options are not available when you select the **Save to source location** option on the **Select Destination Location** page of the wizard.</span></span>  
  
 <span data-ttu-id="6a951-134">**Ignorar configurações**</span><span class="sxs-lookup"><span data-stu-id="6a951-134">**Ignore Configurations**</span></span>  
 <span data-ttu-id="6a951-135">Não carrega configurações de pacotes durante a atualização de pacotes.</span><span class="sxs-lookup"><span data-stu-id="6a951-135">Does not load package configurations during the package upgrade.</span></span> <span data-ttu-id="6a951-136">A seleção dessa opção reduz o tempo necessário para atualizar o pacote.</span><span class="sxs-lookup"><span data-stu-id="6a951-136">Selecting this option reduces the time required to upgrade the package.</span></span>  
  
 <span data-ttu-id="6a951-137">**Fazer backup dos pacotes originais**</span><span class="sxs-lookup"><span data-stu-id="6a951-137">**Backup original packages**</span></span>  
 <span data-ttu-id="6a951-138">Configure o assistente para fazer backup dos pacotes originais em uma pasta **SSISBackupFolder** .</span><span class="sxs-lookup"><span data-stu-id="6a951-138">Have the wizard back up the original packages to an **SSISBackupFolder** folder.</span></span> <span data-ttu-id="6a951-139">O assistente cria a pasta **SSISBackupFolder** como uma subpasta da pasta que contém os pacotes originais e os pacotes atualizados.</span><span class="sxs-lookup"><span data-stu-id="6a951-139">The wizard creates the **SSISBackupFolder** folder as a subfolder to the folder that contains the original packages and the upgraded packages.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6a951-140">Essa opção só está disponível quando você especifica que os pacotes originais e os pacotes atualizados estão armazenados no sistema de arquivos e na mesma pasta.</span><span class="sxs-lookup"><span data-stu-id="6a951-140">This option is available only when you specify that the original packages and the upgraded packages are stored in the file system and in the same folder.</span></span>  
  
 <span data-ttu-id="6a951-141">Para obter mais informações, consulte [Atualizar pacotes do Integration Services usando o Assistente de Atualização de Pacote SSIS](install-windows/upgrade-integration-services-packages-using-the-ssis-package-upgrade-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="6a951-141">For more information, see [Upgrade Integration Services Packages Using the SSIS Package Upgrade Wizard](install-windows/upgrade-integration-services-packages-using-the-ssis-package-upgrade-wizard.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a951-142">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6a951-142">See Also</span></span>  
 [<span data-ttu-id="6a951-143">Atualizar pacotes do Integration Services</span><span class="sxs-lookup"><span data-stu-id="6a951-143">Upgrade Integration Services Packages</span></span>](install-windows/upgrade-integration-services-packages.md)  
  
  
