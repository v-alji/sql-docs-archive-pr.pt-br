---
title: Reordenar colunas (Suplemento MDS para Excel) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: ac00462e-c0f7-4b8d-86f2-d9eda2598a15
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: f0c47a631ffe699936a8d45bcc4e47e0b6f0a985
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680011"
---
# <a name="reorder-columns-mds-add-in-for-excel"></a><span data-ttu-id="e89da-102">Reordenar colunas (suplemento MDS para Excel)</span><span class="sxs-lookup"><span data-stu-id="e89da-102">Reorder Columns (MDS Add-in for Excel)</span></span>
  <span data-ttu-id="e89da-103">No [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], você pode reorganizar colunas filtrando a lista antes de carregar.</span><span class="sxs-lookup"><span data-stu-id="e89da-103">In the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], you can reorder columns by filtering the list before loading.</span></span>  
  
 <span data-ttu-id="e89da-104">Quando você reorganizar atributos na caixa de diálogo **Filtro** , os dados serão carregados no Excel com a nova ordem.</span><span class="sxs-lookup"><span data-stu-id="e89da-104">When you reorder attributes in the **Filter** dialog box, the data is loaded into Excel with the new order.</span></span> <span data-ttu-id="e89da-105">Porém, da próxima vez que você filtrar os dados de atributo, a ordem reverterá para a ordem no design original.</span><span class="sxs-lookup"><span data-stu-id="e89da-105">However, the next time that you filter the attribute data, the order will revert to the order in the original design.</span></span> <span data-ttu-id="e89da-106">Para alterar a ordem permanentemente, um administrador deverá alterar a ordem na área de **Administração do sistema** de Master Data Manager.</span><span class="sxs-lookup"><span data-stu-id="e89da-106">To change the order permanently, an administrator should change the order in the **System Administration** area of Master Data Manager.</span></span> <span data-ttu-id="e89da-107">Para obter mais informações, consulte [Change the Order of Attributes](../change-the-order-of-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="e89da-107">For more information, see [Change the Order of Attributes](../change-the-order-of-attributes.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="e89da-108">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="e89da-108">Prerequisites</span></span>  
 <span data-ttu-id="e89da-109">Para executar esse procedimento:</span><span class="sxs-lookup"><span data-stu-id="e89da-109">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="e89da-110">Você deve ter permissão para acessar a área funcional do **Gerenciador** .</span><span class="sxs-lookup"><span data-stu-id="e89da-110">You must have permission to access the **Explorer** functional area.</span></span>  
  
### <a name="to-reorder-mds-managed-columns"></a><span data-ttu-id="e89da-111">Para reorganizar colunas gerenciadas por MDS</span><span class="sxs-lookup"><span data-stu-id="e89da-111">To reorder MDS-managed columns</span></span>  
  
1.  <span data-ttu-id="e89da-112">Abra o Excel e, na guia **Dados Mestre** , conecte-se a um repositório do MDS.</span><span class="sxs-lookup"><span data-stu-id="e89da-112">Open Excel and on the **Master Data** tab, connect to an MDS repository.</span></span> <span data-ttu-id="e89da-113">Para obter mais informações, consulte [Conectar-se a um repositório do MDS &#40;Suplemento MDS para Excel&#41;](connect-to-an-mds-repository-mds-add-in-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="e89da-113">For more information, see [Connect to an MDS Repository &#40;MDS Add-in for Excel&#41;](connect-to-an-mds-repository-mds-add-in-for-excel.md).</span></span>  
  
2.  <span data-ttu-id="e89da-114">No painel do **Master Data Explorer** , selecione um modelo e uma versão.</span><span class="sxs-lookup"><span data-stu-id="e89da-114">In the **Master Data Explorer** pane, select a model and version.</span></span> <span data-ttu-id="e89da-115">A lista de entidades será preenchida.</span><span class="sxs-lookup"><span data-stu-id="e89da-115">The list of entities is populated.</span></span>  
  
    -   <span data-ttu-id="e89da-116">Se o painel do **Master Data Explorer** não estiver visível, no grupo **Conectar e Carregar** , clique em **Mostrar Explorer**.</span><span class="sxs-lookup"><span data-stu-id="e89da-116">If the **Master Data Explorer** pane is not visible, in the **Connect and Load** group, click **Show Explorer**.</span></span>  
  
    -   <span data-ttu-id="e89da-117">Se o painel **Master Data Explorer** estiver desabilitado, isso significará que a planilha existente já contém dados gerenciados pelo MDS.</span><span class="sxs-lookup"><span data-stu-id="e89da-117">If the **Master Data Explorer** pane is disabled, it is because the existing sheet already contains MDS-managed data.</span></span> <span data-ttu-id="e89da-118">Para habilitar o painel, abra uma nova planilha.</span><span class="sxs-lookup"><span data-stu-id="e89da-118">To enable the pane, open a new worksheet.</span></span>  
  
3.  <span data-ttu-id="e89da-119">No painel do **Master Data Explorer** , clique em uma entidade.</span><span class="sxs-lookup"><span data-stu-id="e89da-119">In the **Master Data Explorer** pane, click an entity.</span></span>  
  
4.  <span data-ttu-id="e89da-120">No grupo **Conectar e Carregar** , clique em **Filtrar**.</span><span class="sxs-lookup"><span data-stu-id="e89da-120">In the **Connect and Load** group, click **Filter**.</span></span>  
  
5.  <span data-ttu-id="e89da-121">Na caixa de diálogo **Filtrar** , na seção **Colunas** , na lista de atributos, clique no atributo que deseja mover.</span><span class="sxs-lookup"><span data-stu-id="e89da-121">In the **Filter** dialog box, in the **Columns** section, in the list of attributes, click the attribute you want to move.</span></span>  
  
6.  <span data-ttu-id="e89da-122">À direita da lista, clique na seta **Para cima** ou **Para baixo** para mover o atributo para a esquerda ou para a direita na planilha.</span><span class="sxs-lookup"><span data-stu-id="e89da-122">To the right of the list, click the **Up** or **Down** arrow to move the attribute left and right in the worksheet.</span></span>  
  
7.  <span data-ttu-id="e89da-123">Repita a etapa 7 para cada atributo até que a ordem de cima para baixo represente a ordem da esquerda para a direita que você deseja na planilha.</span><span class="sxs-lookup"><span data-stu-id="e89da-123">Repeat step 7 for each attribute until the top-to-bottom order represents the left-to-right order you want in the worksheet.</span></span>  
  
8.  <span data-ttu-id="e89da-124">Clique em **Carregar Dados**.</span><span class="sxs-lookup"><span data-stu-id="e89da-124">Click **Load Data**.</span></span> <span data-ttu-id="e89da-125">A planilha será preenchida com dados gerenciados no MDS e as colunas serão exibidas na ordem que você especificou.</span><span class="sxs-lookup"><span data-stu-id="e89da-125">The sheet is populated with MDS-managed data and the columns are displayed in the order you specified.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e89da-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e89da-126">See Also</span></span>  
 [<span data-ttu-id="e89da-127">Carregando dados &#40;Suplemento MDS para Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="e89da-127">Loading Data &#40;MDS Add-in for Excel&#41;</span></span>](overview-exporting-data-to-excel-mds-add-in-for-excel.md)  
  
  
