---
title: Importar do Analysis Services (SSAS tabular) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: b9a21b23-3a06-4ef8-bc06-9c79cdc54870
author: minewiskan
ms.author: owend
ms.openlocfilehash: 7d6c3d226e46cdb4101bc8db52830046d27b0706
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679029"
---
# <a name="import-from-analysis-services-ssas-tabular"></a><span data-ttu-id="4bbc7-102">Importar do Analysis Services (SSAS tabular)</span><span class="sxs-lookup"><span data-stu-id="4bbc7-102">Import from Analysis Services (SSAS Tabular)</span></span>
  <span data-ttu-id="4bbc7-103">Este tópico descreve como você pode criar um novo projeto de modelo de tabela importando os metadados de um modelo de tabela existente usando o modelo de projeto Importar do Servidor no [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4bbc7-103">This topic describes how to create a new tabular model project by importing the metadata from an existing tabular model by using the Import from Server project template in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
## <a name="create-a-new-model-by-importing-metadata-from-an-existing-model-in-analysis-services"></a><span data-ttu-id="4bbc7-104">Criar um novo modelo com a importação de metadados de um modelo existente no Analysis Services</span><span class="sxs-lookup"><span data-stu-id="4bbc7-104">Create a new model by importing metadata from an existing model in Analysis Services</span></span>  
 <span data-ttu-id="4bbc7-105">Use o modelo de projeto Importar de Servidor para criar um novo projeto de modelo tabular copiando os metadados de um modelo tabular existente em um servidor do Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="4bbc7-105">You can use the Import from Server project template to create a new tabular model project by copying the metadata from an existing tabular model on an Analysis Services server.</span></span> <span data-ttu-id="4bbc7-106">O novo projeto será criado com as mesmas conexões da fonte de dados, tabelas, relações, medidas, KPIs, funções, hierarquias, perspectivas e partições como o modelo do qual foi importado.</span><span class="sxs-lookup"><span data-stu-id="4bbc7-106">The new project will be created with the same data source connections, tables, relationships, measures, KPIs, roles, hierarchies, perspectives, and partitions as the model it was imported from.</span></span> <span data-ttu-id="4bbc7-107">Porém, os dados não são copiados do modelo existente para o novo workspace modelo.</span><span class="sxs-lookup"><span data-stu-id="4bbc7-107">The data, however, is not copied from the existing model to the new model workspace.</span></span> <span data-ttu-id="4bbc7-108">Quando o processo de importação tiver sido concluído, e o novo projeto de modelo criado, você deverá executar um Processar Tudo (Atualizar Tudo) para carregar os dados das fontes de dados no novo banco de dados do workspace do projeto do modelo.</span><span class="sxs-lookup"><span data-stu-id="4bbc7-108">Once the import process has completed, and the new model project created, you must run a Process All to load the data from the data sources into the new model project workspace database.</span></span>  
  
#### <a name="to-create-a-new-model-by-importing-metadata-from-an-existing-model"></a><span data-ttu-id="4bbc7-109">Para criar um novo modelo com a importação de metadados de um modelo existente</span><span class="sxs-lookup"><span data-stu-id="4bbc7-109">To create a new model by importing metadata from an existing model</span></span>  
  
1.  <span data-ttu-id="4bbc7-110">No [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], no menu **Arquivo** , clique em **Novo**e, em seguida, em **Projeto**.</span><span class="sxs-lookup"><span data-stu-id="4bbc7-110">In [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], on the **File** menu, click **New**, and then click **Project**.</span></span>  
  
2.  <span data-ttu-id="4bbc7-111">Na caixa de diálogo **Novo Projeto** , em **Modelos Instalados**, clique em **Business Intelligence**e clique em **Importar de Servidor**.</span><span class="sxs-lookup"><span data-stu-id="4bbc7-111">In the **New Project** dialog box, under **Installed Templates**, click **Business Intelligence**, and then click **Import from Server**.</span></span>  
  
3.  <span data-ttu-id="4bbc7-112">Em **Nome**, digite um nome para o projeto e especifique um local e um nome para a solução e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4bbc7-112">In **Name**, type a name for the project, then specify a location and solution name, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="4bbc7-113">Na caixa de diálogo **Importar do Analysis Services** , em **Nome do Servidor**, especifique o nome do servidor do Analysis Services que contém os metadados modelo que você deseja importar.</span><span class="sxs-lookup"><span data-stu-id="4bbc7-113">In the **Import from Analysis Services** dialog box, in **Server Name**, specify the name of the Analysis Services server that contains the model metadata you want to import.</span></span>  
  
5.  <span data-ttu-id="4bbc7-114">Em **Nome do Banco de Dados**, selecione o banco de dados modelo de tabela que contém os metadados de modelo que você deseja importar e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4bbc7-114">In **Database Name**, select the tabular model database that contains the model metadata you want to import, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4bbc7-115">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="4bbc7-115">See Also</span></span>  
 [<span data-ttu-id="4bbc7-116">Propriedades de projeto &#40;SSAS de Tabela&#41;</span><span class="sxs-lookup"><span data-stu-id="4bbc7-116">Project Properties &#40;SSAS Tabular&#41;</span></span>](properties-ssas-tabular.md)  
  
  
