---
title: Associar um relatório ou modelo a uma fonte de dados compartilhada (SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- shared data sources [Reporting Services]
- data sources [Reporting Services], shared
ms.assetid: 23cc15f2-2883-48e2-bc6c-fa0ab61a2e21
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 596caba042d476173b3c49d1ad18e79d0827fe89
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679716"
---
# <a name="bind-a-report-or-model-to-a-shared-data-source-ssrs"></a><span data-ttu-id="938de-102">Associar um relatório ou modelo a uma fonte de dados compartilhada (SSRS)</span><span class="sxs-lookup"><span data-stu-id="938de-102">Bind a Report or Model to a Shared Data Source (SSRS)</span></span>
  <span data-ttu-id="938de-103">Em algumas situações, por exemplo, quando você move um relatório ou modelo de um servidor de teste para um servidor de produção, talvez seja necessário salvar o arquivo no computador local e carregá-lo em um servidor de relatório diferente.</span><span class="sxs-lookup"><span data-stu-id="938de-103">In some situations, such as when you move a report or model from a test server to a production server, you might want to save the file to your local computer and then upload it to a different report server.</span></span> <span data-ttu-id="938de-104">Ao carregar o relatório ou modelo no novo servidor, você precisa associá-lo novamente a uma fonte de dados compartilhados que está armazenada no novo servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="938de-104">When you upload the report or model to the new server, you need to rebind it to a shared data source that is stored on the new report server.</span></span> <span data-ttu-id="938de-105">Se o relatório ou modelo não for associado novamente, ele não funcionará corretamente quando for acessado a partir do novo servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="938de-105">If you don't rebind the report or model, it will not work correctly when accessed from the new report server.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="938de-106">Antes de associar um relatório ou modelo novamente a uma fonte de dados compartilhada, a fonte de dados já deve existir no servidor de relatório ou na biblioteca do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="938de-106">Before rebinding a report or model to a shared data source, the data source must already exist on the report server or SharePoint library.</span></span> <span data-ttu-id="938de-107">Para obter mais informações sobre fontes de dados, consulte [Criar, modificar e excluir fontes de dados compartilhadas &#40;SSRS&#41;](create-modify-and-delete-shared-data-sources-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="938de-107">For more information about data sources, see [Create, Modify, and Delete Shared Data Sources &#40;SSRS&#41;](create-modify-and-delete-shared-data-sources-ssrs.md).</span></span>  
  
### <a name="to-bind-a-report-or-model-to-a-shared-data-source-on-a-report-server-running-in-native-mode"></a><span data-ttu-id="938de-108">Para associar um relatório ou modelo a uma fonte de dados compartilhada em um servidor de relatório em execução no modo nativo</span><span class="sxs-lookup"><span data-stu-id="938de-108">To bind a report or model to a shared data source on a report server running in native mode</span></span>  
  
1.  <span data-ttu-id="938de-109">No **Gerenciador de Relatórios**, clique no nome do relatório ou modelo carregado no servidor.</span><span class="sxs-lookup"><span data-stu-id="938de-109">In **Report Manager**, click the name of the report or model that you uploaded to the server.</span></span>  
  
     <span data-ttu-id="938de-110">A guia Propriedades é exibida.</span><span class="sxs-lookup"><span data-stu-id="938de-110">The Properties tab opens.</span></span>  
  
2.  <span data-ttu-id="938de-111">Clique em **Fontes de Dados**.</span><span class="sxs-lookup"><span data-stu-id="938de-111">Click **Data Sources**.</span></span>  
  
3.  <span data-ttu-id="938de-112">Clique em **Procurar**e navegue até a fonte de dados à qual deseja associar o relatório ou modelo.</span><span class="sxs-lookup"><span data-stu-id="938de-112">Click **Browse**, and then navigate to the data source to which you want to bind the report or model.</span></span>  
  
4.  <span data-ttu-id="938de-113">Selecione a fonte de dados e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="938de-113">Select the data source and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="938de-114">Clique em **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="938de-114">Click **Apply**.</span></span>  
  
     <span data-ttu-id="938de-115">O relatório ou modelo é associado à fonte de dados selecionada.</span><span class="sxs-lookup"><span data-stu-id="938de-115">The report or model is now bound to the data source that you selected.</span></span>  
  
### <a name="to-bind-a-report-or-model-to-a-shared-data-source-on-a-report-server-running-in-sharepoint-integrated-mode"></a><span data-ttu-id="938de-116">Para associar um relatório ou modelo a uma fonte de dados compartilhada em um servidor de relatório em execução no modo integrado do SharePoint</span><span class="sxs-lookup"><span data-stu-id="938de-116">To bind a report or model to a shared data source on a report server running in SharePoint integrated mode</span></span>  
  
1.  <span data-ttu-id="938de-117">Se a biblioteca ainda não estiver aberta, clique no nome dela na barra Início Rápido.</span><span class="sxs-lookup"><span data-stu-id="938de-117">If the library is not already open, click its name on the Quick Launch bar.</span></span> <span data-ttu-id="938de-118">Se o nome da biblioteca não for exibido, clique em **Exibir Todo o Conteúdo do Site**e, em seguida, clique no nome da biblioteca.</span><span class="sxs-lookup"><span data-stu-id="938de-118">If the name of your library does not appear, click **View All Site Content**, and then click the name of your library.</span></span>  
  
2.  <span data-ttu-id="938de-119">Aponte para o relatório ou modelo e clique na seta para baixo.</span><span class="sxs-lookup"><span data-stu-id="938de-119">Point to the report or model and click the down arrow.</span></span>  
  
3.  <span data-ttu-id="938de-120">Clique em **Gerenciar Fontes de Dados**.</span><span class="sxs-lookup"><span data-stu-id="938de-120">Click **Manage Data Sources**.</span></span>  
  
4.  <span data-ttu-id="938de-121">Clique em **dataSource1**.</span><span class="sxs-lookup"><span data-stu-id="938de-121">Click **dataSource1**.</span></span>  
  
5.  <span data-ttu-id="938de-122">Na área **Tipo de Conexão** , verifique se a opção **Fonte de dados compartilhada** está selecionada.</span><span class="sxs-lookup"><span data-stu-id="938de-122">In the **Connection Type** area, verify that **Shared data source** is selected.</span></span>  
  
6.  <span data-ttu-id="938de-123">Na área **link da fonte de dados** , clique no botão de reticências (...).</span><span class="sxs-lookup"><span data-stu-id="938de-123">In the **Data Source Link** area, click the ellipsis (...) button.</span></span>  
  
7.  <span data-ttu-id="938de-124">Localize a fonte de dados que deseja usar.</span><span class="sxs-lookup"><span data-stu-id="938de-124">Locate the data source you want to use.</span></span>  
  
8.  <span data-ttu-id="938de-125">Selecione a fonte de dados e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="938de-125">Select the data source and **click OK**.</span></span>  
  
9. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
10. <span data-ttu-id="938de-126">Clique em **fechar**</span><span class="sxs-lookup"><span data-stu-id="938de-126">Click **Close**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="938de-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="938de-127">See Also</span></span>  
 <span data-ttu-id="938de-128">[Carregar um &#40;de arquivo ou relatório Report Manager&#41;](../reports/upload-a-file-or-report-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="938de-128">[Upload a File or Report &#40;Report Manager&#41;](../reports/upload-a-file-or-report-report-manager.md) </span></span>  
 <span data-ttu-id="938de-129">[Carregar documentos em uma biblioteca do SharePoint &#40;Reporting Services no modo do SharePoint&#41;](../upload-documents-to-a-sharepoint-library-reporting-services-in-sharepoint-mode.md) </span><span class="sxs-lookup"><span data-stu-id="938de-129">[Upload Documents to a SharePoint Library &#40;Reporting Services in SharePoint Mode&#41;](../upload-documents-to-a-sharepoint-library-reporting-services-in-sharepoint-mode.md) </span></span>  
 <span data-ttu-id="938de-130">[Criar e gerenciar fontes de dados compartilhadas &#40;Reporting Services no modo integrado do SharePoint&#41;](../create-manage-shared-data-sources-reporting-services-sharepoint-integrated-mode.md) </span><span class="sxs-lookup"><span data-stu-id="938de-130">[Create and Manage Shared Data Sources &#40;Reporting Services in SharePoint Integrated Mode&#41;](../create-manage-shared-data-sources-reporting-services-sharepoint-integrated-mode.md) </span></span>  
 <span data-ttu-id="938de-131">[Criar, excluir ou modificar uma fonte de dados compartilhada &#40;Report Manager&#41;](../create-delete-or-modify-a-shared-data-source-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="938de-131">[Create, Delete, or Modify a Shared Data Source &#40;Report Manager&#41;](../create-delete-or-modify-a-shared-data-source-report-manager.md) </span></span>  
 <span data-ttu-id="938de-132">[Conexões de dados, fontes de dados e cadeias de conexão no Reporting Services](../data-connections-data-sources-and-connection-strings-in-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="938de-132">[Data Connections, Data Sources, and Connection Strings in Reporting Services](../data-connections-data-sources-and-connection-strings-in-reporting-services.md) </span></span>  
 [<span data-ttu-id="938de-133">Fontes de dados com suporte no Reporting Services &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="938de-133">Data Sources Supported by Reporting Services &#40;SSRS&#41;</span></span>](../create-deploy-and-manage-mobile-and-paginated-reports.md)  
  
  
