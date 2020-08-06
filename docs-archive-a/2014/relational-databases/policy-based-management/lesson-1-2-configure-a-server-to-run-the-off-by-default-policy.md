---
title: Configurar um servidor para executar a política desativada por padrão | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 41c3022d-ab13-443e-ac64-ba1d64584f79
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: c0842a30b7d0bbcd1b01ee9e98ed1ed9a74f0f35
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569971"
---
# <a name="configure-a-server-to-run-the-off-by-default-policy"></a><span data-ttu-id="d17f2-102">Configurar um servidor para executar a política desativada por padrão</span><span class="sxs-lookup"><span data-stu-id="d17f2-102">Configure a Server to Run the Off By Default Policy</span></span>
  <span data-ttu-id="d17f2-103">Agora você tem uma política chamada Desativada por Padrão.</span><span class="sxs-lookup"><span data-stu-id="d17f2-103">Now you have a policy named Off By Default.</span></span> <span data-ttu-id="d17f2-104">Nesta tarefa, você verificará se o servidor está em conformidade com os requisitos dessa política.</span><span class="sxs-lookup"><span data-stu-id="d17f2-104">In this task, you will check to see whether your server complies with the requirements of this policy.</span></span>  
  
### <a name="to-run-the-off-by-default-policy"></a><span data-ttu-id="d17f2-105">Para executar a política Desativada por Padrão</span><span class="sxs-lookup"><span data-stu-id="d17f2-105">To run the Off By Default policy</span></span>  
  
1.  <span data-ttu-id="d17f2-106">No Pesquisador de Objetos, clique com o botão direito do mouse na instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], aponte para **Políticas**e clique em **Avaliar**.</span><span class="sxs-lookup"><span data-stu-id="d17f2-106">In Object Explorer, right-click your instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], point to **Policies**, and then click **Evaluate**.</span></span>  
  
2.  <span data-ttu-id="d17f2-107">Na caixa de diálogo **Avaliar Políticas** , você pode selecionar as políticas de outra instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ou de um arquivo.</span><span class="sxs-lookup"><span data-stu-id="d17f2-107">In the **Evaluate Policies** dialog box you can select policies from another instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or from a file.</span></span> <span data-ttu-id="d17f2-108">Nesta etapa, deixe **Fonte** definida para a sua instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d17f2-108">For this step, leave **Source** set to your instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
3.  <span data-ttu-id="d17f2-109">Na seção **Políticas** , selecione a política **Desativada por Padrão** .</span><span class="sxs-lookup"><span data-stu-id="d17f2-109">In the **Policies** section, select the **Off By Default** policy.</span></span>  
  
4.  <span data-ttu-id="d17f2-110">Para ver se o servidor está em conformidade com a política, clique em **Avaliar**.</span><span class="sxs-lookup"><span data-stu-id="d17f2-110">To see whether the server is in compliance with the policy, click **Evaluate**.</span></span>  
  
5.  <span data-ttu-id="d17f2-111">Na área **Resultados** , você verá um círculo verde com uma marca de seleção se o [!INCLUDE[ssDE](../../includes/ssde-md.md)] estiver em conformidade com a política.</span><span class="sxs-lookup"><span data-stu-id="d17f2-111">In the **Results** area, you will see a green circle with a check mark if the [!INCLUDE[ssDE](../../includes/ssde-md.md)] complies with the policy.</span></span> <span data-ttu-id="d17f2-112">Você verá um círculo vermelho com um X se o [!INCLUDE[ssDE](../../includes/ssde-md.md)] não obedecer a política.</span><span class="sxs-lookup"><span data-stu-id="d17f2-112">You will see a red circle with an X if the [!INCLUDE[ssDE](../../includes/ssde-md.md)] does not comply with the policy.</span></span>  
  
6.  <span data-ttu-id="d17f2-113">Na área **Detalhes de Destino** , você verá informações adicionais na coluna **Mensagem** se ocorrer algum erro.</span><span class="sxs-lookup"><span data-stu-id="d17f2-113">In the **Target Details** area, you will see additional information in the **Message** column if an error occurs.</span></span> <span data-ttu-id="d17f2-114">Na coluna **Mensagem** , clique em **Exibir** para ver um relatório com os resultados da verificação de cada propriedade de faceta verificada.</span><span class="sxs-lookup"><span data-stu-id="d17f2-114">In the **Message** column, click **View** to see a report that contains the results of the check for each facet property that was checked.</span></span>  
  
7.  <span data-ttu-id="d17f2-115">A descrição da política é exibida na parte inferior da página, e a seção **Ajuda adicional** exibe o hiperlink configurado para a política.</span><span class="sxs-lookup"><span data-stu-id="d17f2-115">The policy description is displayed at the bottom of the page, and the **Additional help** section displays the hyperlink that you have configured for the policy.</span></span> <span data-ttu-id="d17f2-116">Clique no hiperlink da mensagem para abrir a página da Web que você especificou quando criou a política.</span><span class="sxs-lookup"><span data-stu-id="d17f2-116">Click the message hyperlink to open the Web page that you specified when you created the policy.</span></span>  
  
8.  <span data-ttu-id="d17f2-117">Feche o navegador e a caixa de diálogo **Exibição Detalhada dos Resultados** .</span><span class="sxs-lookup"><span data-stu-id="d17f2-117">Close the browser, and then close the **Results Detailed View** dialog box.</span></span>  
  
9. <span data-ttu-id="d17f2-118">Se o servidor não estiver em conformidade e você quiser desabilitar o Database Mail, clique em **Aplicar** na página **Resultados da Avaliação** .</span><span class="sxs-lookup"><span data-stu-id="d17f2-118">If the server is out of compliance and you want to disable Database Mail, click **Apply** in the **Evaluation Results** page.</span></span>  
  
10. <span data-ttu-id="d17f2-119">Feche as caixas de diálogo **Exibição Detalhada dos Resultados** e **Avaliar Políticas** .</span><span class="sxs-lookup"><span data-stu-id="d17f2-119">Close both the **Results Detailed View** and the **Evaluate Policies** dialog boxes.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="d17f2-120">Próxima lição</span><span class="sxs-lookup"><span data-stu-id="d17f2-120">Next Lesson</span></span>  
 [<span data-ttu-id="d17f2-121">Lição 2: Criar e aplicar uma política de nomeação de padrões</span><span class="sxs-lookup"><span data-stu-id="d17f2-121">Lesson 2: Create and Apply a Naming Standards Policy</span></span>](lesson-2-create-and-apply-a-naming-standards-policy.md)  
  
  
