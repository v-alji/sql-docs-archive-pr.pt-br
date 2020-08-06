---
title: 'Lição 3: Validando a assinatura e medindo a latência | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- replication [SQL Server], tutorials
ms.assetid: 147f7b93-1804-4e0b-9e17-57a51d035b2a
author: rothja
ms.author: jroth
ms.openlocfilehash: e4893c054d25d131eb2f88f32291606b0b789af7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684652"
---
# <a name="lesson-3-validating-the-subscription-and-measuring-latency"></a><span data-ttu-id="a69dd-102">Lição 3: Validando a assinatura e medindo a latência</span><span class="sxs-lookup"><span data-stu-id="a69dd-102">Lesson 3: Validating the Subscription and Measuring Latency</span></span>
  <span data-ttu-id="a69dd-103">Nesta lição, você usará tokens de rastreadores para verificar se as alterações estão sendo replicadas para o Assinante e para determinar: a latência, o tempo decorrido entre o momento em que a alteração é feita no Publicador, e o momento em que ela aparece no Assinante.</span><span class="sxs-lookup"><span data-stu-id="a69dd-103">In this lesson, you will use tracer tokens to verify that changes are being replicated to the Subscriber and to determine latency, the time it takes for a change made at the Publisher to appear to the Subscriber.</span></span> <span data-ttu-id="a69dd-104">Esta lição exige que você tenha concluído a lição anterior, [Lição 2: Criando uma assinatura na publicação transacional](lesson-2-creating-a-subscription-to-the-transactional-publication.md).</span><span class="sxs-lookup"><span data-stu-id="a69dd-104">This lesson requires that you have completed the previous lesson, [Lesson 2: Creating a Subscription to the Transactional Publication](lesson-2-creating-a-subscription-to-the-transactional-publication.md).</span></span>  
  
### <a name="to-insert-a-tracer-token-and-view-information-on-the-token"></a><span data-ttu-id="a69dd-105">Para inserir um token de rastreamento e exibir informações sobre o token</span><span class="sxs-lookup"><span data-stu-id="a69dd-105">To insert a tracer token and view information on the token</span></span>  
  
1.  <span data-ttu-id="a69dd-106">Conecte-se ao Publicador no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expanda o nó de servidor, clique com o botão direito do mouse na pasta **Replicação** e clique em **Iniciar o Replication Monitor**.</span><span class="sxs-lookup"><span data-stu-id="a69dd-106">Connect to the Publisher in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expand the server node, right-click the **Replication** folder, and then click **Launch Replication Monitor**.</span></span>  
  
     <span data-ttu-id="a69dd-107">O Replication Monitor é iniciado.</span><span class="sxs-lookup"><span data-stu-id="a69dd-107">Replication Monitor launches.</span></span>  
  
2.  <span data-ttu-id="a69dd-108">Expanda um grupo Publicador no painel esquerdo; expanda a instância do Publicador e, depois, clique na publicação **AdvWorksProductTrans** .</span><span class="sxs-lookup"><span data-stu-id="a69dd-108">Expand a Publisher group in the left pane, expand the Publisher instance, and then click the **AdvWorksProductTrans** publication.</span></span>  
  
3.  <span data-ttu-id="a69dd-109">Clique na guia **Tokens de Rastreamento** .</span><span class="sxs-lookup"><span data-stu-id="a69dd-109">Click the **Tracer Tokens** tab.</span></span>  
  
4.  <span data-ttu-id="a69dd-110">Clique em **Inserir Rastreador**.</span><span class="sxs-lookup"><span data-stu-id="a69dd-110">Click **Insert Tracer**.</span></span>  
  
5.  <span data-ttu-id="a69dd-111">Exiba o tempo decorrido para o token de rastreamento nas seguintes colunas: **Publicador para Distribuidor**, **Distribuidor para Assinante**, **Latência Total**.</span><span class="sxs-lookup"><span data-stu-id="a69dd-111">View elapsed time for the tracer token in the following columns: **Publisher to Distributor**, **Distributor to Subscriber**, **Total Latency**.</span></span> <span data-ttu-id="a69dd-112">Um valor **pendente** indica que o token não atingiu um determinado ponto.</span><span class="sxs-lookup"><span data-stu-id="a69dd-112">A value of **Pending** indicates that the token has not reached a given point.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="a69dd-113">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="a69dd-113">Next Steps</span></span>  
 <span data-ttu-id="a69dd-114">Nessa lição, você usou tokens de rastreador com êxito, para validar que as alterações de dados sejam replicadas do Publicador para o Assinante.</span><span class="sxs-lookup"><span data-stu-id="a69dd-114">In this lesson, you successfully used tracer tokens to validate that data changes are being replicated from the Publisher to the Subscriber.</span></span> <span data-ttu-id="a69dd-115">É igualmente possível inserir, atualizar ou excluir dados da tabela **Product** do Publicador e consultar a tabela **Product** do Assinante para exibir essas alterações após serem replicadas.</span><span class="sxs-lookup"><span data-stu-id="a69dd-115">You can also insert, update, or delete data in the **Product** table at the Publisher and query the **Product** table at the Subscriber to view these changes after they are replicated.</span></span>  
  
 <span data-ttu-id="a69dd-116">Isso encerra o tutorial Replicando Dados entre Servidores Conectados Continuamente</span><span class="sxs-lookup"><span data-stu-id="a69dd-116">This completes the Replicating Data Between Continuously Connected Servers tutorial.</span></span> <span data-ttu-id="a69dd-117">Para obter um tutorial semelhante, que utilize replicação de mesclagem, consulte [Tutorial: Replicating Data with Mobile Clients](tutorial-replicating-data-with-mobile-clients.md).</span><span class="sxs-lookup"><span data-stu-id="a69dd-117">For a similar tutorial that uses merge replication, see [Tutorial: Replicating Data with Mobile Clients](tutorial-replicating-data-with-mobile-clients.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a69dd-118">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a69dd-118">See Also</span></span>  
 [<span data-ttu-id="a69dd-119">Medir a latência e validar conexões para replicação transacional</span><span class="sxs-lookup"><span data-stu-id="a69dd-119">Measure Latency and Validate Connections for Transactional Replication</span></span>](monitor/measure-latency-and-validate-connections-for-transactional-replication.md)  
  
  
