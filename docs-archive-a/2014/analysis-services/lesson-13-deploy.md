---
title: 'Lição 14: implantar | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 24863a8a-9017-415a-a97b-fbac76ed0675
author: minewiskan
ms.author: owend
ms.openlocfilehash: c1a55960a0c33a386d978f3c15e489ed7bd861ce
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568838"
---
# <a name="lesson-14-deploy"></a><span data-ttu-id="30355-102">Lição 14: Implantar</span><span class="sxs-lookup"><span data-stu-id="30355-102">Lesson 14: Deploy</span></span>
  <span data-ttu-id="30355-103">Nesta lição, você configurará propriedades de implantação; especificando uma instância de servidor de implantação do Analysis Services executada no modo de Tabela e um nome para o modelo que você está implantando.</span><span class="sxs-lookup"><span data-stu-id="30355-103">In this lesson, you will configure deployment properties; specifying a deployment server instance of Analysis Services running in Tabular mode, and a name for the model you deploy.</span></span> <span data-ttu-id="30355-104">Você implantará o modelo nessa instância.</span><span class="sxs-lookup"><span data-stu-id="30355-104">You will then deploy the model to that instance.</span></span> <span data-ttu-id="30355-105">Depois de implantado, os usuários podem se conectar ao modelo usando um aplicativo cliente de relatório.</span><span class="sxs-lookup"><span data-stu-id="30355-105">After it is deployed, users can connect to the model by using a reporting client application.</span></span> <span data-ttu-id="30355-106">Para saber mais, consulte [Implantação de uma solução de modelo de tabela &#40;SSAS Tabular&#41;](tabular-models/tabular-model-solution-deployment-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="30355-106">To learn more, see [Tabular Model Solution Deployment &#40;SSAS Tabular&#41;](tabular-models/tabular-model-solution-deployment-ssas-tabular.md).</span></span>  
  
 <span data-ttu-id="30355-107">Tempo estimado para concluir esta lição: **5 minutos**</span><span class="sxs-lookup"><span data-stu-id="30355-107">Estimated time to complete this lesson: **5 minutes**</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="30355-108">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="30355-108">Prerequisites</span></span>  
 <span data-ttu-id="30355-109">Este tópico faz parte de um tutorial de modelagem tabular, que deve ser concluído na devida ordem.</span><span class="sxs-lookup"><span data-stu-id="30355-109">This topic is part of a tabular modeling tutorial, which should be completed in order.</span></span> <span data-ttu-id="30355-110">Antes de executar as tarefas desta lição, você deverá ter concluído a lição anterior: [Lição 13: Analisar no Excel](lesson-12-analyze-in-excel.md).</span><span class="sxs-lookup"><span data-stu-id="30355-110">Before performing the tasks in this lesson, you should have completed the previous lesson: [Lesson 13: Analyze in Excel](lesson-12-analyze-in-excel.md).</span></span>  
  
## <a name="deploy-the-model"></a><span data-ttu-id="30355-111">Implantar o modelo</span><span class="sxs-lookup"><span data-stu-id="30355-111">Deploy the Model</span></span>  
  
#### <a name="to-configure-deployment-properties"></a><span data-ttu-id="30355-112">Para configurar propriedades de implantação</span><span class="sxs-lookup"><span data-stu-id="30355-112">To configure deployment properties</span></span>  
  
1.  <span data-ttu-id="30355-113">No [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], no **Gerenciador de Soluções**, clique com o botão direito do mouse no projeto **Modelo de Tabela de Vendas pela Internet do Adventure Works** e, no menu de contexto, clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="30355-113">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], in **Solution Explorer**, right-click on the **Adventure Works Internet Sales Tabular Model** project, and then in the context menu, click **Properties**.</span></span>  
  
2.  <span data-ttu-id="30355-114">Na caixa de diálogo **Páginas de Propriedades de Modelo de Tabela de Vendas pela Internet do AW** , em **Servidor de Implantação**, na propriedade **Server** , digite o nome de uma instância do Analysis Services executada no modo de Tabela.</span><span class="sxs-lookup"><span data-stu-id="30355-114">In the **AW Internet Sales Tabular Model Property Pages** dialog box, under **Deployment Server**, in the **Server** property, type the name of an Analysis Services instance running in Tabular mode.</span></span> <span data-ttu-id="30355-115">Esta será a instância na qual seu modelo será implantado.</span><span class="sxs-lookup"><span data-stu-id="30355-115">This will be the instance your model will be deployed to.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="30355-116">Você deve ter permissões de Administrador em uma instância do Analysis Services para implantá-la.</span><span class="sxs-lookup"><span data-stu-id="30355-116">You must have Administrator permissions on a remote Analysis Services instance in-order to deploy to it.</span></span>  
  
3.  <span data-ttu-id="30355-117">Verifique se a propriedade **modo de consulta** está definida como **na memória**.</span><span class="sxs-lookup"><span data-stu-id="30355-117">Verify the **Query Mode** property is set to **In-Memory**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="30355-118">Não há suporte para o modelo criado por meio deste tutorial no modo DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="30355-118">The model created by using this tutorial is not supported in DirectQuery mode.</span></span>  
  
4.  <span data-ttu-id="30355-119">Na propriedade de **banco de dados** , digite `Adventure Works Internet Sales Model` .</span><span class="sxs-lookup"><span data-stu-id="30355-119">In the **Database** property, type `Adventure Works Internet Sales Model`.</span></span>  
  
5.  <span data-ttu-id="30355-120">Na propriedade nome do **cubo** , digite `Adventure Works Internet Sales Model` .</span><span class="sxs-lookup"><span data-stu-id="30355-120">In the **Cube** Name property, type `Adventure Works Internet Sales Model`.</span></span>  
  
6.  <span data-ttu-id="30355-121">Verifique suas seleções e então clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="30355-121">Verify your selections and then click **OK**.</span></span>  
  
#### <a name="to-deploy-the-adventure-works-internet-sales-tabular-model"></a><span data-ttu-id="30355-122">Para implantar o modelo de tabela de vendas pela Internet da Adventure Works.</span><span class="sxs-lookup"><span data-stu-id="30355-122">To deploy the Adventure Works Internet Sales tabular model</span></span>  
  
1.  <span data-ttu-id="30355-123">No [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], clique no menu **Criar** e em **Implantar Modelo de Tabela de Vendas pela Internet do AW**.</span><span class="sxs-lookup"><span data-stu-id="30355-123">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], click the **Build** menu, and then click **Deploy AW Internet Sales Tabular Model**.</span></span>  
  
     <span data-ttu-id="30355-124">A caixa de diálogo Implantar aparecerá com o status de implantação dos metadados e cada tabela incluída no modelo.</span><span class="sxs-lookup"><span data-stu-id="30355-124">The Deploy dialog box appears and displays the deployment status of the metadata as well as each table included in the model.</span></span>  
  
## <a name="conclusion"></a><span data-ttu-id="30355-125">Conclusão</span><span class="sxs-lookup"><span data-stu-id="30355-125">Conclusion</span></span>  
 <span data-ttu-id="30355-126">Parabéns!</span><span class="sxs-lookup"><span data-stu-id="30355-126">Congratulations!</span></span> <span data-ttu-id="30355-127">Você é terminou de criar e implantar seu primeiro modelo de tabela do Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="30355-127">You are finished authoring and deploying your first Analysis Services tabular model.</span></span> <span data-ttu-id="30355-128">Este tutorial ajudou você a concluir as tarefas mais comuns da criação de um modelo de tabela.</span><span class="sxs-lookup"><span data-stu-id="30355-128">This tutorial has helped guide you through completing the most common tasks in creating a tabular model.</span></span> <span data-ttu-id="30355-129">Agora que o Modelo de Vendas pela Internet do Adventure Works está implantado, você pode usar o SQL Server Management Studio para gerenciar o modelo; crie scripts de processo e um plano de backup.</span><span class="sxs-lookup"><span data-stu-id="30355-129">Now that your Adventure Works Internet Sales Model is deployed, you can use SQL Server Management Studio to manage the model; create process scripts and a backup plan.</span></span> <span data-ttu-id="30355-130">Os usuários podem se conectar ao modelo usando um aplicativo cliente de relatório como o Microsoft Excel ou o [!INCLUDE[ssCrescent](../includes/sscrescent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="30355-130">Users can connect to the model using a reporting client application such as Microsoft Excel or [!INCLUDE[ssCrescent](../includes/sscrescent-md.md)].</span></span>  
  
## <a name="additional-resources"></a><span data-ttu-id="30355-131">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="30355-131">Additional Resources</span></span>  
 <span data-ttu-id="30355-132">Para saber mais sobre as propriedades do modelo de tabela que dão suporte aos relatórios do [!INCLUDE[ssCrescent](../includes/sscrescent-md.md)], consulte [Propriedades de relatório do Power View &#40;SSAS Tabular&#41;](tabular-models/properties-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="30355-132">To learn more about tabular model properties that support [!INCLUDE[ssCrescent](../includes/sscrescent-md.md)] reports, see [Power View Reporting Properties &#40;SSAS Tabular&#41;](tabular-models/properties-ssas-tabular.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30355-133">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="30355-133">See Also</span></span>  
 <span data-ttu-id="30355-134">[Modo DirectQuery &#40;SSAS de tabela&#41;](tabular-models/directquery-mode-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="30355-134">[DirectQuery Mode &#40;SSAS Tabular&#41;](tabular-models/directquery-mode-ssas-tabular.md) </span></span>  
 <span data-ttu-id="30355-135">[Configurar propriedades de implantação e modelagem de dados padrão &#40;SSAS tabular&#41;](tabular-models/configure-default-data-modeling-and-deployment-properties-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="30355-135">[Configure Default Data Modeling and Deployment Properties &#40;SSAS Tabular&#41;](tabular-models/configure-default-data-modeling-and-deployment-properties-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="30355-136">Bancos de dados de modelo de tabela &#40;SSAS de Tabela&#41;</span><span class="sxs-lookup"><span data-stu-id="30355-136">Tabular Model Databases &#40;SSAS Tabular&#41;</span></span>](tabular-models/tabular-model-databases-ssas-tabular.md)  
  
  
