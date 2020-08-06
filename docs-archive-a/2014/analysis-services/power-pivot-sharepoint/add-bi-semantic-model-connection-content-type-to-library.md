---
title: Adicionar um tipo de conteúdo de conexão de modelo semântico de BI a uma biblioteca (PowerPivot para SharePoint) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 145505ed-50bc-4528-912b-2a5cd2566011
author: minewiskan
ms.author: owend
ms.openlocfilehash: ecd40193b382aa692beeadd55ab8f9388c328620
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582167"
---
# <a name="add-a-bi-semantic-model-connection-content-type-to-a-library-powerpivot-for-sharepoint"></a><span data-ttu-id="b00fa-102">Adicionar um tipo de conteúdo de conexão de modelo semântico de BI a uma biblioteca (PowerPivot para SharePoint)</span><span class="sxs-lookup"><span data-stu-id="b00fa-102">Add a BI Semantic Model Connection Content Type to a Library (PowerPivot for SharePoint)</span></span>
  <span data-ttu-id="b00fa-103">Uma conexão de modelo semântico de BI é criada no SharePoint e fornece redirecionamento para dados de modelo de semântica de business intelligence em uma pastas de trabalho PowerPivot ou banco de dados de modelo de tabela do Analysis Services em um servidor de rede.</span><span class="sxs-lookup"><span data-stu-id="b00fa-103">A BI semantic model connection is created in SharePoint and provides redirection to business intelligence semantic model data in a PowerPivot workbook or Analysis Services tabular model database on a network server.</span></span> <span data-ttu-id="b00fa-104">Antes de criar uma conexão de modelo semântico de BI no SharePoint, você deve estender uma biblioteca de documentos para permitir a criação de um arquivo .bism.</span><span class="sxs-lookup"><span data-stu-id="b00fa-104">Before you can create a BI semantic model connection in SharePoint, you must extend a document library to allow the creation of a .bism file.</span></span> <span data-ttu-id="b00fa-105">Esta etapa só precisa ser executada uma vez para cada biblioteca, mas você precisará repeti-la para qualquer biblioteca da qual deseje criar arquivos .bism.</span><span class="sxs-lookup"><span data-stu-id="b00fa-105">This step only needs to be performed once for each library, but you will need to repeat it for any library from which you want to create .bism files.</span></span> <span data-ttu-id="b00fa-106">De acordo com as práticas recomendadas, você deve criar uma biblioteca centralizada para armazenar arquivos .bism, permitindo o gerenciamento de permissões em um local.</span><span class="sxs-lookup"><span data-stu-id="b00fa-106">Best practices recommend that you create a centralized library for storing .bism files so that you can manage permissions in one place.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b00fa-107">Se você já usa Bibliotecas de Conexão de Dados SharePoint, o tipo de conteúdo da Conexão de Modelo Semântico de BI é acrescentado automaticamente a esse modelo de biblioteca.</span><span class="sxs-lookup"><span data-stu-id="b00fa-107">If you already use SharePoint Data Connection Libraries, the BI Semantic Model Connection content type is automatically added to that library template.</span></span> <span data-ttu-id="b00fa-108">Você poderá ignorar as etapas desta seção se usar uma biblioteca de conexão de dados que já o permite criar novos documentos de conexão de modelo semântico de BI.</span><span class="sxs-lookup"><span data-stu-id="b00fa-108">You can skip the steps in this section if you use a data connection library that already lets you create new BI semantic model connection documents.</span></span>  
  
##  <a name="add-the-content-type-to-a-document-library"></a><a name="bkmk_addtype"></a> <span data-ttu-id="b00fa-109">Adicionar o tipo de conteúdo a uma biblioteca de documentos</span><span class="sxs-lookup"><span data-stu-id="b00fa-109">Add the content type to a document library</span></span>  
 <span data-ttu-id="b00fa-110">Você deve ter pelo menos a permissão Gerenciar Listas para adicionar e configurar um tipo de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="b00fa-110">You must have at least the Manage Lists permission to add and configure a content type.</span></span> <span data-ttu-id="b00fa-111">Esta permissão é compilada no nível de permissão Design e superior.</span><span class="sxs-lookup"><span data-stu-id="b00fa-111">This permission is built into the Design permission level and above.</span></span>  
  
 <span data-ttu-id="b00fa-112">O site que contém a biblioteca de documentos deve ter ativação de recurso para PowerPivot para SharePoint.</span><span class="sxs-lookup"><span data-stu-id="b00fa-112">The site that contains the document library must have feature activation for PowerPivot for SharePoint.</span></span> <span data-ttu-id="b00fa-113">Para obter mais informações, consulte [ativar a integração de recursos do PowerPivot para coleções de sites na administração central](activate-power-pivot-integration-for-site-collections-in-ca.md).</span><span class="sxs-lookup"><span data-stu-id="b00fa-113">For more information, see [Activate PowerPivot Feature Integration for Site Collections in Central Administration](activate-power-pivot-integration-for-site-collections-in-ca.md).</span></span>  
  
1.  <span data-ttu-id="b00fa-114">Abra a biblioteca de documentos para a qual você deseja habilitar o tipo de conteúdo da Conexão de Modelo Semântico de BI.</span><span class="sxs-lookup"><span data-stu-id="b00fa-114">Open the document library for which you want to enable the BI Semantic Model Connection content type.</span></span>  
  
2.  <span data-ttu-id="b00fa-115">Na faixa de opções do SharePoint, em Ferramentas de Biblioteca, clique em **Biblioteca**.</span><span class="sxs-lookup"><span data-stu-id="b00fa-115">On the SharePoint ribbon, in Library Tools, click **Library**.</span></span>  
  
3.  <span data-ttu-id="b00fa-116">Clique em **Configurações da Biblioteca**.</span><span class="sxs-lookup"><span data-stu-id="b00fa-116">Click **Library Settings**.</span></span>  
  
4.  <span data-ttu-id="b00fa-117">Em Configurações Gerais, clique em **Configurações avançadas**.</span><span class="sxs-lookup"><span data-stu-id="b00fa-117">In General Settings, click **Advanced settings**.</span></span>  
  
5.  <span data-ttu-id="b00fa-118">Em Tipos de Conteúdo, na seção "Permitir o gerenciamento de tipos de conteúdo?",</span><span class="sxs-lookup"><span data-stu-id="b00fa-118">In Content Types, in the "Allow management of content types?"</span></span> <span data-ttu-id="b00fa-119">clique em **Sim**.</span><span class="sxs-lookup"><span data-stu-id="b00fa-119">section, click **Yes**.</span></span>  
  
6.  <span data-ttu-id="b00fa-120">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="b00fa-120">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="b00fa-121">Na seção Tipos de Conteúdo, clique em **Adicionar a partir de tipos de conteúdo de site existentes**.</span><span class="sxs-lookup"><span data-stu-id="b00fa-121">In the Content Types section, click **Add from existing site content types**.</span></span> <span data-ttu-id="b00fa-122">Se você não vir essa página, volte para o site, clique em **Biblioteca** em Ferramentas de Biblioteca e clique em **Definições da Biblioteca**.</span><span class="sxs-lookup"><span data-stu-id="b00fa-122">If you do not see this page, go back to the site, click **Library** in Library Tools, and then click **Library Settings**.</span></span>  
  
8.  <span data-ttu-id="b00fa-123">Em Tipos de Conteúdo, clique em **Adicionar a partir de tipos de conteúdo de site existentes**.</span><span class="sxs-lookup"><span data-stu-id="b00fa-123">In Content Types, click **Add from existing site content types**.</span></span>  
  
9. <span data-ttu-id="b00fa-124">Em Selecionar tipos de conteúdo de site de:, selecione **Business Intelligence**.</span><span class="sxs-lookup"><span data-stu-id="b00fa-124">In Select site content types from:, select **Business Intelligence**.</span></span>  
  
10. <span data-ttu-id="b00fa-125">Em Tipos Disponíveis de Conteúdo do Site, clique em **Arquivo de Conexão de Modelo Semântico de BI**e em **Adicionar** para mover o tipo de conteúdo selecionado para a lista Tipos de conteúdo a serem adicionados.</span><span class="sxs-lookup"><span data-stu-id="b00fa-125">In Available Site Content Types, click **BI Semantic Model Connection File**, and then click **Add** to move the selected content type to the Content types to add list.</span></span>  
  
11. <span data-ttu-id="b00fa-126">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="b00fa-126">Click **OK**.</span></span>  
  
12. <span data-ttu-id="b00fa-127">Para verificar se você adicionou o tipo de conteúdo, volte para a biblioteca e clique em **Novo Documento** na área de Documentos da faixa de opções de biblioteca.</span><span class="sxs-lookup"><span data-stu-id="b00fa-127">To verify you added the content type, go back to the library and click **New Document** on the Documents area of the library ribbon.</span></span> <span data-ttu-id="b00fa-128">Você deverá ver o **Arquivo de Conexão do Modelo Semântico de BI** na lista Novos Documentos.</span><span class="sxs-lookup"><span data-stu-id="b00fa-128">You should see **BI Semantic Model Connection File** in the New Documents list.</span></span>  
  
     <span data-ttu-id="b00fa-129">![Submenu Novo Documento em uma biblioteca do SharePoint](../media/ssas-bismconnection-new.gif "Submenu Novo Documento em uma biblioteca do SharePoint")</span><span class="sxs-lookup"><span data-stu-id="b00fa-129">![New Document submenu in a SharePoint library](../media/ssas-bismconnection-new.gif "New Document submenu in a SharePoint library")</span></span>  
  
 <span data-ttu-id="b00fa-130">Depois de habilitar o tipo de conteúdo de conexão de modelo semântico de BI para uma biblioteca, você poderá criar uma conexão que fornece redirecionamento para dados de modelo semântico comerciais que podem ser usados pelo Excel ou relatórios do [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b00fa-130">After you enable the BI semantic model connection content type for a library, you can create a connection that provides redirection to business semantic model data that can be used by Excel or [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)] reports.</span></span> <span data-ttu-id="b00fa-131">Escolha os links a seguir para saber mais sobre esta próxima etapa:</span><span class="sxs-lookup"><span data-stu-id="b00fa-131">Choose from the following links to learn more about this next step:</span></span>  
  
 [<span data-ttu-id="b00fa-132">Criar uma conexão de modelo semântico de BI para uma pastas de trabalho PowerPivot</span><span class="sxs-lookup"><span data-stu-id="b00fa-132">Create a BI Semantic Model Connection to a PowerPivot Workbook</span></span>](create-a-bi-semantic-model-connection-to-a-power-pivot-workbook.md)  
  
 [<span data-ttu-id="b00fa-133">Create a BI Semantic Model Connection to a Tabular Model Database</span><span class="sxs-lookup"><span data-stu-id="b00fa-133">Create a BI Semantic Model Connection to a Tabular Model Database</span></span>](create-a-bi-semantic-model-connection-to-a-tabular-model-database.md)  
  
## <a name="see-also"></a><span data-ttu-id="b00fa-134">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b00fa-134">See Also</span></span>  
 <span data-ttu-id="b00fa-135">[Conexão de modelo semântico de BI do PowerPivot &#40;. BISM&#41;](power-pivot-bi-semantic-model-connection-bism.md) </span><span class="sxs-lookup"><span data-stu-id="b00fa-135">[PowerPivot BI Semantic Model Connection &#40;.bism&#41;](power-pivot-bi-semantic-model-connection-bism.md) </span></span>  
 [<span data-ttu-id="b00fa-136">Usar uma conexão de modelo semântico de BI no Excel ou Reporting Services</span><span class="sxs-lookup"><span data-stu-id="b00fa-136">Use a BI Semantic Model Connection in Excel or Reporting Services</span></span>](use-a-bi-semantic-model-connection-in-excel-or-reporting-services.md)  
  
  
