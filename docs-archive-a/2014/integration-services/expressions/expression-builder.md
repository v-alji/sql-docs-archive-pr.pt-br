---
title: Construtor de Expressões | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.expressionbuilder.f1
helpviewer_keywords:
- Expression Builder dialog box
ms.assetid: 4717ce33-bd4e-44bc-81e0-002de075b4d1
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 812b0d744d415d5419d54176359ddcd5837dd206
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573218"
---
# <a name="expression-builder"></a><span data-ttu-id="e47ab-102">Construtor de Expressões</span><span class="sxs-lookup"><span data-stu-id="e47ab-102">Expression Builder</span></span>
  <span data-ttu-id="e47ab-103">Use a caixa de diálogo **Construtor de Expressões** para criar e editar uma expressão de propriedade ou para gravar a expressão que define o valor de uma variável usando uma interface gráfica do usuário que lista as variáveis e oferece uma referência interna às funções, às conversões de tipo e aos operadores que a linguagem de expressão [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] inclui.</span><span class="sxs-lookup"><span data-stu-id="e47ab-103">Use the **Expression Builder** dialog box to create and edit a property expression or write the expression that sets the value of a variable using a graphical user interface that lists variables and provides a built-in reference to the functions, type casts, and operators that the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] expression language includes.</span></span>  
  
 <span data-ttu-id="e47ab-104">Uma expressão de propriedades é uma expressão que é atribuída a uma propriedade.</span><span class="sxs-lookup"><span data-stu-id="e47ab-104">A property expression is an expression that is assigned to a property.</span></span> <span data-ttu-id="e47ab-105">Quando a expressão é avaliada, a propriedade é atualizada de forma dinâmica para usar o resultado da avaliação da expressão.</span><span class="sxs-lookup"><span data-stu-id="e47ab-105">When the expression is evaluated, the property is dynamically updated to use the evaluation result of the expression.</span></span> <span data-ttu-id="e47ab-106">Do mesmo modo, uma expressão usada em uma variável permite que o valor da mesma seja atualizado com o resultado da avaliação da expressão.</span><span class="sxs-lookup"><span data-stu-id="e47ab-106">Likewise, an expression that is used in a variable enables the variable value to be updated with the evaluation result of the expression.</span></span>  
  
 <span data-ttu-id="e47ab-107">Há vários modos em que usar as expressões:</span><span class="sxs-lookup"><span data-stu-id="e47ab-107">There are many ways to use expressions:</span></span>  
  
-   <span data-ttu-id="e47ab-108">**Tarefas** Atualize a linha Para que uma tarefa Enviar Mensagem usa inserindo um endereço de email armazenado em uma variável ou atualize a linha do Assunto concatenando uma cadeia de caracteres como “Vendas para:” e a data atual retornada pela função GETDATE.</span><span class="sxs-lookup"><span data-stu-id="e47ab-108">**Tasks** Update the To line that a Send Mail task uses by inserting an e-mail address that is stored in a variable; or update the Subject line by concatenating a string such as "Sales for: " and the current date returned by the GETDATE function.</span></span>  
  
-   <span data-ttu-id="e47ab-109">**Variáveis** Defina o valor de uma variável para o mês atual usando uma expressão como `DATEPART("mm",GETDATE())`; ou defina o valor de uma cadeia de caracteres concatenando esta cadeia literal e a data atual usando a expressão `"Today's date is " + (DT_WSTR,30)(GETDATE())`.</span><span class="sxs-lookup"><span data-stu-id="e47ab-109">**Variables** Set the value of a variable to the current month by using an expression like `DATEPART("mm",GETDATE())`; or set the value of a string by concatenating the string literal and the current date by using the expression `"Today's date is " + (DT_WSTR,30)(GETDATE())`.</span></span>  
  
-   <span data-ttu-id="e47ab-110">**Gerenciadores de Conexões** Defina a página do código de um gerenciador de conexões de Arquivo Simples usando uma variável que contém um identificador de página de código diferente ou especifique o número de linhas no arquivo de dados a serem ignoradas, digitando um inteiro positivo como 3 na expressão.</span><span class="sxs-lookup"><span data-stu-id="e47ab-110">**Connection Managers** Set the code page of a Flat File connection manager by using a variable that contains a different code page identifier; or specify the number of rows in the data file to skip by entering a positive integer like 3 in the expression.</span></span>  
  
 <span data-ttu-id="e47ab-111">Para saber mais sobre expressões de propriedade e como escrever expressões, consulte [Usar expressões de propriedade em pacotes](use-property-expressions-in-packages.md) e [Expressões do Integration Services &#40;SSIS&#41;](integration-services-ssis-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="e47ab-111">To learn more about property expressions and writing expressions, see [Use Property Expressions in Packages](use-property-expressions-in-packages.md) and [Integration Services &#40;SSIS&#41; Expressions](integration-services-ssis-expressions.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="e47ab-112">Opções</span><span class="sxs-lookup"><span data-stu-id="e47ab-112">Options</span></span>  
  
|<span data-ttu-id="e47ab-113">Termo</span><span class="sxs-lookup"><span data-stu-id="e47ab-113">Term</span></span>|<span data-ttu-id="e47ab-114">Definição</span><span class="sxs-lookup"><span data-stu-id="e47ab-114">Definition</span></span>|  
|----------|----------------|  
|<span data-ttu-id="e47ab-115">**Variáveis**</span><span class="sxs-lookup"><span data-stu-id="e47ab-115">**Variables**</span></span>|<span data-ttu-id="e47ab-116">Expanda a pasta de **Variáveis** e arraste as mesmas para a caixa **Expressão** .</span><span class="sxs-lookup"><span data-stu-id="e47ab-116">Expand the **Variables** folder and drag variables to the **Expression** box.</span></span>|  
|<span data-ttu-id="e47ab-117">**Funções matemáticas**</span><span class="sxs-lookup"><span data-stu-id="e47ab-117">**Mathematical Functions**</span></span><br /><br /> <span data-ttu-id="e47ab-118">**Funções de cadeia de caracteres**</span><span class="sxs-lookup"><span data-stu-id="e47ab-118">**String Functions**</span></span><br /><br /> <span data-ttu-id="e47ab-119">**Funções Data/Hora**</span><span class="sxs-lookup"><span data-stu-id="e47ab-119">**Date/Time Functions**</span></span><br /><br /> <span data-ttu-id="e47ab-120">**Funções NULL**</span><span class="sxs-lookup"><span data-stu-id="e47ab-120">**NULL Functions**</span></span><br /><br /> <span data-ttu-id="e47ab-121">**Conversões de Tipos**</span><span class="sxs-lookup"><span data-stu-id="e47ab-121">**Type Casts**</span></span><br /><br /> <span data-ttu-id="e47ab-122">**Operadores**</span><span class="sxs-lookup"><span data-stu-id="e47ab-122">**Operators**</span></span>|<span data-ttu-id="e47ab-123">Expanda as pastas e arraste as funções, conversões de tipos e operadores para a caixa **Expressão** .</span><span class="sxs-lookup"><span data-stu-id="e47ab-123">Expand the folders and drag functions, type casts, and operators to the **Expression** box.</span></span>|  
|<span data-ttu-id="e47ab-124">**Expression**</span><span class="sxs-lookup"><span data-stu-id="e47ab-124">**Expression**</span></span>|<span data-ttu-id="e47ab-125">Edite ou digite uma expressão.'</span><span class="sxs-lookup"><span data-stu-id="e47ab-125">Edit or type an expression.\`</span></span>|  
|<span data-ttu-id="e47ab-126">**Valor avaliado**</span><span class="sxs-lookup"><span data-stu-id="e47ab-126">**Evaluated value**</span></span>|<span data-ttu-id="e47ab-127">Lista o resultado da avaliação da expressão.</span><span class="sxs-lookup"><span data-stu-id="e47ab-127">Lists the evaluation result of the expression.</span></span>|  
|<span data-ttu-id="e47ab-128">**Avaliar Expressão**</span><span class="sxs-lookup"><span data-stu-id="e47ab-128">**Evaluate Expression**</span></span>|<span data-ttu-id="e47ab-129">Clique em **Avaliar Expressão** para exibir o resultado de avaliação da expressão.</span><span class="sxs-lookup"><span data-stu-id="e47ab-129">Click **Evaluate Expression** to view the evaluation result of the expression.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e47ab-130">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e47ab-130">See Also</span></span>  
 <span data-ttu-id="e47ab-131">[Página Expressões](expressions-page.md) </span><span class="sxs-lookup"><span data-stu-id="e47ab-131">[Expressions Page](expressions-page.md) </span></span>  
 <span data-ttu-id="e47ab-132">[Editor de expressões de propriedades](property-expressions-editor.md) </span><span class="sxs-lookup"><span data-stu-id="e47ab-132">[Property Expressions Editor](property-expressions-editor.md) </span></span>  
 <span data-ttu-id="e47ab-133">[Variáveis do SSIS &#40;Integration Services&#41;](../integration-services-ssis-variables.md) </span><span class="sxs-lookup"><span data-stu-id="e47ab-133">[Integration Services &#40;SSIS&#41; Variables](../integration-services-ssis-variables.md) </span></span>  
 [<span data-ttu-id="e47ab-134">Variáveis do sistema</span><span class="sxs-lookup"><span data-stu-id="e47ab-134">System Variables</span></span>](../system-variables.md)  
  
  
