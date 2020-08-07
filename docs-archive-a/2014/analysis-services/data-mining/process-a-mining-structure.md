---
title: Processar uma estrutura de mineração | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining structures [Analysis Services], processing
ms.assetid: 4162f33e-c23f-4293-8905-271781e45fa4
author: minewiskan
ms.author: owend
ms.openlocfilehash: 76d25a927ae61ee5ffadf4ca21073a1c04cdb542
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681923"
---
# <a name="process-a-mining-structure"></a><span data-ttu-id="a05cb-102">Processar uma estrutura de mineração</span><span class="sxs-lookup"><span data-stu-id="a05cb-102">Process a Mining Structure</span></span>
  <span data-ttu-id="a05cb-103">Para poder procurar ou trabalhar com modelos de mineração que são associados a uma estrutura de mineração, você deve implantar o projeto [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] e processar a estrutura de mineração e os modelos de mineração.</span><span class="sxs-lookup"><span data-stu-id="a05cb-103">Before you can browse or work with the mining models that are associated with a mining structure, you have to deploy the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project and process the mining structure and mining models.</span></span> <span data-ttu-id="a05cb-104">Além disso, se fizer uma alteração na estrutura de mineração ou nos modelos de mineração, você será solicitado a reimplantá-los e processá-los.</span><span class="sxs-lookup"><span data-stu-id="a05cb-104">Also, if you make a change to the mining structure or mining models, you will be prompted to redeploy and process them.</span></span> <span data-ttu-id="a05cb-105">Processar a estrutura na guia de **Estrutura de Mineração** do Designer de Mineração de Dados no [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] , processa todos os modelos associados.</span><span class="sxs-lookup"><span data-stu-id="a05cb-105">Processing the structure in the **Mining Structure** tab of Data Mining Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] processes all the associated models.</span></span>  
  
 <span data-ttu-id="a05cb-106">É possível processar uma estrutura de mineração usando essas ferramentas:</span><span class="sxs-lookup"><span data-stu-id="a05cb-106">You can process a mining structure by using these tools:</span></span>  
  
-   [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]  
  
-   [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]  
  
-   <span data-ttu-id="a05cb-107">XMLA: comando Process</span><span class="sxs-lookup"><span data-stu-id="a05cb-107">XMLA: Process command</span></span>  
  
 <span data-ttu-id="a05cb-108">Para obter informações sobre como processar modelos individuais, consulte [Processar um modelo de mineração](process-a-mining-model.md).</span><span class="sxs-lookup"><span data-stu-id="a05cb-108">For information about how to process individual models, see [Process a Mining Model](process-a-mining-model.md).</span></span>  
  
### <a name="to-process-a-mining-structure-and-all-associated-mining-models-using-sql-server-data-tools"></a><span data-ttu-id="a05cb-109">Para processar uma estrutura de mineração e todos os modelos de mineração associados usando as Ferramentas de Dados do SQL Server</span><span class="sxs-lookup"><span data-stu-id="a05cb-109">To process a mining structure and all associated mining models using SQL Server Data Tools</span></span>  
  
1.  <span data-ttu-id="a05cb-110">Selecione **Estrutura de Mineração do Processo e Todos os Modelos** no item de menu **Modelo de Mineração** no [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a05cb-110">Select **Process Mining Structure and All Models** from the **Mining Model** menu item in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)].</span></span>  
  
     <span data-ttu-id="a05cb-111">Caso faça alterações na estrutura, você receberá uma solicitação para implantar a estrutura novamente antes de processar os modelos.</span><span class="sxs-lookup"><span data-stu-id="a05cb-111">If you made changes to the structure, you will be prompted to redeploy the structure before processing the models.</span></span> <span data-ttu-id="a05cb-112">Clique em **Sim**.</span><span class="sxs-lookup"><span data-stu-id="a05cb-112">Click **Yes**.</span></span>  
  
2.  <span data-ttu-id="a05cb-113">Clique em **executar** na caixa de diálogo \*\*processando estrutura de mineração- \<structure> \*\* .</span><span class="sxs-lookup"><span data-stu-id="a05cb-113">Click **Run** in the **Processing Mining Structure - \<structure>** dialog box.</span></span>  
  
     <span data-ttu-id="a05cb-114">A caixa de diálogo **Andamento do Processo** é aberta para exibir os detalhes sobre o processamento do modelo.</span><span class="sxs-lookup"><span data-stu-id="a05cb-114">The **Process Progress** dialog box opens to display the details of model processing.</span></span>  
  
3.  <span data-ttu-id="a05cb-115">Clique em **Fechar** na caixa de diálogo **Andamento do Processo** após os modelos completarem seu processamento.</span><span class="sxs-lookup"><span data-stu-id="a05cb-115">Click **Close** in the **Process Progress** dialog box after the models have completed processing.</span></span>  
  
4.  <span data-ttu-id="a05cb-116">Clique em **fechar** na caixa de diálogo \*\*processando estrutura de mineração- \<structure> \*\* .</span><span class="sxs-lookup"><span data-stu-id="a05cb-116">Click **Close** in the **Processing Mining Structure - \<structure>** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a05cb-117">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a05cb-117">See Also</span></span>  
 [<span data-ttu-id="a05cb-118">Tarefas e instruções da estrutura de mineração</span><span class="sxs-lookup"><span data-stu-id="a05cb-118">Mining Structure Tasks and How-tos</span></span>](mining-structure-tasks-and-how-tos.md)  
  
  
