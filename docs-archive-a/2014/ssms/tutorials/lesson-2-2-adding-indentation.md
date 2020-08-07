---
title: Adicionando recuo | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
ms.assetid: 9dce05c1-c52f-455d-8b8d-6f303e242760
author: stevestein
ms.author: sstein
ms.openlocfilehash: 2d0b7ee8819f98df5e5658321a3d950ca31083b6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575507"
---
# <a name="adding-indentation"></a><span data-ttu-id="e4405-102">Adicionando recuo</span><span class="sxs-lookup"><span data-stu-id="e4405-102">Adding Indentation</span></span>
  <span data-ttu-id="e4405-103">O Editor de Consultas permite o recuo de grandes seções de código em uma única etapa, além de também possibilitar a alteração da quantidade de recuo.</span><span class="sxs-lookup"><span data-stu-id="e4405-103">Query Editor allows you to indent large sections of code with a single step, and you can change the amount of the indentation.</span></span>  
  
## <a name="indenting-code"></a><span data-ttu-id="e4405-104">Recuando código</span><span class="sxs-lookup"><span data-stu-id="e4405-104">Indenting Code</span></span>  
  
#### <a name="to-indent-multiple-lines-of-code"></a><span data-ttu-id="e4405-105">Para recuar várias linhas de código</span><span class="sxs-lookup"><span data-stu-id="e4405-105">To indent multiple lines of code</span></span>  
  
1.  <span data-ttu-id="e4405-106">Na barra de ferramentas, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="e4405-106">On the toolbar, click **New Query**.</span></span>  
  
2.  <span data-ttu-id="e4405-107">Crie uma segunda consulta que seleciona as colunas **BusinessEntityID**, FirstName, **MiddleName**e **LastName** da tabela **Person** do esquema **Person** .</span><span class="sxs-lookup"><span data-stu-id="e4405-107">Create a second query that selects the **BusinessEntityID**, FirstName, **MiddleName**, and **LastName** columns from the **Person** table of the **Person** schema.</span></span> <span data-ttu-id="e4405-108">Coloque cada coluna em uma linha separada de forma que o código se pareça com o exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="e4405-108">Place each column on a separate line so the code looks like this:</span></span>  
  
    ```  
    -- Search for a contact  
    SELECT   
    BusinessEntityID,  
    FirstName,   
    MiddleName,   
    LastName  
    FROM Person.Person  
    WHERE LastName = 'Sanchez';  
    GO  
    ```  
  
3.  <span data-ttu-id="e4405-109">Selecione todo o texto de `BusinessEntityID` para `LastName`.</span><span class="sxs-lookup"><span data-stu-id="e4405-109">Select all text from `BusinessEntityID` to `LastName`.</span></span>  
  
4.  <span data-ttu-id="e4405-110">Na barra de ferramentas do **Editor SQL** , clique em **Aumentar Recuo** para recuar todas as linhas de uma vez.</span><span class="sxs-lookup"><span data-stu-id="e4405-110">On the **SQL Editor** toolbar, click **Increase Indent** to indent all the lines at once.</span></span>  
  
#### <a name="to-change-the-default-indentation"></a><span data-ttu-id="e4405-111">Para alterar o recuo padrão</span><span class="sxs-lookup"><span data-stu-id="e4405-111">To change the default indentation</span></span>  
  
1.  <span data-ttu-id="e4405-112">No menu **Ferramentas** , clique em **Opções**.</span><span class="sxs-lookup"><span data-stu-id="e4405-112">On the **Tools** menu, click **Options**.</span></span>  
  
2.  <span data-ttu-id="e4405-113">Expanda **Editor de Texto**, expanda **Todos os Idiomas**, clique em **Guias** e defina valores de recuo conforme o necessário.</span><span class="sxs-lookup"><span data-stu-id="e4405-113">Expand **Text Editor**, expand **All Languages**, and click **Tabs** , and set indentation values as appropriate.</span></span> <span data-ttu-id="e4405-114">Note que você pode alterar o tamanho do recuo assim como o tamanho das guias e se as guias serão convertidas em espaços.</span><span class="sxs-lookup"><span data-stu-id="e4405-114">Note that you can change the size of the indent as well as the size of tabs, and whether tabs are converted to spaces.</span></span>  
  
     <span data-ttu-id="e4405-115">![Aparência da caixa de diálogo Guias](media/tabsdialog.gif "Aparência da caixa de diálogo Guias")</span><span class="sxs-lookup"><span data-stu-id="e4405-115">![Appearance of the Tabs dialog box](media/tabsdialog.gif "Appearance of the Tabs dialog box")</span></span>  
  
3.  <span data-ttu-id="e4405-116">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="e4405-116">Click **OK**.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="e4405-117">Próxima tarefa da lição</span><span class="sxs-lookup"><span data-stu-id="e4405-117">Next Task in Lesson</span></span>  
 [<span data-ttu-id="e4405-118">Maximizando o Editor de Consultas</span><span class="sxs-lookup"><span data-stu-id="e4405-118">Maximizing Query Editor</span></span>](lesson-2-3-maximizing-query-editor.md)  
  
  
