---
title: Usar relações de valor em um domínio de composição | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
f1_keywords:
- sql12.dqs.dm.cdvaluerelations.f1
ms.assetid: 5ee468f0-8538-4620-90e8-63f466c9000e
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 135934ec99fed612609e5e1b962f08bb93b98ede
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685939"
---
# <a name="use-value-relations-in-a-composite-domain"></a><span data-ttu-id="33386-102">Usar relações de valor em um domínio composto</span><span class="sxs-lookup"><span data-stu-id="33386-102">Use Value Relations in a Composite Domain</span></span>
  <span data-ttu-id="33386-103">Este tópico descreve como exibir combinações de valores encontradas para o domínio composto durante o processo de descoberta de conhecimento no [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS).</span><span class="sxs-lookup"><span data-stu-id="33386-103">This topic describes how to view value combinations found for the composite domain during the knowledge discovery process in [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS).</span></span> <span data-ttu-id="33386-104">Esta página mostra o número de ocorrências das combinações de valores.</span><span class="sxs-lookup"><span data-stu-id="33386-104">This page shows the number of occurrences of the value combinations.</span></span> <span data-ttu-id="33386-105">O gerenciamento de valores não tem suporte para domínios compostos; portanto, você não pode executar operações nesses valores.</span><span class="sxs-lookup"><span data-stu-id="33386-105">Value management is not supported for composite domains, so you cannot perform any operations on these values.</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="33386-106">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="33386-106">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="33386-107">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="33386-107">Prerequisites</span></span>  
 <span data-ttu-id="33386-108">Para exibir relações de valor, é preciso criar e abrir um domínio composto.</span><span class="sxs-lookup"><span data-stu-id="33386-108">To view value relations, you must have created and opened a composite domain.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="33386-109">Segurança</span><span class="sxs-lookup"><span data-stu-id="33386-109">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="33386-110">Permissões</span><span class="sxs-lookup"><span data-stu-id="33386-110">Permissions</span></span>  
 <span data-ttu-id="33386-111">Você deve ter a função dqs_kb_editor ou dqs_administrator no banco de dados DQS_MAIN para exibir relações de valor em um domínio composto.</span><span class="sxs-lookup"><span data-stu-id="33386-111">You must have the dqs_kb_editor or the dqs_administrator role on the DQS_MAIN database to view value relations in a composite domain.</span></span>  
  
##  <a name="view-value-relations"></a><a name="Use"></a><span data-ttu-id="33386-112">Exibir relações de valor</span><span class="sxs-lookup"><span data-stu-id="33386-112">View Value Relations</span></span>  
  
1.  [!INCLUDE[ssDQSInitialStep](../includes/ssdqsinitialstep-md.md)]<span data-ttu-id="33386-113">[Execute o aplicativo Data Quality Client](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span><span class="sxs-lookup"><span data-stu-id="33386-113">[Run the Data Quality Client Application](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span></span>  
  
2.  <span data-ttu-id="33386-114">Na tela inicial do [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] , abra ou crie uma base de dados de conhecimento.</span><span class="sxs-lookup"><span data-stu-id="33386-114">In the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] home screen, open or create a knowledge base.</span></span> <span data-ttu-id="33386-115">Selecione **Gerenciamento de Domínio** como a atividade e, depois, clique em **Abrir** ou **Criar**.</span><span class="sxs-lookup"><span data-stu-id="33386-115">Select **Domain Management** as the activity, and then click **Open** or **Create**.</span></span> <span data-ttu-id="33386-116">Para obter mais informações, consulte [Criar uma base de dados de conhecimento](../../2014/data-quality-services/create-a-knowledge-base.md) ou [Abrir uma base de dados de conhecimento](../../2014/data-quality-services/open-a-knowledge-base.md).</span><span class="sxs-lookup"><span data-stu-id="33386-116">For more information, see [Create a Knowledge Base](../../2014/data-quality-services/create-a-knowledge-base.md) or [Open a Knowledge Base](../../2014/data-quality-services/open-a-knowledge-base.md).</span></span>  
  
3.  <span data-ttu-id="33386-117">Na **Lista de domínios** na página **Gerenciamento de Domínio** , selecione o domínio composto para o qual você deseja criar uma regra de domínio ou crie um novo domínio composto.</span><span class="sxs-lookup"><span data-stu-id="33386-117">From the **Domain list** on the **Domain Management** page, select the composite domain that you want to create a domain rule for, or create a new composite domain.</span></span> <span data-ttu-id="33386-118">Se você precisar criar um novo domínio, consulte [Create a Composite Domain](../../2014/data-quality-services/create-a-composite-domain.md).</span><span class="sxs-lookup"><span data-stu-id="33386-118">If you have to create a new domain, see [Create a Composite Domain](../../2014/data-quality-services/create-a-composite-domain.md).</span></span>  
  
4.  <span data-ttu-id="33386-119">Clique na guia **Relações de Valor** .</span><span class="sxs-lookup"><span data-stu-id="33386-119">Click the **Value Relations** tab.</span></span>  
  
5.  <span data-ttu-id="33386-120">Exiba as frequências exibidas para cada combinação de valor.</span><span class="sxs-lookup"><span data-stu-id="33386-120">View the frequencies displayed for each value combination.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="33386-121">A tabela **Value** mostra cada combinação de valores que existe no domínio composto.</span><span class="sxs-lookup"><span data-stu-id="33386-121">The **Value** table shows each combination of values that exists in the composite domain.</span></span> <span data-ttu-id="33386-122">Cada valor é mostrado no único domínio ao qual ele se aplica.</span><span class="sxs-lookup"><span data-stu-id="33386-122">Each value is shown in the single domain that it applies to.</span></span> <span data-ttu-id="33386-123">A classificação padrão da tabela de relações de valor é por frequência, mas você pode clicar em outra coluna para classificar por essa coluna.</span><span class="sxs-lookup"><span data-stu-id="33386-123">The default sorting of the value relations table is by frequency, but you can click on another column to sort by that column.</span></span> <span data-ttu-id="33386-124">Somente esses valores com uma frequência maior que ou igual a 20 são exibidos.</span><span class="sxs-lookup"><span data-stu-id="33386-124">Only those values with a frequency greater than or equal to 20 are displayed.</span></span>  
  
6.  <span data-ttu-id="33386-125">Você não pode alterar os valores na tabela.</span><span class="sxs-lookup"><span data-stu-id="33386-125">You cannot change any of the values in the table.</span></span> <span data-ttu-id="33386-126">Se você executou outras operações, clique em **Concluir** para concluir a atividade de gerenciamento de domínio.</span><span class="sxs-lookup"><span data-stu-id="33386-126">If you have performed other operations, click **Finish** to complete the domain management activity.</span></span> <span data-ttu-id="33386-127">Caso contrário, clique em **Cancelar**.</span><span class="sxs-lookup"><span data-stu-id="33386-127">Otherwise, click **Cancel**.</span></span>  
  
##  <a name="follow-up-after-viewing-value-relations"></a><a name="FollowUp"></a><span data-ttu-id="33386-128">Acompanhamento: depois de exibir relações de valor</span><span class="sxs-lookup"><span data-stu-id="33386-128">Follow Up: After Viewing Value Relations</span></span>  
 <span data-ttu-id="33386-129">Depois de exibir relações de valor, você poderá executar outras tarefas de gerenciamento de domínio, executar a descoberta da base de dados de conhecimento para adicionar conhecimento ao domínio ou adicionar uma política de correspondência ao domínio.</span><span class="sxs-lookup"><span data-stu-id="33386-129">After you view value relations, you can perform other domain management tasks on the domain, you can perform knowledge discovery to add knowledge to the domain, or you can add a matching policy to the domain.</span></span> <span data-ttu-id="33386-130">Para obter mais informações, consulte [Executar a descoberta de conhecimento](../../2014/data-quality-services/perform-knowledge-discovery.md), [Gerenciando um domínio](../../2014/data-quality-services/managing-a-domain.md) ou [Criar uma política de conciliação](../../2014/data-quality-services/create-a-matching-policy.md).</span><span class="sxs-lookup"><span data-stu-id="33386-130">For more information, see [Perform Knowledge Discovery](../../2014/data-quality-services/perform-knowledge-discovery.md), [Managing a Domain](../../2014/data-quality-services/managing-a-domain.md), or [Create a Matching Policy](../../2014/data-quality-services/create-a-matching-policy.md).</span></span>  
  
  
