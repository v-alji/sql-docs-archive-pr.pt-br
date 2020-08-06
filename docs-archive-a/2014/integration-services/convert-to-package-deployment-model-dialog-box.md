---
title: Caixa de diálogo Converter em modelo de implantação de pacote | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.bids.converttolegacydeployment.f1
ms.assetid: 9e60a34a-10f7-48d1-966f-b3ff236ab4b7
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b52932ad26f8cebd2e67b0025f4b881241119f6e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574843"
---
# <a name="convert-to-package-deployment-model-dialog-box"></a><span data-ttu-id="9e036-102">Caixa de diálogo Converter em Modelo de Implantação de Pacote</span><span class="sxs-lookup"><span data-stu-id="9e036-102">Convert to Package Deployment Model Dialog Box</span></span>
  <span data-ttu-id="9e036-103">A caixa de diálogo **Converter em Modelo de Implantação de Pacote** permite converter um pacote para o modelo de implantação de pacote depois de verificar se o projeto e cada pacote do projeto são compatíveis com esse modelo.</span><span class="sxs-lookup"><span data-stu-id="9e036-103">The **Convert to Package Deployment Model** command allows you to convert a package to the package deployment model after checking the project and each package in the project for compatibility with that model.</span></span> <span data-ttu-id="9e036-104">Se um pacote usar recursos exclusivos para o modelo de implantação de projeto, como parâmetros, o pacote não poderá ser convertido.</span><span class="sxs-lookup"><span data-stu-id="9e036-104">If a package uses features unique to the project deployment model, such as parameters, then the package cannot be converted.</span></span>  
  
## <a name="task-list"></a><span data-ttu-id="9e036-105">Lista de Tarefas</span><span class="sxs-lookup"><span data-stu-id="9e036-105">Task List</span></span>  
 <span data-ttu-id="9e036-106">Converter um pacote para o modelo de implantação de pacote exige duas etapas.</span><span class="sxs-lookup"><span data-stu-id="9e036-106">Converting a package to the package deployment model requires two steps.</span></span>  
  
1.  <span data-ttu-id="9e036-107">Quando você seleciona o comando **Converter em Modelo de Implantação de Pacote** no menu **Project** , o projeto e cada pacote do projeto terão a compatibilidade verificada com esse modelo.</span><span class="sxs-lookup"><span data-stu-id="9e036-107">When you select the **Convert to Package Deployment Model** command from the **Project** menu, the project and each package are checked for compatibility with this model.</span></span> <span data-ttu-id="9e036-108">Os resultados são exibidos na tabela **Resultados** .</span><span class="sxs-lookup"><span data-stu-id="9e036-108">The results are displayed in the **Results** table.</span></span>  
  
     <span data-ttu-id="9e036-109">Se o projeto ou pacote falhar no teste de compatibilidade, clique em **Falha** na coluna **Resultado** para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="9e036-109">If the project or a package fails the compatibility test, click **Failed** in the **Result** column for more information.</span></span> <span data-ttu-id="9e036-110">Clique em **Salvar Relatório** para salvar uma cópia destas informações em um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="9e036-110">Click **Save Report** to save a copy of this information to a text file.</span></span>  
  
2.  <span data-ttu-id="9e036-111">Se o projeto e todos os pacotes passarem no teste de compatibilidade, clique em **OK** para converter o pacote.</span><span class="sxs-lookup"><span data-stu-id="9e036-111">If the project and all packages pass the compatibility test, then click **OK** to convert the package.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9e036-112">Para converter um projeto no modelo de implantação de projeto, use o **Assistente de Conversão de Projeto do Integration Services**.</span><span class="sxs-lookup"><span data-stu-id="9e036-112">To convert a project to the project deployment model, use the **Integration Services Project Conversion Wizard**.</span></span> <span data-ttu-id="9e036-113">Para obter mais informações, consulte [Integration Services Project Conversion Wizard](../../2014/integration-services/integration-services-project-conversion-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="9e036-113">For more information, see [Integration Services Project Conversion Wizard](../../2014/integration-services/integration-services-project-conversion-wizard.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e036-114">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9e036-114">See Also</span></span>  
 <span data-ttu-id="9e036-115">[Implantação de projetos e pacotes](packages/deploy-integration-services-ssis-projects-and-packages.md) </span><span class="sxs-lookup"><span data-stu-id="9e036-115">[Deployment of Projects and Packages](packages/deploy-integration-services-ssis-projects-and-packages.md) </span></span>  
 <span data-ttu-id="9e036-116">[Implantação de pacote &#40;SSIS&#41;](packages/legacy-package-deployment-ssis.md) </span><span class="sxs-lookup"><span data-stu-id="9e036-116">[Package Deployment &#40;SSIS&#41;](packages/legacy-package-deployment-ssis.md) </span></span>  
 [<span data-ttu-id="9e036-117">Assistente de Conversão de Projeto do Integration Services</span><span class="sxs-lookup"><span data-stu-id="9e036-117">Integration Services Project Conversion Wizard</span></span>](../../2014/integration-services/integration-services-project-conversion-wizard.md)  
  
  
