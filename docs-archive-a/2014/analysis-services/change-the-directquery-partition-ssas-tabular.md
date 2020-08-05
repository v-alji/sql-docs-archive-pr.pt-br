---
title: Alterar a partição DirectQuery (SSAS tabular) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: f9df1e66-dd23-41b4-95eb-af110d10eda4
author: minewiskan
ms.author: owend
ms.openlocfilehash: 43d14785f72d9bfe6406e2b81d3f1b97e9b7cc2e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571711"
---
# <a name="change-the-directquery-partition-ssas-tabular"></a><span data-ttu-id="f4533-102">Alterar a partição DirectQuery (SSAS tabular)</span><span class="sxs-lookup"><span data-stu-id="f4533-102">Change the DirectQuery Partition (SSAS Tabular)</span></span>
  <span data-ttu-id="f4533-103">Como apenas uma partição em uma tabela pode ser designada como a partição DirectQuery, por padrão, o Analysis Services usa a primeira partição criada na tabela.</span><span class="sxs-lookup"><span data-stu-id="f4533-103">Because only one partition in a table can be designated as the DirectQuery partition, by default, Analysis Services uses the first partition that was created in the table.</span></span> <span data-ttu-id="f4533-104">Durante a criação do projeto de modelo, você pode alterar a partição DirectQuery usando a caixa de diálogo Gerenciador de Partições no [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f4533-104">During model project authoring, you can change the DirectQuery partition by using the Partition Manager dialog box in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="f4533-105">Para modelos implantados, você pode alterar a partição DirectQuery usando o [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f4533-105">For deployed models, you can change the DirectQuery partition by using [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
### <a name="change-the-directquery-partition-for-a-tabular-model-project"></a><span data-ttu-id="f4533-106">Alterar a partição DirectQuery para um projeto de modelo de tabela</span><span class="sxs-lookup"><span data-stu-id="f4533-106">Change the DirectQuery partition for a tabular model project</span></span>  
  
1.  <span data-ttu-id="f4533-107">No [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], no designer de modelos, clique na tabela (guia) que contém a tabela particionada.</span><span class="sxs-lookup"><span data-stu-id="f4533-107">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], in the model designer, click on the table (tab) that contains the partitioned table.</span></span>  
  
2.  <span data-ttu-id="f4533-108">Clique no menu **Tabela** e clique em **Partições**.</span><span class="sxs-lookup"><span data-stu-id="f4533-108">Click on the **Table** menu, and then click **Partitions**.</span></span>  
  
3.  <span data-ttu-id="f4533-109">No **Gerenciador de Partições**, a partição que é a partição atual Direct Query é indicada pelo prefixo **(DirectQuery)** no nome da partição.</span><span class="sxs-lookup"><span data-stu-id="f4533-109">In **Partition Manager**, the partition that is the current Direct Query partition in indicated by the prefix **(DirectQuery)** on the partition name.</span></span>  
  
     <span data-ttu-id="f4533-110">Selecione outra partição na lista **Partições** e clique em **Definir como DirectQuery**.</span><span class="sxs-lookup"><span data-stu-id="f4533-110">Select a different partition from the **Partitions** list, and then click **Set as DirectQuery**.</span></span> <span data-ttu-id="f4533-111">O botão **Definir como DirectQuery** não é habilitado quando a partição DirectQuery atual é selecionada e não fica visível quando o modelo não está habilitado no modo Direct Query.</span><span class="sxs-lookup"><span data-stu-id="f4533-111">The **Set as DirectQuery** button is not enabled when the current DirectQuery partition is selected, and is not visible if the model has not been enabled for Direct Query mode.</span></span>  
  
4.  <span data-ttu-id="f4533-112">Se necessário, altere as opções de processamento e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="f4533-112">If necessary, change the processing options, and then click **OK**.</span></span>  
  
### <a name="change-the-directquery-partition-for-a-deployed-tabular-model"></a><span data-ttu-id="f4533-113">Alterar a partição DirectQuery para um modelo de tabela implantado</span><span class="sxs-lookup"><span data-stu-id="f4533-113">Change the DirectQuery partition for a deployed tabular model</span></span>  
  
1.  <span data-ttu-id="f4533-114">No [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], abra o banco de dados modelo no Pesquisador de Objetos.</span><span class="sxs-lookup"><span data-stu-id="f4533-114">In [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], open the model database in Object Explorer.</span></span>  
  
2.  <span data-ttu-id="f4533-115">Expanda o nó **Tabelas** , clique com o botão direito do mouse na tabela particionada e selecione **Partições**.</span><span class="sxs-lookup"><span data-stu-id="f4533-115">Expand the **Tables** node, then right-click the partitioned table, and then select **Partitions**.</span></span>  
  
     <span data-ttu-id="f4533-116">A partição que é designada para uso com o modo DirectQuery tem o prefixo (DirectQuery) no nome da partição.</span><span class="sxs-lookup"><span data-stu-id="f4533-116">The partition that is designated for use with DirectQuery mode has the prefix (DirectQuery) on the partition name.</span></span>  
  
3.  <span data-ttu-id="f4533-117">Para alterar para uma partição diferente, clique no ícone da barra de ferramentas **Direct Query** para abrir a caixa de diálogo **Definir Partição DirectQuery** .</span><span class="sxs-lookup"><span data-stu-id="f4533-117">To change to a different partition, click the **Direct Query** toolbar icon to open the **Set DirectQuery Partition** dialog box.</span></span> <span data-ttu-id="f4533-118">O ícone da barra de ferramentas DirectQuery não está disponível em modelos não habilitados para Direct Query.</span><span class="sxs-lookup"><span data-stu-id="f4533-118">The DirectQuery toolbar icon is not available on models that have not been enabled for Direct Query.</span></span>  
  
4.  <span data-ttu-id="f4533-119">Escolha outra partição na lista suspensa **Nome da Partição** e altere opções de processamento na partição, caso seja necessário.</span><span class="sxs-lookup"><span data-stu-id="f4533-119">Choose a different partition from the **Partition Name** dropdown list, and then change processing options on the partition if necessary.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4533-120">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f4533-120">See Also</span></span>  
 [<span data-ttu-id="f4533-121">Partições &#40;SSAS de Tabela&#41;</span><span class="sxs-lookup"><span data-stu-id="f4533-121">Partitions &#40;SSAS Tabular&#41;</span></span>](tabular-models/partitions-ssas-tabular.md)  
  
  
