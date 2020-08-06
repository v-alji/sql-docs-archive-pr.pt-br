---
title: Agendar as políticas | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
ms.assetid: 59417a54-55f1-4468-ba41-368aa852c2d4
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 1bce1b9d650606e9485899c34c72ca6b27a72dae
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683186"
---
# <a name="schedule-the-policies"></a><span data-ttu-id="d4819-102">Agendar as políticas</span><span class="sxs-lookup"><span data-stu-id="d4819-102">Schedule the Policies</span></span>
  <span data-ttu-id="d4819-103">Nesta tarefa, você agendará as políticas de práticas recomendadas que você importou na tarefa anterior.</span><span class="sxs-lookup"><span data-stu-id="d4819-103">In this task, you will schedule the best practices policies that you imported in the previous task.</span></span>  
  
### <a name="to-schedule-the-best-practices-policies"></a><span data-ttu-id="d4819-104">Para agendar as políticas de práticas recomendadas</span><span class="sxs-lookup"><span data-stu-id="d4819-104">To schedule the best practices policies</span></span>  
  
1.  <span data-ttu-id="d4819-105">No Pesquisador de objetos, expanda **Gerenciamento**, **Gerenciamento de políticas**, expanda **políticas**, clique com o botão direito do mouse em uma política de práticas recomendadas e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="d4819-105">In Object Explorer, expand **Management**, expand **Policy Management**, expand **Policies**, right-click a best practices policy, and then click **Properties**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d4819-106">Como alternativa, para ver facilmente quais políticas estão associadas às práticas recomendadas e para classificar as categorias de práticas recomendadas, expanda **Gerenciamento**, expanda **Gerenciamento de políticas**e clique em **políticas**.</span><span class="sxs-lookup"><span data-stu-id="d4819-106">As an alternative, to easily see which policies are associated with best practices and to sort the best practices categories, expand **Management**, expand **Policy Management**, and then click **Policies**.</span></span> <span data-ttu-id="d4819-107">No menu **Exibir** , clique em **Detalhes do Pesquisador de Objetos**.</span><span class="sxs-lookup"><span data-stu-id="d4819-107">On the **View** menu, click **Object Explorer Details**.</span></span> <span data-ttu-id="d4819-108">No painel **detalhes** do pesquisador de objetos, clique no título **categoria** para classificar as políticas por categoria.</span><span class="sxs-lookup"><span data-stu-id="d4819-108">In the **Object Explorer Details** pane, click the **Category** heading to sort the policies by category.</span></span> <span data-ttu-id="d4819-109">As políticas de práticas recomendadas têm o prefixo práticas **recomendadas da Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="d4819-109">The best practices policies have the prefix **Microsoft Best Practices**.</span></span> <span data-ttu-id="d4819-110">Clique com o botão direito do mouse na política que você deseja configurar e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="d4819-110">Right-click the policy that you want to configure, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="d4819-111">Na página **geral** da caixa de diálogo **abrir política** , na lista **modo de avaliação** , clique **em agendar**.</span><span class="sxs-lookup"><span data-stu-id="d4819-111">On the **General** page of the **Open Policy** dialog box, in the **Evaluation Mode** list, click **On schedule**.</span></span>  
  
3.  <span data-ttu-id="d4819-112">Ao lado da caixa **agenda** , clique em **escolher** para especificar uma agenda existente ou clique em **novo** para criar uma nova agenda.</span><span class="sxs-lookup"><span data-stu-id="d4819-112">Next to the **Schedule** box, click **Pick** to specify an existing schedule, or click **New** to create a new schedule.</span></span>  
  
4.  <span data-ttu-id="d4819-113">Depois de configurar uma agenda, você pode marcar a caixa de seleção **habilitado** na parte superior da página para habilitar a política agendada.</span><span class="sxs-lookup"><span data-stu-id="d4819-113">After you have configured a schedule, you can select the **Enabled** check box near the top of the page to enable the scheduled policy.</span></span>  
  
5.  <span data-ttu-id="d4819-114">Repita as etapas de 1 a 4 para cada política que você deseja agendar.</span><span class="sxs-lookup"><span data-stu-id="d4819-114">Repeats steps 1 through 4 for each policy that you want to schedule.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d4819-115">Para exibir os resultados da avaliação após a execução de uma diretiva agendada, abra o log Histórico da Diretiva na instância de destino.</span><span class="sxs-lookup"><span data-stu-id="d4819-115">To view the evaluation results after a scheduled policy runs, open the Policy History log on the target instance.</span></span> <span data-ttu-id="d4819-116">Para abrir o log, clique com o botão direito do mouse em **Gerenciamento de políticas**e clique em **Exibir histórico**.</span><span class="sxs-lookup"><span data-stu-id="d4819-116">To open the log, right-click **Policy Management**, and then click **View History**.</span></span>  
  
## <a name="summary"></a><span data-ttu-id="d4819-117">Resumo</span><span class="sxs-lookup"><span data-stu-id="d4819-117">Summary</span></span>  
 <span data-ttu-id="d4819-118">Você configurou políticas agendadas para serem executadas em uma única instância do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d4819-118">You configured scheduled policies to run on a single instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="d4819-119">Se você desejar implantar políticas agendadas em várias instâncias, continue na próxima tarefa deste tutorial.</span><span class="sxs-lookup"><span data-stu-id="d4819-119">If you want to deploy scheduled policies to multiple instances, continue to the next task in this tutorial.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="d4819-120">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="d4819-120">Next Steps</span></span>  
 [<span data-ttu-id="d4819-121">Implantar diretivas agendadas em várias instâncias</span><span class="sxs-lookup"><span data-stu-id="d4819-121">Deploy Scheduled Policies to Multiple Instances</span></span>](../../2014/tutorials/deploy-scheduled-policies-to-multiple-instances.md)  
  
  
