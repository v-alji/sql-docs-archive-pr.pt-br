---
title: Implantar do SQL Server Data Tools (SSAS tabular) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.deploystatus.f1
ms.assetid: 67dde3fe-ba43-41f3-b56c-c656029ee93f
author: minewiskan
ms.author: owend
ms.openlocfilehash: 8bc8008e7c79e1652b54b21e6afb116301d1700b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574923"
---
# <a name="deploy-from-sql-server-data-tools-ssas-tabular"></a><span data-ttu-id="f31ee-102">Implantar das Ferramentas de Dados do SQL Server (SSAS tabular)</span><span class="sxs-lookup"><span data-stu-id="f31ee-102">Deploy From SQL Server Data Tools (SSAS Tabular)</span></span>
  <span data-ttu-id="f31ee-103">Use as tarefas neste tópico para implantar uma solução de modelo de tabela, usando o comando Implantar do [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f31ee-103">Use the tasks in this topic to deploy a tabular model solution by using the Deploy command in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="f31ee-104">Seções neste tópico:</span><span class="sxs-lookup"><span data-stu-id="f31ee-104">Sections in this topic:</span></span>  
  
-   [<span data-ttu-id="f31ee-105">Configurar opções de implantação e propriedades do servidor de implantação</span><span class="sxs-lookup"><span data-stu-id="f31ee-105">Configure Deployment Options and Deployment Server Properties</span></span>](#bkmk_deploy)  
  
-   [<span data-ttu-id="f31ee-106">Implantar uma solução de modelo tabular</span><span class="sxs-lookup"><span data-stu-id="f31ee-106">Deploy a Tabular Model Solution</span></span>](#bkmk_deploy_proc)  
  
-   [<span data-ttu-id="f31ee-107">Status de Implantação</span><span class="sxs-lookup"><span data-stu-id="f31ee-107">Deploy Status</span></span>](#bkmk_deploy_status)  
  
##  <a name="configure-deployment-options-and-deployment-server-properties"></a><a name="bkmk_deploy"></a><span data-ttu-id="f31ee-108">Configurar opções de implantação e propriedades do servidor de implantação</span><span class="sxs-lookup"><span data-stu-id="f31ee-108">Configure Deployment Options and Deployment Server Properties</span></span>  
 <span data-ttu-id="f31ee-109">Antes de implantar sua solução modelo tabular, primeiro especifique as propriedades Deployment Options e Deployment Server.</span><span class="sxs-lookup"><span data-stu-id="f31ee-109">Before you deploy your tabular model solution, you must first specify the Deployment Options and Deployment Server properties.</span></span> <span data-ttu-id="f31ee-110">Para obter mais informações sobre configurações e propriedades de implantação, consulte [Implantação de uma solução de modelo de tabela &#40;SSAS de Tabela&#41;](tabular-model-solution-deployment-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="f31ee-110">For more information about deployment properties and settings, see [Tabular Model Solution Deployment &#40;SSAS Tabular&#41;](tabular-model-solution-deployment-ssas-tabular.md).</span></span>  
  
#### <a name="to-configure-deployment-options-and-deployment-server-properties"></a><span data-ttu-id="f31ee-111">Para configurar as propriedades Opções de Implantação e Servidor de Implantação</span><span class="sxs-lookup"><span data-stu-id="f31ee-111">To configure Deployment Options and Deployment Server properties</span></span>  
  
1.  <span data-ttu-id="f31ee-112">No [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], no **Gerenciador de Soluções**, clique com o botão direito do mouse no nome do projeto e, em seguida, clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="f31ee-112">In [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], in **Solution Explorer**, right-click the project name, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="f31ee-113">Na caixa de diálogo \*\* \<project name> Propriedades\*\* , em **Opções de implantação**, especifique as configurações de propriedade se forem diferentes das configurações padrão.</span><span class="sxs-lookup"><span data-stu-id="f31ee-113">In the **\<project name> Properties** dialog, in **Deployment Options**, specify property settings if different from the default settings.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f31ee-114">Para modelos em modo armazenado em cache, o **Modo de Consulta** é sempre **Na Memória**.</span><span class="sxs-lookup"><span data-stu-id="f31ee-114">For models in cached mode, **Query Mode** is always **In-Memory**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f31ee-115">Você não pode especificar **Configurações de Representação** para modelos no modo DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="f31ee-115">You cannot specify **Impersonation Settings** for models in DirectQuery mode.</span></span>  
  
3.  <span data-ttu-id="f31ee-116">Em **Servidor de Implantação**, especifique as configurações de propriedade **Servidor** (nome), **Edição**, **Banco de Dados** (nome) e **Nome do Cubo** se estiverem diferentes das configurações padrão e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="f31ee-116">In **Deployment Server**, specify the **Server** (name), **Edition**, **Database** (name), and **Cube Name** property settings, if different from the default settings, and then click **OK**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f31ee-117">Você também pode especificar a configuração de propriedade Servidor de Implantação Padrão para que qualquer projeto que você crie seja automaticamente implantado no servidor especificado.</span><span class="sxs-lookup"><span data-stu-id="f31ee-117">You can also specify the Default Deployment Server property setting so any new projects you create will automatically be deployed to the specified server.</span></span> <span data-ttu-id="f31ee-118">Para obter mais informações, consulte [Configurar propriedades padrão de implantação e modelagem de dados &#40;SSAS de Tabela&#41;](properties-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="f31ee-118">For more information, see [Configure Default Data Modeling and Deployment Properties &#40;SSAS Tabular&#41;](properties-ssas-tabular.md).</span></span>  
  
##  <a name="deploy-a-tabular-model-solution"></a><a name="bkmk_deploy_proc"></a><span data-ttu-id="f31ee-119">Implantar uma solução de modelo tabular</span><span class="sxs-lookup"><span data-stu-id="f31ee-119">Deploy a Tabular Model Solution</span></span>  
  
#### <a name="to-deploy-a-tabular-model-solution"></a><span data-ttu-id="f31ee-120">Para implantar uma solução de modelo tabular</span><span class="sxs-lookup"><span data-stu-id="f31ee-120">To deploy a tabular model solution</span></span>  
  
-   <span data-ttu-id="f31ee-121">No [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)] , no menu **Compilar** , clique em \*\*implantar \<project name> \*\*.</span><span class="sxs-lookup"><span data-stu-id="f31ee-121">In [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], on the **Build** menu, click **Deploy \<project name>**.</span></span>  
  
     <span data-ttu-id="f31ee-122">A caixa de diálogo **Implantação** aparecerá e indicará o status da implantação de metadados e o processamento (a menos que a propriedade Opção de Processamento esteja configurada como Não Processar) de cada tabela incluída no modelo.</span><span class="sxs-lookup"><span data-stu-id="f31ee-122">The **Deploy** dialog box will appear and indicate the status of the metadata deployment and the processing (unless Processing Option property is set to Do Not Process) of each table included in the model.</span></span> <span data-ttu-id="f31ee-123">Depois que o processo de implantação for concluído, use o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] para conectar à instância do Analysis Services e verificar se o novo objeto de banco de dados modelo foi criado ou use um aplicativo de relatório cliente para conectar-se ao modelo implantado.</span><span class="sxs-lookup"><span data-stu-id="f31ee-123">After the deployment process is complete, use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to connect to the Analysis Services instance and verify the new model database object has been created or use a client reporting application to connect to the deployed model.</span></span>  
  
##  <a name="deploy-status"></a><a name="bkmk_deploy_status"></a><span data-ttu-id="f31ee-124">Status da implantação</span><span class="sxs-lookup"><span data-stu-id="f31ee-124">Deploy Status</span></span>  
 <span data-ttu-id="f31ee-125">A caixa de diálogo **Implantar** o habilita a monitorar o progresso de uma operação de Implantação.</span><span class="sxs-lookup"><span data-stu-id="f31ee-125">The **Deploy** dialog box enables you to monitor the progress of a Deploy operation.</span></span> <span data-ttu-id="f31ee-126">Uma operação de implantação também pode ser interrompida.</span><span class="sxs-lookup"><span data-stu-id="f31ee-126">A deploy operation can also be stopped.</span></span>  
  
 <span data-ttu-id="f31ee-127">**Status**</span><span class="sxs-lookup"><span data-stu-id="f31ee-127">**Status**</span></span>  
 <span data-ttu-id="f31ee-128">Indica se a operação de implantação foi bem-sucedida ou não.</span><span class="sxs-lookup"><span data-stu-id="f31ee-128">Indicates whether the Deploy operation was successful or not.</span></span>  
  
 <span data-ttu-id="f31ee-129">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="f31ee-129">**Details**</span></span>  
 <span data-ttu-id="f31ee-130">Lista os itens de metadados que foram implantados, o status de cada item de metadados, e fornece uma mensagem de quaisquer problemas.</span><span class="sxs-lookup"><span data-stu-id="f31ee-130">Lists the metadata items that were deployed, the status for each metadata item, and provides a message of any issues.</span></span>  
  
 <span data-ttu-id="f31ee-131">**Parar a implantação**</span><span class="sxs-lookup"><span data-stu-id="f31ee-131">**Stop Deploy**</span></span>  
 <span data-ttu-id="f31ee-132">Clique para interromper a operação de implantação.</span><span class="sxs-lookup"><span data-stu-id="f31ee-132">Click to halt the Deploy operation.</span></span> <span data-ttu-id="f31ee-133">Essa opção será útil se a operação de implantação estiver demorando muito ou se houver muitos erros.</span><span class="sxs-lookup"><span data-stu-id="f31ee-133">This option is useful if the Deploy operation is taking too long, or if there are too many errors.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f31ee-134">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f31ee-134">See Also</span></span>  
 <span data-ttu-id="f31ee-135">[Implantação de solução de modelo de tabela &#40;SSAS de tabela&#41;](tabular-model-solution-deployment-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="f31ee-135">[Tabular Model Solution Deployment &#40;SSAS Tabular&#41;](tabular-model-solution-deployment-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="f31ee-136">Configurar propriedades padrão de implantação e modelagem de dados &#40;SSAS de Tabela&#41;</span><span class="sxs-lookup"><span data-stu-id="f31ee-136">Configure Default Data Modeling and Deployment Properties &#40;SSAS Tabular&#41;</span></span>](properties-ssas-tabular.md)  
  
  
