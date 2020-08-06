---
title: Carregar dados do MDS para o Excel | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: dd29389b-928c-4e50-995c-c6af27f97805
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 35672807d5bb108e9386f892aea1847d45ebeb33
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680517"
---
# <a name="load-data-from-mds-into-excel"></a><span data-ttu-id="689ab-102">Carregar dados do MDS no Excel</span><span class="sxs-lookup"><span data-stu-id="689ab-102">Load Data from MDS into Excel</span></span>
  <span data-ttu-id="689ab-103">No [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] [!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)] , você deve carregar dados do repositório do MDS para trabalhar com ele.</span><span class="sxs-lookup"><span data-stu-id="689ab-103">In the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], you must load data from the MDS repository in order to work with it.</span></span>  
  
 <span data-ttu-id="689ab-104">Se você quiser filtrar o conjunto de dados antes de carregá-lo, confira [filtro antes de carregar &#40;Suplemento MDS para Excel&#41;](filter-data-before-exporting-mds-add-in-for-excel.md) em vez disso.</span><span class="sxs-lookup"><span data-stu-id="689ab-104">If you want to filter the dataset before loading, see [Filter Data before Loading &#40;MDS Add-in for Excel&#41;](filter-data-before-exporting-mds-add-in-for-excel.md) instead.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="689ab-105">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="689ab-105">Prerequisites</span></span>  
 <span data-ttu-id="689ab-106">Para executar esse procedimento:</span><span class="sxs-lookup"><span data-stu-id="689ab-106">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="689ab-107">Você deve ter permissão para acessar a área funcional do **Gerenciador** .</span><span class="sxs-lookup"><span data-stu-id="689ab-107">You must have permission to access the **Explorer** functional area.</span></span>  
  
### <a name="to-load-data-from-mds-into-excel"></a><span data-ttu-id="689ab-108">Para carregar dados do MDS no Excel</span><span class="sxs-lookup"><span data-stu-id="689ab-108">To load data from MDS into Excel</span></span>  
  
1.  <span data-ttu-id="689ab-109">Abra o Excel e, na guia **Dados Mestre** , conecte-se a um repositório do MDS.</span><span class="sxs-lookup"><span data-stu-id="689ab-109">Open Excel and on the **Master Data** tab, connect to an MDS repository.</span></span> <span data-ttu-id="689ab-110">Para obter mais informações, consulte [Conectar-se a um repositório do MDS &#40;Suplemento MDS para Excel&#41;](connect-to-an-mds-repository-mds-add-in-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="689ab-110">For more information, see [Connect to an MDS Repository &#40;MDS Add-in for Excel&#41;](connect-to-an-mds-repository-mds-add-in-for-excel.md).</span></span>  
  
2.  <span data-ttu-id="689ab-111">No painel do **Master Data Explorer** , selecione um modelo e uma versão.</span><span class="sxs-lookup"><span data-stu-id="689ab-111">In the **Master Data Explorer** pane, select a model and version.</span></span> <span data-ttu-id="689ab-112">A lista de entidades será preenchida.</span><span class="sxs-lookup"><span data-stu-id="689ab-112">The list of entities is populated.</span></span>  
  
    -   <span data-ttu-id="689ab-113">Se o painel do **Master Data Explorer** não estiver visível, no grupo **Conectar e Carregar** , clique em **Mostrar Explorer**.</span><span class="sxs-lookup"><span data-stu-id="689ab-113">If the **Master Data Explorer** pane is not visible, in the **Connect and Load** group, click **Show Explorer**.</span></span>  
  
    -   <span data-ttu-id="689ab-114">Se o painel **Master Data Explorer** estiver desabilitado, isso significará que a planilha existente já contém dados gerenciados pelo MDS.</span><span class="sxs-lookup"><span data-stu-id="689ab-114">If the **Master Data Explorer** pane is disabled, it is because the existing sheet already contains MDS-managed data.</span></span> <span data-ttu-id="689ab-115">Para habilitar o painel, abra uma nova planilha.</span><span class="sxs-lookup"><span data-stu-id="689ab-115">To enable the pane, open a new worksheet.</span></span>  
  
3.  <span data-ttu-id="689ab-116">No painel **Master Data Explorer** , na lista de entidades, clique duas vezes na entidade que você deseja carregar.</span><span class="sxs-lookup"><span data-stu-id="689ab-116">In the **Master Data Explorer** pane, in the list of entities, double-click the entity you want to load.</span></span>  
  
    > [!NOTE]  
    >  -   <span data-ttu-id="689ab-117">Somente os primeiros um milhão de membros serão carregados no Excel.</span><span class="sxs-lookup"><span data-stu-id="689ab-117">Only the first one million members are loaded into Excel.</span></span> <span data-ttu-id="689ab-118">Para filtrar a lista antes de carregar na faixa de opções, no grupo **Conectar e Carregar** , clique em **Filtrar**.</span><span class="sxs-lookup"><span data-stu-id="689ab-118">To filter the list before loading, on the ribbon in the **Connect and Load** group, click **Filter**.</span></span>  
    > -   <span data-ttu-id="689ab-119">Nas colunas que são listas restritas (atributos baseados em domínio), os primeiros 25.000 valores serão carregados.</span><span class="sxs-lookup"><span data-stu-id="689ab-119">In columns that are constrained lists (domain-based attributes), only the first 25,000 values are loaded.</span></span> <span data-ttu-id="689ab-120">Você pode alterar este número na propriedade MaximumDbaEntitySize no arquivo excelusersettings.config localizado no computador no qual o Excel está instalado.</span><span class="sxs-lookup"><span data-stu-id="689ab-120">You can change this number in the MaximumDbaEntitySize property in the excelusersettings.config file located on the computer that Excel is installed on.</span></span> <span data-ttu-id="689ab-121">Esse arquivo está localizado em C:\Users \\<usuário \> \AppData\Local\Microsoft\Microsoft SQL Server\120\MasterDataServices \\ .</span><span class="sxs-lookup"><span data-stu-id="689ab-121">This file is located in C:\Users\\<user\>\AppData\Local\Microsoft\Microsoft SQL Server\120\MasterDataServices\\.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="689ab-122">Quando você carrega dados delimitados por texto usando o Suplemento para Microsoft Excel com o Excel de 32 bits, e as configurações para as propriedades **Cell Count to Load** e **Cell Count to Publish** são configuradas para o máximo de 1000, ocorrerá um erro de memória insuficiente.</span><span class="sxs-lookup"><span data-stu-id="689ab-122">When you load text-delimited data using the Add-in for Microsoft Excel with 32-bit Excel, and the settings for the **Cell Count to Load** and **Cell Count to Publish** properties are both set to the maximum of 1000, an out-of-memory error will occur.</span></span> <span data-ttu-id="689ab-123">Você deve usar o Excel de 64 bits para usar as configurações máximas para **Contagem de Células para Carregamento** e **Contagem de Células para Publicação**.</span><span class="sxs-lookup"><span data-stu-id="689ab-123">You have to use 64-bit Excel to use the maximum settings for **Cell Count to Load** and **Cell Count to Publish**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="689ab-124">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="689ab-124">Next Steps</span></span>  
 [<span data-ttu-id="689ab-125">Publicar dados do Excel para o MDS &#40;Suplemento MDS para Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="689ab-125">Publish Data from Excel to MDS &#40;MDS Add-in for Excel&#41;</span></span>](import-data-from-excel-to-master-data-services-mds-add-in-for-excel.md)  
  
## <a name="see-also"></a><span data-ttu-id="689ab-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="689ab-126">See Also</span></span>  
 <span data-ttu-id="689ab-127">[Carregando dados &#40;Suplemento MDS para Excel&#41;](overview-exporting-data-to-excel-mds-add-in-for-excel.md) </span><span class="sxs-lookup"><span data-stu-id="689ab-127">[Loading Data &#40;MDS Add-in for Excel&#41;](overview-exporting-data-to-excel-mds-add-in-for-excel.md) </span></span>  
 <span data-ttu-id="689ab-128">[Caixa de diálogo de filtro &#40;Suplemento MDS para Excel&#41;](filter-dialog-box-mds-add-in-for-excel.md) </span><span class="sxs-lookup"><span data-stu-id="689ab-128">[Filter Dialog Box &#40;MDS Add-in for Excel&#41;](filter-dialog-box-mds-add-in-for-excel.md) </span></span>  
 [<span data-ttu-id="689ab-129">Publicando dados &#40;Suplemento MDS para Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="689ab-129">Publishing Data &#40;MDS Add-in for Excel&#41;</span></span>](overview-importing-data-from-excel-mds-add-in-for-excel.md)  
  
  
