---
title: 'Tarefa 8: criando uma regra de domínio composto | Microsoft Docs'
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: cff3b662-7876-4445-9bdd-96be35b3ca0c
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 4766a1206eb09e98bb20d3712a63762126b682b7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581634"
---
# <a name="task-8-creating-a-composite-domain-rule"></a><span data-ttu-id="216c5-102">Tarefa 8: Criando uma regra de domínio composto</span><span class="sxs-lookup"><span data-stu-id="216c5-102">Task 8: Creating a Composite Domain Rule</span></span>
  <span data-ttu-id="216c5-103">Nesta tarefa, você cria uma regra para o domínio composto de **validação de endereço** .</span><span class="sxs-lookup"><span data-stu-id="216c5-103">In this task, you create a rule for the **Address Validation** composite domain.</span></span> <span data-ttu-id="216c5-104">Você define uma regra de domínio cruzado: se **City** for **los Angeles**, o **estado** deverá ser **CA** em que **City** e **State** são dois domínios.</span><span class="sxs-lookup"><span data-stu-id="216c5-104">You define a cross-domain rule: if **City** is **Los Angeles**, **State** must be **CA** where **City** and **State** are two domains.</span></span>  
  
1.  <span data-ttu-id="216c5-105">No painel direito, alterne para a guia **regras de CD** .</span><span class="sxs-lookup"><span data-stu-id="216c5-105">In the right pane, switch to the **CD Rules** tab.</span></span>  
  
2.  <span data-ttu-id="216c5-106">Clique em **Adicionar uma nova regra de domínio** na barra de ferramentas.</span><span class="sxs-lookup"><span data-stu-id="216c5-106">Click **Add a new domain rule** from the toolbar.</span></span>  
  
3.  <span data-ttu-id="216c5-107">Digite **regra de Estado cidade** para **nome** e pressione **Enter**.</span><span class="sxs-lookup"><span data-stu-id="216c5-107">Type **City-State Rule** for **Name** and press **ENTER**.</span></span>  
  
4.  <span data-ttu-id="216c5-108">No painel **criar uma regra** , selecione **cidade** na lista domínio e selecione valor da condição **é igual a** e digite **los Angeles** para o valor.</span><span class="sxs-lookup"><span data-stu-id="216c5-108">In the **Build a Rule** pane, select **City** in the domain list, and select condition **Value is equal to** and type **Los Angeles** for the value.</span></span>  
  
5.  <span data-ttu-id="216c5-109">No painel **em seguida** , selecione **estado** na lista domínio e selecione **valor é igual a**, digite **CA** para o valor e pressione **Tab**.</span><span class="sxs-lookup"><span data-stu-id="216c5-109">In the **Then** pane, select **State** in the domain list, and select **Value is equal to**, type **CA** for the value, and press **TAB**.</span></span>  
  
     <span data-ttu-id="216c5-110">![Regra Domínio Composto](../../2014/tutorials/media/et-creatingacompositedomainrule.jpg "Regra Domínio Composto")</span><span class="sxs-lookup"><span data-stu-id="216c5-110">![Composite Domain Rule](../../2014/tutorials/media/et-creatingacompositedomainrule.jpg "Composite Domain Rule")</span></span>  
  
6.  <span data-ttu-id="216c5-111">Clique no botão **fechar** na parte inferior da página para alternar para a página principal do cliente do DQS.</span><span class="sxs-lookup"><span data-stu-id="216c5-111">Click **Close** button at the bottom of the page to switch to the main page of DQS Client.</span></span> <span data-ttu-id="216c5-112">Você publicará a base de dados de conhecimento na próxima lição.</span><span class="sxs-lookup"><span data-stu-id="216c5-112">You will publish the knowledge base in the next lesson.</span></span> <span data-ttu-id="216c5-113">Observe que a base de dados de conhecimento está no estado bloqueado (ícone de bloqueio).</span><span class="sxs-lookup"><span data-stu-id="216c5-113">Notice that the knowledge base is in locked state (lock icon).</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="216c5-114">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="216c5-114">Next Step</span></span>  
 [<span data-ttu-id="216c5-115">Tarefa 9: Configurando um serviço de dados de referência</span><span class="sxs-lookup"><span data-stu-id="216c5-115">Task 9: Configuring a Reference Data Service</span></span>](../../2014/tutorials/task-9-configuring-a-reference-data-service.md)  
  
  
