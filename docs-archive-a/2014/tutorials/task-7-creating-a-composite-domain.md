---
title: 'Tarefa 7: Criando um domínio composto | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: ae778647-1df0-4952-9a69-0ef6177eea9c
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 42936d25e267bcad5ba8ae512750f9e12f041579
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568935"
---
# <a name="task-7-creating-a-composite-domain"></a><span data-ttu-id="eb43a-102">Tarefa 7: Criando uma regra de domínio composto</span><span class="sxs-lookup"><span data-stu-id="eb43a-102">Task 7: Creating a Composite Domain</span></span>
  <span data-ttu-id="eb43a-103">Nesta tarefa, você cria um domínio composto, uma **validação de endereço**, que abrange os domínios de **linha de endereço**, **cidade**, **estado**e **zip** .</span><span class="sxs-lookup"><span data-stu-id="eb43a-103">In this task, you create a composite domain, **Address Validation**, which comprises **Address Line**, **City**, **State**, and **Zip** domains.</span></span> <span data-ttu-id="eb43a-104">Um domínio composto permite definir uma regra entre domínios que envolve vários domínios em uma regra.</span><span class="sxs-lookup"><span data-stu-id="eb43a-104">A composite domain lets you define a cross-domain rule that involves multiple domains in a rule.</span></span> <span data-ttu-id="eb43a-105">Há outras vantagens para um domínio composto, como analisar um valor de campo em vários domínios.</span><span class="sxs-lookup"><span data-stu-id="eb43a-105">There are other advantages to a composite domain such as being able to parse a field value into multiple domains.</span></span>  <span data-ttu-id="eb43a-106">Por exemplo, um valor para um campo Nome Completo pode ser analisado em domínios separados de Nome, Nome do Meio e Sobrenome.</span><span class="sxs-lookup"><span data-stu-id="eb43a-106">For example, a value for a Full Name field can be parsed into separate First Name, Middle Name, and Last Name domains.</span></span> <span data-ttu-id="eb43a-107">Neste tutorial, você define apenas uma regra entre domínios.</span><span class="sxs-lookup"><span data-stu-id="eb43a-107">In this tutorial, you only define a cross-domain rule.</span></span> <span data-ttu-id="eb43a-108">Consulte [Gerenciando um domínio de composição](https://msdn.microsoft.com/library/hh510399.aspx) para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="eb43a-108">See [Managing a Composite Domain](https://msdn.microsoft.com/library/hh510399.aspx) for more details.</span></span>  
  
1.  <span data-ttu-id="eb43a-109">No painel esquerdo, clique no botão **criar um domínio composto** na barra de ferramentas.</span><span class="sxs-lookup"><span data-stu-id="eb43a-109">In the left pane, click **Create a composite domain** button on the toolbar.</span></span>  
  
     <span data-ttu-id="eb43a-110">![Botão de barra de ferramentas Criar um Domínio Composto](../../2014/tutorials/media/et-creatingacompositedomain-01.jpg "Botão de barra de ferramentas Criar um Domínio Composto")</span><span class="sxs-lookup"><span data-stu-id="eb43a-110">![Create a Composite Domain Toolbar Button](../../2014/tutorials/media/et-creatingacompositedomain-01.jpg "Create a Composite Domain Toolbar Button")</span></span>  
  
2.  <span data-ttu-id="eb43a-111">Insira a **validação de endereço** para o nome de **domínio composto**.</span><span class="sxs-lookup"><span data-stu-id="eb43a-111">Enter **Address Validation** for the **Composite Domain Name**.</span></span>  
  
     <span data-ttu-id="eb43a-112">![Domínio Composto de Validação de Endereço](../../2014/tutorials/media/et-creatingacompositedomain-02.jpg "Domínio Composto de Validação de Endereço")</span><span class="sxs-lookup"><span data-stu-id="eb43a-112">![Address Validation Composite Domain](../../2014/tutorials/media/et-creatingacompositedomain-02.jpg "Address Validation Composite Domain")</span></span>  
  
3.  <span data-ttu-id="eb43a-113">Na lista de domínios, **selecione linha de endereço**, **cidade**, **estado**e **CEP** e clique na seta para a **direita** para adicioná-los aos **domínios na lista domínio composto** .</span><span class="sxs-lookup"><span data-stu-id="eb43a-113">From the domain list select **Address Line**, **City**, **State**, and **Zip** and click **right arrow** to add them to the **Domains in Composite Domain** list.</span></span>  
  
4.  <span data-ttu-id="eb43a-114">Clique em **OK** para fechar a caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="eb43a-114">Click **OK** to close the dialog box.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="eb43a-115">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="eb43a-115">Next Step</span></span>  
 [<span data-ttu-id="eb43a-116">Tarefa 8: Criando uma regra de domínio composto</span><span class="sxs-lookup"><span data-stu-id="eb43a-116">Task 8: Creating a Composite Domain Rule</span></span>](../../2014/tutorials/task-8-creating-a-composite-domain-rule.md)  
  
  
