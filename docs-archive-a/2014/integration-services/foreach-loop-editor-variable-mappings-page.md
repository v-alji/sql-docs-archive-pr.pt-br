---
title: Editor de loop foreach (página Mapeamentos de variáveis) | Microsoft Docs
ms.custom: ''
ms.date: 08/22/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.foreachloopcontainer.mapping.f1
ms.assetid: aa847b87-f391-48a5-9849-eeda2d6b00b9
author: chugugrace
ms.author: chugu
ms.openlocfilehash: cd37c8c6c00f18d8b5493a058239cc880ecc1f5e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87686335"
---
# <a name="foreach-loop-editor-variable-mappings-page"></a><span data-ttu-id="fca75-102">Editor de Loop Foreach (página Mapeamentos de Variáveis)</span><span class="sxs-lookup"><span data-stu-id="fca75-102">Foreach Loop Editor (Variable Mappings Page)</span></span>
  <span data-ttu-id="fca75-103">Use a página **Mapeamentos de Variáveis** da caixa de diálogo **Editor de Loop Foreach** para mapear variáveis para o valor da coleção.</span><span class="sxs-lookup"><span data-stu-id="fca75-103">Use the **Variables Mappings** page of the **Foreach Loop Editor** dialog box to map variables to the collection value.</span></span> <span data-ttu-id="fca75-104">O valor da variável é atualizado com os valores da coleção em cada iteração do loop.</span><span class="sxs-lookup"><span data-stu-id="fca75-104">The value of the variable is updated with the collection values on each iteration of the loop.</span></span>  
  
 <span data-ttu-id="fca75-105">Para saber mais sobre como usar o contêiner do Loop Foreach em um pacote de Serviços de Integração, consulte [Contêiner do Loop Foreach](control-flow/foreach-loop-container.md) .</span><span class="sxs-lookup"><span data-stu-id="fca75-105">To learn about how to use the Foreach Loop container in an Integration Services package,  see [Foreach Loop Container](control-flow/foreach-loop-container.md) .</span></span> <span data-ttu-id="fca75-106">Para saber mais sobre como configurá-lo, consulte [Configurar um contêiner do Loop Foreach](../../2014/integration-services/configure-a-foreach-loop-container.md).</span><span class="sxs-lookup"><span data-stu-id="fca75-106">To learn about how to configure it, see [Configure a Foreach Loop Container](../../2014/integration-services/configure-a-foreach-loop-container.md).</span></span>  
  
 <span data-ttu-id="fca75-107">O tutorial do [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], Criando um Pacote ETL Simples, inclui uma lição que ensina a adicionar e configurar um Loop Foreach.</span><span class="sxs-lookup"><span data-stu-id="fca75-107">The [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] tutorial, Creating a Simple ETL Package Tutorial, includes a lesson that teaches you to add and configure a Foreach Loop.</span></span>  
  
## <a name="options"></a><span data-ttu-id="fca75-108">Opções</span><span class="sxs-lookup"><span data-stu-id="fca75-108">Options</span></span>  
 <span data-ttu-id="fca75-109">**Variável**</span><span class="sxs-lookup"><span data-stu-id="fca75-109">**Variable**</span></span>  
 <span data-ttu-id="fca75-110">Selecione uma variável existente ou clique em \<**New variable...**> para criar uma variável.</span><span class="sxs-lookup"><span data-stu-id="fca75-110">Select an existing variable, or click \<**New variable...**> to create a new variable.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fca75-111">Depois que você mapeia uma variável, uma nova linha é adicionada automaticamente à lista **Variável**.</span><span class="sxs-lookup"><span data-stu-id="fca75-111">After you map a variable, a new row is automatically added to the **Variable** list.</span></span>  
  
 <span data-ttu-id="fca75-112">**Tópicos relacionados**: [Variáveis do Integration Services &#40;SSIS&#41;](integration-services-ssis-variables.md), [Adicionar variável](../../2014/integration-services/add-variable.md)</span><span class="sxs-lookup"><span data-stu-id="fca75-112">**Related Topics**: [Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md), [Add Variable](../../2014/integration-services/add-variable.md)</span></span>  
  
 <span data-ttu-id="fca75-113">**Index**</span><span class="sxs-lookup"><span data-stu-id="fca75-113">**Index**</span></span>  
 <span data-ttu-id="fca75-114">Se estiver usando o Enumerador de Item Foreach, especifique o índice da coluna no valor da coleção para mapear para a variável.</span><span class="sxs-lookup"><span data-stu-id="fca75-114">If using the Foreach Item enumerator, specify the index of the column in the collection value to map to the variable.</span></span> <span data-ttu-id="fca75-115">Em outros tipos de enumerador, o índice é somente leitura.</span><span class="sxs-lookup"><span data-stu-id="fca75-115">For other enumerator types, the index is read-only.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fca75-116">O índice é baseado em 0.</span><span class="sxs-lookup"><span data-stu-id="fca75-116">The index is 0-based.</span></span>  
  
 <span data-ttu-id="fca75-117">**Tópicos relacionados**: [Como fazer loop por meio de arquivos e tabelas do Excel usando um contêiner do Loop Foreach](control-flow/loop-through-excel-files-and-tables-by-using-a-foreach-loop-container.md)</span><span class="sxs-lookup"><span data-stu-id="fca75-117">**Related Topics**: [Loop through Excel Files and Tables by Using a Foreach Loop Container](control-flow/loop-through-excel-files-and-tables-by-using-a-foreach-loop-container.md)</span></span>  
  
 <span data-ttu-id="fca75-118">**Delete (excluir)**</span><span class="sxs-lookup"><span data-stu-id="fca75-118">**Delete**</span></span>  
 <span data-ttu-id="fca75-119">Selecione uma variável e clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="fca75-119">Select a variable, and then click **Delete**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fca75-120">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="fca75-120">See Also</span></span>  
 <span data-ttu-id="fca75-121">[Referência de mensagens e erros do Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="fca75-121">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="fca75-122">[Editor de loop foreach &#40;página Geral&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="fca75-122">[Foreach Loop Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="fca75-123">[Editor de loop foreach &#40;página de coleção&#41;](../../2014/integration-services/foreach-loop-editor-collection-page.md) </span><span class="sxs-lookup"><span data-stu-id="fca75-123">[Foreach Loop Editor &#40;Collection Page&#41;](../../2014/integration-services/foreach-loop-editor-collection-page.md) </span></span>  
 <span data-ttu-id="fca75-124">[Página Expressões](expressions/expressions-page.md) </span><span class="sxs-lookup"><span data-stu-id="fca75-124">[Expressions Page](expressions/expressions-page.md) </span></span>  
 [<span data-ttu-id="fca75-125">Contêiner Loop For</span><span class="sxs-lookup"><span data-stu-id="fca75-125">For Loop Container</span></span>](control-flow/for-loop-container.md)  
  
  
