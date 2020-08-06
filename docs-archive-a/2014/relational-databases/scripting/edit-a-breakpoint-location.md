---
title: Editar um local de ponto de interrupção
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Transact-SQL debugger, breakpoint location
ms.assetid: 5c28e411-0377-4210-a7ce-2a5c13dcdf74
author: rothja
ms.author: jroth
ms.openlocfilehash: 919e62d53d5c9e8898bf1d49c4b5e5aa4c0ed107
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568418"
---
# <a name="edit-a-breakpoint-location"></a><span data-ttu-id="00927-102">Editar um local de ponto de interrupção</span><span class="sxs-lookup"><span data-stu-id="00927-102">Edit a Breakpoint Location</span></span>
  <span data-ttu-id="00927-103">O local do ponto de interrupção especifica a linha e o caractere em que o ponto de interrupção reside em um arquivo de script [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="00927-103">The breakpoint location specifies the line and character where the breakpoint resides in a [!INCLUDE[tsql](../../includes/tsql-md.md)] script file.</span></span> <span data-ttu-id="00927-104">Você pode editar o local do ponto de interrupção para movê-lo para outro local no script ou para outro script.</span><span class="sxs-lookup"><span data-stu-id="00927-104">You can edit the breakpoint location to move the breakpoint to another location in the script, or to a different script.</span></span>  
  
## <a name="editing-a-location"></a><span data-ttu-id="00927-105">Editando um local</span><span class="sxs-lookup"><span data-stu-id="00927-105">Editing a Location</span></span>  
 <span data-ttu-id="00927-106">Quando você edita um local de ponto de interrupção, ele se move para o novo local, levando consigo todas as propriedades existentes, como contagem de ocorrências ou condição.</span><span class="sxs-lookup"><span data-stu-id="00927-106">When you edit a breakpoint location, the breakpoint moves to the new location, carrying with it all of the existing properties, such as a hit count or condition.</span></span>  
  
#### <a name="to-edit-a-breakpoint-location"></a><span data-ttu-id="00927-107">Para editar um local de ponto de interrupção</span><span class="sxs-lookup"><span data-stu-id="00927-107">To Edit a Breakpoint Location</span></span>  
  
1.  <span data-ttu-id="00927-108">Na janela do editor, clique com o botão direito do mouse no glifo do ponto de interrupção e clique em **Local** no menu de atalho.</span><span class="sxs-lookup"><span data-stu-id="00927-108">In the editor window, right-click the breakpoint glyph, and then click **Location** on the shortcut menu.</span></span>  
  
     <span data-ttu-id="00927-109">-ou-</span><span class="sxs-lookup"><span data-stu-id="00927-109">-or-</span></span>  
  
     <span data-ttu-id="00927-110">Na janela **Pontos de Interrupção** , clique com o botão direito do mouse no glifo do ponto de interrupção e clique em **Local** no menu de atalho.</span><span class="sxs-lookup"><span data-stu-id="00927-110">In the **Breakpoints** window, right-click the breakpoint glyph, and then click **Location** on the shortcut menu.</span></span>  
  
2.  <span data-ttu-id="00927-111">Na caixa de diálogo **Ponto de Interrupção de Arquivo** , edite **Arquivo** para especificar um novo arquivo, **Linha** para especificar uma nova linha ou **Caractere** para especificar um novo local na linha.</span><span class="sxs-lookup"><span data-stu-id="00927-111">In the **File Breakpoint** dialog box, edit **File** to specify a new file, **Line** to specify a new line, or **Character** to specify a new location within the line.</span></span> <span data-ttu-id="00927-112">Se o novo arquivo especificado já estiver aberto em uma janela do editor de consulta, o ponto de interrupção será movido para essa janela do editor.</span><span class="sxs-lookup"><span data-stu-id="00927-112">If the new file you specify is already open in a query editor window, the breakpoint is moved to that editor window.</span></span> <span data-ttu-id="00927-113">Se o arquivo não estiver aberto, uma nova janela do editor será aberta, o arquivo será carregado nela e o ponto de interrupção será movido para o novo local.</span><span class="sxs-lookup"><span data-stu-id="00927-113">If the file is not opened, a new editor window is opened, the file is loaded in, and the breakpoint moved to the new location.</span></span>  
  
     <span data-ttu-id="00927-114">A opção **Permitir que o código-fonte seja diferente da versão original** não tem efeito durante a depuração de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="00927-114">The **Allow the source code to be different from the original version** option has no effect when debugging [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00927-115">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="00927-115">See Also</span></span>  
 <span data-ttu-id="00927-116">[Especificar uma contagem de acesso](specify-a-hit-count.md) </span><span class="sxs-lookup"><span data-stu-id="00927-116">[Specify a Hit Count](specify-a-hit-count.md) </span></span>  
 <span data-ttu-id="00927-117">[Especificar uma ação de ponto de interrupção](specify-a-breakpoint-action.md) </span><span class="sxs-lookup"><span data-stu-id="00927-117">[Specify a Breakpoint Action](specify-a-breakpoint-action.md) </span></span>  
 <span data-ttu-id="00927-118">[Especificar uma condição de ponto de interrupção](specify-a-breakpoint-condition.md) </span><span class="sxs-lookup"><span data-stu-id="00927-118">[Specify a Breakpoint Condition](specify-a-breakpoint-condition.md) </span></span>  
 [<span data-ttu-id="00927-119">Especificar um filtro de ponto de interrupção</span><span class="sxs-lookup"><span data-stu-id="00927-119">Specify a Breakpoint Filter</span></span>](specify-a-breakpoint-filter.md)  
