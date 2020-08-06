---
title: Encerrar a atividade de gerenciamento de domínio | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: ab6505ad-3090-453b-bb01-58435e7fa7c0
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: c776674a369bfae8c7da6fa0deabfbd932029570
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680638"
---
# <a name="end-the-domain-management-activity"></a><span data-ttu-id="c2ed6-102">Terminar a atividade Gerenciamento de Domínio</span><span class="sxs-lookup"><span data-stu-id="c2ed6-102">End the Domain Management Activity</span></span>
  <span data-ttu-id="c2ed6-103">Este tópico descreve como concluir, fechar ou cancelar a atividade de gerenciamento de domínio no [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS).</span><span class="sxs-lookup"><span data-stu-id="c2ed6-103">This topic describes how to complete, close, or cancel the domain management activity in [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS).</span></span> <span data-ttu-id="c2ed6-104">O gerenciamento de domínio não é executado por um assistente, portanto, os controles descritos abaixo podem ser usados de qualquer uma das páginas da atividade de gerenciamento de domínio.</span><span class="sxs-lookup"><span data-stu-id="c2ed6-104">Domain management is not performed by a wizard, so the controls described below can used from any of the pages of the domain management activity.</span></span>  
  
## <a name="end-domain-management"></a><span data-ttu-id="c2ed6-105">Gerenciamento de Domínio de Fim</span><span class="sxs-lookup"><span data-stu-id="c2ed6-105">End Domain Management</span></span>  
 <span data-ttu-id="c2ed6-106">**Concluir**</span><span class="sxs-lookup"><span data-stu-id="c2ed6-106">**Finish**</span></span>  
 <span data-ttu-id="c2ed6-107">Clique para concluir o gerenciamento de domínio.</span><span class="sxs-lookup"><span data-stu-id="c2ed6-107">Click to complete domain management.</span></span> <span data-ttu-id="c2ed6-108">Será exibido um pop-up que permite que você faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c2ed6-108">A popup will be displayed enabling you to do the following:</span></span>  
  
-   <span data-ttu-id="c2ed6-109">**Sim – Publique a base de dados de conhecimento e saia**: a base de dados de conhecimento será publicada para uso do usuário atual ou de outros usuários.</span><span class="sxs-lookup"><span data-stu-id="c2ed6-109">**Yes - Publish the knowledge base and exit**: The knowledge base will be published for the current user or others to use.</span></span> <span data-ttu-id="c2ed6-110">A base de dados de conhecimento não será bloqueada, o estado da base de dados de conhecimento (na tabela de bases de dados de conhecimento) será definido como vazio e as atividades de Gerenciamento de Domínio e Descoberta da Base de Dados de Conhecimento estarão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="c2ed6-110">The knowledge base will not be locked, the state of the knowledge base (in the knowledge base table) will be set to empty, and both the Domain Management and Knowledge Discovery activities will be available.</span></span> <span data-ttu-id="c2ed6-111">Você será retornado à tela Abrir Base de Dados de Conhecimento.</span><span class="sxs-lookup"><span data-stu-id="c2ed6-111">You will be returned to the Open Knowledge Base screen.</span></span>  
  
-   <span data-ttu-id="c2ed6-112">**Não-salve o trabalho na base de dados de conhecimento e saia**: seu trabalho será salvo, a base de dados de conhecimento permanecerá bloqueada e o estado da base de dados de conhecimento será definido como em funcionamento.</span><span class="sxs-lookup"><span data-stu-id="c2ed6-112">**No - Save the work on the knowledge base and exit**: Your work will be saved, the knowledge base will remained locked, and the state of the knowledge base will be set to In work.</span></span> <span data-ttu-id="c2ed6-113">As atividades de Gerenciamento de Domínio e Descoberta da Base de Dados de Conhecimento estarão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="c2ed6-113">Both the Domain Management and Knowledge Discovery activities will be available.</span></span> <span data-ttu-id="c2ed6-114">Você será retornado à home page.</span><span class="sxs-lookup"><span data-stu-id="c2ed6-114">You will be returned to the home page.</span></span>  
  
-   <span data-ttu-id="c2ed6-115">**Cancelar – Mantenha-se na tela atual**: o pop-up será fechado e você será retornado para a tela Gerenciamento de Domínio.</span><span class="sxs-lookup"><span data-stu-id="c2ed6-115">**Cancel - Stay on the current screen**: The popup will be closed and you will be returned to the Domain Management screen.</span></span>  
  
 <span data-ttu-id="c2ed6-116">**Cancelar**</span><span class="sxs-lookup"><span data-stu-id="c2ed6-116">**Cancel**</span></span>  
 <span data-ttu-id="c2ed6-117">Clique para encerrar a atividade de Gerenciamento de Domínio, o que resultará na perda do trabalho, e retorne à página inicial do DQS.</span><span class="sxs-lookup"><span data-stu-id="c2ed6-117">Click to terminate the Domain Management activity, losing your work, and return to the DQS home page.</span></span>  
  
 <span data-ttu-id="c2ed6-118">**Fechar**</span><span class="sxs-lookup"><span data-stu-id="c2ed6-118">**Close**</span></span>  
 <span data-ttu-id="c2ed6-119">Clique para salvar seu trabalho e retornar para a home page do DQS.</span><span class="sxs-lookup"><span data-stu-id="c2ed6-119">Click to save your work, and return to the DQS home page.</span></span> <span data-ttu-id="c2ed6-120">A base de conhecimento será bloqueada e o estado da base de conhecimento na tabela de base de conhecimento na tela **Abrir Base de Dados de Conhecimento** será **Gerenciamento de Domínio**.</span><span class="sxs-lookup"><span data-stu-id="c2ed6-120">The knowledge base will be locked, and the state of the knowledge base in the knowledge base table in the **Open Knowledge Base** screen will be **Domain Management**.</span></span> <span data-ttu-id="c2ed6-121">Depois de clicar em **Fechar**para executar a atividade de Gerenciamento de Domínio, você precisará retornar para a tela **Gerenciamento de Domínio** , clicar em **Concluir**e, em seguida, clicar em **Sim** para publicar a base de conhecimento ou em **Não** para salvar o trabalho na base de conhecimento e sair.</span><span class="sxs-lookup"><span data-stu-id="c2ed6-121">After clicking **Close**, to perform the Knowledge Discovery activity, you would have to return to the **Domain Management** screen, click **Finish**, and then click either **Yes** to publish the knowledge base or **No** to save the work on the knowledge base and exit.</span></span>  <span data-ttu-id="c2ed6-122">Para obter mais informações sobre como abrir uma base de dados de conhecimento bloqueada, consulte [Open a Knowledge Base](../../2014/data-quality-services/open-a-knowledge-base.md).</span><span class="sxs-lookup"><span data-stu-id="c2ed6-122">For more information on opening a locked knowledge base, see [Open a Knowledge Base](../../2014/data-quality-services/open-a-knowledge-base.md).</span></span>  
  
  
