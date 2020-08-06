---
title: Importar uma base de dados de conhecimento de um arquivo .dqs | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 9b9786fe-9e80-429a-afcb-dc3b3dd6f0b0
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 522c5f6d8f962cef77e215c21133927e8da4d04f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681217"
---
# <a name="import-a-knowledge-base-from-a-dqs-file"></a><span data-ttu-id="4c3a8-102">Importar uma base de dados de conhecimento de um arquivo .dqs</span><span class="sxs-lookup"><span data-stu-id="4c3a8-102">Import a Knowledge Base from a .dqs File</span></span>
  <span data-ttu-id="4c3a8-103">Este tópico descreve como importar uma base de dados de conhecimento inteira de um arquivo de dados .dqs no [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS).</span><span class="sxs-lookup"><span data-stu-id="4c3a8-103">This topic describes how to import an entire knowledge base from a .dqs data file in [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS).</span></span> <span data-ttu-id="4c3a8-104">Você cria o arquivo de dados exportando uma base de dados de conhecimento existente do aplicativo [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] (consulte [exportar uma Base de dados de conhecimento para um arquivo. DQS](../../2014/data-quality-services/export-a-knowledge-base-to-a-dqs-file.md)).</span><span class="sxs-lookup"><span data-stu-id="4c3a8-104">You create the data file by exporting an existing knowledge base from within the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] application (see [Export a Knowledge Base to a .dqs File](../../2014/data-quality-services/export-a-knowledge-base-to-a-dqs-file.md)).</span></span>  
  
 <span data-ttu-id="4c3a8-105">O uso de um arquivo de dados .dqs para exportar o conteúdo de uma base de dados de conhecimento e, depois, importar o conteúdo para outra base de dados de conhecimento no mesmo [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] ou em outro [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] simplifica o processo de geração de conhecimento, economizando tempo e esforço.</span><span class="sxs-lookup"><span data-stu-id="4c3a8-105">Using a .dqs data file to export the contents of a knowledge base and then import the contents into another knowledge base on the same [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] or a different [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] simplifies the knowledge generation process, saving time and effort.</span></span> <span data-ttu-id="4c3a8-106">Isso permite que você compartilhe uma base de dados de conhecimento e seu conhecimento com outras pessoas, fazendo-as ganhar tempo.</span><span class="sxs-lookup"><span data-stu-id="4c3a8-106">It enables you to share a knowledge base and its knowledge with others, saving them time.</span></span> <span data-ttu-id="4c3a8-107">O arquivo .dqs conterá todas as informações da base de dados de conhecimento, inclusive domínios e a política de correspondência, exceto as informações de dados de referência anexadas.</span><span class="sxs-lookup"><span data-stu-id="4c3a8-107">The .dqs file will contain all knowledge base information, including domains and the matching policy, except for the attached reference data information.</span></span> <span data-ttu-id="4c3a8-108">Os dados publicados e não publicados serão importados.</span><span class="sxs-lookup"><span data-stu-id="4c3a8-108">Published and unpublished data will be imported.</span></span>  
  
 <span data-ttu-id="4c3a8-109">Um arquivo de dados .dqs é criptografado e, portanto, não pode ser exibido.</span><span class="sxs-lookup"><span data-stu-id="4c3a8-109">A .dqs data file is encrypted, so cannot be viewed.</span></span>  
  
 <span data-ttu-id="4c3a8-110">Quando você importa uma base de dados de conhecimento, pode usar o mesmo nome, a menos que o nome da base de dados de conhecimento já exista no aplicativo cliente; nesse caso, você deverá renomeá-la.</span><span class="sxs-lookup"><span data-stu-id="4c3a8-110">When you import a knowledge base, you can use the same name, unless the knowledge base name already exists in the client application, in which case you must rename it.</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="4c3a8-111">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="4c3a8-111">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="4c3a8-112">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="4c3a8-112">Prerequisites</span></span>  
 <span data-ttu-id="4c3a8-113">Para importar uma base de dados de conhecimento de um arquivo .dqs, é necessário já ter exportado a base de dados de conhecimento para o arquivo .dqs.</span><span class="sxs-lookup"><span data-stu-id="4c3a8-113">To import a knowledge base from a .dqs file, you must have already exported the knowledge base into the .dqs file.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="4c3a8-114">Segurança</span><span class="sxs-lookup"><span data-stu-id="4c3a8-114">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="4c3a8-115">Permissões</span><span class="sxs-lookup"><span data-stu-id="4c3a8-115">Permissions</span></span>  
 <span data-ttu-id="4c3a8-116">Você deve ter a função dqs_kb_editor ou dqs_administrator no banco de dados DQS_MAIN para importar uma base de dados de conhecimento de um arquivo de dados .dqs.</span><span class="sxs-lookup"><span data-stu-id="4c3a8-116">You must have the dqs_kb_editor or the dqs_administrator role on the DQS_MAIN database to import a knowledge base from a .dqs data file.</span></span>  
  
##  <a name="import-a-knowledge-base-from-a-dqs-file"></a><a name="Import"></a><span data-ttu-id="4c3a8-117">Importar uma base de dados de conhecimento de um arquivo. DQS</span><span class="sxs-lookup"><span data-stu-id="4c3a8-117">Import a knowledge base from a .dqs file</span></span>  
  
1.  [!INCLUDE[ssDQSInitialStep](../includes/ssdqsinitialstep-md.md)]<span data-ttu-id="4c3a8-118">[Execute o aplicativo Data Quality Client](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span><span class="sxs-lookup"><span data-stu-id="4c3a8-118">[Run the Data Quality Client Application](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span></span>  
  
2.  <span data-ttu-id="4c3a8-119">Na tela inicial do [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] , clique em **Nova base de dados de conhecimento**.</span><span class="sxs-lookup"><span data-stu-id="4c3a8-119">In the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] home screen, click **New knowledge base**.</span></span>  
  
3.  <span data-ttu-id="4c3a8-120">Digite um nome para a base de dados de conhecimento.</span><span class="sxs-lookup"><span data-stu-id="4c3a8-120">Enter a name for the knowledge base.</span></span>  
  
4.  <span data-ttu-id="4c3a8-121">Clique na seta para baixo para **Criar base de dados de conhecimento de**e selecione **Importar do arquivo DQS**.</span><span class="sxs-lookup"><span data-stu-id="4c3a8-121">Click the down arrow for **Create knowledge base from**, and then select **Import from DQS file**.</span></span>  
  
5.  <span data-ttu-id="4c3a8-122">Para **Selecionar o arquivo de dados**, clique em **Procurar**.</span><span class="sxs-lookup"><span data-stu-id="4c3a8-122">For **Select data file**, click **Browse**.</span></span>  
  
6.  <span data-ttu-id="4c3a8-123">Na caixa de diálogo **Importar do Arquivo de Dados** , vá para a pasta que contém o arquivo .dqs que você deseja importar e clique no nome do arquivo.</span><span class="sxs-lookup"><span data-stu-id="4c3a8-123">In the **Import from Data File** dialog box, move to the folder that contains the .dqs file that you want to import, and then click the name of the file.</span></span> <span data-ttu-id="4c3a8-124">Clique em **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="4c3a8-124">Click **Open**.</span></span>  
  
7.  <span data-ttu-id="4c3a8-125">Verifique que a base de dados de conhecimento e os domínios corretos são exibidos na lista **Domínio** .</span><span class="sxs-lookup"><span data-stu-id="4c3a8-125">Verify that the correct knowledge base and domains are displayed in the **Domain** list.</span></span>  
  
8.  <span data-ttu-id="4c3a8-126">Selecione a atividade a ser executada e clique em **Criar**.</span><span class="sxs-lookup"><span data-stu-id="4c3a8-126">Select the activity that you want to perform, and then click **Create**.</span></span>  
  
9. <span data-ttu-id="4c3a8-127">Na caixa de diálogo **Importar Base de Dados de Conhecimento** , verifique se a linha de status indica que a importação foi concluída.</span><span class="sxs-lookup"><span data-stu-id="4c3a8-127">In the **Import Knowledge Base** dialog box, verify that the status line indicates that the import completed.</span></span> <span data-ttu-id="4c3a8-128">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4c3a8-128">Click **OK**.</span></span>  
  
10. <span data-ttu-id="4c3a8-129">Conclua as tarefas de descoberta de conhecimento, gerenciamento de domínio ou política de correspondência que você precisa executar e clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="4c3a8-129">Complete the knowledge discovery, domain management, or matching policy tasks that you need to perform, and then click **Finish**.</span></span>  
  
11. <span data-ttu-id="4c3a8-130">Clique em **Publicar** para publicar o conhecimento na base de dados de conhecimento ou em **Não** para não publicá-lo.</span><span class="sxs-lookup"><span data-stu-id="4c3a8-130">Click **Publish** to publish the knowledge in the knowledge base, or **No** not to.</span></span>  
  
12. <span data-ttu-id="4c3a8-131">Se você publicou a base de dados de conhecimento, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4c3a8-131">If you published the knowledge base, click **OK**.</span></span>  
  
13. <span data-ttu-id="4c3a8-132">Na home page do Data Quality Services, verifique se a base de dados de conhecimento está listada em **Bases de dados de conhecimento recentes**.</span><span class="sxs-lookup"><span data-stu-id="4c3a8-132">In the Data Quality Services home page, verify that the knowledge base is listed under **Recent knowledge bases**.</span></span>  
  
##  <a name="follow-up-after-importing-a-knowledge-base-from-a-dqs-file"></a><a name="FollowUp"></a> <span data-ttu-id="4c3a8-133">Acompanhamento: após importar uma base de dados de conhecimento de um arquivo .dqs</span><span class="sxs-lookup"><span data-stu-id="4c3a8-133">Follow Up: After Importing a Knowledge Base from a .dqs File</span></span>  
 <span data-ttu-id="4c3a8-134">Após importar uma base de dados de conhecimento de um arquivo .dqs, você poderá adicionar o conhecimento à base de dados de conhecimento ou usar a base de dados de conhecimento em um projeto de limpeza ou de correspondência, de acordo com o conteúdo da base de dados de conhecimento.</span><span class="sxs-lookup"><span data-stu-id="4c3a8-134">After you import a knowledge base from a .dqs file, you can add knowledge to the knowledge base or use the knowledge base in a cleansing or matching project, depending on the contents of the knowledge base.</span></span> <span data-ttu-id="4c3a8-135">Para obter mais informações, consulte [Executar a descoberta de conhecimento](../../2014/data-quality-services/perform-knowledge-discovery.md), [Gerenciando um domínio](../../2014/data-quality-services/managing-a-domain.md), [Gerenciando um domínio de composição](../../2014/data-quality-services/managing-a-composite-domain.md), [Criar uma política de conciliação](../../2014/data-quality-services/create-a-matching-policy.md), [Limpeza de dados](../../2014/data-quality-services/data-cleansing.md) ou [Correspondência de dados](../../2014/data-quality-services/data-matching.md).</span><span class="sxs-lookup"><span data-stu-id="4c3a8-135">For more information, see [Perform Knowledge Discovery](../../2014/data-quality-services/perform-knowledge-discovery.md), [Managing a Domain](../../2014/data-quality-services/managing-a-domain.md), [Managing a Composite Domain](../../2014/data-quality-services/managing-a-composite-domain.md), [Create a Matching Policy](../../2014/data-quality-services/create-a-matching-policy.md), [Data Cleansing](../../2014/data-quality-services/data-cleansing.md), or [Data Matching](../../2014/data-quality-services/data-matching.md).</span></span>  
  
  
