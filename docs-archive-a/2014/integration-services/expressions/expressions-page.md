---
title: Página expressões | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.expressionspage.f1
helpviewer_keywords:
- Expressions Page dialog box
ms.assetid: c9016ec6-11c1-4ebd-b2a7-0fa6631fd9e4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: ba4e73ea495456e8f9e452108ab09106a65543ae
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573219"
---
# <a name="expressions-page"></a><span data-ttu-id="c8686-102">Página Expressões</span><span class="sxs-lookup"><span data-stu-id="c8686-102">Expressions Page</span></span>
  <span data-ttu-id="c8686-103">Use a página **Expressões** para editar as expressões de propriedade e para acessar as caixas de diálogo **Editor de Expressões de Propriedades** e **Construtor de Expressões de Propriedade** .</span><span class="sxs-lookup"><span data-stu-id="c8686-103">Use the **Expressions** page to edit property expressions and to access the **Property Expressions Editor** and **Property Expression Builder** dialog boxes.</span></span>  
  
 <span data-ttu-id="c8686-104">Quando o pacote é executado, as expressões de propriedades atualizam os valores das propriedades.</span><span class="sxs-lookup"><span data-stu-id="c8686-104">Property expressions update the values of properties when the package is run.</span></span> <span data-ttu-id="c8686-105">As expressões de propriedades são usadas com as propriedades dos pacotes, tarefas, contêiners, gerenciadores de conexões, bem como com alguns componentes do fluxo de dados.</span><span class="sxs-lookup"><span data-stu-id="c8686-105">Property expressions can be used with the properties of packages, tasks, containers, connection managers, as well as some data flow components.</span></span> <span data-ttu-id="c8686-106">As expressões são avaliadas e seus resultados são usados em vez dos valores que você definiu para as propriedades ao configurar o pacote e os objetos do pacote.</span><span class="sxs-lookup"><span data-stu-id="c8686-106">The expressions are evaluated and their results are used instead of the values to which you set the properties when you configured the package and package objects.</span></span> <span data-ttu-id="c8686-107">As expressões podem incluir variáveis e funções bem como operadores que o idioma da expressão fornece.</span><span class="sxs-lookup"><span data-stu-id="c8686-107">The expressions can include variables and the functions and operators that the expression language provides.</span></span> <span data-ttu-id="c8686-108">Por exemplo, você pode gerar a linha do assunto para a tarefa Enviar Mensagem concatenando o valor de uma variável que contém a cadeia de caracteres "Previsão do tempo para" e os resultados retornados da função GETDATE() para desenvolver a cadeia de caracteres "Previsão do tempo para 4/5/2006.</span><span class="sxs-lookup"><span data-stu-id="c8686-108">For example, you can generate the subject line for the Send Mail task by concatenating the value of a variable that contains the string "Weather forecast for " and the return results of the GETDATE() function to make the string "Weather forecast for 4/5/2006".</span></span>  
  
 <span data-ttu-id="c8686-109">Para saber mais sobre expressões de gravação e como usar expressões de propriedade, consulte [Expressões do Integration Services &#40;SSIS&#41;](integration-services-ssis-expressions.md) e [Usar expressões de propriedade em pacotes](use-property-expressions-in-packages.md).</span><span class="sxs-lookup"><span data-stu-id="c8686-109">To learn more about writing expressions and using property expressions, see [Integration Services &#40;SSIS&#41; Expressions](integration-services-ssis-expressions.md) and [Use Property Expressions in Packages](use-property-expressions-in-packages.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="c8686-110">Opções</span><span class="sxs-lookup"><span data-stu-id="c8686-110">Options</span></span>  
 <span data-ttu-id="c8686-111">**Expressões (...)**</span><span class="sxs-lookup"><span data-stu-id="c8686-111">**Expressions (...)**</span></span>  
 <span data-ttu-id="c8686-112">Clique nas reticências para abrir a caixa de diálogo **Editor de Expressões de Propriedade** .</span><span class="sxs-lookup"><span data-stu-id="c8686-112">Click the ellipsis to open the **Property Expressions Editor** dialog box.</span></span> <span data-ttu-id="c8686-113">Para obter mais informações, consulte [Editor de expressões de propriedade](property-expressions-editor.md).</span><span class="sxs-lookup"><span data-stu-id="c8686-113">For more information, see [Property Expressions Editor](property-expressions-editor.md).</span></span>  
  
 **\<property name>**  
 <span data-ttu-id="c8686-114">Clique nas reticências para abrir a caixa de diálogo **Construtor de Expressões** .</span><span class="sxs-lookup"><span data-stu-id="c8686-114">Click the ellipsis to open the **Expression Builder** dialog box.</span></span> <span data-ttu-id="c8686-115">Para obter mais informações, consulte [Expression Builder](expression-builder.md).</span><span class="sxs-lookup"><span data-stu-id="c8686-115">For more information, see [Expression Builder](expression-builder.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8686-116">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c8686-116">See Also</span></span>  
 <span data-ttu-id="c8686-117">[Variáveis do SSIS &#40;Integration Services&#41;](../integration-services-ssis-variables.md) </span><span class="sxs-lookup"><span data-stu-id="c8686-117">[Integration Services &#40;SSIS&#41; Variables](../integration-services-ssis-variables.md) </span></span>  
 <span data-ttu-id="c8686-118">[Variáveis do Sistema](../system-variables.md) </span><span class="sxs-lookup"><span data-stu-id="c8686-118">[System Variables](../system-variables.md) </span></span>  
 [<span data-ttu-id="c8686-119">Expressões do SSIS &#40;Integration Services&#41;</span><span class="sxs-lookup"><span data-stu-id="c8686-119">Integration Services &#40;SSIS&#41; Expressions</span></span>](integration-services-ssis-expressions.md)  
  
  
