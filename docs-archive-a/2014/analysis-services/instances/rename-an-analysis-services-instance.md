---
title: Renomear uma instância de Analysis Services | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- instances of Analysis Services, renaming
- renaming instances of Analysis Services
- names [Analysis Services], renaming instances
- names [Analysis Services]
ms.assetid: 87494741-4a2e-4fed-8061-418fd1e111c3
author: minewiskan
ms.author: owend
ms.openlocfilehash: 763986d82dda7424f2187daf401424fd256ddd64
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681241"
---
# <a name="rename-an-analysis-services-instance"></a><span data-ttu-id="f337a-102">Renomear uma instância do Analysis Services</span><span class="sxs-lookup"><span data-stu-id="f337a-102">Rename an Analysis Services Instance</span></span>
  <span data-ttu-id="f337a-103">Você pode renomear uma instância existente do usando [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] a caixa de diálogo **renomear instância** .</span><span class="sxs-lookup"><span data-stu-id="f337a-103">You can rename an existing instance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] by using the **Rename Instance** dialog box.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="f337a-104">Na renomeação da instância, a ferramenta Renomeação de Instância do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] é executada com privilégios elevados, atualizando o nome do serviço Windows, contas de segurança e entradas do Registro associados com essa instância.</span><span class="sxs-lookup"><span data-stu-id="f337a-104">While renaming the instance, the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Instance Rename tool runs under elevated privileges, updating the Windows service name, security accounts, and registry entries associated with that instance.</span></span> <span data-ttu-id="f337a-105">Para garantir a execução dessas ações, execute essa ferramenta como um administrador do sistema local.</span><span class="sxs-lookup"><span data-stu-id="f337a-105">To ensure that these actions are performed, be sure to run this tool as a local system administrator.</span></span>  
  
 <span data-ttu-id="f337a-106">A ferramenta Renomeação de Instância do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] não modifica a pasta de programa que foi criada para a instância original.</span><span class="sxs-lookup"><span data-stu-id="f337a-106">The [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Instance Rename tool does not modify the program folder that was created for the original instance.</span></span> <span data-ttu-id="f337a-107">Não modifique o nome da pasta de programa para coincidir com a instância que você está renomeando.</span><span class="sxs-lookup"><span data-stu-id="f337a-107">Do not modify the program folder name to match the instance you are renaming.</span></span> <span data-ttu-id="f337a-108">A alteração de um nome de pasta de programa pode impedir o reparo da instalação ou sua desinstalação.</span><span class="sxs-lookup"><span data-stu-id="f337a-108">Changing a program folder name can prevent Setup from repairing or uninstalling the installation.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f337a-109">A Ferramenta que renomeia a instância do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] não tem suporte para uso em um ambiente de cluster.</span><span class="sxs-lookup"><span data-stu-id="f337a-109">The [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Instance Rename tool is not supported for use in a cluster environment.</span></span>  
  
### <a name="to-rename-an-instance-of-analysis-services"></a><span data-ttu-id="f337a-110">Para renomear uma instância do Analysis Services</span><span class="sxs-lookup"><span data-stu-id="f337a-110">To rename an instance of Analysis Services</span></span>  
  
1.  <span data-ttu-id="f337a-111">Inicie a ferramenta de **renomeação da instância** , **asinstancerename.exe**, em C:\Program Files\Microsoft SQL Server\110\Tools\Binn\ManagementStudio.</span><span class="sxs-lookup"><span data-stu-id="f337a-111">Launch the **Instance Rename** tool, **asinstancerename.exe**, from C:\Program Files\Microsoft SQL Server\110\Tools\Binn\ManagementStudio.</span></span>  
  
2.  <span data-ttu-id="f337a-112">Na caixa de diálogo **Renomear Instância** , na lista **Instância a ser renomeada** , selecione a instância que você deseja renomear.</span><span class="sxs-lookup"><span data-stu-id="f337a-112">In the **Rename Instance** dialog box, in the **Instance to rename** list, select the instance that you want to rename.</span></span>  
  
3.  <span data-ttu-id="f337a-113">Na caixa **Novo nome da instância** , digite o novo nome da instância.</span><span class="sxs-lookup"><span data-stu-id="f337a-113">In the **New instance name** box, enter the new name for the instance.</span></span>  
  
4.  <span data-ttu-id="f337a-114">Verifique se o nome de usuário e senha estão corretos e, então, clique em **Renomear**.</span><span class="sxs-lookup"><span data-stu-id="f337a-114">Verify that the user name and password are correct, and then click **Rename**.</span></span>  
  
     <span data-ttu-id="f337a-115">A instância do Analysis Services será interrompida e reiniciará como parte da alteração de nome.</span><span class="sxs-lookup"><span data-stu-id="f337a-115">The Analysis Services instance will be stopped and restarted as part of the name change.</span></span>  
  
### <a name="post-rename-checklist"></a><span data-ttu-id="f337a-116">Lista de verificação pós-renomeação</span><span class="sxs-lookup"><span data-stu-id="f337a-116">Post-rename checklist</span></span>  
  
1.  <span data-ttu-id="f337a-117">Para retomar o acesso a bancos de dados em execução na instância renomeada, atualize as conexões de dados manualmente no Excel ou em outros aplicativos cliente.</span><span class="sxs-lookup"><span data-stu-id="f337a-117">To resume access to databases that are running on the renamed instance, you will need to manually update the data connections in Excel or other client applications.</span></span> <span data-ttu-id="f337a-118">Também verifique qualquer conexão predefinida, como fontes de dados compartilhadas do Reporting Services, arquivos ODC do Excel ou arquivos de conexão de Modelo Semântico BI que possam referenciar a instância recém-renomeada.</span><span class="sxs-lookup"><span data-stu-id="f337a-118">Also check any predefined connections, such as Reporting Services shared data sources, Excel ODC files, or BI Semantic Model connection files that might reference the instance you just renamed.</span></span> <span data-ttu-id="f337a-119">Para obter mais informações, consulte [Conectar ao Analysis Services](connect-to-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="f337a-119">For more information, see [Connect to Analysis Services](connect-to-analysis-services.md).</span></span>  
  
2.  <span data-ttu-id="f337a-120">Atualize scripts do PowerShell ou scripts AMO que você costuma usar para fazer backup, sincronizar ou processar bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="f337a-120">Update PowerShell scripts or AMO scripts that you routinely use to backup, synchronize, or process databases.</span></span>  
  
3.  <span data-ttu-id="f337a-121">Atualize propriedades de projeto para projetos do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] com os quais você trabalha no [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f337a-121">Update project properties for [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] projects that you work with in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)].</span></span> <span data-ttu-id="f337a-122">Para instâncias de servidor de modo de tabela, atualize a propriedade de Servidor de Workspace no arquivo model.bim, assim como a propriedade Servidor no projeto.</span><span class="sxs-lookup"><span data-stu-id="f337a-122">For tabular mode server instances, be sure to update the Workspace Server property on the model.bim file, as well as the Server property on the project.</span></span>  
  
4.  <span data-ttu-id="f337a-123">Dependendo de como você especificou a conta de serviço, poderá precisar atualizar logons de banco de dados ou permissões de arquivo que concedam ao serviço direitos de acesso a dados (por exemplo, se você usar a conta de serviço para processar dados ou acessar objetos vinculados em outro servidor).</span><span class="sxs-lookup"><span data-stu-id="f337a-123">Depending on how you specified the service account, you might need to update database logins or file permissions that grant data access rights to the service (for example, if you use the service account to process data or access linked objects on another server).</span></span>  
  
     <span data-ttu-id="f337a-124">A atualização de um logon de banco de dados ou de permissões de arquivo será necessária se você tiver usado uma conta virtual para provisionar o serviço.</span><span class="sxs-lookup"><span data-stu-id="f337a-124">Updating a database login or file permissions will be necessary if you used a virtual account to provision the service.</span></span> <span data-ttu-id="f337a-125">Contas virtuais se baseiam no nome de instância; portanto, se você renomear a instância, a conta virtual também será atualizada ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="f337a-125">Virtual accounts are based on the instance name, so if you rename the instance, the virtual account is also updated at the same time.</span></span> <span data-ttu-id="f337a-126">Isso significa que qualquer logon anterior ou permissões criadas para a instância anterior não serão mais válidas.</span><span class="sxs-lookup"><span data-stu-id="f337a-126">This means that any previous logins or permissions that you created for the previous instance are no longer valid.</span></span>  
  
     <span data-ttu-id="f337a-127">O exemplo a seguir ilustra esse cenário.</span><span class="sxs-lookup"><span data-stu-id="f337a-127">The following example provides an illustration.</span></span> <span data-ttu-id="f337a-128">Suponha que você instalou um servidor de modo de tabela como uma instância chamada "tabular" usando a conta virtual padrão, resultando na seguinte configuração:</span><span class="sxs-lookup"><span data-stu-id="f337a-128">Suppose you installed a tabular mode server as an instance named "Tabular" using the default virtual account, resulting in the following configuration:</span></span>  
  
    1.  <span data-ttu-id="f337a-129">Nome da instância = \<server> \TABULAR</span><span class="sxs-lookup"><span data-stu-id="f337a-129">Instance name = \<server>\TABULAR</span></span>  
  
    2.  <span data-ttu-id="f337a-130">Nome de serviço = MSOLAP$TABULAR</span><span class="sxs-lookup"><span data-stu-id="f337a-130">Service name = MSOLAP$TABULAR</span></span>  
  
    3.  <span data-ttu-id="f337a-131">Conta virtual = NT Service\ MSOLAP$TABULAR</span><span class="sxs-lookup"><span data-stu-id="f337a-131">Virtual account = NT Service\ MSOLAP$TABULAR</span></span>  
  
     <span data-ttu-id="f337a-132">Agora suponha que você renomeie a instância como "TAB2".</span><span class="sxs-lookup"><span data-stu-id="f337a-132">Now suppose you rename the instance to "TAB2".</span></span> <span data-ttu-id="f337a-133">Como resultado da alteração de nome, sua configuração teria a seguinte aparência agora:</span><span class="sxs-lookup"><span data-stu-id="f337a-133">As a result of the name change, your configuration would now look like the following:</span></span>  
  
    1.  <span data-ttu-id="f337a-134">Nome da instância = \<server> \TAB2</span><span class="sxs-lookup"><span data-stu-id="f337a-134">Instance name = \<server>\TAB2</span></span>  
  
    2.  <span data-ttu-id="f337a-135">Nome de serviço = MSOLAP$TAB2</span><span class="sxs-lookup"><span data-stu-id="f337a-135">Service name = MSOLAP$TAB2</span></span>  
  
    3.  <span data-ttu-id="f337a-136">Conta virtual = NT Service\ MSOLAP$TAB2</span><span class="sxs-lookup"><span data-stu-id="f337a-136">Virtual account = NT Service\ MSOLAP$TAB2</span></span>  
  
     <span data-ttu-id="f337a-137">Como você pode ver, as permissões de banco de dados e arquivo que foram concedidas anteriormente para "NT Service \ MSOLAP $ TABULAr" não são mais válidas.</span><span class="sxs-lookup"><span data-stu-id="f337a-137">As you can see, database and file permissions that were previously granted to "NT Service\ MSOLAP$TABULAR" are no longer valid.</span></span> <span data-ttu-id="f337a-138">Para garantir que as tarefas e operações executadas pelo serviço sejam executadas como antes, agora você precisará conceder novas permissões de banco de dados e arquivo ao "NT Service \ MSOLAP $ TAB2".</span><span class="sxs-lookup"><span data-stu-id="f337a-138">To ensure that tasks and operations performed by the service run as before, you would now need to grant new database and file permissions to "NT Service\ MSOLAP$TAB2".</span></span>  
  
  
