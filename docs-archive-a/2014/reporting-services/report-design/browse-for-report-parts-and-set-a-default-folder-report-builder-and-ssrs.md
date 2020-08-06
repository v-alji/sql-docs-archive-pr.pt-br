---
title: Procurar partes de relatório e definir uma pasta padrão (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 5cf38068-65d1-4fe8-81f3-a404d8fbc663
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 6605a23732799ec07b3dbe8481e88c91b18ebe5d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570453"
---
# <a name="browse-for-report-parts-and-set-a-default-folder-report-builder-and-ssrs"></a><span data-ttu-id="55922-102">Procurar partes de relatório e definir uma pasta padrão (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="55922-102">Browse for Report Parts and Set a Default Folder (Report Builder and SSRS)</span></span>
  <span data-ttu-id="55922-103">O modo mais fácil de criar um relatório é adicionar partes de relatório existentes, como tabelas e gráficos, ao relatório a partir da Galeria de Partes de Relatório.</span><span class="sxs-lookup"><span data-stu-id="55922-103">The easiest way to create a report is to add existing report parts, such as tables and charts, to your report from the Report Part Gallery.</span></span> <span data-ttu-id="55922-104">Quando você adiciona uma parte de relatório a seu relatório, também está adicionando tudo que ele deve ter para funcionar.</span><span class="sxs-lookup"><span data-stu-id="55922-104">When you add a report part to your report, you are also adding everything it must have to work.</span></span> <span data-ttu-id="55922-105">Por exemplo, qualquer parte de relatório que exiba dados depende de um conjunto de dados, ou seja, uma consulta e uma conexão com uma fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="55922-105">For example, any report part that displays data depends on a dataset, that is, a query and a connection to a data source.</span></span> <span data-ttu-id="55922-106">Depois que você adicionar a parte de relatório a seu relatório, poderá modificá-la tanto quanto necessário.</span><span class="sxs-lookup"><span data-stu-id="55922-106">After you add the report part to your report, you can modify it as much as you need.</span></span>  
  
 <span data-ttu-id="55922-107">Você pode definir uma pasta padrão para publicar partes de relatório no servidor de relatório ou no site do SharePoint integrado a um servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="55922-107">You can set a default folder to publish report parts to the report server or SharePoint site integrated with a report server.</span></span>  
  
 <span data-ttu-id="55922-108">Para obter mais informações, consulte [Partes de relatório &#40;Construtor de Relatórios e SSRS&#41;](../report-parts-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="55922-108">For more information, see [Report Parts &#40;Report Builder and SSRS&#41;](../report-parts-report-builder-and-ssrs.md).</span></span>  
  
### <a name="to-browse-for-report-parts"></a><span data-ttu-id="55922-109">Para procurar partes de relatório</span><span class="sxs-lookup"><span data-stu-id="55922-109">To browse for report parts</span></span>  
  
1.  <span data-ttu-id="55922-110">No menu **Inserir** , clique em **Partes de Relatório**.</span><span class="sxs-lookup"><span data-stu-id="55922-110">On the **Insert** menu, click **Report Parts**.</span></span>  
  
     <span data-ttu-id="55922-111">Se você ainda não estiver conectado, clique em **Conectar a um servidor de relatório**e insira o nome.</span><span class="sxs-lookup"><span data-stu-id="55922-111">If you are not already connected, click **Connect to a report server**, and enter the name.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="55922-112">Você deve estar conectado a um servidor de relatório para procurar partes de relatório.</span><span class="sxs-lookup"><span data-stu-id="55922-112">You must be connected to a report server to browse for report parts.</span></span>  
  
2.  <span data-ttu-id="55922-113">Agora você pode restringir sua pesquisa especificando detalhes sobre a parte de relatório.</span><span class="sxs-lookup"><span data-stu-id="55922-113">You can narrow your search by specifying details about the report part.</span></span> <span data-ttu-id="55922-114">Digite o nome (ou parte dele) e a descrição na caixa **Pesquisar** ou clique em **Adicionar Critérios** e adicione valores a qualquer um destes campos:</span><span class="sxs-lookup"><span data-stu-id="55922-114">Type all or part of the name and description in the **Search** box, or click **Add Criteria** and add values for any or all of these fields:</span></span>  
  
    -   <span data-ttu-id="55922-115">Criado por</span><span class="sxs-lookup"><span data-stu-id="55922-115">Created by</span></span>  
  
    -   <span data-ttu-id="55922-116">Data de criação</span><span class="sxs-lookup"><span data-stu-id="55922-116">Date created</span></span>  
  
    -   <span data-ttu-id="55922-117">Data da última modificação</span><span class="sxs-lookup"><span data-stu-id="55922-117">Date last modified</span></span>  
  
    -   <span data-ttu-id="55922-118">Última modificação feita por</span><span class="sxs-lookup"><span data-stu-id="55922-118">Last modified by</span></span>  
  
    -   <span data-ttu-id="55922-119">Pasta do servidor</span><span class="sxs-lookup"><span data-stu-id="55922-119">Server folder</span></span>  
  
    -   <span data-ttu-id="55922-120">Type</span><span class="sxs-lookup"><span data-stu-id="55922-120">Type</span></span>  
  
     <span data-ttu-id="55922-121">Por exemplo, para localizar uma imagem, clique em **Adicionar Critérios**e em **Tipo**.</span><span class="sxs-lookup"><span data-stu-id="55922-121">For example, to find an image, click **Add Criteria**, and then click **Type**.</span></span> <span data-ttu-id="55922-122">Na caixa suspensa, marque a caixa de seleção **Imagem** , pressione ENTER e clique na lupa Pesquisar.</span><span class="sxs-lookup"><span data-stu-id="55922-122">In the dropdown box, select the **Image** check box, press ENTER, and then click the Search magnifying glass.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="55922-123">Para os valores **Criado por** e **Última modificação** , é necessário procurar o nome de usuário da pessoa, conforme representado no servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="55922-123">For the **Created by** and **Last modified by** values, search for the person's user name as it is represented on the report server.</span></span>  
  
### <a name="to-set-a-default-folder-for-report-parts"></a><span data-ttu-id="55922-124">Para definir uma pasta padrão para partes de relatório</span><span class="sxs-lookup"><span data-stu-id="55922-124">To set a default folder for report parts</span></span>  
  
1.  <span data-ttu-id="55922-125">Clique em **Construtor de Relatórios**e em **Opções**.</span><span class="sxs-lookup"><span data-stu-id="55922-125">Click **Report Builder**, and then click **Options**.</span></span>  
  
2.  <span data-ttu-id="55922-126">Na caixa de diálogo **Opções** , na guia **Configurações** , digite um nome de pasta na caixa de texto **Publicar partes de relatório nesta pasta por padrão** .</span><span class="sxs-lookup"><span data-stu-id="55922-126">In the **Options** dialog box, on the **Settings** tab, type a folder name in the **Publish report parts to this folder by default** textbox.</span></span>  
  
 <span data-ttu-id="55922-127">O Construtor de Relatórios criará essa pasta se você tiver permissões para criar pastas no servidor de relatório e se a pasta ainda não existir.</span><span class="sxs-lookup"><span data-stu-id="55922-127">Report Builder will create this folder if you have permissions to create folders on the report server and the folder does not exist yet.</span></span>  
  
 <span data-ttu-id="55922-128">Você não precisa reiniciar o Construtor de Relatórios para que essa configuração tenha efeito.</span><span class="sxs-lookup"><span data-stu-id="55922-128">You do not need to restart Report Builder for this setting to take effect.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55922-129">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="55922-129">See Also</span></span>  
 <span data-ttu-id="55922-130">[Verificar se há atualizações ou desativar as atualizações &#40;Construtor de Relatórios e SSRS&#41;](../check-for-updates-or-turn-updates-off-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="55922-130">[Check for Updates or Turn Updates Off &#40;Report Builder and SSRS&#41;](../check-for-updates-or-turn-updates-off-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="55922-131">[Partes de relatório &#40;Construtor de Relatórios e SSRS&#41;](../report-parts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="55922-131">[Report Parts &#40;Report Builder and SSRS&#41;](../report-parts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="55922-132">[Partes de relatório e conjuntos de dados no Construtor de Relatórios](../report-data/report-parts-and-datasets-in-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="55922-132">[Report Parts and Datasets in Report Builder](../report-data/report-parts-and-datasets-in-report-builder.md) </span></span>  
 <span data-ttu-id="55922-133">[Solucionar problemas de partes de relatório &#40;Construtor de Relatórios e SSRS&#41;](../troubleshoot-report-parts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="55922-133">[Troubleshoot Report Parts &#40;Report Builder and SSRS&#41;](../troubleshoot-report-parts-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="55922-134">Publicar e republicar partes de relatório &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="55922-134">Publish and Republish Report Parts &#40;Report Builder and SSRS&#41;</span></span>](publish-and-republish-report-parts-report-builder-and-ssrs.md)  
  
  
