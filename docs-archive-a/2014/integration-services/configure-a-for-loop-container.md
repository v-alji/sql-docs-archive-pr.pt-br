---
title: Configurar um contêiner loop for | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- containers [Integration Services], For Loop
- For Loop containers
ms.assetid: b9cd7ea7-b198-4a35-8b16-6acf09611ca5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9cb33ea5b7f3f59baad3c94f6bc845c281613ec9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570173"
---
# <a name="configure-a-for-loop-container"></a><span data-ttu-id="2e743-102">Configurar um contêiner Loop For</span><span class="sxs-lookup"><span data-stu-id="2e743-102">Configure a For Loop Container</span></span>
  <span data-ttu-id="2e743-103">Este procedimento descreve como configurar um contêiner Loop For usando a caixa de diálogo **Editor do Loop For** .</span><span class="sxs-lookup"><span data-stu-id="2e743-103">This procedure describes how to configure a For Loop container by using the **For Loop Editor** dialog box.</span></span>  
  
### <a name="to-configure-the-for-loop-container"></a><span data-ttu-id="2e743-104">Para configurar um contêiner Loop For</span><span class="sxs-lookup"><span data-stu-id="2e743-104">To configure the For Loop container</span></span>  
  
1.  <span data-ttu-id="2e743-105">No [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], clique duas vezes em contêiner Loop For para abrir o **Editor do Loop For**.</span><span class="sxs-lookup"><span data-stu-id="2e743-105">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], double-click the For Loop container to open the **For Loop Editor**.</span></span>  
  
2.  <span data-ttu-id="2e743-106">Como alternativa, modifique o nome e a descrição do contêiner Loop For.</span><span class="sxs-lookup"><span data-stu-id="2e743-106">Optionally, modify the name and description of the For Loop container.</span></span>  
  
3.  <span data-ttu-id="2e743-107">Como alternativa, digite uma expressão de inicialização na caixa de texto **InitExpression** .</span><span class="sxs-lookup"><span data-stu-id="2e743-107">Optionally, type an initialization expression in the **InitExpression** text box.</span></span>  
  
4.  <span data-ttu-id="2e743-108">Como alternativa, digite uma expressão de inicialização na caixa de texto **EvalExpression** .</span><span class="sxs-lookup"><span data-stu-id="2e743-108">Type an evaluation expression in the **EvalExpression** text box.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="2e743-109">A expressão deve ser avaliada como um booliano.</span><span class="sxs-lookup"><span data-stu-id="2e743-109">The expression must evaluate to a Boolean.</span></span> <span data-ttu-id="2e743-110">Quando a expressão for avaliada como `false`, o loop irá parar sua execução.</span><span class="sxs-lookup"><span data-stu-id="2e743-110">When the expression evaluates to `false`, the loop stops running.</span></span>  
  
5.  <span data-ttu-id="2e743-111">Como alternativa, digite uma expressão de atribuição na caixa de texto **AssignExpression** .</span><span class="sxs-lookup"><span data-stu-id="2e743-111">Optionally, type an assignment expression in the **AssignExpression** text box.</span></span>  
  
6.  <span data-ttu-id="2e743-112">Como alternativa, clique em **Expressões** e, na página **Expressões** , crie expressões de propriedade para as propriedades do contêiner Loop For.</span><span class="sxs-lookup"><span data-stu-id="2e743-112">Optionally, click **Expressions** and, on the **Expressions** page, create property expressions for the properties of the For Loop container.</span></span> <span data-ttu-id="2e743-113">Para obter mais informações, consulte [Adicionar ou alterar uma expressão de propriedade](expressions/add-or-change-a-property-expression.md).</span><span class="sxs-lookup"><span data-stu-id="2e743-113">For more information, see [Add or Change a Property Expression](expressions/add-or-change-a-property-expression.md).</span></span>  
  
7.  <span data-ttu-id="2e743-114">Clique em **OK** para fechar o **Editor do Loop For**.</span><span class="sxs-lookup"><span data-stu-id="2e743-114">Click **OK** to close the **For Loop Editor**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e743-115">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2e743-115">See Also</span></span>  
 <span data-ttu-id="2e743-116">[Contêiner loop for](control-flow/for-loop-container.md) </span><span class="sxs-lookup"><span data-stu-id="2e743-116">[For Loop Container](control-flow/for-loop-container.md) </span></span>  
 <span data-ttu-id="2e743-117">[Integration Services &#40;expressões&#41; SSIS](expressions/integration-services-ssis-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="2e743-117">[Integration Services &#40;SSIS&#41; Expressions](expressions/integration-services-ssis-expressions.md) </span></span>  
 [<span data-ttu-id="2e743-118">Usar expressões de propriedade em pacotes</span><span class="sxs-lookup"><span data-stu-id="2e743-118">Use Property Expressions in Packages</span></span>](expressions/use-property-expressions-in-packages.md)  
  
  
