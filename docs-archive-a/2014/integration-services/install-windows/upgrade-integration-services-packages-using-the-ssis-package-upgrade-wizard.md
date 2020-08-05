---
title: Fazer upgrade de pacotes do Integration Services usando o Assistente para Upgrade de Pacote SSIS | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Integration Services packages, upgrading
- upgrading Integration Services packages
ms.assetid: 9359275a-48f5-4d1e-8ae7-e797759e3ccf
author: chugugrace
ms.author: chugu
ms.openlocfilehash: bcafd1c9750d8333639ca2d315512a2c2b8759c0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574191"
---
# <a name="upgrade-integration-services-packages-using-the-ssis-package-upgrade-wizard"></a><span data-ttu-id="6430c-102">Atualizar pacotes do Integration Services usando o Assistente de Atualização de Pacote SSIS</span><span class="sxs-lookup"><span data-stu-id="6430c-102">Upgrade Integration Services Packages Using the SSIS Package Upgrade Wizard</span></span>
  <span data-ttu-id="6430c-103">Você pode atualizar pacotes criados nas versões anteriores do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] para o formato do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] usado pelo [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6430c-103">You can upgrade packages that were created in earlier versions of [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] to the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] format that [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] uses.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="6430c-104">fornece o Assistente de Atualização de Pacote [!INCLUDE[ssIS](../../includes/ssis-md.md)] para ajudar neste processo.</span><span class="sxs-lookup"><span data-stu-id="6430c-104">provides the [!INCLUDE[ssIS](../../includes/ssis-md.md)] Package Upgrade Wizard to help in this process.</span></span> <span data-ttu-id="6430c-105">Como é possível configurar o assistente para fazer backup dos pacotes originais, você poderá continuar usando esses pacotes caso tenha dificuldades com a atualização.</span><span class="sxs-lookup"><span data-stu-id="6430c-105">Because you can configure the wizard to backup up your original packages, you can continue to use the original packages if you experience upgrade difficulties.</span></span>  
  
 <span data-ttu-id="6430c-106">O Assistente de Atualização de Pacote [!INCLUDE[ssIS](../../includes/ssis-md.md)] é instalado junto com o [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6430c-106">The [!INCLUDE[ssIS](../../includes/ssis-md.md)] Package Upgrade Wizard is installed when [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] is installed.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6430c-107">O Assistente de Atualização de Pacote [!INCLUDE[ssIS](../../includes/ssis-md.md)] está disponível nas edições Standard, Enterprise e Developer do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6430c-107">The [!INCLUDE[ssIS](../../includes/ssis-md.md)] Package Upgrade Wizard is available in the Standard, Enterprise, and Developer Editions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="6430c-108">Para obter mais informações sobre como atualizar pacotes [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] , veja [Atualizar pacotes do Integration Services](upgrade-integration-services-packages.md).</span><span class="sxs-lookup"><span data-stu-id="6430c-108">For more information about how to upgrade [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages, see [Upgrade Integration Services Packages](upgrade-integration-services-packages.md).</span></span>  
  
 <span data-ttu-id="6430c-109">O restante deste tópico descreve como executar o assistente e fazer backup dos pacotes originais.</span><span class="sxs-lookup"><span data-stu-id="6430c-109">The remainder of this topic describes how to run the wizard and back up the original packages.</span></span>  
  
## <a name="running-the-ssis-package-upgrade-wizard"></a><span data-ttu-id="6430c-110">Executando o Assistente de Atualização de Pacote SSIS</span><span class="sxs-lookup"><span data-stu-id="6430c-110">Running the SSIS Package Upgrade Wizard</span></span>  
 <span data-ttu-id="6430c-111">Você pode executar o Assistente de Atualização de Pacote [!INCLUDE[ssIS](../../includes/ssis-md.md)] do [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], do [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]ou do prompt de comando.</span><span class="sxs-lookup"><span data-stu-id="6430c-111">You can run the [!INCLUDE[ssIS](../../includes/ssis-md.md)] Package Upgrade Wizard from [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], from [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], or at the command prompt.</span></span>  
  
#### <a name="to-run-the-wizard-from-sql-server-data-tools"></a><span data-ttu-id="6430c-112">Para executar o assistente das Ferramentas de Dados do SQL Server</span><span class="sxs-lookup"><span data-stu-id="6430c-112">To run the wizard from SQL Server Data Tools</span></span>  
  
1.  <span data-ttu-id="6430c-113">No [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], crie ou abra um projeto do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6430c-113">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], create or open an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project.</span></span>  
  
2.  <span data-ttu-id="6430c-114">No Gerenciador de Soluções, clique com o botão direito do mouse no nó **Pacotes SSIS** e clique em **Atualizar Todos os Pacotes** para atualizar todos os pacotes neste nó.</span><span class="sxs-lookup"><span data-stu-id="6430c-114">In Solution Explorer, right-click the **SSIS Packages** node, and then click **Upgrade All Packages** to upgrade all the packages under this node.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="6430c-115">Quando você abre um projeto do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] que contém pacotes do [!INCLUDE[ssISversion2005](../../includes/ssisversion2005-md.md)] ou do [!INCLUDE[ssISversion10](../../includes/ssisversion10-md.md)], o [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] abre automaticamente o Assistente de Atualização de Pacote [!INCLUDE[ssIS](../../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6430c-115">When you open an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project that contains [!INCLUDE[ssISversion2005](../../includes/ssisversion2005-md.md)] or [!INCLUDE[ssISversion10](../../includes/ssisversion10-md.md)] packages, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] automatically opens the [!INCLUDE[ssIS](../../includes/ssis-md.md)] Package Upgrade Wizard.</span></span>  
  
#### <a name="to-run-the-wizard-from-sql-server-management-studio"></a><span data-ttu-id="6430c-116">Para executar o assistente do SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="6430c-116">To run the wizard from SQL Server Management Studio</span></span>  
  
-   <span data-ttu-id="6430c-117">No [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], conecte-se ao [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], expanda o nó **Pacotes Armazenados** e clique com o botão direito do mouse no nó **Sistema de Arquivos** ou **MSDB** e clique em **Atualizar Pacotes**.</span><span class="sxs-lookup"><span data-stu-id="6430c-117">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], expand the **Stored Packages** node, and right-click the **File System** or **MSDB** node, and then click **Upgrade Packages**.</span></span>  
  
#### <a name="to-run-the-wizard-at-the-command-prompt"></a><span data-ttu-id="6430c-118">Para executar o assistente no prompt de comando</span><span class="sxs-lookup"><span data-stu-id="6430c-118">To run the wizard at the command prompt</span></span>  
  
-   <span data-ttu-id="6430c-119">No prompt de comando, execute o arquivo SSISUpgrade.exe na pasta **C:\Program Files\Microsoft SQL Server\120\DTS\Binn**</span><span class="sxs-lookup"><span data-stu-id="6430c-119">At the command prompt, run the SSISUpgrade.exe file from the **C:\Program Files\Microsoft SQL Server\120\DTS\Binn** folder.</span></span>  
  
## <a name="backing-up-the-original-packages"></a><span data-ttu-id="6430c-120">Fazendo backup de pacotes originais</span><span class="sxs-lookup"><span data-stu-id="6430c-120">Backing Up the Original Packages</span></span>  
 <span data-ttu-id="6430c-121">Para fazer backup de pacotes originais, esses pacotes originais e os pacotes atualizados devem ser armazenados na mesma pasta no sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="6430c-121">To back up the original packages, both the original packages and the upgraded packages must be stored in the same folder in the file system.</span></span> <span data-ttu-id="6430c-122">Dependendo do modo como você executa o assistente, o local de armazenamento pode ser selecionado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="6430c-122">Depending on how you run the wizard, this storage location might be automatically selected.</span></span>  
  
-   <span data-ttu-id="6430c-123">Quando você executa o Assistente de Atualização de Pacote [!INCLUDE[ssIS](../../includes/ssis-md.md)] do [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], esse assistente armazena automaticamente os pacotes originais e atualizados na mesma pasta no sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="6430c-123">When you run the [!INCLUDE[ssIS](../../includes/ssis-md.md)] Package Upgrade Wizard from [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], the wizard automatically stores both the original packages and upgraded packages in the same folder in the file system.</span></span>  
  
-   <span data-ttu-id="6430c-124">Quando você executa o Assistente de Atualização de Pacote [!INCLUDE[ssIS](../../includes/ssis-md.md)] do [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou no prompt de comando, pode especificar locais de armazenamento diferentes para os pacotes originais e atualizados.</span><span class="sxs-lookup"><span data-stu-id="6430c-124">When you run the [!INCLUDE[ssIS](../../includes/ssis-md.md)] Package Upgrade Wizard from [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or at the command prompt, you can specify different storage locations for the original and upgraded packages.</span></span> <span data-ttu-id="6430c-125">Para fazer backup de pacotes originais, não se esqueça de especificar que os pacotes originais e os pacotes atualizados devem ser armazenados na mesma pasta no sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="6430c-125">To back up the original packages, make sure to specify that both the original and upgraded packages are stored in the same folder in the file system.</span></span> <span data-ttu-id="6430c-126">Se você especificar qualquer outra opção de armazenamento, o assistente não poderá fazer backup dos pacotes originais.</span><span class="sxs-lookup"><span data-stu-id="6430c-126">If you specify any other storage options, the wizard will not be able to back up the original packages.</span></span>  
  
 <span data-ttu-id="6430c-127">Quando o assistente faz backup dos pacotes originais, ele armazena uma cópia desses pacotes em uma pasta **SSISBackupFolder** .</span><span class="sxs-lookup"><span data-stu-id="6430c-127">When the wizard backs up the original packages, the wizard stores a copy of the original packages in an **SSISBackupFolder** folder.</span></span> <span data-ttu-id="6430c-128">O assistente cria essa pasta **SSISBackupFolder** como uma subpasta da pasta que contém os pacotes originais e os pacotes atualizados.</span><span class="sxs-lookup"><span data-stu-id="6430c-128">The wizard creates this **SSISBackupFolder** folder as a subfolder to the folder that contains the original packages and the upgraded packages.</span></span>  
  
#### <a name="to-back-up-the-original-packages-in-sql-server-management-studio-or-at-the-command-prompt"></a><span data-ttu-id="6430c-129">Para fazer backup dos pacotes originais no SQL Server Management Studio ou no prompt de comando</span><span class="sxs-lookup"><span data-stu-id="6430c-129">To back up the original packages in SQL Server Management Studio or at the command prompt</span></span>  
  
1.  <span data-ttu-id="6430c-130">Salve os pacotes originais em um local no sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="6430c-130">Save the original packages to a location on the file system.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="6430c-131">A opção de backup no assistente funciona apenas com pacotes que foram armazenados no sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="6430c-131">The backup option in the wizard only works with packages that have been stored to the file system.</span></span>  
  
2.  <span data-ttu-id="6430c-132">No [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou no prompt de comando, execute o Assistente de Atualização de Pacote do [!INCLUDE[ssIS](../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6430c-132">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or at the command prompt, run the [!INCLUDE[ssIS](../../includes/ssis-md.md)] Package Upgrade Wizard.</span></span>  
  
3.  <span data-ttu-id="6430c-133">Na página **Selecionar Local de Origem** do assistente, defina a propriedade **Origem do pacote** como **Sistema de Arquivos**.</span><span class="sxs-lookup"><span data-stu-id="6430c-133">On the **Select Source Location** page of the wizard, set the **Package source** property to **File System**.</span></span>  
  
4.  <span data-ttu-id="6430c-134">Na página **Selecionar Local de Destino** do assistente, selecione **Salvar no local de origem** para salvar os pacotes atualizados no mesmo local que os pacotes originais.</span><span class="sxs-lookup"><span data-stu-id="6430c-134">On the **Select Destination Location** page of the wizard, select **Save to source location** tosave the upgraded packages to the same location as the original packages.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="6430c-135">A opção de backup no assistente está disponível somente quando os pacotes atualizados são armazenados na mesma pasta que os pacotes originais.</span><span class="sxs-lookup"><span data-stu-id="6430c-135">The backup option in the wizard is available only when the upgraded packages are stored in the same folder as the original packages.</span></span>  
  
5.  <span data-ttu-id="6430c-136">Na página **Selecionar Opções de Gerenciamento de Pacote** do assistente, selecione a opção **Fazer backup dos pacotes originais** .</span><span class="sxs-lookup"><span data-stu-id="6430c-136">On the **Select Package Management Options** page of the wizard, select the **Backup original packages** option.</span></span>  
  
#### <a name="to-back-up-the-original-packages-in-sql-server-data-tools"></a><span data-ttu-id="6430c-137">Para fazer backup dos pacotes originais nas Ferramentas de Dados do SQL Server</span><span class="sxs-lookup"><span data-stu-id="6430c-137">To back up the original packages in SQL Server Data Tools</span></span>  
  
1.  <span data-ttu-id="6430c-138">Salve os pacotes originais em um local no sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="6430c-138">Save the original packages to a location on the file system.</span></span>  
  
2.  <span data-ttu-id="6430c-139">Na página **Selecionar Opções de Gerenciamento de Pacote** do assistente, selecione a opção **Fazer backup dos pacotes originais** .</span><span class="sxs-lookup"><span data-stu-id="6430c-139">On the **Select Package Management Options** page of the wizard, select the **Backup original packages** option.</span></span>  
  
    > [!WARNING]  
    >  <span data-ttu-id="6430c-140">A opção **fazer backup de pacotes originais** não é exibida quando você abre um [!INCLUDE[ssISversion2005](../../includes/ssisversion2005-md.md)] [!INCLUDE[ssISversion10](../../includes/ssisversion10-md.md)] projeto do ou no [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] , que inicia automaticamente o assistente.</span><span class="sxs-lookup"><span data-stu-id="6430c-140">The **Backup original packages** option is not displayed when you open a [!INCLUDE[ssISversion2005](../../includes/ssisversion2005-md.md)] or [!INCLUDE[ssISversion10](../../includes/ssisversion10-md.md)] project in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], which automatically launches the wizard.</span></span>  
  
3.  <span data-ttu-id="6430c-141">No [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], execute o Assistente de Atualização de Pacote [!INCLUDE[ssIS](../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6430c-141">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], run the [!INCLUDE[ssIS](../../includes/ssis-md.md)] Package Upgrade Wizard.</span></span>  
  
  
