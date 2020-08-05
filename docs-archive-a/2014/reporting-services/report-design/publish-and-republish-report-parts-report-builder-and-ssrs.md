---
title: Publicar e publicar novamente partes de relatório (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 92dce484-f39b-403c-9caf-d8772bc3aca3
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 95fd5e3f7519c6a0d4a6f08cb9bcbf2507d32aaa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572386"
---
# <a name="publish-and-republish-report-parts-report-builder-and-ssrs"></a><span data-ttu-id="df191-102">Publicar e republicar partes de relatório (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="df191-102">Publish and Republish Report Parts (Report Builder and SSRS)</span></span>
  <span data-ttu-id="df191-103">Você pode publicar uma parte de relatório com configurações padrão em um local padrão ou pode editar os metadados de parte do relatório, como nome e descrição e salvá-lo em outro lugar no servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="df191-103">You can publish a report part with default settings in a default location, or you can edit report part metadata such as name and description, and save it somewhere else on a report server.</span></span> <span data-ttu-id="df191-104">Também será possível salvá-lo em um site do SharePoint integrado com um servidor de relatório se você tiver as permissões corretas.</span><span class="sxs-lookup"><span data-stu-id="df191-104">You can also save it to a SharePoint site that is integrated with a report server if you have the correct permissions.</span></span>  
  
 <span data-ttu-id="df191-105">Você pode publicar apenas a parte de relatório, com o conjunto de dados do qual ela depende ou está inserida, ou pode publicar o conjunto de dados separadamente.</span><span class="sxs-lookup"><span data-stu-id="df191-105">You can publish just the report part, with the dataset that it depends on embedded in it, or you can publish the dataset separately.</span></span> <span data-ttu-id="df191-106">Se você publicar o conjunto de dados separadamente, ele se tornará um conjunto de dados compartilhado e a parte de relatório será vinculada a ele.</span><span class="sxs-lookup"><span data-stu-id="df191-106">If you publish the dataset separately, it becomes a shared dataset, and the report part links to it.</span></span> <span data-ttu-id="df191-107">Para obter mais informações, consulte [Partes de relatório e conjuntos de dados no Construtor de Relatórios](../report-data/report-parts-and-datasets-in-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="df191-107">For more information, see [Report Parts and Datasets in Report Builder](../report-data/report-parts-and-datasets-in-report-builder.md).</span></span>  
  
 <span data-ttu-id="df191-108">Você pode publicar novamente uma parte de relatório existente.</span><span class="sxs-lookup"><span data-stu-id="df191-108">You can republish an existing report part.</span></span> <span data-ttu-id="df191-109">Se tiver permissões, você poderá salvar sobre a instância original da parte de relatório no servidor, mesmo que não a tenha criado.</span><span class="sxs-lookup"><span data-stu-id="df191-109">If you have permissions, you can save over the original instance of the report part on the server, even if you didn't create it.</span></span> <span data-ttu-id="df191-110">Também é possível publicá-la como uma nova parte de relatório e salvá-la no mesmo ou em outro local.</span><span class="sxs-lookup"><span data-stu-id="df191-110">You can also publish it as a new report part and save it either in the same or a different location.</span></span>  
  
### <a name="to-publish-a-report-part"></a><span data-ttu-id="df191-111">Para publicar uma parte de relatório</span><span class="sxs-lookup"><span data-stu-id="df191-111">To publish a report part</span></span>  
  
1.  <span data-ttu-id="df191-112">No menu Construtor de Relatórios, clique em **Publicar Partes de Relatório**.</span><span class="sxs-lookup"><span data-stu-id="df191-112">On the Report Builder menu, click **Publish Report Parts**.</span></span>  
  
     <span data-ttu-id="df191-113">Se você não estiver conectado a um servidor de relatório, receberá uma solicitação para se conectar.</span><span class="sxs-lookup"><span data-stu-id="df191-113">If you are not connected to a report server, you will be prompted to connect.</span></span> <span data-ttu-id="df191-114">Se você não puder se conectar a um servidor de relatório, não poderá publicar partes de relatório.</span><span class="sxs-lookup"><span data-stu-id="df191-114">If you cannot connect to a report server, you cannot publish report parts.</span></span>  
  
2.  <span data-ttu-id="df191-115">Para salvar suas partes de relatório com configurações padrão para o local padrão, clique em **Publicar todas as partes de relatório com configurações padrão**.</span><span class="sxs-lookup"><span data-stu-id="df191-115">To save your report parts with default settings to the default location, click **Publish all report parts with default settings**.</span></span>  
  
     <span data-ttu-id="df191-116">Caso contrário, clique em **Examine e modifique as partes de relatório antes da publicação**.</span><span class="sxs-lookup"><span data-stu-id="df191-116">Otherwise, click **Review and modify report parts before publishing**.</span></span>  
  
3.  <span data-ttu-id="df191-117">Edite o nome da parte de relatório e a descrição: clique duas vezes no nome para editá-lo e clique no campo **Descrição** para adicionar uma descrição.</span><span class="sxs-lookup"><span data-stu-id="df191-117">Edit the report part name and description: Double-click the name to edit it and click in the **Description** field to add a description.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="df191-118">É conveniente dar à parte de relatório nome e descrição claros, para facilitar a identificação durante a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="df191-118">It is a good idea to give the report part name and description, to help people identify it when searching.</span></span> <span data-ttu-id="df191-119">O comprimento máximo para o nome de uma parte de relatório é 260 caracteres para o caminho inteiro, inclusive os nomes das pastas no servidor, seguido pelo nome real da parte de relatório.</span><span class="sxs-lookup"><span data-stu-id="df191-119">The maximum length for the name of a report part is 260 characters for the entire path, including the names of the folders on the server, followed by the actual name of the report part.</span></span>  
  
4.  <span data-ttu-id="df191-120">Para salvar sua parte de relatório em outra pasta que não a padrão, clique no botão **Procurar** .</span><span class="sxs-lookup"><span data-stu-id="df191-120">To save your report part to a folder other than the default, click the **Browse** button.</span></span>  
  
5.  <span data-ttu-id="df191-121">Depois de definir as opções para todas as partes de relatório no relatório, clique em **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="df191-121">When you have set the options for all the report parts in the report, click **Publish**.</span></span>  
  
     <span data-ttu-id="df191-122">Depois que você publicar as partes de relatório, a caixa de diálogo mostrará as que foram publicadas com êxito e as que não foram.</span><span class="sxs-lookup"><span data-stu-id="df191-122">After you publish the report parts, the dialog box shows which were successfully published and which were not.</span></span> <span data-ttu-id="df191-123">Você pode exibir detalhes na caixa de diálogo **Publicar Partes de Relatório** para as partes de relatório que não foram publicadas.</span><span class="sxs-lookup"><span data-stu-id="df191-123">You can view details in the **Publish Report Parts** dialog box for the report parts that failed to publish.</span></span>  
  
6.  <span data-ttu-id="df191-124">Clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="df191-124">Click **Close**.</span></span>  
  
### <a name="to-republish-a-report-part"></a><span data-ttu-id="df191-125">Para publicar uma parte de relatório novamente</span><span class="sxs-lookup"><span data-stu-id="df191-125">To republish a report part</span></span>  
  
1.  <span data-ttu-id="df191-126">Siga o procedimento anterior para publicar uma parte de relatório.</span><span class="sxs-lookup"><span data-stu-id="df191-126">Follow the previous procedure for publishing a report part.</span></span>  
  
2.  <span data-ttu-id="df191-127">Na caixa de diálogo **Publicar Partes de Relatório** , se você clicar em **Publicar como uma Nova Cópia da Parte de Relatório**, o Construtor de Relatórios não salvará sobre a parte de relatório existente no servidor, mas criará outra parte de relatório.</span><span class="sxs-lookup"><span data-stu-id="df191-127">In the **Publish Report Parts** dialog box, if you click **Publish as a New Copy of the Report Part**, Report Builder will not save over the existing report part on the server, but will create another report part instead.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="df191-128">Se você publicá-la como uma nova parte de relatório, ela terá uma nova ID exclusiva.</span><span class="sxs-lookup"><span data-stu-id="df191-128">If you publish it as a new report part, it will have a new unique ID.</span></span> <span data-ttu-id="df191-129">Ela não receberá mais atualizações se a parte de relatório original for alterada.</span><span class="sxs-lookup"><span data-stu-id="df191-129">It will no longer receive updates if the original report part changes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df191-130">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="df191-130">See Also</span></span>  
 <span data-ttu-id="df191-131">[Partes de relatório &#40;Construtor de Relatórios e SSRS&#41;](../report-parts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="df191-131">[Report Parts &#40;Report Builder and SSRS&#41;](../report-parts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="df191-132">[Partes de relatório e conjuntos de valores no Construtor de Relatórios](../report-data/report-parts-and-datasets-in-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="df191-132">[Report Parts and Datasets in Report Builder](../report-data/report-parts-and-datasets-in-report-builder.md) </span></span>  
 <span data-ttu-id="df191-133">[Solucionar problemas de partes de relatório &#40;Construtor de Relatórios e SSRS&#41;](../troubleshoot-report-parts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="df191-133">[Troubleshoot Report Parts &#40;Report Builder and SSRS&#41;](../troubleshoot-report-parts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="df191-134">[Verificar se há atualizações ou desativar as atualizações &#40;Construtor de Relatórios e SSRS&#41;](../check-for-updates-or-turn-updates-off-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="df191-134">[Check for Updates or Turn Updates Off &#40;Report Builder and SSRS&#41;](../check-for-updates-or-turn-updates-off-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="df191-135">Procurar partes de relatório e definir uma pasta padrão &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="df191-135">Browse for Report Parts and Set a Default Folder &#40;Report Builder and SSRS&#41;</span></span>](browse-for-report-parts-and-set-a-default-folder-report-builder-and-ssrs.md)  
  
  
