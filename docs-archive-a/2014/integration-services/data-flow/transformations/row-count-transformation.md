---
title: Transformação Contagem de Linhas | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.rowcounttrans.f1
helpviewer_keywords:
- updating variables
- Row Count transformation
- number of rows
- variables [Integration Services], updating
- counting rows
ms.assetid: b68293b9-a68c-40be-9d81-77342da1be29
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1b0940d608aeaa96b7ec43fa4486944ce0f887e3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87686352"
---
# <a name="row-count-transformation"></a><span data-ttu-id="369bf-102">Transformação Contagem de Linhas</span><span class="sxs-lookup"><span data-stu-id="369bf-102">Row Count Transformation</span></span>
  <span data-ttu-id="369bf-103">A transformação Contagem de Linhas conta as linhas quando passam por um fluxo de dados e armazena a contagem final em uma variável.</span><span class="sxs-lookup"><span data-stu-id="369bf-103">The Row Count transformation counts rows as they pass through a data flow and stores the final count in a variable.</span></span>  
  
 <span data-ttu-id="369bf-104">O pacote [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] pode usar contagens de linhas para atualizar as variáveis usadas em scripts, expressões e expressões de propriedade.</span><span class="sxs-lookup"><span data-stu-id="369bf-104">A [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] package can use row counts to update the variables used in scripts, expressions, and property expressions.</span></span> <span data-ttu-id="369bf-105">Por exemplo, a variável que armazena a contagem de linhas pode atualizar o texto de mensagem em uma mensagem de email para incluir o número de linhas. A variável que a transformação Contagem de Linhas usa já deve existir e deve estar no escopo da tarefa de Fluxo de Dados ao qual esse fluxo com a transformação Contagem de Linhas pertence.</span><span class="sxs-lookup"><span data-stu-id="369bf-105">(For example, the variable that stores the row count can update the message text in an e-mail message to include the number of rows.) The variable that the Row Count transformation uses must already exist, and it must be in the scope of the Data Flow task to which the data flow with the Row Count transformation belongs.</span></span>  
  
 <span data-ttu-id="369bf-106">A transformação só armazena o valor da contagem de linhas na variável após a última linha ter passado pela transformação.</span><span class="sxs-lookup"><span data-stu-id="369bf-106">The transformation stores the row count value in the variable only after the last row has passed through the transformation.</span></span> <span data-ttu-id="369bf-107">Portanto, o valor da variável não é atualizado a tempo de usar o valor atualizado no fluxo de dados que contém a transformação Contagem de Linhas.</span><span class="sxs-lookup"><span data-stu-id="369bf-107">Therefore, the value of the variable is not updated in time to use the updated value in the data flow that contains the Row Count transformation.</span></span> <span data-ttu-id="369bf-108">Você pode usar a variável atualizada em um fluxo de dados separado.</span><span class="sxs-lookup"><span data-stu-id="369bf-108">You can use the updated variable in a separate data flow.</span></span>  
  
 <span data-ttu-id="369bf-109">Essa transformação tem uma entrada e uma saída.</span><span class="sxs-lookup"><span data-stu-id="369bf-109">This transformation has one input and one output.</span></span> <span data-ttu-id="369bf-110">Não dá suporte a uma saída de erro.</span><span class="sxs-lookup"><span data-stu-id="369bf-110">It does not support an error output.</span></span>  
  
## <a name="configuration-of-the-row-count-transformation"></a><span data-ttu-id="369bf-111">Configuração da transformação Contagem de Linhas</span><span class="sxs-lookup"><span data-stu-id="369bf-111">Configuration of the Row Count Transformation</span></span>  
 <span data-ttu-id="369bf-112">Você pode definir propriedades pelo Designer do [!INCLUDE[ssIS](../../../includes/ssis-md.md)] ou programaticamente.</span><span class="sxs-lookup"><span data-stu-id="369bf-112">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="369bf-113">A caixa de diálogo **Editor Avançado** reflete as propriedades que podem ser definidas programaticamente.</span><span class="sxs-lookup"><span data-stu-id="369bf-113">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="369bf-114">Para obter mais informações sobre as propriedades que podem ser definidas na caixa de diálogo **Editor Avançado** ou programaticamente, clique em um dos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="369bf-114">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="369bf-115">Propriedades comuns</span><span class="sxs-lookup"><span data-stu-id="369bf-115">Common Properties</span></span>](../../common-properties.md)  
  
-   [<span data-ttu-id="369bf-116">Propriedades personalizadas de Transformação</span><span class="sxs-lookup"><span data-stu-id="369bf-116">Transformation Custom Properties</span></span>](transformation-custom-properties.md)  
  
## <a name="related-tasks"></a><span data-ttu-id="369bf-117">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="369bf-117">Related Tasks</span></span>  
 <span data-ttu-id="369bf-118">Para obter informações sobre como definir as propriedades desse componente, consulte [Definir as propriedades de um componente de fluxo de dados](../set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="369bf-118">For information about how to set the properties of this component, see [Set the Properties of a Data Flow Component](../set-the-properties-of-a-data-flow-component.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="369bf-119">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="369bf-119">See Also</span></span>  
 <span data-ttu-id="369bf-120">[Variáveis do SSIS &#40;Integration Services&#41;](../../integration-services-ssis-variables.md) </span><span class="sxs-lookup"><span data-stu-id="369bf-120">[Integration Services &#40;SSIS&#41; Variables](../../integration-services-ssis-variables.md) </span></span>  
 <span data-ttu-id="369bf-121">[Fluxo de Dados](../data-flow.md) </span><span class="sxs-lookup"><span data-stu-id="369bf-121">[Data Flow](../data-flow.md) </span></span>  
 [<span data-ttu-id="369bf-122">Transformações do Integration Services</span><span class="sxs-lookup"><span data-stu-id="369bf-122">Integration Services Transformations</span></span>](integration-services-transformations.md)  
  
  
