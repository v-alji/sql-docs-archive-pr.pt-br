---
title: Exportar uma base de dados de conhecimento para um arquivo .dqs | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: a324ead5-c8aa-4e26-abe3-ef415add00f8
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 81dfc8e7f20fae9dacd521595d101be3117a6794
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570853"
---
# <a name="export-a-knowledge-base-to-a-dqs-file"></a><span data-ttu-id="87ea0-102">Exportar uma base de dados de conhecimento para um arquivo .dqs</span><span class="sxs-lookup"><span data-stu-id="87ea0-102">Export a Knowledge Base to a .dqs File</span></span>
  <span data-ttu-id="87ea0-103">Este tópico descreve como exportar uma base de dados de conhecimento inteira para um arquivo de dados .dqs no [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS).</span><span class="sxs-lookup"><span data-stu-id="87ea0-103">This topic describes how to export an entire knowledge base to a .dqs data file in [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS).</span></span> <span data-ttu-id="87ea0-104">Você pode exportar um domínio ou uma base de dados de conhecimento inteira para um arquivo de dados.</span><span class="sxs-lookup"><span data-stu-id="87ea0-104">You can export a domain or an entire knowledge base to a data file.</span></span> <span data-ttu-id="87ea0-105">Para obter informações sobre como exportar um domínio, consulte [Exportar um domínio para um arquivo .dqs](../../2014/data-quality-services/export-a-domain-to-a-dqs-file.md).</span><span class="sxs-lookup"><span data-stu-id="87ea0-105">For information about exporting a domain, see [Export a Domain to a .dqs File](../../2014/data-quality-services/export-a-domain-to-a-dqs-file.md).</span></span>  
  
 <span data-ttu-id="87ea0-106">A exportação de uma base de dados de conhecimento para um arquivo .dqs e sua subsequente importação como outra base de dados de conhecimento simplifica o processo de geração de conhecimento, economizando tempo e esforço.</span><span class="sxs-lookup"><span data-stu-id="87ea0-106">Exporting a knowledge base to a .dqs file, and then importing it as another knowledge base simplifies the knowledge generation process, saving time and effort.</span></span> <span data-ttu-id="87ea0-107">Isso permite que você compartilhe uma base de dados de conhecimento e seu conhecimento com outras pessoas.</span><span class="sxs-lookup"><span data-stu-id="87ea0-107">It enables you to share a knowledge base and its knowledge with others.</span></span> <span data-ttu-id="87ea0-108">O arquivo .dqs conterá todas as informações da base de dados de conhecimento, inclusive domínios e a política de correspondência, exceto as informações de dados de referência anexadas.</span><span class="sxs-lookup"><span data-stu-id="87ea0-108">The .dqs file will contain all knowledge base information, including domains and the matching policy, except for the attached reference data information.</span></span> <span data-ttu-id="87ea0-109">Você deve anexar novamente os domínios requeridos aos serviços de dados de referência, se necessário, depois de importar o arquivo .dqs.</span><span class="sxs-lookup"><span data-stu-id="87ea0-109">You must attach the required domains to appropriate reference data services again, if required, after importing the .dqs file.</span></span> <span data-ttu-id="87ea0-110">Os dados publicados e não publicados em uma base de dados de conhecimento são exportados.</span><span class="sxs-lookup"><span data-stu-id="87ea0-110">Both published and unpublished data in a knowledge base is exported.</span></span>  
  
 <span data-ttu-id="87ea0-111">O arquivo de dados .dqs criado pelo processo de exportação é criptografado; portanto, o conteúdo não pode ser exibido.</span><span class="sxs-lookup"><span data-stu-id="87ea0-111">The .dqs data file created by the export process is encrypted, so the contents cannot be viewed.</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="87ea0-112">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="87ea0-112">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="87ea0-113">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="87ea0-113">Prerequisites</span></span>  
 <span data-ttu-id="87ea0-114">Para exportar uma base de dados de conhecimento para um arquivo de dados .dqs, você precisa ter criado e aberto uma base de dados de conhecimento.</span><span class="sxs-lookup"><span data-stu-id="87ea0-114">To export a knowledge base to a .dqs data file, you must have created and opened a knowledge base.</span></span> <span data-ttu-id="87ea0-115">Você não precisa ter um arquivo .dqs para exportação; um arquivo será criado para você.</span><span class="sxs-lookup"><span data-stu-id="87ea0-115">You do not need to have a .dqs file to export into; one will be created for you.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="87ea0-116">Segurança</span><span class="sxs-lookup"><span data-stu-id="87ea0-116">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="87ea0-117">Permissões</span><span class="sxs-lookup"><span data-stu-id="87ea0-117">Permissions</span></span>  
 <span data-ttu-id="87ea0-118">Você deve ter a função dqs_kb_editor ou dqs_administrator no banco de dados DQS_MAIN para exportar uma base de dados de conhecimento para um arquivo de dados .dqs.</span><span class="sxs-lookup"><span data-stu-id="87ea0-118">You must have the dqs_kb_editor or the dqs_administrator role on the DQS_MAIN database to export a knowledge base to a .dqs data file.</span></span>  
  
##  <a name="export-a-knowledge-base-to-a-dqs-file"></a><a name="Export"></a><span data-ttu-id="87ea0-119">Exportar uma base de dados de conhecimento para um arquivo. DQS</span><span class="sxs-lookup"><span data-stu-id="87ea0-119">Export a knowledge base to a .dqs file</span></span>  
  
1.  [!INCLUDE[ssDQSInitialStep](../includes/ssdqsinitialstep-md.md)]<span data-ttu-id="87ea0-120">[Execute o aplicativo Data Quality Client](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span><span class="sxs-lookup"><span data-stu-id="87ea0-120">[Run the Data Quality Client Application](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span></span>  
  
2.  <span data-ttu-id="87ea0-121">Na tela inicial do [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] , abra uma base de dados de conhecimento na atividade Gerenciamento de Domínio.</span><span class="sxs-lookup"><span data-stu-id="87ea0-121">In the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] home screen, open a knowledge base in the Domain Management activity.</span></span>  
  
3.  <span data-ttu-id="87ea0-122">Na página Gerenciamento de Domínio (com qualquer guia selecionada), clique no ícone **Exportar dados da Base de Dados de Conhecimento** , acima da lista de domínios, e clique em **Exportar Base de Dados de Conhecimento**.</span><span class="sxs-lookup"><span data-stu-id="87ea0-122">In the Domain Management page (with any tab selected), click the **Export Knowledge Base data** icon above the Domain list, and then click **Export Knowledge Base**.</span></span> <span data-ttu-id="87ea0-123">Outra alternativa é clicar com o botão direito do mouse na lista de **domínios** , passar o mouse sobre **Exportar**e clicar em **Exportar Base de Dados de Conhecimento**.</span><span class="sxs-lookup"><span data-stu-id="87ea0-123">Alternatively, you can also right-click in the **Domain** list, hover over **Export**, and then click **Export Knowledge Base**.</span></span>  
  
4.  <span data-ttu-id="87ea0-124">Na caixa de diálogo **Exportar para Arquivo de Dados**, vá para a pasta na qual você deseja salvar o arquivo, nomeie o arquivo ou mantenha o nome da base de dados de conhecimento, mantenha **Arquivos de Dados do DQS (\*.dqs)** como o tipo **Salvar como** e, em seguida, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="87ea0-124">In the **Export to Data File** dialog box, move to the folder that you want to save the file in, name the file or keep the knowledge base name, keep **DQS Data Files (\*.dqs)** as the **Save as** type, and then click **Save**.</span></span>  
  
5.  <span data-ttu-id="87ea0-125">Na caixa de diálogo **Exportar Base de Dados de Conhecimento** , verifica se a linha de status indica que a exportação foi concluída.</span><span class="sxs-lookup"><span data-stu-id="87ea0-125">In the **Export Knowledge Base** dialog box, verify that the status line indicates that the export completed.</span></span> <span data-ttu-id="87ea0-126">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="87ea0-126">Click **OK**.</span></span>  
  
##  <a name="follow-up-after-exporting-a-domain-to-a-dqs-file"></a><a name="FollowUp"></a> <span data-ttu-id="87ea0-127">Acompanhamento: após exportar um domínio para um arquivo .dqs</span><span class="sxs-lookup"><span data-stu-id="87ea0-127">Follow Up: After Exporting a Domain to a .dqs File</span></span>  
 <span data-ttu-id="87ea0-128">Após exportar uma base de dados de conhecimento para um arquivo .dqs, você poderá importar a base de dados de conhecimento para o mesmo [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] (com um novo nome) ou para outro [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)].</span><span class="sxs-lookup"><span data-stu-id="87ea0-128">After you export a knowledge base to a .dqs file, you can import the knowledge base into the same [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] (with a new name) or into a different [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)].</span></span>  
  
  
