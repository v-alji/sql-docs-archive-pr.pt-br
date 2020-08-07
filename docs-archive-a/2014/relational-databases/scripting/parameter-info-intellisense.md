---
title: Informações sobre Parâmetros (IntelliSense)
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Parameter Info option [IntelliSense]
- stored function parameter completion [Intellisense]
- language references [SQL Server]
- IntelliSense [SQL Server], Parameter Info option
ms.assetid: 56c2aac9-c65c-4679-b62c-d9f689876dde
author: rothja
ms.author: jroth
ms.openlocfilehash: b7e5e7496753006808f75378182db0d3cb606d4b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582405"
---
# <a name="parameter-info-intellisense"></a><span data-ttu-id="68454-102">Informações sobre Parâmetros (IntelliSense)</span><span class="sxs-lookup"><span data-stu-id="68454-102">Parameter Info (IntelliSense)</span></span>
  <span data-ttu-id="68454-103">A opção [!INCLUDE[msCoName](../../includes/msconame-md.md)] Informações sobre Parâmetros **do** IntelliSense abre uma lista de parâmetros com informações sobre número, nomes e tipos dos parâmetros necessários para uma função ou um procedimento armazenado.</span><span class="sxs-lookup"><span data-stu-id="68454-103">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] IntelliSense **Parameter Info** option opens a parameters list that provides information about the number, names, and types of the parameters that are required by a function or stored procedure.</span></span> <span data-ttu-id="68454-104">O parâmetro em negrito indica o próximo parâmetro exigido à medida que você digita uma função ou um procedimento armazenado.</span><span class="sxs-lookup"><span data-stu-id="68454-104">The parameter in bold indicates the next parameter that is required as you type a function or stored procedure.</span></span>  
  
 <span data-ttu-id="68454-105">A lista de parâmetros também é exibida para funções aninhadas.</span><span class="sxs-lookup"><span data-stu-id="68454-105">The parameter list is also displayed for nested functions.</span></span> <span data-ttu-id="68454-106">Se você digitar uma função como um parâmetro para outra função, a lista de parâmetros exibirá os parâmetros da função interna.</span><span class="sxs-lookup"><span data-stu-id="68454-106">If you type a function as a parameter to another function, the parameter list displays the parameters for the inner function.</span></span> <span data-ttu-id="68454-107">Em seguida, quando a lista de parâmetros da função interna estiver completa, a lista de parâmetros é revertida para exibir os parâmetros da função externa.</span><span class="sxs-lookup"><span data-stu-id="68454-107">Then, when the inner function parameter list is complete, the parameter list reverts to displaying the outer function parameters.</span></span>  
  
#### <a name="to-view-parameter-info-for-functions-or-stored-procedures"></a><span data-ttu-id="68454-108">Para exibir Informações sobre Parâmetros para funções ou procedimentos armazenados</span><span class="sxs-lookup"><span data-stu-id="68454-108">To view Parameter Info for functions or stored procedures</span></span>  
  
1.  <span data-ttu-id="68454-109">Depois do nome de uma função, digite um parêntese de abertura como normalmente o faz para abrir a lista de parâmetros.</span><span class="sxs-lookup"><span data-stu-id="68454-109">After the name of a function, type an open parenthesis as you usually type to open the parameters list.</span></span> <span data-ttu-id="68454-110">Após digitar o nome de um procedimento armazenado, digite um espaço como normalmente o faz para obter informações sobre os parâmetros do procedimento.</span><span class="sxs-lookup"><span data-stu-id="68454-110">After you type the name of a stored procedure, type a space as you usually type to obtain information about the procedure parameters.</span></span>  
  
     <span data-ttu-id="68454-111">O IntelliSense exibe a declaração completa da função ou os parâmetros de um procedimento armazenado em uma janela pop-up sob o ponto de inserção.</span><span class="sxs-lookup"><span data-stu-id="68454-111">IntelliSense displays the complete declaration for the function or the parameters for a stored procedure in a pop-up window just under the insertion point.</span></span> <span data-ttu-id="68454-112">O primeiro parâmetro da lista aparece em negrito.</span><span class="sxs-lookup"><span data-stu-id="68454-112">The first parameter in the list appears in bold.</span></span>  
  
2.  <span data-ttu-id="68454-113">À medida que você digita os parâmetros, a fonte em negrito se altera para refletir o próximo parâmetro que você precisa digitar.</span><span class="sxs-lookup"><span data-stu-id="68454-113">As you type the parameters, the bold font changes to reflect the next parameter that you need to enter.</span></span>  
  
3.  <span data-ttu-id="68454-114">Pressione ESC a qualquer momento para fechar a lista ou continue digitando até concluir a função.</span><span class="sxs-lookup"><span data-stu-id="68454-114">Press ESC at any time to close the list, or continue typing until you have completed the function.</span></span>  
  
     <span data-ttu-id="68454-115">Para uma função, se você digitar o parêntese de fechamento, também fechará a lista de parâmetros.</span><span class="sxs-lookup"><span data-stu-id="68454-115">For a function, if you type the closing parenthesis you also close the parameter list.</span></span>  
  
#### <a name="to-manually-start-parameter-info"></a><span data-ttu-id="68454-116">Para iniciar manualmente as Informações sobre Parâmetros</span><span class="sxs-lookup"><span data-stu-id="68454-116">To manually start Parameter Info</span></span>  
  
1.  <span data-ttu-id="68454-117">No menu **Editar** , selecione **IntelliSense** e selecione **Informações sobre Parâmetros**.</span><span class="sxs-lookup"><span data-stu-id="68454-117">On the **Edit** menu, select **IntelliSense** and then select **Parameter Info**.</span></span>  
  
2.  <span data-ttu-id="68454-118">Pressione as teclas de atalho CTRL+SHIFT+ESPAÇO.</span><span class="sxs-lookup"><span data-stu-id="68454-118">Press the CTRL+SHIFT+SPACE keyboard shortcut.</span></span>  
  
 <span data-ttu-id="68454-119">Para obter mais informações, consulte [Configurar IntelliSense &#40;SQL Server Management Studio&#41;](configure-intellisense-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="68454-119">For more information, see [Configure IntelliSense &#40;SQL Server Management Studio&#41;](configure-intellisense-sql-server-management-studio.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="68454-120">A opção **Informações sobre Parâmetros** só está disponível para o Editor de Consultas do [!INCLUDE[ssDE](../../includes/ssde-md.md)] e o Editor de Consultas XML.</span><span class="sxs-lookup"><span data-stu-id="68454-120">The **Parameter Info** option is available only for the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor and the XML Query Editor.</span></span>  
  
  
