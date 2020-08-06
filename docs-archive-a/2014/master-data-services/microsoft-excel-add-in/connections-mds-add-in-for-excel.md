---
title: Conexões (Suplemento MDS para Excel) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: 2f2b2f9d-7744-460e-83cd-56d34ea70ff0
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: d4dc41afc6dd59cade9e75475c7cb914d14a8937
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568678"
---
# <a name="connections-mds-add-in-for-excel"></a><span data-ttu-id="ac2a7-102">Conexões (suplemento MDS para Excel)</span><span class="sxs-lookup"><span data-stu-id="ac2a7-102">Connections (MDS Add-in for Excel)</span></span>
  <span data-ttu-id="ac2a7-103">Para baixar dados no [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], você deve primeiramente criar uma conexão.</span><span class="sxs-lookup"><span data-stu-id="ac2a7-103">To download data in to the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], you must first create a connection.</span></span> <span data-ttu-id="ac2a7-104">Uma conexão é como o serviço Web do [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] sabe a qual banco de dados do MDS deve se conectar.</span><span class="sxs-lookup"><span data-stu-id="ac2a7-104">A connection is how the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] web service knows which MDS database to connect to.</span></span>  
  
 <span data-ttu-id="ac2a7-105">Normalmente, a cadeia de conexão é a URL do aplicativo Web do [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)], por exemplo, http://contoso/mds.</span><span class="sxs-lookup"><span data-stu-id="ac2a7-105">The connection string is usually the URL of the [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web application, for example http://contoso/mds.</span></span>  
  
 <span data-ttu-id="ac2a7-106">Sempre que você iniciar o Excel, deverá conectar-se a um repositório do MDS.</span><span class="sxs-lookup"><span data-stu-id="ac2a7-106">Each time you start Excel, you must connect to an MDS repository.</span></span> <span data-ttu-id="ac2a7-107">A única exceção é quando a planilha ativa já contêm dados gerenciados no MDS.</span><span class="sxs-lookup"><span data-stu-id="ac2a7-107">The only exception is when the active spreadsheet already contains MDS-managed data.</span></span> <span data-ttu-id="ac2a7-108">Nesse caso, uma conexão será estabelecida automaticamente sempre que você atualizar ou publicar dados na planilha.</span><span class="sxs-lookup"><span data-stu-id="ac2a7-108">In this case, a connection is automatically made each time you refresh or publish data in the sheet.</span></span>  
  
 <span data-ttu-id="ac2a7-109">É possível criar várias conexões.</span><span class="sxs-lookup"><span data-stu-id="ac2a7-109">You can create multiple connections.</span></span> <span data-ttu-id="ac2a7-110">A conexão acessada mais recentemente será considerada como padrão.</span><span class="sxs-lookup"><span data-stu-id="ac2a7-110">The most recently-accessed connection is considered the default.</span></span>  
  
 <span data-ttu-id="ac2a7-111">Vários usuários podem ser conectados ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="ac2a7-111">Multiple users can be connected at the same time.</span></span> <span data-ttu-id="ac2a7-112">No entanto, conflitos podem ocorrer quando vários usuários tentarem publicar os mesmos dados.</span><span class="sxs-lookup"><span data-stu-id="ac2a7-112">However, conflicts can arise when multiple users attempt to publish the same data.</span></span> <span data-ttu-id="ac2a7-113">Para obter mais informações, consulte [Publishing Data &#40;Suplemento MDS para Excel&#41;](overview-importing-data-from-excel-mds-add-in-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="ac2a7-113">For more information, see [Publishing Data &#40;MDS Add-in for Excel&#41;](overview-importing-data-from-excel-mds-add-in-for-excel.md).</span></span>  
  
## <a name="connect-automatically-and-load-frequently-used-data"></a><span data-ttu-id="ac2a7-114">Conectar-se automaticamente e carregar dados usados frequentemente</span><span class="sxs-lookup"><span data-stu-id="ac2a7-114">Connect Automatically and Load Frequently-Used Data</span></span>  
 <span data-ttu-id="ac2a7-115">Se você desejar conectar-se sempre ao mesmo servidor e carregar o mesmo conjunto de dados, poderá criar arquivos de consulta de atalho que contenham informações de conexão e de filtro.</span><span class="sxs-lookup"><span data-stu-id="ac2a7-115">If you want to always connect to the same server and load the same set of data, you can create shortcut query files, which contain connection and filter information.</span></span> <span data-ttu-id="ac2a7-116">Para obter mais informações sobre arquivos de consulta, consulte [Arquivos de consulta de atalho &#40;Suplemento MDS para Excel&#41;](shortcut-query-files-mds-add-in-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="ac2a7-116">For more information about query files, see [Shortcut Query Files &#40;MDS Add-in for Excel&#41;](shortcut-query-files-mds-add-in-for-excel.md).</span></span>  
  
## <a name="data-quality-services"></a><span data-ttu-id="ac2a7-117">Data Quality Services</span><span class="sxs-lookup"><span data-stu-id="ac2a7-117">Data Quality Services</span></span>  
 <span data-ttu-id="ac2a7-118">O [!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)] possui a funcionalidade Data Quality Services para ajudar a combinar os dados antes de publicá-los no repositório do MDS.</span><span class="sxs-lookup"><span data-stu-id="ac2a7-118">The [!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)] has Data Quality Services functionality to help you match data before publishing it to the MDS repository.</span></span> <span data-ttu-id="ac2a7-119">Ao fazer uma conexão, se um banco de dados DQS estiver instalado na mesma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] em que está o banco de dados MDS, você poderá ver os botões do DQS na faixa de opções.</span><span class="sxs-lookup"><span data-stu-id="ac2a7-119">When you make a connection, if a DQS database is installed on the same instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] as the MDS database, you will be able to view DQS buttons on the ribbon.</span></span> <span data-ttu-id="ac2a7-120">Se o banco de dados DQS_Main não existir na instância, esses botões não serão exibidos e a funcionalidade de qualidade de dados não estará disponível.</span><span class="sxs-lookup"><span data-stu-id="ac2a7-120">If the DQS_Main database does not exist on the instance, these buttons are not displayed and data quality functionality is not available.</span></span>  
  
## <a name="troubleshooting-connections"></a><span data-ttu-id="ac2a7-121">Solucionando problemas de conexões</span><span class="sxs-lookup"><span data-stu-id="ac2a7-121">Troubleshooting Connections</span></span>  
 <span data-ttu-id="ac2a7-122">Quando você se conectar ao MDS, se encontrar algum problema, consulte [https://social.technet.microsoft.com/wiki/contents/articles/4520.aspx](https://social.technet.microsoft.com/wiki/contents/articles/4520.aspx) para obter dicas de solução de problemas.</span><span class="sxs-lookup"><span data-stu-id="ac2a7-122">When you connect to MDS, if you encounter any issues see [https://social.technet.microsoft.com/wiki/contents/articles/4520.aspx](https://social.technet.microsoft.com/wiki/contents/articles/4520.aspx) for troubleshooting tips.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="ac2a7-123">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="ac2a7-123">Related Tasks</span></span>  
  
|<span data-ttu-id="ac2a7-124">Descrição da tarefa</span><span class="sxs-lookup"><span data-stu-id="ac2a7-124">Task Description</span></span>|<span data-ttu-id="ac2a7-125">Tópico</span><span class="sxs-lookup"><span data-stu-id="ac2a7-125">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="ac2a7-126">Crie uma conexão com um banco de dados do [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ac2a7-126">Create a connection to a [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] database.</span></span>|[<span data-ttu-id="ac2a7-127">Conectar-se a um repositório do MDS &#40;Suplemento MDS para Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="ac2a7-127">Connect to an MDS Repository &#40;MDS Add-in for Excel&#41;</span></span>](connect-to-an-mds-repository-mds-add-in-for-excel.md)|  
|<span data-ttu-id="ac2a7-128">Carregue os dados do MDS no Excel.</span><span class="sxs-lookup"><span data-stu-id="ac2a7-128">Load MDS data into Excel.</span></span>|[<span data-ttu-id="ac2a7-129">Carregar dados do MDS no Excel</span><span class="sxs-lookup"><span data-stu-id="ac2a7-129">Load Data from MDS into Excel</span></span>](export-data-to-excel-from-master-data-services.md)|  
|<span data-ttu-id="ac2a7-130">Filtre os dados do MDS antes de carregá-los no Excel.</span><span class="sxs-lookup"><span data-stu-id="ac2a7-130">Filter MDS data before you load it into Excel.</span></span>|[<span data-ttu-id="ac2a7-131">Filtrar dados antes de carregar &#40;Suplemento MDS para Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="ac2a7-131">Filter Data before Loading &#40;MDS Add-in for Excel&#41;</span></span>](filter-data-before-exporting-mds-add-in-for-excel.md)|  
  
## <a name="related-content"></a><span data-ttu-id="ac2a7-132">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="ac2a7-132">Related Content</span></span>  
  
-   [<span data-ttu-id="ac2a7-133">Carregando dados &#40;Suplemento MDS para Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="ac2a7-133">Loading Data &#40;MDS Add-in for Excel&#41;</span></span>](overview-exporting-data-to-excel-mds-add-in-for-excel.md)  
  
-   [<span data-ttu-id="ac2a7-134">Arquivos de consulta de atalho &#40;Suplemento MDS para Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="ac2a7-134">Shortcut Query Files &#40;MDS Add-in for Excel&#41;</span></span>](shortcut-query-files-mds-add-in-for-excel.md)  
  
-   [<span data-ttu-id="ac2a7-135">Suplemento do Master Data Services para Microsoft Excel</span><span class="sxs-lookup"><span data-stu-id="ac2a7-135">Master Data Services Add-in for Microsoft Excel</span></span>](master-data-services-add-in-for-microsoft-excel.md)  
  
  
