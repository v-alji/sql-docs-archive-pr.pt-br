---
title: Criar uma base de dados de conhecimento | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
f1_keywords:
- sql12.dqs.kb.selectkb.f1
- sql12.dqs.kb.newkb.f1
ms.assetid: 2733a284-975f-4650-abcc-cc2aad074cab
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 281fa663362cc4462cd4e32839c1eaf6908394e0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570270"
---
# <a name="create-a-knowledge-base"></a><span data-ttu-id="6c4b6-102">Criar uma base de dados de conhecimento</span><span class="sxs-lookup"><span data-stu-id="6c4b6-102">Create a Knowledge Base</span></span>
  <span data-ttu-id="6c4b6-103">Este tópico descreve como criar uma base de dados de conhecimento no [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS) e prepará-la para o gerenciamento de domínio, a descoberta de conhecimento ou a adição de uma política de correspondência.</span><span class="sxs-lookup"><span data-stu-id="6c4b6-103">This topic describes how to create a knowledge base in [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS), and prepare it for domain management, knowledge discovery, or adding a matching policy.</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="6c4b6-104">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="6c4b6-104">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="6c4b6-105">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="6c4b6-105">Prerequisites</span></span>  
 <span data-ttu-id="6c4b6-106">Para criar uma base de dados de conhecimento, você deve instalar o [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] e o [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6c4b6-106">To create a knowledge base, you must have installed [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] and [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)].</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="6c4b6-107">Segurança</span><span class="sxs-lookup"><span data-stu-id="6c4b6-107">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="6c4b6-108">Permissões</span><span class="sxs-lookup"><span data-stu-id="6c4b6-108">Permissions</span></span>  
 <span data-ttu-id="6c4b6-109">Você deve ter a função dqs_kb_editor ou dqs_administrator no banco de dados DQS_MAIN para criar uma base de dados de conhecimento.</span><span class="sxs-lookup"><span data-stu-id="6c4b6-109">You must have the dqs_kb_editor or the dqs_administrator role on the DQS_MAIN database to create a knowledge base.</span></span>  
  
##  <a name="create-a-knowledge-base"></a><a name="Createaknowledgebase"></a><span data-ttu-id="6c4b6-110">Criar uma base de dados de conhecimento</span><span class="sxs-lookup"><span data-stu-id="6c4b6-110">Create a knowledge base</span></span>  
  
1.  [!INCLUDE[ssDQSInitialStep](../includes/ssdqsinitialstep-md.md)]<span data-ttu-id="6c4b6-111">[Execute o aplicativo Data Quality Client](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span><span class="sxs-lookup"><span data-stu-id="6c4b6-111">[Run the Data Quality Client Application](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span></span>  
  
2.  <span data-ttu-id="6c4b6-112">Na tela inicial do [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] , clique em **Nova base de dados de conhecimento**.</span><span class="sxs-lookup"><span data-stu-id="6c4b6-112">In the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] home screen, click **New knowledge base**.</span></span>  
  
3.  <span data-ttu-id="6c4b6-113">Digite um nome e uma descrição para a nova base de dados de conhecimento.</span><span class="sxs-lookup"><span data-stu-id="6c4b6-113">Enter a name and description for the new knowledge base.</span></span>  
  
4.  <span data-ttu-id="6c4b6-114">Em **Criar base de dados de conhecimento de**, selecione a base da nova base de dados de conhecimento.</span><span class="sxs-lookup"><span data-stu-id="6c4b6-114">In **Create knowledge base from**, select what to base the knowledge base on:</span></span>  
  
    -   <span data-ttu-id="6c4b6-115">Selecione **Nenhum** se você não quiser basear a nova base de conhecimento em uma já existente ou em um arquivo de dados.</span><span class="sxs-lookup"><span data-stu-id="6c4b6-115">Select **None** if you do not want to base the new knowledge base on an existing knowledge base or data file.</span></span>  
  
    -   <span data-ttu-id="6c4b6-116">Selecione **Base de dados de conhecimento existente** para basear a nova base de dados de conhecimento em uma já criada no [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)]ou na base de dados de conhecimento padrão.</span><span class="sxs-lookup"><span data-stu-id="6c4b6-116">Select **Existing Knowledge Base** to base the new knowledge base on a knowledge base that has already been created on [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)], or on the default knowledge base.</span></span> <span data-ttu-id="6c4b6-117">Selecione a base de dados de conhecimento na lista suspensa **Selecionar Base de Dados de Conhecimento** ou clique em **Procurar** para exibir a caixa de diálogo **Selecionar uma Base de Dados de Conhecimento** , selecione uma base de dados de conhecimento existente para basear a nova base de dados de conhecimento e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="6c4b6-117">Select the knowledge base from the **Select Knowledge Base** drop-down list, or click **Browse** to display the **Select a Knowledge Base** dialog box, select an existing knowledge base to base the new knowledge base on, and then click **OK**.</span></span> <span data-ttu-id="6c4b6-118">Quando você seleciona uma base de dados de conhecimento no tablet, os domínios e as regras de correspondência da base de dados de conhecimento são exibidos no painel à direita da caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="6c4b6-118">When you select a knowledge base from the tablet, the domains and matching rules in the knowledge base will be displayed in the right-hand pane of the dialog box.</span></span> <span data-ttu-id="6c4b6-119">Você também pode selecionar a base de dados de conhecimento **Dados do DQS** , que é a base de dados de conhecimento padrão que contém domínios e conhecimento comuns predefinidos, relacionados a dados de empresas, endereços e participantes nos EUA.</span><span class="sxs-lookup"><span data-stu-id="6c4b6-119">You can also select the **DQS Data** knowledge base, which is the default knowledge base that contains common out-of-the-box domains and knowledge related to U.S. company, address, and party data.</span></span>  
  
    -   <span data-ttu-id="6c4b6-120">Selecione **Importar do Arquivo DQS** para basear a nova base de dados de conhecimento em um arquivo DQS no [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6c4b6-120">Select **Import from DQS File** to base the new knowledge base on a DQS file on [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)].</span></span> <span data-ttu-id="6c4b6-121">Clique em **Procurar**, selecione um arquivo de dados do DQS com a extensão .dqs e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="6c4b6-121">Click **Browse**, select a DQS data file with an extension of .dqs, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="6c4b6-122">Em **Selecionar Atividade**, selecione a atividade que você deseja executar na nova base de dados de conhecimento:</span><span class="sxs-lookup"><span data-stu-id="6c4b6-122">In **Select Activity**, select the activity that you want to perform on the new knowledge base:</span></span>  
  
    -   <span data-ttu-id="6c4b6-123">Selecione **Gerenciamento de Domínio** para criar a base de dados de conhecimento e entrar nas telas que você usa para modificar os domínios na base de dados de conhecimento.</span><span class="sxs-lookup"><span data-stu-id="6c4b6-123">Select **Domain Management** to create the knowledge base and enter the screens that you use to modify the domains in the knowledge base.</span></span>  
  
    -   <span data-ttu-id="6c4b6-124">Selecione **Descoberta da Base de Dados de Conhecimento** para criar a base de dados de conhecimento e entrar no assistente que você usa para analisar um exemplo de dados e popular os domínios da base de dados de conhecimento com os resultados.</span><span class="sxs-lookup"><span data-stu-id="6c4b6-124">Select **Knowledge Discovery** to create the knowledge base and enter the wizard that you use to analyze a data sample and populate the domains of the knowledge base with the results.</span></span>  
  
    -   <span data-ttu-id="6c4b6-125">Selecione **Política de Correspondência** para criar uma política de correspondência e adicioná-la à base de dados de conhecimento.</span><span class="sxs-lookup"><span data-stu-id="6c4b6-125">Select **Matching Policy** to create a matching policy and add it to the knowledge base.</span></span>  
  
6.  <span data-ttu-id="6c4b6-126">Clique em **Criar**.</span><span class="sxs-lookup"><span data-stu-id="6c4b6-126">Click **Create**.</span></span>  
  
##  <a name="follow-up-after-creating-a-knowledge-base"></a><a name="FollowUp"></a><span data-ttu-id="6c4b6-127">Acompanhamento: depois de criar uma base de dados de conhecimento</span><span class="sxs-lookup"><span data-stu-id="6c4b6-127">Follow Up: After Creating a Knowledge Base</span></span>  
 <span data-ttu-id="6c4b6-128">Depois que você criar uma base de dados de conhecimento, verá um assistente para executar a descoberta da base de dados de conhecimento, um assistente para criar uma política de correspondência ou páginas para fazer o gerenciamento do domínio.</span><span class="sxs-lookup"><span data-stu-id="6c4b6-128">After you create a knowledge base, you are presented with a wizard that you can use to perform knowledge discovery, a wizard to create a matching policy, or pages to perform domain management.</span></span> <span data-ttu-id="6c4b6-129">Para obter mais informações sobre a descoberta de conhecimento, o gerenciamento de domínio ou a política de conciliação, consulte [Executar a descoberta de conhecimento](../../2014/data-quality-services/perform-knowledge-discovery.md), [Gerenciando um domínio](../../2014/data-quality-services/managing-a-domain.md) ou [Criar uma política de conciliação](../../2014/data-quality-services/create-a-matching-policy.md).</span><span class="sxs-lookup"><span data-stu-id="6c4b6-129">For more information about the knowledge discovery, domain management, or matching policy, see [Perform Knowledge Discovery](../../2014/data-quality-services/perform-knowledge-discovery.md), [Managing a Domain](../../2014/data-quality-services/managing-a-domain.md), or [Create a Matching Policy](../../2014/data-quality-services/create-a-matching-policy.md).</span></span>  
  
  
