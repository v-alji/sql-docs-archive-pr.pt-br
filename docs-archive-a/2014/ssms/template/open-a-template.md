---
title: Abrir um modelo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- templates [Transact-SQL], opening
- opening templates
ms.assetid: 605b0f4c-5ba1-4249-ad1c-6341df77cd7a
author: stevestein
ms.author: sstein
ms.openlocfilehash: 43b75d68fafea759e4d7873c1fb738d7964dcf57
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575518"
---
# <a name="open-a-template"></a><span data-ttu-id="8d6b4-102">Abrir um modelo</span><span class="sxs-lookup"><span data-stu-id="8d6b4-102">Open a Template</span></span>
  <span data-ttu-id="8d6b4-103">Você pode abrir um modelo a partir do Explorador de Modelos.</span><span class="sxs-lookup"><span data-stu-id="8d6b4-103">You can open a template from Template Explorer.</span></span>  
  
## <a name="to-open-a-template-from-template-explorer"></a><span data-ttu-id="8d6b4-104">Para abrir um modelo a partir do Explorador de Modelos</span><span class="sxs-lookup"><span data-stu-id="8d6b4-104">To open a template from Template Explorer</span></span>  
 <span data-ttu-id="8d6b4-105">Você pode abrir modelos a partir do Explorador de Modelos.</span><span class="sxs-lookup"><span data-stu-id="8d6b4-105">You can open templates from the Template Explorer.</span></span>  
  
1.  <span data-ttu-id="8d6b4-106">Para abrir o Gerenciador de Modelos, no menu **Exibir** , clique em **Gerenciador de Modelos**.</span><span class="sxs-lookup"><span data-stu-id="8d6b4-106">To open Template Explorer, on the **View** menu, click **Template Explorer**.</span></span>  
  
2.  <span data-ttu-id="8d6b4-107">Na lista de categorias de modelo, expanda a categoria que contém o modelo que você deseja abrir.</span><span class="sxs-lookup"><span data-stu-id="8d6b4-107">In the list of template categories, expand the category that contains the template you want to open.</span></span>  
  
3.  <span data-ttu-id="8d6b4-108">Há três modos de abrir o modelo:</span><span class="sxs-lookup"><span data-stu-id="8d6b4-108">There are three ways to open the template:</span></span>  
  
    1.  <span data-ttu-id="8d6b4-109">Clique duas vezes no modelo para abri-lo em uma janela de editor de código.</span><span class="sxs-lookup"><span data-stu-id="8d6b4-109">Double-click the template to open it in a code editor window.</span></span>  
  
    2.  <span data-ttu-id="8d6b4-110">Clique com o botão direito do mouse no modelo e selecione **Abrir** para abri-lo em uma janela do editor de código.</span><span class="sxs-lookup"><span data-stu-id="8d6b4-110">Right-click the template and select **Open** to open it in a code editor window.</span></span>  
  
    3.  <span data-ttu-id="8d6b4-111">Arraste o modelo para uma janela do editor de código para adicionar o código do modelo ao conteúdo da janela do editor.</span><span class="sxs-lookup"><span data-stu-id="8d6b4-111">Drag the template into a code editor window to add the template code to the contents of the editor window.</span></span>  
  
 <span data-ttu-id="8d6b4-112">Após abrir o modelo, use a caixa de diálogo **Substituir Parâmetros do Modelo** para substituir os parâmetros do modelo pelos seus próprios valores.</span><span class="sxs-lookup"><span data-stu-id="8d6b4-112">After the template is open, use the **Replace Template Parameters** dialog box to replace the template parameters with your values.</span></span>  
  
 <span data-ttu-id="8d6b4-113">Se a abertura de um modelo iniciar uma nova janela do editor, a janela será aberta com as credenciais da conexão ativa atual.</span><span class="sxs-lookup"><span data-stu-id="8d6b4-113">If opening a template launches a new editor window, the window will open with the credentials of the current active connection.</span></span> <span data-ttu-id="8d6b4-114">Por exemplo, se você estiver concentrado em uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)] no Pesquisador de Objetos quando você abrir o modelo CREATE DATABASE, uma nova janela do editor será aberta usando uma conexão com essa instância.</span><span class="sxs-lookup"><span data-stu-id="8d6b4-114">For example, if you are focused on an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] in Object Explorer when you open the CREATE DATABASE template, a new editor window will be opened using a connection to that instance.</span></span> <span data-ttu-id="8d6b4-115">Se não houver nenhuma conexão ativa, o [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] apresentará uma caixa de diálogo de logon.</span><span class="sxs-lookup"><span data-stu-id="8d6b4-115">If there is no active connection, [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] will present a login dialog.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d6b4-116">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8d6b4-116">See Also</span></span>  
 <span data-ttu-id="8d6b4-117">[Gerenciador de modelos](template-explorer.md) </span><span class="sxs-lookup"><span data-stu-id="8d6b4-117">[Template Explorer](template-explorer.md) </span></span>  
 [<span data-ttu-id="8d6b4-118">Substituir parâmetros do modelo</span><span class="sxs-lookup"><span data-stu-id="8d6b4-118">Replace Template Parameters</span></span>](replace-template-parameters.md)  
  
  
